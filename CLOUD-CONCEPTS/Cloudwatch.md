Main AWS tool for monitoring and observability. Provides metrics for all services in AWS. The metrics from CW can be streamed near real-time through Amazon Kinesis Data Firehose to any internal/external tool of choice including Datadog/Splunk/Sumo Logic/Redshift/Opensearch etc.. You can filter all/or some namespaces.
**Composite Alarms:** Combine multiple alarms into one to reduce "alarm noise" (e.g., alert only if _both_ CPU and IOPS are high)

Components
1. Metrics: Tracks variables over time, such as CPU utilization or network traffic. For GenAI, it monitors **token usage** (Input/OutputTokenCount), invocation latency, and error rates
2. **Logs:** Collects and stores logs from services like Bedrock, Lambda, and SageMaker. **CloudWatch Logs Insights** allows you to query these logs using a purpose-built language to find specific errors or patterns
3. **Alarms:** Triggers notifications or automated actions (like scaling) when a metric exceeds a threshold.
4. **Dashboards:** Provides unified visualizations of your metrics and alarms for real-time monitoring

**Role in GenAI Development**

- **Observability:** Essential for tracking model behavior, user feedback, and security events across all application layers.
- **Performance Tuning:** Helps identify bottlenecks like **Time to First Token (TTFT)** or high latency in RAG pipelines 
- **Cost Management:** Monitors token consumption to detect anomalies and attribute costs using Bedrock metrics.
- **Model Evaluation:** Integrates with services like **SageMaker Model Monitor** to detect data or bias drift in production models

