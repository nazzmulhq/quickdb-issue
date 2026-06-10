<div align="center">
  <img src="https://nazmulhaque.netlify.app/images/quickdb-icon.png" alt="QuickDB Logo" width="64" height="64" align="center">
  <h1></h1>
  <p><b>The Ultimate Database Management & AI Integration Extension for VS Code</b></p>
  <p>A DataGrip-inspired database client built right into your editor. Browse tables, run complex queries, manage schemas, and supercharge your workflow with our built-in MCP (Model Context Protocol) Server for AI tools.</p>
</div>

<p align="center">
  <img src="https://nazmulhaque.netlify.app/gifs/quickdb/mcp-server-intro.gif" alt="MCP Server Intro">
</p>

---

## 🚀 Why QuickDB?

QuickDB turns VS Code into a powerhouse database management tool. Whether you're inspecting data, visualizing relationships, or letting AI write your queries, QuickDB provides a seamless, context-rich experience without ever leaving your editor.

### ✨ Key Features at a Glance

*   **Universal Database Support:** Connect to PostgreSQL, MySQL, SQLite, MongoDB, and Redis—all from a single unified interface.
*   **AI-Ready with Built-In MCP Server:** Instantly expose your database schema and data to AI agents like Cursor, Claude Desktop, Antigravity, Windsurf, and more.
*   **Visual Query Builder:** Construct complex queries, joins, and aggregations visually—no SQL required.
*   **Powerful Table Manager:** Create, modify, and visualize your schema with an intuitive UI.
*   **Relationship Navigation:** Follow foreign keys by clicking—jump to a referenced row or list every row that references it, no manual `JOIN`s.
*   **Data Visualization:** Instantly chart any query result into stunning, exportable Ant Design Plots graphs.
*   **Import & Export:** Move data easily between SQL dumps, JSON, CSV, and Excel.

---

## Table of Contents

1. [Getting Started](#getting-started)
2. [Supported Databases](#supported-databases)
3. [Connection Management](#connection-management)
4. [Table Viewer](#table-viewer)
5. [Query Console](#query-console)
6. [Visual Query Builder](#visual-query-builder)
7. [Table Manager](#table-manager)
8. [Import & Export](#import--export)
9. [Data Compare](#data-compare)
10. [Copy to Database](#copy-to-database)
11. [Data Visualization](#data-visualization)
12. [MCP Server Integration](#mcp-server-integration)
13. [Chat Commands (@quickdb)](#chat-commands-quickdb)
14. [Keyboard Shortcuts](#keyboard-shortcuts)
15. [Troubleshooting](#troubleshooting)

---

## 📸 See It in Action

### Database Management & Imports
Easily connect to your servers and import data seamlessly.
![Connect server and import database](https://nazmulhaque.netlify.app/gifs/quickdb/connect-server-import-database.gif)

### Visual Query Builder
Build complex SQL queries visually without writing code.
![Query Builder demo](https://nazmulhaque.netlify.app/gifs/quickdb/query-builder.gif)

### Connect with External AI Clients

Connect QuickDB to your favorite AI assistant (Cursor, Claude Desktop, JetBrains AI, Windsurf, Continue, etc.) in just a few clicks:

1. **Open the Setup Panel:** Press `Cmd+Shift+P` (macOS) or `Ctrl+Shift+P` (Windows/Linux) and run `QuickDB: Setup MCP Server`.
2. **Select Connections:** Choose which databases you want the AI to have access to.
3. **Copy Snippet:** Click "Copy snippet" on the card matching your AI client.
4. **Paste & Restart:** Paste the JSON into your client's config file and restart the client.

![External client setup](https://nazmulhaque.netlify.app/gifs/quickdb/external-client-setup.gif)



## 🏁 Getting Started

### 📦 Installation

1. **Open VS Code** and navigate to the Extensions view (`Ctrl+Shift+X` or `Cmd+Shift+X`).
2. **Search** for `"QuickDB"`.
3. **Click Install** on the QuickDB extension.

> **Note:** After installation, a new **QuickDB icon** will appear in your Activity Bar (left sidebar). Click it to open the connections view.

### ⚡ Quick Start (Adding a Database)

Follow these steps to connect your first database:

1. **Open the Panel:** Click the QuickDB icon in the sidebar.
2. **Add a Connection:** Click the **`+`** icon at the top of the panel, or run `QuickDB: Add Connection` from the Command Palette.
3. **Provide Details:** Select your database engine (PostgreSQL, MySQL, MongoDB, SQLite, or Redis) and fill in your connection credentials.
4. **Test & Save:** Click **Test connection** to verify your details, then click **Create connection** to save it.
5. **Explore:** Your new database will appear in the tree view. Expand it and click any table to start browsing and editing data!

---

## Supported Databases

QuickDB supports both SQL and NoSQL databases:

| Database   | Type  | Default Port | Notes                                                      |
| ---------- | ----- | ------------ | ---------------------------------------------------------- |
| SQLite     | SQL   | N/A          | File-based, supports `:memory:`                            |
| MySQL      | SQL   | 3306         | Full INFORMATION_SCHEMA support                            |
| PostgreSQL | SQL   | 5432         | SSL/TLS supported                                          |
| MongoDB    | NoSQL | 27017        | Connection string or host/port                             |
| Redis      | NoSQL | 6379         | All data types (strings, hashes, lists, sets, sorted sets) |

---

## Connection Management

### Adding a Connection

1. Open the QuickDB sidebar
2. Click the **+** button or run `QuickDB: Add Connection`
3. Select the database type from the 5 available options
4. Fill in the required fields:

**SQLite:**

- Connection name
- Database file path (use Browse... to select)
- Supports `.db`, `.sqlite`, `.sqlite3` files
- Use `:memory:` for an in-memory database

**MySQL / PostgreSQL:**

- Connection name
- Host (default: `localhost`)
- Port (MySQL: `3306`, PostgreSQL: `5432`)
- Username / Password
- Database name
- SSL/TLS toggle

**MongoDB:**

- Connection name
- Option A: Host, Port, Username, Password — and an optional Database name. Leave empty to connect and browse every database on the server (the sidebar tree expands to show databases first).
- Option B: Full connection string (`mongodb://...`)
- SSL/TLS toggle

**Redis:**

- Connection name
- Host (default: `localhost`)
- Port (default: `6379`)
- Password (optional)
- Database index (0-15)
- SSL/TLS toggle

### Color Coding

Assign a color to each connection for quick visual distinction:

| Color  | Suggested Use |
| ------ | ------------- |
| Red    | Production    |
| Orange | Staging       |
| Yellow | Warning       |
| Green  | Development   |
| Blue   | Default       |
| Purple | Testing       |

Production connections (red) show a warning indicator in the tree view.

### Editing & Removing Connections

- **Edit:** Right-click a connection > Edit Connection
- **Remove:** Right-click a connection > Remove Connection
- **Refresh:** Right-click a connection > Refresh, or press F5

### Filtering Tables

Filter tables instantly per database:

1. Expand a connection in the sidebar
2. Type in the **Find table...** input box directly below the connection name
3. The list of tables will filter live as you type

## Table Viewer

The Table Viewer is the primary data browsing interface. Click any table in the sidebar tree to open it.

### View Modes

Switch between 4 view modes using the toolbar buttons:

| Mode      | Icon | Description                      |
| --------- | ---- | -------------------------------- |
| Table     | #    | Standard grid view (default)     |
| Transpose | T    | Rows displayed as columns        |
| Text      | A    | Plain text / export-ready format |
| Tree      | >    | Hierarchical tree view           |

### Editing Data

- **Edit a cell:** Click on a cell and type the new value
- **Add a row:** Click **+ Add** in the toolbar or press `Ctrl+N`
- **Delete rows:** Select rows (click the checkbox), then click **- Delete** or press `Del`
- **Set NULL:** Right-click a cell > Set NULL (`Ctrl+Alt+N`)
- **Duplicate Row:** Right-click a cell > Duplicate Row

### Saving Changes

- **Save:** Click **Save** or press `Ctrl+S` - applies all pending changes to the database
- **Discard:** Click **Discard** to undo all pending changes
- **Preview SQL:** Right-click > Preview SQL Changes (`Ctrl+P`) to see the generated DML statements before applying

The status bar shows the number of pending changes.

### Value Editor

For editing long text, JSON, or complex values:

1. Select a cell
2. Press `Shift+Enter` or right-click > Open in Value Editor
3. A side panel opens with a full text editor
4. Edit the value and click Confirm

### Single Record View

View one row at a time in a form layout:

1. Select a cell
2. Press `Ctrl+Shift+Enter` or right-click > View as Single Record
3. Navigate between rows using the arrow buttons
4. Edit values inline

### Go To Row

Jump to a specific row:

1. Press `Ctrl+G` or click **Go To** in the toolbar
2. Enter the row number
3. The table scrolls to and selects that row

### Aggregate View

View aggregate statistics for selected data:

1. Select one or more rows (click checkboxes)
2. Click the **Agg** button in the toolbar
3. Shows count, sum, average, min, max of numeric values

### Filtering & Sorting

**Global Search:** Type in the search bar to filter across all columns.

**Column Filters:**

1. Click **+ Filter** to add a column-specific filter
2. Select the column, operator, and value
3. Multiple filters can be combined

**Sorting:** Click any column header to sort. Click again to toggle ascending/descending.

### Exporting Data

- **CSV:** Click the **CSV** button in the toolbar
- **JSON:** Click the **JSON** button in the toolbar

### Context Menu

Right-click any cell to access:

- Copy / Copy as JSON
- Set NULL
- Open in Value Editor
- View as Single Record
- Duplicate Row
- Preview SQL Changes
- Delete Row

### Relationship Navigation

QuickDB reads foreign keys from your schema (SQLite, MySQL, PostgreSQL) and turns
key cells into clickable links — no manual `JOIN`s. Hover a cell to reveal the
relationship actions:

- **Jump to the referenced row (↗):** On a foreign-key cell, opens the parent
  table in a new tab, pre-filtered to that key (e.g. open `actor` where
  `actor_id = 19`).
- **Show referencing rows (branch icon):** On a primary-key (or referenced)
  cell, opens the child table filtered to rows that point back to this one.
  When several tables reference it, a menu lets you pick which relationship to
  follow.

Each jump opens a full table viewer tab with a visible filter chip describing
how it was reached, so navigation stays chainable and easy to trace.

**Inferred relationships:** For schemas without declared foreign keys — MongoDB
especially, but also FK-less SQL tables — QuickDB infers links by naming
convention. A column like `user_id` / `userId` is matched to the `users`
collection/table (with singular/plural handling such as `category_id` →
`categories`). Inferred links navigate exactly like declared ones and are
labelled **inferred** in their tooltip/menu so you know they're a best-effort
guess. Declared foreign keys always take precedence.

### Fill a Column

Select one or more columns by clicking their type badge in the header, then edit
any cell in a selected column — the value fills every filtered row across all
selected columns. Click **Save** to write the change.

---

## Query Console

Run arbitrary queries against your database.

### Toolbar

| Button        | Description                                                                             |
| ------------- | --------------------------------------------------------------------------------------- |
| **Run**       | Run the selected text, or the statement at the cursor (`Ctrl/Cmd+Enter`)                |
| **Run all**   | Run every statement in the editor                                                       |
| **Explain**   | Wrap the current statement in `EXPLAIN` (`EXPLAIN QUERY PLAN` on SQLite) and run it to see the query plan |
| **Ask AI**    | Hand the current query off to the `@quickdb` chat assistant (opens chat — no API key; uses the editor's built-in model) |
| **Clear**     | Empty the editor                                                                        |
| **Format**    | Pretty-print the SQL — one major clause per line, indented `ON / AND / OR`              |
| **Copy SQL**  | Copy the editor contents to the clipboard                                               |
| **Save**      | Pin the current query to your Saved library (per-workspace, scoped to this connection)  |
| **History**   | Toggle the side panel showing past executions for this connection + database            |
| **Saved**     | Toggle the side panel showing your saved snippets — click an entry to load it           |
| **Schema**    | Toggle the schema browser side panel                                                    |
| **Templates** | Pick a starter SQL snippet (inserted at the cursor — never replaces your current query) |
| **Read-only** | Toggle (top-right). When on, only read statements (SELECT/SHOW/EXPLAIN/…) may run — writes are blocked before they reach the database |

Destructive statements (`DROP TABLE`, `DROP DATABASE`, `TRUNCATE`, and unscoped `DELETE` / `UPDATE`) prompt for confirmation before running.

### Editor

- **Context-aware autosuggest** triggers as you type (debounced) and offers only what's valid at the cursor — tables after `FROM`/`JOIN`, columns + functions after `SELECT`, columns + operators + `IS NULL`/`EXISTS` after `WHERE`, `ASC`/`DESC` after `ORDER BY`, and top-level keywords at the start — rather than dumping every category at once. It stays **closed where it would just be noise**: inside string literals, inside `--`/`/* */` comments, and while typing a bare number (e.g. `LIMIT 10`). **Click into a word** (its end or middle) to re-open suggestions for exactly that position — clicking in whitespace, a string, or a comment closes it; and accepting a suggestion mid-word replaces the whole word, not just the part before the caret. Use `Ctrl/Cmd+Space` to force open. `Tab` / `Enter` accepts. Each row carries a kind tag (`COL`/`TBL`/`ƒn`/…), the matched prefix in **bold**, and — for columns — the data type plus a **PK**/**FK** marker.
- **Type `table.` (or `alias.`)** to list that table's columns instantly (a leading `*` option inserts `table.*`; primary keys sort first). Columns/foreign keys for tables you reference are pre-loaded as you type, so the dot list is ready immediately.
- **Foreign-key JOIN completion**: in a `… JOIN <here>` position, related tables are offered with a ready-made `ON` clause derived from foreign keys (in either direction), e.g. `JOIN orders ON users.id = orders.user_id`.
- **Live, dialect-aware validation** flags problems as you type and underlines the offending word in red. Generic SQL checks: unknown tables, **unknown columns** (`users.naem`), unbalanced parens / quotes, trailing commas, missing `FROM`, unscoped `UPDATE`/`DELETE`, `= NULL` (→ `IS NULL`), `SELECT TOP …` (→ `LIMIT`), invalid operators (`==`, `=<`, `=>`), empty `IN ()`, a `JOIN` with no `ON`/`USING` (accidental cross join), duplicate clauses, and out-of-order clauses (e.g. `WHERE` after `ORDER BY`). Per engine: backtick identifiers flagged on **PostgreSQL/SQLite**, `ILIKE` flagged off **PostgreSQL**, `LIMIT a, b` flagged on **PostgreSQL**, and `||` flagged on **MySQL** (it's logical OR there). **MongoDB** queries are checked for `db.…` shape and brace/bracket balance; **Redis** for unknown commands — neither is run through the SQL rules. The identifier you're currently typing isn't flagged until you move off it.
- **Smart error fixes**: for an unknown column/table the panel suggests the closest real identifier — **Did you mean `…`? [Apply fix]** rewrites the editor text (it never runs anything). **Fix with AI** copies the failing query + error to the clipboard and hands it to the `@quickdb` chat assistant.
- The bottom **results pane** is resizable — drag the splitter above it. The **side panel** (History / Saved / Schema) is also resizable — drag the splitter on its left edge.
- A live **status bar** shows current row/column and connection.

### Saved query library

The Saved tab persists named SQL snippets per workspace, scoped to the connection + database the editor is currently bound to.

- Click **Save** with SQL in the editor → you're prompted for a name (with a sensible default like `select users`).
- Switch tabs to **Saved** to browse: click an entry's name to load it back into the editor; hover for inline rename / delete actions.
- Saved snippets survive VS Code reloads; they're stored in extension `globalState`.

### Result export

Click **CSV** or **JSON** above the results table to export. Exports stream from the host directly to disk — no row data is shipped through the webview, so even 100k-row exports complete promptly. Use **Copy to clipboard** for quick paste.

### SQL Databases (SQLite, MySQL, PostgreSQL)

Write standard SQL queries:

```sql
SELECT * FROM users WHERE role = 'admin';
INSERT INTO products (name, price) VALUES ('Widget', 9.99);
UPDATE users SET role = 'moderator' WHERE id = 5;
```

### MongoDB

Use the `db.collection.method()` syntax:

```
db.users.find({"role": "admin"})
db.users.findOne({"_id": "abc123"})
db.users.insertOne({"name": "Alice", "role": "user"})
db.users.updateOne({"_id": "abc123"}, {"$set": {"role": "admin"}})
db.users.deleteOne({"_id": "abc123"})
db.users.countDocuments({"role": "user"})
db.users.aggregate([{"$group": {"_id": "$role", "count": {"$sum": 1}}}])
```

Supported methods: `find`, `findOne`, `insertOne`, `insertMany`, `updateOne`, `updateMany`, `deleteOne`, `deleteMany`, `countDocuments`, `aggregate`, `distinct`

### Redis

Use standard Redis commands:

```
GET mykey
SET mykey "hello world"
DEL mykey
KEYS user:*
HGETALL myhash
HSET myhash field1 "value1"
LRANGE mylist 0 -1
LPUSH mylist "item1"
SMEMBERS myset
SADD myset "member1"
ZRANGE myzset 0 -1 WITHSCORES
TYPE mykey
TTL mykey
INFO
DBSIZE
PING
```

### Query Results

- Results display in a table below the query editor
- Column names and row counts are shown
- Execution time is displayed
- Errors appear with descriptive messages

---

## Visual Query Builder

Build complex SQL queries visually without writing code.

### Opening the Query Builder

- Right-click a connection in the sidebar > **Query Builder**
- Or click the **Query Builder** icon (`ConsoleSqlOutlined`) when hovering over a connection

![Query Builder demo](https://nazmulhaque.netlify.app/gifs/quickdb/query-builder.gif)

### Header controls

- **Connection** dropdown — switch which database you're querying without leaving the panel.
- **Query type** segmented — SELECT / INSERT / UPDATE / DELETE.
- **From table** — single-select dropdown. Pick the FROM target.
- **+ Add join** — single-select dropdown that appears once a main table is set. Picking a table adds it as an unconfigured `INNER JOIN`; the dropdown then resets so you can add more.
- **Subquery** — toggle button (highlighted when active) to use a hand-written subquery as the FROM target instead of a real table.

### Features

- **Drag-to-join**: drag from a column in one table to a column in another to wire up the `ON` clause.
- **Custom subqueries**: use a custom SQL subquery as the main table or as a joined table.
- **Select columns**: tick the columns you want in `SELECT`; group, sort, and filter from the same panel.
- **Joins**: `INNER`, `LEFT`, `RIGHT`, `FULL` — configure type, columns, and aliases.
- **Filters (WHERE / HAVING)**: nested AND/OR groups with operators `=`, `!=`, `<`, `>`, `LIKE`, `IN`, `BETWEEN`, `IS NULL`, …
- **Sorting (ORDER BY)** and **pagination (LIMIT/OFFSET)** — drive both from the column picker.

### Layout

The bottom of the panel shows **SQL Preview and Results side-by-side**, separated by a draggable vertical splitter. Drag the top edge of the bottom panel to resize the editor/results split; drag the inner splitter to favour SQL or Results. No more flipping tabs.

### Saved visual queries

QueryBuilder has its own per-connection library of saved snippets (separate from the QueryConsole Saved tab — these entries carry the structured model, not just rendered SQL):

- **Save** in the toolbar — names and pins the current model. Opens an input box with a sensible default like `select users`.
- **Saved** in the toolbar — opens a popover listing pinned visual queries. Click an entry to rehydrate the entire builder state (main table, joins, columns, filters, sort, limit). Hover for inline rename / delete.

### Schema cache

Column and foreign-key metadata for every table you've expanded is cached and persisted across panel close/reopen, so the visual picker doesn't re-fetch on every reopen. Cache is cleared when you switch connections.

---

## Table Manager

Create and modify database tables with a visual interface.

### Creating a Table

1. Right-click a connection > Create Table
2. Enter the table name
3. Add columns with:
    - Name and data type
    - Primary key / Auto-increment
    - Nullable / Unique constraints
    - Default values
    - Comments (MySQL/PostgreSQL)
    - Character set / Collation (MySQL)
    - Check constraints
    - Generated columns

### Managing Tables

You can access these options by **Right-Clicking** a table or using the **Inline Action Icons** visible when hovering over a table in the sidebar:

- **Edit Table:** Opens the visual Table Manager
- **Import Data:** Import CSV/JSON/SQL/Excel into the table
- **Export Data:** Export table data to CSV/JSON/SQL/Excel
- **Delete Table:** Drop the table (with confirmation)
- **Rename/Modify Columns:** Use the Table Manager Interface

### Index Management

- View all indexes for a table
- Create new indexes (unique or non-unique)
- Drop existing indexes

---

## Import & Export

Move data between QuickDB and `.sql` / `.json` / `.csv` / `.xlsx` files. Right-click a connection in the sidebar for **Export Database** / **Import Database**, or right-click a table for **Export Table** / **Import to Table**.

![Connect server and import database](https://nazmulhaque.netlify.app/gifs/quickdb/connect-server-import-database.gif)

### Export

Pick a destination format on the panel:

- **SQL** — schema + data dump. Toggle "DROP TABLE statements" to make the dump idempotent on re-import. Toggle "Schema only" to skip the row data.
- **JSON** — one file containing every selected table.
- **CSV** — one CSV file per table, written into a folder you pick.
- **Excel (xlsx)** — one workbook with one sheet per table.

Use the search box to filter the table list, then tick the tables you want included. Progress is reported live, and the success screen shows tables, rows exported, and elapsed time.

### Import

Pick a `.sql`, `.json`, `.xlsx`, or `.csv` file:

- **SQL** — replays statements. For MySQL the extension uses the local `mysql` CLI when available (much faster than the in-process parser); it falls back to the internal parser otherwise. For Postgres / SQLite, the native CLI is also used when available. Imports are routed to the database you opened the panel against (no more "wrong database" surprises).
- **JSON** — streams every table in the dump straight into the destination database. Memory usage stays bounded regardless of file size.
- **XLSX** — one sheet per destination table.
- **CSV** — a small QuickPick lets you pick (or create) the destination table. Numeric-looking strings (phone numbers, ZIP codes, leading zeros) are preserved as strings; identifiers are SQL-escaped so column names containing quotes don't break the insert.

### Security notes

- Native CLI imports use `execFile` / `spawn` with argv arrays — never a shell-parsed string — so filenames, hosts, database names, or paths containing shell metacharacters can't break out.
- All identifiers (column names, table names) are properly quoted with the SQL standard double-the-quote-char rule.

---

## Data Compare

Compare data between two tables or connections.

1. Open via the Command Palette: `QuickDB: Compare Data`
2. Select source and target connections/tables
3. View differences highlighted in the comparison grid

---

## Copy to Database

Copy table data from one database to another.

1. Open via the Command Palette: `QuickDB: Copy to Database`
2. Select the source table
3. Choose the target connection
4. Configure copy options
5. Click Execute to perform the copy

---

## Data Visualization

Chart any query result, save the chart, and download it as PNG / SVG / HTML / spec JSON. The same engine renders charts inside the extension and answers AI requests via the MCP server, so output is identical regardless of which surface kicked the render.

### Opening the Visualization panel

| From                | How                                                                                                                                                   |
| ------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Query Console**   | Run a query → click the **Visualize** button on the results toolbar. The panel opens pre-loaded with the result columns + rows + the originating SQL. |
| **Command palette** | `Ctrl/Cmd+Shift+P` → `QuickDB: Open Visualization`. Empty panel; paste data via the spec editor.                                                      |

### Two modes

**Template mode** (default) — pick a chart type (`bar`, `line`, `area`, `pie`, `scatter`, `histogram`, `heatmap`, `boxplot`, etc.) and map your columns to X axis / Y axis / Group-by / Aggregation. The panel synthesizes a Ant Design Plots config live; the generated config is shown in a read-only pane below the mappings so you can copy it.

**Spec mode** — paste any config from the [Ant Design Plots gallery](https://ant-design-charts.antgroup.com/en/examples). Your data fills `data` automatically (unless your config sets one). Full gallery is reachable: dual axes, faceted plots, and advanced statistical visualisations that Ant Design Plots ships natively, etc.

### Chart types built in

Available template names: `bar`, `bar_grouped`, `bar_stacked`, `bar_horizontal`, `line`, `line_multi`, `step_line`, `trail`, `area`, `area_stacked`, `area_streamgraph`, `pie`, `donut`, `arc`, `scatter`, `bubble`, `histogram`, `density`, `boxplot`, `heatmap`, `rect_heatmap`, `tick_strip`, `error_bar`, `regression`, `text_table`, `radial`.

Anything else from the Ant Design Plots gallery → use Spec mode.

### Download formats

The **Download** button is a dropdown:

| Format   | What you get                                                                                             |
| -------- | -------------------------------------------------------------------------------------------------------- |
| **SVG**  | Vector text — sharp at any zoom.                                                                         |
| **HTML** | Standalone HTML that loads `react` + `ant-design/plots` from jsDelivr. Open in any browser, shareable.                   |
| **JSON** | The Ant Design Plots config itself. Replays in any Ant Design tool.                                                     |

The Save dialog opens at the first workspace folder by default; if no folder is open, it falls back to `~/Downloads` (or `~/Documents`/`~` if Downloads isn't available). If you see a "Permission denied" toast on download, pick a folder you own — VS Code's default path can otherwise resolve into the extension install directory, which is read-only.

### Saved charts

The **Save** button names the current chart and persists it to workspace global state (`quickdb.savedVisualizations`). The left panel lists every saved chart — click to rehydrate (spec + data snapshot if ≤ 2000 rows). Delete via the trash icon.

### MCP visualization tools

External MCP clients (Cursor, Claude Desktop, Antigravity, Windsurf, …) get three new tools that drive the same Ant Design Plots engine:

| Tool                      | Purpose                                                                                         |
| ------------------------- | ----------------------------------------------------------------------------------------------- |
| `quickdb_visualize_query` | Run SQL, render the result as a chart, return PNG file path + base64 data URL + Ant Design Plots config. |
| `quickdb_visualize_data`  | Render a chart from a caller-supplied data array (no SQL).                                      |
| `quickdb_chart_types`     | List supported templates with required/optional fields and an example spec each.                |

**Two input modes per tool**, mirroring the panel:

- **Template mode**: pass `template` (e.g. `"bar"`) + `xField`, `yField`, `groupBy?`, `aggregation?`. Easiest for an AI to author.
- **Raw-spec mode**: pass `spec` containing a complete Ant Design Plots config object. Data is injected into `data` for you unless the spec sets its own. Full Ant Design Plots gallery is reachable this way.

**Output (every visualization tool)**:

```json
{
  "path": "/<tmp or extension storage>/<sha1>.png",
  "svgPath": "/<...>/<sha1>.svg",
  "specPath": "/<...>/<sha1>.spec.json",
  "image": "data:image/png;base64,iVBORw0KG...",
  "svg": "<svg xmlns=...>",
  "spec": { ...ant-design-plots JSON... },
  "rowsRendered": 1234,
  "width": 500,
  "height": 320,
  "ms": 87
}
```

The PNG is content-addressed (SHA-1 of the spec) so identical re-renders hit a stat cache. Storage is bounded at 100 MB with LRU eviction.

### Safety caps

| Limit                | Default   | Override                                                               |
| -------------------- | --------- | ---------------------------------------------------------------------- |
| Max rows per chart   | 50,000    | — (hard cap, larger requires SQL-side aggregation)                     |
| Render timeout       | 10,000 ms | — (deliberate runaway protection)                                      |
| Content cache budget | 100 MB    | `QUICKDB_VIZ_STORAGE_DIR` env var to relocate; auto-LRU within the dir |

---

## MCP Server Integration

QuickDB includes a Model Context Protocol (MCP) server that enables AI tools to interact with your databases.

Note: The MCP server needs at least one saved connection. Use the setup panel to embed the connections you want exposed. See [docs/mcp-server-setup.md](docs/mcp-server-setup.md).

### Starting the MCP Server

The MCP server starts automatically when the extension activates. You can also:

- Start: Command Palette > `QuickDB: Start MCP Server`
- Stop: Command Palette > `QuickDB: Stop MCP Server`

### Available MCP Tools

| Tool                       | Description                                                  | Type  |
| -------------------------- | ------------------------------------------------------------ | ----- |
| `quickdb_list_connections` | List all saved database connections                          | Read  |
| `quickdb_list_tables`      | List tables for a connection                                 | Read  |
| `quickdb_describe_table`   | Get column details for a table                               | Read  |
| `quickdb_execute_query`    | Execute a read-only SQL/MongoDB/Redis query                  | Read  |
| `quickdb_execute_write`    | Execute a write SQL query (see safety rules below)           | Write |
| `quickdb_get_schema`       | Get full database schema                                     | Read  |
| `quickdb_get_rows`         | Get rows with filtering, sorting, pagination                 | Read  |
| `quickdb_count_rows`       | Count rows with optional filter                              | Read  |
| `quickdb_search_value`     | Search for text across columns                               | Read  |
| `quickdb_insert_row`       | Insert a row — returns the inserted row with auto-IDs        | Write |
| `quickdb_update_rows`      | Update rows matching a filter (filter required)              | Write |
| `quickdb_delete_rows`      | Delete rows matching a filter (filter required)              | Write |
| `quickdb_sample_rows`      | Uniform random sample of rows — quick shape recon            | Read  |
| `quickdb_distinct_values`  | Distinct values of one column, ordered by frequency          | Read  |
| `quickdb_table_stats`      | Row count, column count, PKs, FKs, column list with types    | Read  |
| `quickdb_health_check`     | Verify a connection is reachable without running user SQL    | Read  |
| `quickdb_visualize_query`  | Run SQL and render the result as an Ant Design Plots chart (PNG) | Read  |
| `quickdb_visualize_data`   | Render a chart from a caller-supplied data array             | Read  |
| `quickdb_chart_types`      | List supported chart templates + example specs               | Read  |

### Safety rules

- **`quickdb_execute_query`** allows only read forms: `SELECT`, `SHOW`, `DESCRIBE`, `EXPLAIN`, `VALUES`, `TABLE`, and `WITH … SELECT` (CTEs). Multi-statement queries (`SELECT 1; DELETE FROM x`) and `EXPLAIN ANALYZE INSERT/UPDATE/DELETE` (which Postgres actually executes) are rejected.
- **`quickdb_execute_write`** refuses to run `DROP DATABASE`/`DROP SCHEMA`, `TRUNCATE`, and unscoped `DELETE FROM x` / `UPDATE x SET …` (no `WHERE`) by default. Set the environment variable `QUICKDB_ALLOW_DESTRUCTIVE=1` in the MCP server config to opt out.
- **`quickdb_update_rows` / `quickdb_delete_rows`** require a non-empty `filter` so an AI can't wipe a table accidentally.
- **Row cap.** Structured read tools (`get_rows`, `sample_rows`, `distinct_values`, …) are hard-capped at 500 rows per call regardless of the `limit` argument. Defaults to 100 if `limit` is omitted. This protects calling LLM context windows from stray `limit: 1000000` requests.
- **Per-call timeout.** Every query goes through a wall-clock timeout (default 30 s). Override via `QUICKDB_QUERY_TIMEOUT_MS` so runaway queries can't lock the MCP channel.

These tools run their writes immediately when called. The Copilot/AI host is expected to confirm with the user before invoking write tools.

### Multi-database routing

If a connection has no database selected (MySQL / PostgreSQL / MongoDB), the MCP tools auto-resolve: structured tools like `quickdb_get_rows` walk every database in parallel to find the table. The `database` argument on any tool routes that single call to a specific database without changing the connection's default.

### Environment variables (stdio server)

When running the standalone stdio MCP server (`server/index.ts`):

| Variable                    | Default | Effect                                                                                 |
| --------------------------- | ------- | -------------------------------------------------------------------------------------- |
| `QUICKDB_CONNECTIONS`       | (unset) | JSON array of `ConnectionConfig` to seed the server's connection store on startup      |
| `QUICKDB_LOG_LEVEL`         | `info`  | `debug` \| `info` \| `warn` \| `error` — controls stderr verbosity                     |
| `QUICKDB_ALLOW_DESTRUCTIVE` | (unset) | Set to `1` to allow `DROP DATABASE`, `TRUNCATE`, and unscoped DELETE/UPDATE statements |
| `QUICKDB_QUERY_TIMEOUT_MS`  | `30000` | Per-tool-call query timeout in milliseconds — runaway queries are aborted              |

### Universal Table Auto-Resolution

When using AI tools or Copilot Chat for structured commands (like `get_rows` or `describe_table`), QuickDB features a **Universal Table Auto-Resolution Engine**.
If you simply ask the AI to "Show me 10 rows from the users table", you do NOT need to specify the connection or database. The MCP server will automatically scan all your saved connections and root out the proper underlying database that contains that target table, preventing tedious disambiguation prompts.

### External MCP Clients (Cursor, Claude Desktop, Antigravity, JetBrains AI, ...)

QuickDB ships a standalone stdio MCP server (`out/server/index.js`) that any MCP-compatible client can spawn. Open the setup panel via **`Cmd+Shift+P` → `QuickDB: Setup MCP Server (Cursor, Claude Desktop, …)`** (command id `quickdb.exportMcpConfig`). **The same JSON snippet works on Windows, macOS, and Linux** — path separators are OS-native and JSON-escaped automatically.

![MCP server setup panel](https://nazmulhaque.netlify.app/gifs/quickdb/mcp-quickdb.gif)

#### Step-by-step setup

Follow these six steps once per client (Cursor, Claude Desktop, Windsurf, Antigravity, Continue, JetBrains AI, …). After step 6 you're done; you only need to re-run steps 3–6 when you add/remove a connection.

##### 1. Verify Node.js 18+ is installed

The MCP server is a Node.js script — the client spawns `node` as a subprocess, so `node` must be on the system PATH (or you must supply an absolute path in step 3).

```sh
node --version
```

If you see anything ≥ `v18.x`, you're good. If `node` isn't found:

| OS                    | Install command                                                             |
| --------------------- | --------------------------------------------------------------------------- |
| macOS (Homebrew)      | `brew install node`                                                         |
| Windows               | Download the LTS installer from [nodejs.org](https://nodejs.org/)           |
| Linux (Debian/Ubuntu) | `sudo apt install nodejs npm` (or use [nvm](https://github.com/nvm-sh/nvm)) |

The setup panel has a **Test Node in terminal** button that runs `node --version` in a VS Code terminal so you don't have to leave the editor.

##### 2. Open the QuickDB setup panel

`Cmd+Shift+P` (macOS) / `Ctrl+Shift+P` (Windows/Linux) → type **`QuickDB: Setup MCP Server`** → hit Enter. The panel opens with:

- A red banner if `out/server/index.js` is missing (with a one-click **Run `npm run build`** button to fix it).
- A "Setup in 5 steps" overview at the top.
- Anchored cards lower down — one per supported client.

##### 3. Pick which connections to embed

Scroll to the _Connections to embed_ card. Tick the connections you want the MCP server to know about. Their credentials get baked into a `QUICKDB_CONNECTIONS` environment variable inside the snippet.

- Use **Select all** / **Select none** as shortcuts.
- Toggle **Replace passwords with `<set this>`** if you want to share or commit the snippet — the placeholders make it obvious where to plug real credentials back in.

> ⚠️ Without this toggle, the snippet contains your plaintext passwords. Treat the resulting config file as a credential.

##### 4. Copy the snippet for your client

Scroll to the _Client configurations_ section. Each client has its own card with:

- An **OS-aware JSON snippet** (the absolute path to `out/server/index.js` is filled in for your machine).
- **Copy snippet** — copies the JSON to your clipboard.
- **Copy script path** — copies just the server bundle path, for clients that ask for `command` / `args` separately.
- (File-based clients only) **Open config file** — creates the file pre-seeded with an empty `mcpServers` if it doesn't yet exist.
- (File-based clients only) **Reveal config file** — opens the containing folder in your OS file manager.

Pick the card matching your client.

##### 5. Paste into the client's config

Open the client config file (the **Open config file** button does it for you on file-based clients). The locations differ per client and per OS — see the table below.

When pasting:

- If the file already has an `mcpServers` key, **merge** under it — don't replace the whole object. The setup panel's snippet is one entry under `mcpServers`.
- If the file is empty or brand new, paste the entire `{ "mcpServers": { ... } }` block.
- Continue.dev uses an **array** shape (`mcpServers: [ ... ]`); the panel emits that shape automatically for its card.

Save the file.

##### 6. Restart the client and verify

Close and reopen the client (or use its **Reload MCP servers** action if it has one). Then ask the assistant a discovery question:

> "List my QuickDB connections."

It should call `quickdb_list_connections` and reply with the connection names you ticked in step 3. A few more sanity prompts:

| Prompt                                | What it calls                                                                 | What you should see                        |
| ------------------------------------- | ----------------------------------------------------------------------------- | ------------------------------------------ |
| "Show me 5 rows from the users table" | `quickdb_get_rows` (Universal Table Auto-Resolution picks the right database) | 5 rows of real data                        |
| "Describe the users table"            | `quickdb_describe_table`                                                      | Column names, types, nullability           |
| "What QuickDB tools do you have?"     | client's tool-listing path                                                    | At least 19 tools prefixed with `quickdb_` |

If you see those, the integration is live. Move on; you're done.

#### What's inside the panel — quick reference

| Section                       | Purpose                                                                                                                    |
| ----------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| **Setup in 5 steps** banner   | Anchor links to each step's card below                                                                                     |
| **Server bundle banner**      | Red if `out/server/index.js` is missing; one-click `npm run build`                                                         |
| **Test Node in terminal**     | Spawns a VS Code terminal and runs `node --version`                                                                        |
| **Connections to embed**      | Checkboxes per saved connection + password redaction toggle                                                                |
| **Client configurations**     | One copyable JSON card per client (Cursor, Claude Desktop, Antigravity, Windsurf, Continue, JetBrains AI, raw)             |
| **Available tools** chip list | The 19 `quickdb_*` tool names — useful when crafting prompts                                                               |
| **Environment knobs** table   | `QUICKDB_QUERY_TIMEOUT_MS`, `QUICKDB_ALLOW_DESTRUCTIVE`, `QUICKDB_LOG_LEVEL`                                               |
| **OS support** card           | How to handle PATH issues per OS (override `"command": "node"` with an absolute Node path when GUI clients can't see PATH) |
| **Verify it works** card      | Sample prompts and which tool each maps to                                                                                 |

#### Reference: config file location per client

The panel shows resolved absolute paths for your platform with the others listed for reference. For copy/paste:

| Client                             | Config location                                                                                                                                                                          | Wrapping shape                                                                            |
| ---------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| **Cursor**                         | Global: `~/.cursor/mcp.json` · Per-workspace: `.cursor/mcp.json`                                                                                                                         | Record under `mcpServers`                                                                 |
| **Claude Desktop**                 | macOS: `~/Library/Application Support/Claude/claude_desktop_config.json` · Windows: `%APPDATA%/Claude/claude_desktop_config.json` · Linux: `~/.config/Claude/claude_desktop_config.json` | Record under `mcpServers`                                                                 |
| **Google Antigravity**             | Settings → MCP Servers → **Edit JSON**                                                                                                                                                   | Record under `mcpServers`                                                                 |
| **Windsurf**                       | `~/.codeium/windsurf/mcp_config.json`                                                                                                                                                    | Record under `mcpServers`                                                                 |
| **JetBrains AI Assistant / Junie** | IDE Settings → Tools → AI Assistant → MCP Servers                                                                                                                                        | Record under `mcpServers`                                                                 |
| **Continue.dev**                   | `~/.continue/config.json`                                                                                                                                                                | Array under `mcpServers` (Continue uses a different shape — the panel emits it correctly) |
| **Other / raw**                    | Any client that asks for `command`, `args`, and `env` separately                                                                                                                         | Bare object (no `mcpServers` wrapper)                                                     |

If you already have other MCP servers configured in the same file, merge the QuickDB entry under your existing `mcpServers` key rather than replacing the whole file.

#### Refreshing after you change connections

Whenever you **add, remove, or edit** a saved connection in QuickDB:

1. Open the setup panel again (`Cmd+Shift+P` → `QuickDB: Setup MCP Server`, or click **Refresh** if the panel is still open).
2. Re-copy the snippet for your client.
3. Replace the matching block in your config file.
4. Restart the client.

The connection details are baked into the environment variable at copy-time, so the spawned server has no other way to learn about new connections.

#### Server script in another machine / container

If you want to copy the QuickDB MCP server to a different machine (e.g. a remote dev box), copy the entire extension folder — the server script lives at `<extension-root>/out/server/index.js` and depends on the surrounding `node_modules`. The setup-panel snippet's `command: "node"` and absolute path assumes Node.js is installed wherever the client will spawn it.

#### Environment variables you can tune

The exported snippet sets `QUICKDB_CONNECTIONS` only. The server respects a couple more env vars you can add manually:

| Variable                    | Default               | Effect                                                                                 |
| --------------------------- | --------------------- | -------------------------------------------------------------------------------------- |
| `QUICKDB_CONNECTIONS`       | (set by export panel) | JSON array of `ConnectionConfig` the server uses on startup                            |
| `QUICKDB_LOG_LEVEL`         | `info`                | `debug` \| `info` \| `warn` \| `error` — controls stderr verbosity                     |
| `QUICKDB_ALLOW_DESTRUCTIVE` | (unset)               | Set to `1` to allow `DROP DATABASE`, `TRUNCATE`, and unscoped DELETE/UPDATE statements |

Add them inside the same `env` object the panel emitted, e.g.:

```json
"env": {
  "QUICKDB_CONNECTIONS": "[...]",
  "QUICKDB_LOG_LEVEL": "debug"
}
```

#### Troubleshooting external clients

- **"Server not found" / no tools appear** — the client probably can't find `node`. Some clients run with a stripped PATH; pin an absolute path to your node binary in the snippet (e.g. `"command": "/usr/local/bin/node"`).
- **"ENOENT" on the server script** — VS Code may not have installed the extension at the path the snippet baked in. Click **Reveal in file manager** on the setup panel to confirm the script exists, then re-copy the snippet.
- **Tools show up but every call fails with "Not connected"** — your `QUICKDB_CONNECTIONS` env was lost or empty. Re-export and re-paste, and confirm the JSON wasn't accidentally truncated by a single-quote shell when you pasted it.
- **Want to see what the server is doing?** Set `QUICKDB_LOG_LEVEL=debug` in the env block. The server logs every `tool/call` and timing to stderr; most clients surface it in their MCP server panel.

> The exported snippet contains any saved passwords. Treat the config file as a credential — don't commit it to git, and prefer per-workspace `.cursor/mcp.json` (gitignored) over the global one for non-trivial environments.

### Cursor IDE Integration

Run `QuickDB: Generate .cursorrules` to create a `.cursorrules` file in your workspace that helps Cursor AI understand your database schema.

### Configuration

VS Code settings (search for "QuickDB" in Settings):

| Setting                  | Default | Description                                                |
| ------------------------ | ------- | ---------------------------------------------------------- |
| `quickdb.maxRowsPerPage` | `100`   | Page size in the Table Viewer                              |
| `quickdb.autoConnect`    | `false` | Auto-connect to saved connections when the extension loads |
| `quickdb.saveHistory`    | `true`  | Persist query history across reloads                       |

The MCP server starts automatically when the extension activates; there is no separate port (it runs in-process inside VS Code and via stdio for the language-model host).

---

## Chat Commands (@quickdb)

QuickDB provides 12 slash commands for interacting with your databases through GitHub Copilot Chat.

### Basic Commands

| Command             | Description              | Usage                                         |
| ------------------- | ------------------------ | --------------------------------------------- |
| `/list-connections` | List all connections     | `@quickdb /list-connections`                  |
| `/list-tables`      | List tables              | `@quickdb /list-tables`                       |
| `/describe-table`   | Get table schema         | `@quickdb /describe-table users`              |
| `/execute-query`    | Execute raw SQL          | `@quickdb /execute-query SELECT * FROM users` |
| `/get-schema`       | Get full database schema | `@quickdb /get-schema`                        |

### Structured Query Commands (No SQL Required)

These commands use interactive prompts to build queries without writing SQL:

| Command         | Description                       | Usage                    |
| --------------- | --------------------------------- | ------------------------ |
| `/get-rows`     | Get rows with filters and sorting | `@quickdb /get-rows`     |
| `/count-rows`   | Count rows with optional filter   | `@quickdb /count-rows`   |
| `/search-value` | Search for text in columns        | `@quickdb /search-value` |

### Data Modification Commands (Require Confirmation)

| Command        | Description          | Usage                   |
| -------------- | -------------------- | ----------------------- |
| `/insert-row`  | Insert a new row     | `@quickdb /insert-row`  |
| `/update-rows` | Update matching rows | `@quickdb /update-rows` |
| `/delete-rows` | Delete matching rows | `@quickdb /delete-rows` |

### Utility Commands

| Command    | Description                  | Usage               |
| ---------- | ---------------------------- | ------------------- |
| `/history` | View and re-run past queries | `@quickdb /history` |

### Interactive Prompts

Commands marked as structured guide you through Quick Pick dialogs to:

- Select tables from dropdowns
- Choose columns with multi-select
- Build complex filters with operators: `=`, `!=`, `>`, `<`, `>=`, `<=`, `LIKE`, `IN`, `IS NULL`, `IS NOT NULL`, `BETWEEN`
- Add sorting and pagination
- Preview changes before executing

### Filter Operators

| Operator                  | Description                                            |
| ------------------------- | ------------------------------------------------------ |
| `=` (equals)              | Exact match                                            |
| `!=` (not equals)         | Exclude matches                                        |
| `>`, `<`, `>=`, `<=`      | Numeric/date comparisons                               |
| `LIKE` (contains)         | Text pattern matching (case-insensitive on PostgreSQL) |
| `IN` (in list)            | Match any value in a comma-separated list              |
| `IS NULL` / `IS NOT NULL` | Null checks                                            |
| `BETWEEN` (range)         | Value between two bounds                               |

### Export Results

After viewing query results, click:

- **Export as CSV** - Save or copy results as CSV
- **Export as JSON** - Save or copy results as JSON

### Query History

The `/history` command shows your last 20 queries with timestamps and row counts. Select one to view its parameters or clear all history.

---

## Keyboard Shortcuts

### Global

| Shortcut       | Action          |
| -------------- | --------------- |
| `Ctrl+Shift+P` | Command Palette |
| `F5`           | Refresh data    |

### Table Viewer

| Shortcut           | Action               |
| ------------------ | -------------------- |
| `Ctrl+S`           | Save changes         |
| `Ctrl+N`           | Add new row          |
| `Ctrl+G`           | Go to row            |
| `Del`              | Delete selected rows |
| `Shift+Enter`      | Open Value Editor    |
| `Ctrl+Shift+Enter` | Single Record View   |
| `Ctrl+Alt+N`       | Set cell to NULL     |
| `Ctrl+P`           | Preview SQL (DML)    |
| `Ctrl+C`           | Copy cell value      |

### Sidebar

| Shortcut    | Action            |
| ----------- | ----------------- |
| Click table | Open Table Viewer |
| Right-click | Context menu      |

---

## Troubleshooting

### Connection Issues

**SQLite: "Database file not found"**

- Ensure the file path is correct and the file exists
- Check file permissions

**MySQL/PostgreSQL: "Connection refused"**

- Verify the database server is running
- Check host, port, username, and password
- Ensure the database accepts remote connections
- Try enabling SSL if required

**MongoDB: "Server selection timed out"**

- Check if MongoDB is running
- Verify the connection string format
- Ensure network connectivity to the MongoDB host

**Redis: "Connection timeout"**

- Verify Redis is running on the specified host/port
- Check if authentication is required
- Ensure the correct database index

### General Issues

**Extension not loading:**

1. Check the VS Code Output panel (View > Output > QuickDB)
2. Reload the window (Ctrl+Shift+P > Reload Window)

**Data not refreshing:**

- Press F5 to force refresh
- Disconnect and reconnect the connection

**Sample Database:**

- Use the `QuickDB: Open Sample Database` command to create an in-memory SQLite database with demo data for testing

---

## FAQ

**Q: Where are connection credentials stored?**
A: Connections are stored in VS Code's global state (extension storage). Passwords are stored as-is - consider using environment variables for sensitive credentials.

**Q: Can I connect to remote databases?**
A: Yes, for all server-based databases (MySQL, PostgreSQL, MongoDB, Redis). Simply enter the remote host and port.

**Q: Does QuickDB support SSL/TLS?**
A: Yes. Toggle the SSL option when creating or editing a connection (available for MySQL, PostgreSQL, MongoDB, Redis).

**Q: How many rows can I view at once?**
A: The Table Viewer loads data with pagination. The default limit is configurable. The status bar shows total row count.

**Q: Can I use QuickDB with Docker containers?**
A: Yes. Point the host to `localhost` and use the exposed port from your Docker container.

---

_QuickDB - Database management, simplified._
