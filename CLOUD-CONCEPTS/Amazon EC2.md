#aws-cloud 

**Amazon EC2 (Elastic Compute Cloud)** provides resizable virtual servers (instances) in the cloud. It is the foundational compute layer of AWS — unlike managed services such as **Amazon Bedrock** or **SageMaker**, EC2 gives you full control over the operating system, software stack, and infrastructure, at the cost of managing it yourself.

- **Service Type:** Infrastructure as a Service (IaaS)
- **Unit of Work:** Virtual Machines (Instances)
- **Control:** You have full control over the operating system, hardware configurations, and networking 
Management: You are responsible for provisioning, patching, and maintaining the underlying servers

**Role in GenAI / ML Architectures**

- **Self-Managed Model Hosting:** Used to host open-source foundation models (e.g., via Hugging Face, vLLM, or custom containers) when a team needs more control than Bedrock or SageMaker endpoints provide.
- **Training Infrastructure:** SageMaker training jobs run on managed EC2 instances under the hood; teams doing fully custom training pipelines may provision EC2 directly instead.
- **GPU/Accelerator Access:** Instance families like **P** (NVIDIA GPUs) and **Trn/Inf** (AWS Trainium/Inferentia) are used for large-scale training and cost-optimized inference.

**Key Instance Considerations**

- **Instance Types:** Chosen based on workload — compute-optimized (C), memory-optimized (R), GPU-accelerated (P, G), or purpose-built ML silicon (Trn1, Inf2).
- **Purchasing Options:** On-Demand for flexibility, Reserved/Savings Plans for steady-state workloads, Spot Instances for fault-tolerant, interruptible jobs like batch inference or training checkpoints.
- **Auto Scaling:** EC2 Auto Scaling groups adjust instance count based on demand, useful for variable inference traffic.

**Exam Tip: EC2 vs. SageMaker vs. Bedrock**

- **Use EC2** when you need full control over the environment (custom frameworks, licensing, low-level optimization).
- **Use SageMaker** when you want managed training/hosting infrastructure without giving up model flexibility.
- **Use Bedrock** when you want a fully managed foundation model API with no infrastructure to operate.
