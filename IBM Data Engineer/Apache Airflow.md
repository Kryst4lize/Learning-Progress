Overview of Apache Airflow
- **Definition**: Apache Airflow is an open-source workflow orchestration tool that allows users to programmatically author, schedule, and monitor workflows. ([[Data Pipeline]] [[ETL]] [[Automating Database Task]], [[Database Administrator]])
- **Workflow Representation**: Workflows in Airflow are represented as Directed Acyclic Graphs (DAGs), which consist of tasks arranged in a specific order of execution.

Key Components of Apache Airflow
![[AirflowArchitecture.png]]
1. **Scheduler**:
    - Responsible for triggering all scheduled workflows.
    - Determines when tasks can run based on their dependencies.
2. **Executor**:
    - Handles the execution of tasks by assigning them to available workers.
    - Manages the actual running of tasks.
3. **Web Server**:
    - Provides a graphical user interface (GUI) for users to interact with their workflows.
    - Allows users to inspect, trigger, and debug DAGs and their tasks.
4. **DAG Directory**:
    - Contains all DAG files that the scheduler, executor, and workers can access.
5. **Metadata Database**:
    - Stores the state of each DAG and its tasks, which is used by the scheduler, executor, and web server.
6. **Worker:** 
	- Execution unit to run and operate the workflow

**Task Lifecycle States**

![[ApacheAirflowImage.png]]

**Main Features of Apache Airflow**

- **Pure Python**: Users can create workflows using standard Python, providing flexibility in building data pipelines.
- **User Interface**: The UI allows for monitoring, scheduling, and manual execution of workflows, offering insights into task statuses.
- **Integration**: Airflow supports numerous plug-and-play integrations, such as IBM Data Band for continuous observability and monitoring.
- **Ease of Use**: Workflows can be easily created and deployed by anyone with prior Python knowledge, allowing for a wide range of tasks.
- **Open Source**: Users can contribute to the project by sharing improvements through pull requests, fostering a collaborative community.

Principles of Airflow Pipelines

1. **Scalable**: Airflow's modular architecture and message queue system allow it to scale to accommodate many workers.
2. **Dynamic**: Pipelines are defined in Python, enabling dynamic generation and execution of multiple simultaneous tasks.
3. **Extensible**: Users can define custom operators and extend libraries to fit their specific environments.
4. **Lean**: Airflow pipelines are explicit and lean, with built-in parameterization using the Jinja templating engine.
**Common Use Cases**

- **Adobe Experience Platform**: Uses Airflow's plugin interface to write custom operators for their specific use cases, managing scheduling and dependencies effectively.
- **Adyen**: Extends existing operators and sensors to simplify the writing of ETL DAGs.
- **Big Fish**: Utilizes Airflow to programmatically control workflows and efficiently monitor tasks through the web UI.
- **Walmart**: Automates data processing tasks, such as extracting data from databases and loading it into data warehouses.
---
# Direct Acyclic Graph 

- **DAG Definition**: A Directed Acyclic Graph (DAG) is a graph structure used in Apache Airflow to represent workflows. It consists of nodes (tasks) and directed edges (dependencies).
    
- **Components of a DAG**:
    - **Nodes**: Represent tasks in the workflow.
    - **Edges**: Define the order of task execution.
- **Terminology:** 
	- **Operators**: Each task in a DAG is implemented using operators (e.g., Python operator, SQL operator, Bash operator).
	- **Sensors**: A type of operator that checks for certain conditions (e.g., file existence).
	- **Airflow Scheduler**: A service that deploys and schedules the execution of DAGs based on specified intervals.
- **DAG Structure**:
1. **Library Imports**:
    - The first block of the DAG script includes necessary Python libraries. For example, you might import the DAG module from Airflow:
        ```python
        from airflow import DAG
        ```
2. **DAG Arguments**:
    - This section specifies default arguments for the DAG, such as:
        - `start_date`: The date when the DAG should start running.
        - `retries`: The number of times to retry a task in case of failure.
        - `retry_delay`: The delay between retries.
    Example:
    ```python
    default_args = {
        'owner': 'airflow',
        'start_date': datetime(2023, 1, 1),
        'retries': 1,
        'retry_delay': timedelta(minutes=5),
    }
    ```
3. **DAG Definition**:
    - This block instantiates the DAG object, where you define the DAG's properties, including its ID and default arguments. Example:
    ```python
    dag = DAG(
        'my_dag',
        default_args=default_args,
        schedule_interval='@daily',
    )
    ```
4. **Task Definitions**:
    - Each task in the DAG is defined here. Tasks are created using operators, which determine what each task does. For example:
    ```python
    task1 = BashOperator(
        task_id='run_bash_command',
        bash_command='echo "Hello World"',
        dag=dag,
    ) ```
5. **Task Pipeline**:
    - This section specifies the dependencies between tasks, indicating the order in which they should run. You can set dependencies using the `>>` operator or the `set_downstream()` method. Example:
    ```python
    task1 >> task2  # task2 will run after task1 completes
    ```
- **Advantages of DAGs**:
    - **Maintainability**: Workflows are defined as code, making them easier to manage.
    - **Version Control**: Code revisions can be tracked using systems like Git.
    - **Collaboration**: Teams can work together on the code.
    - **Testability**: Code can be tested to ensure it functions as intended.
---
# Logging and Monitoring
Airflow Logging and Monitoring
**Overview:**

- The video focuses on how to utilize Airflow's logging capabilities to monitor task statuses and diagnose problems within Directed Acyclic Graph (DAG) runs.

**Logging in Airflow:**

- **Default Logging:**
    - Airflow logs are saved to local file systems by default, which is convenient for developers during the development phase.
- **Production Logging:**
    - In production environments, logs can be sent to cloud storage solutions such as IBM Cloud, AWS, or Azure for remote access.
    - Logs can also be sent to search engines and dashboards for further analysis.
    - Recommended tools for log analysis include Elasticsearch and Splunk.

**Navigating Log Files:**

- Log files are organized by:
    - `dag_ids`
    - `run_ids`
    - `task_ids`
    - Attempt numbers
- Example path to access a specific log file:
    
    ```
    logs/dag_id=dummy_dag/run_id=scheduled_time/task_id=task1/attempt=1.log
    ```
    
- The log file contains crucial information such as:
    - Running command
    - Command result
    - Task result

**Airflow UI:**

- The Airflow web server provides a user interface to quickly review task events.
- Users can search for events using fields like DAG ID, Task ID, and Logical Date to get an overview of specific DAGs and tasks.

**Metrics Monitoring:**

- Airflow produces three types of metrics for monitoring component health:
    - **Counters:** Metrics that continuously increase (e.g., total counts of successful or failed tasks).
    - **Gauges:** Metrics that can fluctuate (e.g., number of currently running tasks).
    - **Timers:** Metrics related to time duration (e.g., time taken for a task to complete).
- For production deployments, metrics should be sent to dedicated monitoring systems.
- **Recommended Tools:**
    - **StatsD:** A network daemon that gathers metrics from Airflow and sends them to a metrics monitoring system.
    - **Prometheus:** A popular system for metrics monitoring and analysis, which can aggregate and visualize metrics in a dashboard.