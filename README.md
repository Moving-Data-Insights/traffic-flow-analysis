# traffic-flow-analysis

Spatiotemporal traffic flow analysis using MobilityDB, Jupyter, and Grafana — querying and visualising movement data stored in a PostgreSQL/MobilityDB database.

## The Problem

- Traditional relational databases handle static data well but struggle with time-evolving spatial objects such as vehicle trajectories.
- MobilityDB extends PostgreSQL with native temporal-spatial types, enabling SQL queries over moving objects without pre-aggregating the data.
- Analysing traffic flow patterns requires both a capable data store and an accessible visualisation layer.

## The Approach

**Inputs:** Traffic movement data loaded into MobilityDB (PostgreSQL with the MobilityDB extension), running in Docker.

**Processing:** `main.ipynb` queries MobilityDB using JupySQL (SQL in Jupyter notebooks) via a SQLAlchemy + psycopg2 connection. Analysis and transformation is done in Python with Pandas and NumPy.

**Outputs:** Query results and visualisations displayed in the notebook; a Grafana dashboard connects to the same database for live charting.

## Value Delivered

- Demonstrates end-to-end spatiotemporal analysis workflow using MobilityDB.
- Shows how to combine Jupyter SQL notebooks and Grafana against the same containerised database.
- Practical reference for anyone exploring MobilityDB for movement data.

## Scope & Status

- **Project type:** Research / internal tool
- **Current state:** Paused
- **Known limitations:**
  - Requires Docker; no cloud deployment configuration.
  - No sample dataset included; users must supply their own movement data.
  - Grafana dashboard configuration is not version-controlled.

## Tech Stack

- **Database:** MobilityDB (PostgreSQL extension), via Docker
- **Visualisation:** Grafana (Docker container)
- **Analysis:** Python, Jupyter Notebook, JupySQL
- **Libraries:** SQLAlchemy, psycopg2, Pandas, NumPy

## Who This Is For

Data engineers and analysts exploring spatiotemporal query capabilities with MobilityDB.

## Getting Started

Prerequisites: Docker, Python 3.x, pip.

```bash
# Install Python dependencies
pip install -r requirements.txt

# Create a shared Docker network so Grafana and MobilityDB can communicate
docker network create my-network
docker network connect my-network <grafana-container-name>
docker network connect my-network <postgres-container-name>

# Open the analysis notebook
jupyter notebook main.ipynb
```

See [ploomber/jupysql](https://github.com/ploomber/jupysql) for JupySQL usage.

## License

Not specified.
