# scikit-learn docs RAG assistant

AI-ассистент по официальной документации scikit-learn. Задаёте вопрос
на естественном языке — получаете ответ с цитатами из документации.

## Архитектура

\`\`\`mermaid
flowchart LR
    USER[Пользователь] --> NGINX[Nginx HTTPS]
    NGINX --> APP[FastAPI + Gradio streaming]
    APP --> EMB[multilingual-e5-small embedder]
    APP --> Q[(Qdrant)]
    APP --> LLM[deepseek-v4-flash]
\`\`\`

## Метрики

Замеры на реальной системе (22 вопроса golden-датасета,
10 sklearn-модулей + about.md → 560 чанков, deepseek-v4-flash,
`notebooks/rag_eval.ipynb`):

| Метрика | Значение | Что измеряет |
|---|---|---|
| Recall@4 | **1.00** | retriever возвращает релевантный URL во всех 10 случаях |
| Faithfulness | **0.94** | LLM-судья: ответ не противоречит контексту |
| Response Relevancy | **0.93** | LLM-судья: ответ по делу, не уходит в сторону |
| Avg retrieval | **50 ms** | embed + Qdrant top-4 |
| Avg LLM (no stream) | **7.0 s** | invoke() через OpenRouter |
| TTFT (streaming) | **<1 s** | stream(), время до первого токена |

## Локальный запуск

\`\`\`bash
docker compose up
python -m app.scripts.load_corpus
python -m app.scripts.index_corpus
\`\`\`

Откройте http://localhost:8000