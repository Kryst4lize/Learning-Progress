Relevant keyword : [[Docker]] [[Apache Spark]]
- **Kubernetes Overview**: Kubernetes (k8s) is an open-source framework designed for managing containerized applications across a cluster. It is highly scalable and allows for flexible deployments, whether on-premises or in the cloud.
    
- **Benefits of Kubernetes**:
    
    - **Network Service Discovery**: Helps in finding services within the cluster.
    - **Load Balancing**: Distributes workloads evenly across the cluster.
    - **Automated Scaling**: Automatically adjusts the number of active systems based on demand.
    - **Storage Orchestration**: Efficiently manages storage resources.
- **Local vs. Cloud Deployment**:
    
    - Kubernetes can be run locally (e.g., using tools like minikube) for development and testing purposes.
    - For production, hosting on the cloud is recommended due to ease of deployment and flexibility.
- **Running Apache Spark on Kubernetes**:
    
    - Spark version 2.3 and above can be deployed on Kubernetes.
    - **Containerization**: This allows Spark applications to be more portable and manage dependencies effectively.
    - **Resource Sharing**: Multiple Spark applications can run concurrently, sharing resources while remaining isolated.
- **Submitting Spark Applications**:
    
    - To submit a Spark application, set the `--master` option to the Kubernetes API server URL.
    - Spark creates a driver that manages executors, both running in Kubernetes pods.
    - **Pods**: A pod is a group of containers that share resources.
- **Deployment Modes**:
    - Applications can be deployed in either client or cluster mode.
    - In client mode, special considerations are needed for communication between executors and the driver.