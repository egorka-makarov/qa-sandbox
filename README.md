# qa-sandbox

Учебный проект для подготовки к квалификации Senior Crossfunc QA.

## Первый запуск

```bash
python -m venv .venv
# Windows: .venv\Scripts\activate
# macOS / Linux: source .venv/bin/activate
pip install -r requirements.txt
playwright install
cp .env.example .env   # затем указать BASE_URL
```

## Залить на GitHub

```bash
git init
git add .
git commit -m "Initial project skeleton"
git branch -M main
git remote add origin https://github.com/<username>/qa-sandbox.git
git push -u origin main
```

## Что будет добавляться по ходу
- Dockerfile и docker-compose.yml: блок Docker
- Jenkinsfile: блок Jenkins
- `.github/workflows/`: блок CI
