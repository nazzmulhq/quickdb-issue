<div align="center">
  <img src="https://nazmulhaque.netlify.app/images/quickdb-icon.png" alt="QuickDB Logo" width="64" height="64" align="center">
  <h1></h1>
  <p><b>The Ultimate Database Management & AI Integration Extension for VS Code</b></p>
  <p>A DataGrip-inspired database client built right into your editor. Browse tables, run complex queries, manage schemas, and supercharge your workflow with a built-in MCP (Model Context Protocol) Server for AI tools.</p>
</div>

<p align="center">
  <img src="https://nazmulhaque.netlify.app/gifs/quickdb/mcp-server-intro.gif" alt="MCP Server Intro">
</p>

---

## 🚀 Why QuickDB?

QuickDB turns VS Code into a powerhouse database management tool. Whether you're inspecting data, visualizing relationships, or letting AI write your queries, QuickDB provides a seamless, context-rich experience without ever leaving your editor.

- **Universal database support** — connect to PostgreSQL, MySQL, SQLite, MongoDB, Redis and **81+ engines** from one unified interface.
- **AI-ready MCP server** — expose your schema and data to AI agents like Cursor, Claude Desktop, Antigravity and Windsurf.
- **Query Console** — IntelliSense-powered SQL editor with inline result inspection, formatting and history.
- **Visual Query Builder** — construct joins and aggregations visually, no SQL required.
- **Table Manager** — create, modify and visualize your schema with an intuitive UI.
- **Data visualization** — chart any query result into exportable graphs.
- **Import & export** — move data between SQL dumps, JSON, CSV and Excel.

---

## 📸 See It in Action

### Connect & import
Connect to your servers and import data seamlessly.

![Connect server and import database](https://nazmulhaque.netlify.app/gifs/quickdb/connect-server-import-database.gif)

### Query Console
Write and run SQL with autocomplete, linting and inline results.

![Query Console demo](https://nazmulhaque.netlify.app/gifs/quickdb/queryconsole.gif)

### Visual Query Builder
Build complex SQL queries visually without writing code.

![Query Builder demo](https://nazmulhaque.netlify.app/gifs/quickdb/query-builder.gif)

### AI charts via MCP
Ask your AI assistant a question and let it query your data and chart the result — all through MCP.

![Use MCP to make a chart](https://nazmulhaque.netlify.app/gifs/quickdb/use-mcp-to-make-chart.gif)

### Connect external AI clients
Connect QuickDB to your favorite AI assistant (Cursor, Claude Desktop, Windsurf, Continue, …) in a few clicks: run **`QuickDB: Setup MCP Server`**, pick your connections, copy the snippet into your client's config, and restart.

![External client setup](https://nazmulhaque.netlify.app/gifs/quickdb/external-client-setup.gif)

---

## 🗄️ Supported Databases

**81+ engines** across SQL, NoSQL, graph, time-series, vector, file-format, streaming and cloud-analytics systems:

- **Relational (MySQL):** MySQL · MariaDB · TiDB · SingleStore · StarRocks · Apache Doris
- **Relational (PostgreSQL):** PostgreSQL · CockroachDB · Timescale · Amazon Redshift · Greenplum · QuestDB · RisingWave · YugabyteDB · KingbaseES · Netezza · PGlite
- **Relational (SQL Server):** SQL Server · Azure SQL · Azure Synapse · SAP ASE (Sybase) · Microsoft Fabric
- **Relational (SQLite):** SQLite · libSQL (Turso) · Cloudflare D1
- **Relational (other):** Oracle · IBM DB2 · IBM i · Vertica · Firebird · Dameng · Exasol · H2 · Apache Derby · Microsoft Access
- **Analytics / Warehouse:** ClickHouse · DuckDB · MotherDuck · DuckLake · Snowflake · BigQuery · Databricks · Trino · Amazon Athena · Apache Druid · Apache Pinot · Apache Hive · Apache Impala
- **Document:** MongoDB · CouchDB · Couchbase · RavenDB · Firebase Firestore · Dataverse
- **Key-value / Cache:** Redis · Memcached · Aerospike · Amazon DynamoDB
- **Wide-column:** Cassandra · ScyllaDB · Google Spanner
- **Graph:** Neo4j · Memgraph · TypeDB
- **Search:** Elasticsearch · OpenSearch
- **Time-series:** InfluxDB
- **Multi-model:** SurrealDB
- **Vector:** Qdrant · Milvus · Pinecone · Weaviate · ChromaDB · LanceDB
- **Streaming:** Apache Kafka · RabbitMQ
- **Files:** CSV · Excel · Parquet · Avro · Apache Iceberg
- **SaaS:** Salesforce

---

## 🏁 Get Started

1. Open the **Extensions** view (`Ctrl/Cmd+Shift+X`) and search for **QuickDB**, then **Install**.
2. Click the **QuickDB icon** in the Activity Bar to open the connections view.
3. Click **`+`** (or run `QuickDB: Add Connection`), pick your engine, fill in credentials, **Test**, then **Create**.
4. Expand your connection and click any table to start browsing, querying and editing.

---

<div align="center">
  <sub>Built by <a href="https://nazmulhaque.netlify.app/">Nazmul Haque</a> · <a href="https://nazmulhaque.netlify.app/quickdb">Learn more</a></sub>
</div>
