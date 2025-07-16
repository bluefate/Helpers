---

## 📁 Helpers

**Random useful notes**

---

## 📦 `docker-compose.qnap.yml` – For QNAP NAS

Sample `docker-compose` file intended for use within **QNAP Container Station** to deploy multiple containers simultaneously.

### 🛠 Usage Options:

* Can be deployed via **Portainer**, if available.
* Alternatively, use **"Create Application"** under the **Create** tab in Container Station.

### 💡 Volume Creation:

* It is recommended to create named volumes via **Portainer** for better control and reusability.

---

## 📦 `docker-compose.jupyter.yml` – Jupyter + Spark + Hadoop

Sets up a lightweight big data lab using Docker containers for:

* **Hadoop HDFS**: NameNode + DataNode
* **Apache Spark**: Master-only (standalone mode)
* **Jupyter Notebook**: PySpark-enabled kernel

### 🗂 Notebook Persistence:

Mounts a local folder from your Windows machine into the notebook container so that your `.ipynb` files are stored and accessible locally:

```yaml
volumes:
  - "/c/Users/yourusername/somefolder:/home/jovyan/somefolder/"
```

Replace `yourusername` and `somefolder` with your actual Windows path.

---

### 🌐 Web Interfaces

| Component       | URL                     | Purpose                            |
| --------------- | ----------------------- | ---------------------------------- |
| **HDFS UI**     | `http://localhost:9870` | View file system status and health |
| **Spark UI**    | `http://localhost:8080` | Monitor Spark master and workers   |
| **Jupyter Lab** | `http://localhost:8888` | Access Jupyter notebooks           |

---
