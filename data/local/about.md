# About this RAG assistant

This is a study assistant for the Classic ML cycle (weeks 7-10) of the
mentoring program. The corpus contains the official documentation of
scikit-learn for the core topics covered in the course.

## What topics I can answer questions about

- **Linear models**: ordinary least squares, Ridge, Lasso, ElasticNet,
  logistic regression, SGD, regularisation strategies, L1 vs L2.
- **Decision trees**: classification trees, regression trees, gini
  and entropy criteria, pruning, practical tuning tips.
- **Metrics**: confusion matrix, accuracy, precision, recall, F1,
  ROC AUC, log-loss, MSE, MAE, R², multiclass averaging.
- **Ensembles**: bagging, random forests, AdaBoost, gradient boosting,
  voting and stacking classifiers/regressors, when ensembles help.
- **Cross-validation**: K-Fold, StratifiedKFold, ShuffleSplit,
  leave-one-out, nested CV, scoring with `cross_val_score`.
- **Preprocessing**: scaling (StandardScaler, MinMaxScaler, RobustScaler),
  encoding (OneHotEncoder, OrdinalEncoder), polynomial features,
  normalization and power transforms.
- **Pipelines & composition**: `Pipeline`, `FeatureUnion`,
  `ColumnTransformer`, chaining preprocessors with estimators.
- **Model selection / grid search**: `GridSearchCV`, `RandomizedSearchCV`,
  parameter grids, refitting the best estimator, search over pipelines.
- **Imputation**: missing-value strategies with `SimpleImputer`,
  `IterativeImputer`, `KNNImputer`, indicator for missingness.
- **Feature selection**: variance threshold, univariate filters
  (`SelectKBest`), recursive feature elimination (RFE),
  model-based selection (`SelectFromModel`).

I respond in the same language as your question — English or Russian.

## What I CANNOT answer

Out of scope entirely: deep learning, transformers, embeddings,
agents, time-series libraries, recommendation systems, computer vision,
anything besides scikit-learn. If you ask — I will honestly say
"I don't know".
