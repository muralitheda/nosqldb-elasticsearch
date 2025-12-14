# 🔧 Elasticsearch & Kibana Installation and Workouts

## 📌 Prerequisites

* Linux machine
* Java installed (for Elasticsearch 7.x)
* Internet access
* User: `hduser`

---

## 1️⃣ Install and Configure Elasticsearch & Kibana

### 📂 Navigate to Installation Directory

```bash
cd /home/hduser/install/
```

### ⬇️ Download Required Packages

```bash
wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-7.17.18-linux-aarch64.tar.gz
tar xvzf elasticsearch-7.17.18-linux-aarch64.tar.gz
cd /home/hduser/install/elasticsearch-7.17.18/bin
nohup ./elasticsearch &

wget https://artifacts.elastic.co/downloads/kibana/kibana-7.17.18-linux-aarch64.tar.gz
tar xvzf kibana-7.17.18-linux-aarch64.tar.gz
cd /home/hduser/install/kibana-7.17.18-linux/bin
nohup ./kibana &

```

📌 **Access URLs**

* Elasticsearch: `http://localhost:9200`
* Kibana: `http://localhost:5601`

---

## 3️⃣ Stop Elasticsearch and Kibana Services

### 🛑 Stop Elasticsearch

```bash
jps | grep elasticsearch
kill -9 <process_id>
```

### 🛑 Stop Kibana

```bash
ps -ef | grep kibana
kill -9 <process_id>
```

---

## 🧪 Verification (Optional)

### ✔️ Check Elasticsearch Status

```bash
curl http://localhost:9200
```

---

## 🧠  Notes

* Elasticsearch 7.x **does not require X-Pack configuration for basic usage**
* Always stop services gracefully in production (avoid `kill -9`)
* Use `nohup` or `systemd` for long-running services

---

