# AWS Event-Driven Data Pipeline (ETL Demo)

This project demonstrates a scalable, event-driven, and serverless data pipeline on AWS. It is designed to ingest raw data (from a source like S3 or an API), process it asynchronously, transform it, and load it into a clean, queryable database.

This architecture is ideal for any business that needs to process high volumes of data without crashing servers, such as user analytics, IoT data, or financial transactions.

---

## 1. Architecture Diagram

<img width="930" height="299" alt="image" src="https://github.com/user-attachments/assets/bc10ddbe-ef25-4c45-b7e7-9a2894fc1679" />

---

## 2. The Business Problem (What This Solves)

* **Ingestion:** Handling unpredictable "spikes" in incoming data (e.g., 100 CSV files dumped at once) without failing.
* **Decoupling:** Allowing the "upload" service to run fast without waiting for the *entire* data transformation to finish.
* **Scalability:** The system scales automatically. If 10,000 messages hit the queue, AWS Lambda will scale up processors automatically to handle the load.
* **Resilience:** If the transformation of one file fails, it doesn't break the whole system. The message can be retried from the queue.

---

## 3. Tech Stack & Key Services

This section proves you use modern, best-practice tools.

* **Python 3.11+**: The core language for data transformation.
* **Pandas**: For robust and efficient in-memory data manipulation.
* **AWS Lambda**: Serverless compute for the "Transform" and "Load" steps.
* **AWS SQS**: A fully-managed message queue to decouple the pipeline.
* [cite_start]**Amazon DynamoDB** (or **RDS/PostgreSQL** [cite: 49]): The final destination for the clean, structured data.
* **AWS CloudWatch**: For logging, monitoring, and alerts.
* **Infrastructure as Code (IaC)**:
    * [ **CHOOSE ONE and use it for the project** -> `Serverless Framework` / `Terraform` / `AWS SAM` ] - Proves you know modern DevOps.

---

## 4. How to Deploy & Run

This is where you *prove* it's real. A senior client will *love* that you included this.

*(This is an example using the Serverless Framework)*

### Prerequisites
* Node.js v20+
* Python 3.11+
* An AWS Account configured with credentials
* `npm install -g serverless`

### 1. Clone the repository
```bash
git clone [https://github.com/jordy-garcia/aws-data-pipeline-demo.git](https://github.com/jordy-garcia/aws-data-pipeline-demo.git)
cd aws-data-pipeline-demo
