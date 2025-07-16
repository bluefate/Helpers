
## 🐳 Jupyter + Spark + Hadoop via Docker Compose (Windows/macOS)

### 1. Install Docker and Docker Compose

* Download and install **Docker Desktop**:
  [https://www.docker.com/products/docker-desktop/](https://www.docker.com/products/docker-desktop/)

* After installation, **restart your computer** if prompted.

* Open **Command Prompt** (CMD) or PowerShell and verify installation:

  ```bash
  docker --version
  docker compose version
  ```

---

### 2. Set Up Your Project Directory

Create a folder to hold your Docker setup and notebooks, e.g.:

```bash
mkdir C:\hadoop-spark-jupyter\jupyter\notebooks
```

---

### 3. Prepare Your `docker-compose.jupyter.yml`

Save your custom `docker-compose.jupyter.yml` file in:

```
C:\hadoop-spark-jupyter\
```

---

### 4. Adjust Volume Mounts in Compose File

Update the `volumes:` section in the `jupyter` service to point to your **local path** where notebooks will be saved:

```yaml
volumes:
  - "/c/Users/yourname/somefolder:/home/jovyan/somefolder/"
```

Make sure the left side (host path) matches your actual user folder.

---

### 5. Launch the Containers

Open a terminal and navigate to your project directory:

```bash
cd C:\hadoop-spark-jupyter
```

Then start your environment with:

```bash
docker compose -f docker-compose.jupyter.yml up --build
```

---

### 6. Access Jupyter

Open your browser and go to:

```
http://localhost:8888
```

If Jupyter asks for a token:

```bash
docker logs jupyter
```

Look for a line like:

```
http://127.0.0.1:8888/?token=abcdef123456...
```

Copy and paste it into your browser to authenticate.

---

### 7. Install Python Packages Inside Jupyter

#### Option A: Using Jupyter Terminal

In JupyterLab, open **File > New > Terminal** and run:

```bash
pip install pandas matplotlib pyarrow
```

#### Option B: Inside a Notebook Cell

```python
!pip install pandas matplotlib pyarrow
```

---

### 8. Shut Down the Environment

To gracefully stop and remove the containers:

```bash
docker compose -f docker-compose.jupyter.yml down
```

---

### 9. Access Haddop
```
http://localhost:8888
```

---

### 10. Access Spark Master UI
```
http://localhost:8080
```

