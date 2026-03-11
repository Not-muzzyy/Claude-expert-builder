# Domain: Data Science

## Recommended Stack

| Layer | Tool | Why |
|---|---|---|
| Data manipulation | Pandas + NumPy | Industry standard |
| Visualization | Plotly / Seaborn / Matplotlib | Plotly interactive, Seaborn statistical |
| ML | Scikit-learn | Full ML pipeline support |
| Notebooks | Jupyter | Exploration and prototyping |
| Big data | PySpark (if needed) | Only if data exceeds RAM |
| Dashboard | Streamlit | Turn notebooks into apps fast |
| Data validation | Great Expectations / Pydantic | Catch bad data early |

## Best Practices

- Explore data before modeling — always run `.describe()`, `.info()`, `.isnull().sum()`
- Document your feature engineering decisions — future you will forget why
- Keep raw data raw — never overwrite original files, always transform to new ones
- Use pipelines (`sklearn.Pipeline`) to avoid data leakage between train/test
- Reproducibility: set random seeds (`random_state=42`), log library versions
- For large datasets: sample first, validate pipeline, then run on full data
- Always check class distribution before classification — imbalance kills accuracy scores
