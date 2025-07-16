# Helpers
Ramdon useful notes

# docker-compose.qnap.yml for QNAP
Helpful docker-compose sample file to use within Container Station to implement multiple dockers at the same time.
- Can be implmented via Portainer, if running, or via Create Application in the Create Tab.
- To create volume, is recommended to use Portainer since it will give you more control over the create process


# docker-compose.jupyter.yml for JUPYTER, SPARK & HADOOP
Sets up a mini big data lab using Docker containers for:
- Hadoop HDFS (NameNode + DataNode)
- Apache Spark (Master-only mode)
- Jupyter Notebook (PySpark kernel)

Maps a local folder from your Windows machine into the notebook's workspace. You can save and open .ipynb files directly from your PC

volumes:
  - "/c/Users/usnername/somefolder:/home/jovyan/somefolder/"
  

HDFS NameNode UI - http://localhost:9870 File system status, health
Spark UI - http://localhost:8080 Job & worker monitoring
Jupyter Lab - 	http://localhost:8888 Interactive coding, PySpark use