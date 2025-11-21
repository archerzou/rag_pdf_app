# command for API
uv run uvicorn main:app

# command for inngest
npx inngest-cli@latest dev -u http://127.0.0.0:8000/api/inngest --no-discovery

# command for streamlit
uv run streamlit run streamlit_app.py 
