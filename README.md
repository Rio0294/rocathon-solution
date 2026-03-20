# rocathon-solution
Build a semantic projected score search engine for rocathon where users can search for creators by category and vibe. Then rank them by GMV and projected score. 

The submission returns 8 results instead of 10. A match_threshold of 0.3 was chosen to make sure only creators who are genuinely relevant to the query are returned. Higher values (e.g., 0.5) would return too few results from our 200-creator dataset. Lower values (e.g., 0.1) would allow unrelated creators. 0.3 is relevant enough to match the brand vibe, loose enough to return meaningful results.
Thus, balancing creative fit with commercial viability.

## Setup

### 1. Clone + install

```bash
git clone <your-fork>
cd roc-hackathon
npm install
```

### 2. Configure environment

```bash
cp .env.example .env
# Fill in OPENAI_API_KEY and DATABASE_URL
```

### 3. Set up your vector DB

Option A — Supabase (recommended, no Docker):
- Create a free project at supabase.com
- Enable the `pgvector` extension: SQL Editor → `CREATE EXTENSION IF NOT EXISTS vector;`
- Copy the connection string to `DATABASE_URL`

Option B — Local Docker:
- Requires Docker installed
- Set up your own `docker-compose.yml` with `pgvector/pgvector:pg15`

### 4. Create your schema

Design your own table schema. At minimum you'll need a `vector` column for embeddings.

### 5. Ingest creators

```bash
npm run ingest
```

### 6. Run demo

```bash
npm run demo
```
