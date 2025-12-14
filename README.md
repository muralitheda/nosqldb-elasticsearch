# 📘 Elasticsearch Fundamentals


## 1️⃣ What is Elasticsearch?

**Elasticsearch** is a **distributed search and analytics engine** used to:

* Search large amounts of data quickly ⚡
* Analyze data in near real-time
* Store and retrieve structured & unstructured data

### Simple Analogy 🧠

Think of Elasticsearch as **Google for your data**.

* You type a query → It searches millions of records → Returns results instantly

### Common Use Cases

* Application search (products, users, logs)
* Log analysis (ELK Stack)
* Monitoring & observability
* Text search with ranking

---

## 2️⃣ Why Elasticsearch is Fast?

Elasticsearch is fast because:

* Data is **indexed**, not scanned line-by-line
* Works in **distributed mode** (multiple machines)
* Uses **in-memory operations** where possible

📌 It is built on **Apache Lucene**, a powerful search library.

---

## 3️⃣ Core Components (Very Important for Teaching)

### 🔹 Cluster

A **cluster** is a group of one or more Elasticsearch nodes working together.

> 💡 Even a single Elasticsearch server is a cluster.

---

### 🔹 Node

A **node** is one running instance of Elasticsearch.

Types of nodes:

* Master node – manages cluster
* Data node – stores data
* Coordinating node – handles requests

> 💡 In small setups, one node does everything.

---

### 🔹 Index

An **index** is like a **database**.

| Relational DB | Elasticsearch |
| ------------- | ------------- |
| Database      | Index         |

Example:

* `employees` index
* `logs_2025` index

---

### 🔹 Document

A **document** is a single record stored in an index.

| Relational DB | Elasticsearch |
| ------------- | ------------- |
| Row           | Document      |

Documents are stored in **JSON format**.

Example:

```json
{
  "name": "Murali",
  "role": "Trainer",
  "experience": 10
}
```

---

### 🔹 Field

A **field** is a key-value pair inside a document.

Example fields:

* `name`
* `role`
* `experience`

---

## 4️⃣ Indexing (Heart of Elasticsearch ❤️)

**Indexing** means preparing data so it can be searched quickly.

### What happens during indexing?

* Text is **tokenized** (broken into words)
* Words are stored in an **inverted index**

---

## 5️⃣ Inverted Index (Must-Know Concept)

Instead of storing:

> Document → Words

Elasticsearch stores:

> Word → List of Documents

### Example

| Word  | Documents  |
| ----- | ---------- |
| spark | doc1, doc3 |
| kafka | doc2       |

💡 This is why search is extremely fast.

---

## 6️⃣ Mapping (Schema Definition)

**Mapping** defines:

* Field names
* Field data types

Similar to **schema in RDBMS**, but flexible.

### Example

```json
{
  "name": { "type": "text" },
  "experience": { "type": "integer" }
}
```

### Dynamic Mapping

* Elasticsearch can automatically guess field types
* Good for beginners, risky for production

---

## 7️⃣ Data Types (Basic Ones)

| Type    | Use Case             |
| ------- | -------------------- |
| text    | Full-text search     |
| keyword | Exact match, filters |
| integer | Numbers              |
| date    | Time-based data      |
| boolean | true/false           |

💡 Teaching Tip: `text` ≠ `keyword`

---

## 8️⃣ Shards (Scalability Concept)

An **index is split into shards**.

### Why shards?

* Store big data
* Parallel search
* Scale horizontally

Example:

* Index with 3 shards → data split into 3 parts

---

## 9️⃣ Replicas (High Availability)

**Replica shards** are copies of primary shards.

Benefits:

* Fault tolerance
* Load balancing for searches

Example:

* 1 primary shard + 1 replica = 2 copies

---

## 🔟 CRUD Operations

| Operation | Meaning         |
| --------- | --------------- |
| Create    | Add document    |
| Read      | Get document    |
| Update    | Modify document |
| Delete    | Remove document |

---

## 1️⃣1️⃣ Search Basics

### Match Query (Full Text Search)

```json
{
  "query": {
    "match": { "role": "trainer" }
  }
}
```

### Term Query (Exact Match)

Used with `keyword` fields.

---

## 1️⃣2️⃣ Relevance & Scoring

Elasticsearch returns results with a **score**.

* Higher score → More relevant
* Based on text frequency & position

> 💡 This is why Google-like ranking is possible.

---

## 1️⃣3️⃣ Near Real-Time Search

* Data is searchable within **~1 second** after indexing
* Not truly real-time, but **near real-time**

---

## 1️⃣4️⃣ Elasticsearch vs RDBMS (Quick Comparison)

| Feature | RDBMS       | Elasticsearch |
| ------- | ----------- | ------------- |
| Schema  | Fixed       | Flexible      |
| Search  | Slow (LIKE) | Very fast     |
| Scaling | Vertical    | Horizontal    |
| Joins   | Yes         | Limited       |

---

## 1️⃣5️⃣ ELK Stack (Context for Teaching)

| Component     | Purpose          |
| ------------- | ---------------- |
| Elasticsearch | Storage & search |
| Logstash      | Data ingestion   |
| Kibana        | Visualization    |

---

## 🎯 Points

1. Problem with traditional databases
2. What is Elasticsearch
3. Index → Document → Field
4. Inverted index
5. Mapping & data types
6. Shards & replicas
7. Search queries
8. ELK use case

---

## 🧠 One-Line Summary

> **Elasticsearch = Fast, distributed search engine that stores JSON documents and searches them using inverted indexes.**

---


