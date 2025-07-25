# 8 Python Libraries for all DevOps Engineer 






## 1. `docker` – Docker SDK for Python

**Why use it:** Manage Docker containers and images programmatically.

**Example:**

```
import docker

client = docker.from_env()
container = client.containers.run("nginx", detach=True)
print(f"Started container with ID: {container.id}")
```

---

## 2. `kubernetes` – Kubernetes Python Client

**Why use it:** Interact with Kubernetes clusters directly from Python.


**Example:**

```
from kubernetes import client, config

config.load_kube_config()
v1 = client.CoreV1Api()

pods = v1.list_pod_for_all_namespaces(watch=False)
for pod in pods.items:
    print(f"{pod.metadata.namespace} - {pod.metadata.name}")
```

---
## 3. `paramiko` – SSH Automation

**Why use it:** Execute remote commands securely over SSH.



**Example:**

```
import paramiko

ssh = paramiko.SSHClient()
ssh.set_missing_host_key_policy(paramiko.AutoAddPolicy())
ssh.connect('192.168.1.10', username='devops', password='secret')

stdin, stdout, stderr = ssh.exec_command('uptime')
print(stdout.read().decode())

ssh.close()
```

---

## 4. `pyyaml` – YAML Parsing and Generation

**Why use it:** Read and write YAML config files.

**Example:**

```
import yaml

with open("config.yaml") as f:
    config = yaml.safe_load(f)

print(config["environment"])
```

---

## 5. `requests` – HTTP Requests

**Why use it:** Communicate with REST APIs easily.


**Example:**

```
import requests

response = requests.get("https://httpbin.org/get")
print(response.json())
```

---
## 6. `pytest` – Testing Infrastructure

**Why use it:** Write tests for your automation scripts and infrastructure code.


**Example:**

```
def test_add():
    assert 1 + 1 == 2
```

Run test:

`pytest test_script.py`

---


## 7. `boto3` – AWS SDK for Python

**Why use it:** Automate AWS resource provisioning and management.

**Example:**

```
import boto3

ec2 = boto3.client('ec2')
response = ec2.describe_instances()
for reservation in response['Reservations']:
    for instance in reservation['Instances']:
        print(f"Instance ID: {instance['InstanceId']}")
```

---

## 8. `fabric` – Command Line Automation

**Why use it:** Execute shell commands and deploy scripts across multiple servers.


**Example:**

```
from fabric import Connection

conn = Connection("devops@192.168.1.10")
conn.run("sudo systemctl restart nginx")
```

