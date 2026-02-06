# COE Analytics (FastAPI + React)

Interactive dashboard for COE seasonality, analysis, and premium tracking. The backend is FastAPI with SQLite, and the frontend is a React app (Vite).

## Prerequisites

- Python 3.11+

## Setup

1) Create the database from the CSV:

```sh
python backend/db/init_db.py
```

2) Run the API server:

```sh
python -m uvicorn backend.main:app --reload
```

3) Run the React frontend (new terminal):

```sh
cd frontend
npm install
npm run dev
```

## API

- `GET /api/seasonality`
  - Query params:
    - `vehicle_class` (e.g. `Category A`)
    - `start_year` (e.g. `2010`)
    - `end_year` (e.g. `2019`)
    - `aggregation` (`mean` or `median`)

Example:

```sh
curl "http://127.0.0.1:8000/api/seasonality?vehicle_class=Category%20A&start_year=2010&end_year=2019&aggregation=mean"
```

- `GET /api/analysis`
- `GET /api/premium`

## Frontend build

To serve the React build from FastAPI:

```sh
cd frontend
npm run build
```

Then open:

```
http://127.0.0.1:8000/
```
