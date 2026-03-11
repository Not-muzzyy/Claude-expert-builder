# Domain: AI / ML

## Recommended Stack

| Layer | Tool | Why |
|---|---|---|
| UI | Streamlit | Fast to build, no JS needed |
| LLM inference | Groq (LLaMA 3.1/3.3) | Free tier, extremely fast |
| Classical ML | Scikit-learn | Industry standard, well-documented |
| Deep learning | PyTorch / TensorFlow | PyTorch preferred for flexibility |
| Data | Pandas + NumPy | Standard for structured data |
| Visualization | Plotly / Matplotlib | Plotly for interactive, Matplotlib for reports |
| Model storage | joblib / pickle | joblib faster for large numpy arrays |
| Embeddings | HuggingFace sentence-transformers | Free, runs locally |
| Vector DB | ChromaDB / FAISS | ChromaDB easier to set up |
| Deployment | Streamlit Cloud / HuggingFace Spaces | Both free, ML-friendly |

## Best Practices

- Always split data: train/validation/test (70/15/15 or 80/10/10)
- Save trained models with joblib, not pickle (better for sklearn)
- Version your datasets — a model is only as good as its data
- Log metrics during training (accuracy, F1, loss per epoch)
- For LLM apps: always handle API failures with retry logic
- RAG apps: chunk documents thoughtfully (500–1000 tokens with overlap)
- Never hardcode API keys — use `st.secrets` in Streamlit or `.env` elsewhere
- Evaluate with real examples before shipping — don't trust only accuracy score
- For classification: check precision/recall, not just accuracy (especially imbalanced data)
