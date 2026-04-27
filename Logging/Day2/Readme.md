# ELK Stack Setup using Docker Compose 

## 🚀 1. Prerequisites

* Docker installed
* Docker Compose installed
* Basic Linux commands knowledge

---

## 📁 2. Project Structure

```
elk/
├── docker-compose.yml
├── logstash/
│   └── logstash.conf
```

---

## ⚙️ 3. docker-compose.yml

```yaml
version: '3.8'

services:

  elasticsearch:
    image: docker.elastic.co/elasticsearch/elasticsearch:7.16.3
    container_name: elasticsearch
    environment:
      - discovery.type=single-node
      - xpack.security.enabled=false
      - ES_JAVA_OPTS=-Xms512m -Xmx512m
    ports:
      - "9200:9200"
    networks:
      - elk

  logstash:
    image: docker.elastic.co/logstash/logstash:7.16.3
    container_name: logstash
    volumes:
      - ./logstash/logstash.conf:/usr/share/logstash/pipeline/logstash.conf
    ports:
      - "5000:5000"
    depends_on:
      - elasticsearch
    networks:
      - elk

  kibana:
    image: docker.elastic.co/kibana/kibana:7.16.3
    container_name: kibana
    environment:
      - ELASTICSEARCH_HOSTS=http://elasticsearch:9200
    ports:
      - "5601:5601"
    depends_on:
      - elasticsearch
    networks:
      - elk

networks:
  elk:
    driver: bridge
```

---

## 📝 4. logstash.conf

```conf
input {
  tcp {
    port => 5000
    codec => plain
  }
}

output {
  elasticsearch {
    hosts => ["http://elasticsearch:9200"]
    index => "logs-%{+YYYY.MM.dd}"
  }
}
```

---

## ▶️ 5. Run Setup

```bash
docker-compose up -d
```

Check containers:

```bash
docker ps
```
<img width="1915" height="968" alt="image" src="https://github.com/user-attachments/assets/7d5300fa-063b-42e9-a4bc-689b3690bad9" />

---

## 🌐 6. Access Services

* Elasticsearch → [http://localhost:9200](http://localhost:9200)
* Kibana → [http://localhost:5601](http://localhost:5601)

<img width="1226" height="802" alt="image" src="https://github.com/user-attachments/assets/cece8196-abe7-418d-9158-3f3cb148d603" />

---

## 🧪 7. Test Logs

```bash
echo '{"message":"ELK working"}' | nc localhost 5000
```

---

## 📊 8. Kibana Setup

1. Open Kibana
2. Go to Discover
3. Create index pattern:

```
logs-*
```
<img width="1919" height="979" alt="image" src="https://github.com/user-attachments/assets/bbba30f9-1f7d-4d7c-a702-6d7b9806f49d" />
---

## ⚠️ 9. Common Issues & Fixes

### ❌ Volume Error

Cause: file vs directory mismatch
Fix:

```
rm -rf logstash.conf
touch logstash.conf
```

---

### ❌ Elasticsearch not starting

Fix:

```
sysctl -w vm.max_map_count=262144
```

---

### ❌ curl localhost not working

Use correct ports:

* 9200 → Elasticsearch
* 5601 → Kibana

---

## 🎯 10. Architecture

Application → Logstash → Elasticsearch → Kibana

---

## 🧠 11. Interview Points

* Docker Compose manages multi-container apps
* Environment → configuration
* Volumes → data sharing
* Networks → communication

---

## 🔥 Final Note

This is a complete production-like ELK setup using Docker Compose.



