
# MLOps Engineer

- [[#Tell me About Yourself|Tell me About Yourself]]
	- [[#Tell me About Yourself#Long version|Long version]]
	- [[#Tell me About Yourself#1-Minute Version|1-Minute Version]]
	- [[#Tell me About Yourself#20-Second Version|20-Second Version]]
- [[#ML Infrastructure & Architecture|ML Infrastructure & Architecture]]
	- [[#ML Infrastructure & Architecture#1. End-to-End ML Infrastructure (DVC + MLflow + Training + Triton + FastAPI)|1. End-to-End ML Infrastructure (DVC + MLflow + Training + Triton + FastAPI)]]
	- [[#ML Infrastructure & Architecture#2. ML Serving (Triton + FastAPI)|2. ML Serving (Triton + FastAPI)]]
	- [[#ML Infrastructure & Architecture#3. Training & Dataset Versioning Architecture (DVC + MLflow)|3. Training & Dataset Versioning Architecture (DVC + MLflow)]]
	- [[#ML Infrastructure & Architecture#4. On-Prem GPU Deployment (Proxmox + Docker + Triton)|4. On-Prem GPU Deployment (Proxmox + Docker + Triton)]]
	- [[#ML Infrastructure & Architecture#5. High-Throughput Inference Pipeline (Batching + FastAPI)|5. High-Throughput Inference Pipeline (Batching + FastAPI)]]
- [[#Questions and Answers|Questions and Answers]]
	- [[#Questions and Answers#How would you design an end-to-end ML infrastructure for a computer vision pipeline?|How would you design an end-to-end ML infrastructure for a computer vision pipeline?]]
	- [[#Questions and Answers#Why did you choose Docker Compose instead of Kubernetes for deployment?|Why did you choose Docker Compose instead of Kubernetes for deployment?]]
	- [[#Questions and Answers#What are the core components of a modern MLOps infrastructure?|What are the core components of a modern MLOps infrastructure?]]
	- [[#Questions and Answers#How do you architect reproducible ML pipelines?|How do you architect reproducible ML pipelines?]]
	- [[#Questions and Answers#How would you handle large imaging/video data efficiently?|How would you handle large imaging/video data efficiently?]]
	- [[#Questions and Answers#How do you scale GPU inference without Kubernetes?|How do you scale GPU inference without Kubernetes?]]
	- [[#Questions and Answers#How would you design a model registry and promotion workflow?|How would you design a model registry and promotion workflow?]]
	- [[#Questions and Answers#What is your approach to monitoring ML systems in production?|What is your approach to monitoring ML systems in production?]]
	- [[#Questions and Answers#If you had to build this ML infrastructure again from scratch, what would you prioritize first?|If you had to build this ML infrastructure again from scratch, what would you prioritize first?]]
	- [[#Questions and Answers#What challenges did you face when building ML infrastructure at LPKF?|What challenges did you face when building ML infrastructure at LPKF?]]
	- [[#Questions and Answers#How do you prevent data leakage in an automated ML pipeline?|How do you prevent data leakage in an automated ML pipeline?]]
	- [[#Questions and Answers#Why use Triton instead of a custom FastAPI inference server?|Why use Triton instead of a custom FastAPI inference server?]]
	- [[#Questions and Answers#How would you optimize Triton for high-throughput real-time inference?|How would you optimize Triton for high-throughput real-time inference?]]
	- [[#Questions and Answers#Explain dynamic batching in Triton.|Explain dynamic batching in Triton.]]
	- [[#Questions and Answers#How to expose a scalable inference API with FastAPI?|How to expose a scalable inference API with FastAPI?]]
	- [[#Questions and Answers#How do you handle model A/B testing and canary deployments for ML models?|How do you handle model A/B testing and canary deployments for ML models?]]
		- [[#How do you handle model A/B testing and canary deployments for ML models?#Blue/Green Deployment|Blue/Green Deployment]]
		- [[#How do you handle model A/B testing and canary deployments for ML models?#Canary Deployment|Canary Deployment]]
		- [[#How do you handle model A/B testing and canary deployments for ML models?#Shadow Testing (a.k.a. Dark Launching)|Shadow Testing (a.k.a. Dark Launching)]]
- [[#Leadership Questions|Leadership Questions]]
	- [[#Leadership Questions#Give an example of standardizing engineering workflow across teams.|Give an example of standardizing engineering workflow across teams.]]
	- [[#Leadership Questions#How do you communicate ML system limitations to non-technical stakeholders?|How do you communicate ML system limitations to non-technical stakeholders?]]
	- [[#Leadership Questions#How do you mentor junior engineers or contributors?|How do you mentor junior engineers or contributors?]]
## Tell me About Yourself

### Long version

“Sure. I’m an MLOps Engineer with over eight years of experience spanning MLOps, machine learning, backend engineering, and building large-scale data systems. What makes my background unique is that I’ve consistently worked at the intersection of ML, software engineering, and platform building—so my strength is operationalizing AI systems end-to-end, not just developing models.

Most recently, I’ve been working at LPKF, where I had the opportunity to build the entire ML infrastructure from the ground up. When I joined, there was no existing ML pipeline and they were just using Jupyter Notebooks for their ML experiments, so I designed and implemented everything from data versioning with DVC to experiment tracking and model registry with MLflow. I also set up GPU-accelerated model serving using NVIDIA Triton Server and deployed it in on-premise Proxmox Severs for our internal customer and also in  Azure Cloud for external customer. This whole process included designing the data flow architecture for high-resolution images and videos data coming from microscopy  imaging systems. I use MinIO as our S3 data storage for on-premise server. This experience really strengthened my ability to design ML systems that are reliable, maintainable, and production-ready.

Before that, I spent six years at Telekom Malaysia, where I took multiple roles—from Machine Learning Engineer to even led a small Backend Engineering team. I built real-time analytics engines for sensors data, and also developed video analytics systems for people-counting and behavior analysis. One of my achievements there was developing  backend  microservices  and data pipelines that reduced helpdesk operational workload by 50%.  These roles gave me a strong foundation in API design, security, and data processing at scale.

I hold a master’s degree in Data Analytics from the University of Hildesheim, where I did my master thesis in knowledge distillation for improving LLM efficiency. I’ve also completed several nanodegrees in LLMOps, DevOps, and Computer Vision, which reflect my commitment to continuous learning.

Outside of office work, I founded the Alex Snow School in Myanmar. It is a AI and ML learning community with over 13,000 learners. I also enjoy building open-source projects. The most recent project was a BBC-audio RAG system which I built using Whisper for transcription and Genimi for interactive chatting with the audio lecture. 

Overall, I bring a blend of ML engineering, MLOps architecture, backend development, and real-world system deployment. I’m passionate about building scalable ML platforms that make model development faster, more reproducible, and more impactful.”


### 1-Minute Version

“Sure. I’m an MLOps Engineer with over 8 years of experience across ML engineering, backend development, and large-scale data systems. Most recently at LPKF, I built the entire ML infrastructure from scratch. I set up MLflow for experiment tracking and model registry, DVC for data versioning, and deployed GPU-accelerated models using NVIDIA Triton Server orchestrated through Docker and Docker Compose on our on-prem Proxmox environment and Azure Cloud VM. I also designed the data architecture for processing high-resolution image and video microscopy data, ensuring reproducible training workflows and scalable inference performance.

Before that, I spent six years at Telekom Malaysia in roles ranging from ML Engineer to Lead Backend Engineer. I developed real-time analytics systems, video analytics pipelines, and later led backend teams building microservices and ETL workflows that reduced internal operational workload by 50%. 

I hold a Master’s in Data Analytics, specialize in MLOps and LLMOps, and build open-source projects like a BBC-audio RAG system and an AI-driven career conversation tool. Overall, I bring strong hands-on experience in MLOps, ML engineering, and backend architecture—especially around deploying, serving, and operationalizing ML models with Docker-based GPU environments.”

### 20-Second Version

“I’m an MLOps Engineer with 8+ years across ML, backend engineering, and large-scale data systems. At LPKF, I built the full ML infrastructure—MLflow, DVC, and GPU inference using Triton Server deployed with Docker Compose on-prem. Before that, I led backend engineering at Telekom Malaysia, delivering high-impact microservices, analytics pipelines, and FinTech systems. I specialize in building scalable, reliable AI and ML platforms.

## ML Infrastructure & Architecture

### 1. End-to-End ML Infrastructure (DVC + MLflow + Training + Triton + FastAPI)

```pgsql 
                         ┌─────────────────────────┐
                         │        Developers       │
                         └───────────┬─────────────┘
                                     │ (Git Push)
                          ┌──────────▼──────────┐
                          │    Git Repository   │
                          └──────────┬──────────┘
                                     │
                                     │ triggers CI
──────────────────────────────────────────────────────────────────────
                          TRAINING & VERSIONING LAYER
──────────────────────────────────────────────────────────────────────
                                     │
                     ┌───────────────┴────────────────┐
                     │                                │
          ┌──────────▼──────────┐          ┌──────────▼──────────┐
          │        DVC          │          │       MLflow        │
          │ Data Versioning     │          │ Experiment Tracking  │
          └──────────┬──────────┘          └──────────┬──────────┘
                     │                                 │
                     │                                 │
             ┌───────▼─────────┐               ┌───────▼────────┐
             │  Training Jobs   │──────────────▶│ Model Registry  │
             │ (Docker + GPU)   │   log models  │ (MLflow)        │
             └───────┬─────────┘               └───────┬────────┘
                     │                                 │
──────────────────────────────────────────────────────────────────────
                           SERVING / INFERENCE LAYER
──────────────────────────────────────────────────────────────────────
                     │                                 │ model pull
             ┌───────▼──────────┐      gRPC/HTTP  ┌────▼───────────┐
             │    FastAPI        │ <────────────── │ Triton Server  │
             │  API Gateway      │────────────────▶│ GPU Inference  │
             └───────┬──────────┘                 └────┬───────────┘
                     │                                   │
                     │             Metrics               │
                     ▼                                   ▼
           ┌────────────────┐                   ┌────────────────────┐
           │ Client Apps    │                   │ Prometheus/Grafana │
           └────────────────┘                   └────────────────────┘

```

### 2. ML Serving (Triton + FastAPI)

```pgsql
                     ┌───────────────────────────┐
                     │       docker-compose       │
                     └──────────────┬────────────┘
                                    │
     ┌──────────────────────────────┼─────────────────────────────────┐
     │                              │                                 │
┌────▼─────┐                 ┌──────▼──────┐                  ┌───────▼─────┐
│  FastAPI │                 │ Triton      │                  │ MLflow      │
│  Gateway │  <────────────► │ GPU Server  │ ◄──────────────►│ Tracking/   │
│ (CPU)    │  gRPC/HTTP      │ (CUDA/ONNX) │   load models    │ Registry    │
└────┬─────┘                 └──────┬──────┘                  └───────┬─────┘
     │                               │                                  │
     │                               │ metrics                          │
┌────▼──────┐                 ┌──────▼────────┐                 ┌───────▼─────┐
│  Client   │                 │ Prometheus     │                 │   Postgres   │
│ Requests  │                 │ (Monitoring)   │                 │ MLflow DB    │
└───────────┘                 └───────────────┘                 └──────────────┘

```


### 3. Training & Dataset Versioning Architecture (DVC + MLflow)
```pgsql
                     ┌────────────────────────────────┐
                     │           Developer             │
                     └────────────────┬───────────────┘
                                      │ git + dvc push
                                      ▼
                           ┌───────────────────────┐
                           │   Git Repo + DVC      │
                           │ (.dvc files + code)   │
                           └──────────┬────────────┘
─────────── Data Versioning ──────────┼────────────────────────────────
                                      │ dvc pull/push
                           ┌──────────▼────────────┐
                           │   DVC Remote Storage   │
                           │ (NAS/MinIO/Blob)       │
                           └──────────┬────────────┘
                                      │
                       ┌──────────────▼──────────────┐
                       │     Training Containers      │
                       │ (Docker + CUDA + PyTorch)    │
                       └───────┬─────────────────────┘
                               │ logs metrics/artifacts
                               ▼
                       ┌─────────────────────────────┐
                       │        MLflow Server        │
                       │  - Experiment Tracking       │
                       │  - Parameters & Metrics      │
                       │  - Models & Artifacts        │
                       └─────────────────────────────┘

```

### 4. On-Prem GPU Deployment (Proxmox + Docker + Triton)
```pgsql
                  ┌────────────────────────────────────────┐
                  │              Proxmox Node              │
                  │ GPU Passthrough Enabled (NVIDIA GPUs)  │
                  └───────────────────┬────────────────────┘
                                      │
                   ┌──────────────────▼───────────────────┐
                   │        Ubuntu VM w/ NVIDIA Driver    │
                   │   + CUDA Toolkit + Docker Runtime     │
                   └───────────────────┬───────────────────┘
                                       │
                              ┌────────▼────────┐
                              │ docker-compose   │
                              └───────┬─────────┘
      ┌───────────────────────────────┼──────────────────────────────┐
      │                               │                              │
┌─────▼─────┐                  ┌──────▼───────┐               ┌──────▼──────┐
│ FastAPI    │                  │ Triton       │               │ MLflow       │
│ Gateway    │◄────────────────►│ GPU Server   │◄────────────►│ Tracking/    │
└────────────┘   gRPC/HTTP      │ Inference    │   model pull  │ Registry     │
                             ┌──┴──────────────┘               └──────────────┘
                             │
                       ┌─────▼────────┐
                       │   GPU HW      │
                       │  (A100, T4)   │
                       └───────────────┘

```


### 5. High-Throughput Inference Pipeline (Batching + FastAPI)

```pgsql
Client Requests
       │
       ▼
┌────────────┐       ┌────────────────────────────┐
│ FastAPI    │       │  Dynamic Batching (Triton) │
│ Preprocess │──────▶│  Combine N requests        │
└─────┬──────┘       │  Single GPU Forward Pass   │
      │               └───────────┬────────────────┘
      ▼                           │
┌────────────┐                    ▼
│ Triton GPU │──────────────▶ GPU Kernel
│ Inference  │                    │
└─────┬──────┘                    ▼
      │                ┌────────────────────┐
      ▼                │ FastAPI Postprocess│
┌────────────┐         └───────────┬────────┘
│ Response   │                     ▼
└────────────┘               Back to Client

```

## Questions and Answers
### How would you design an end-to-end ML infrastructure for a computer vision pipeline?

“My approach is to design the infrastructure around reproducibility, modularity, and scalable inference. A typical architecture looks like this:

1. **Data Layer**
	- Raw images and videos stored in a structured directory or object storage.  
	- DVC handles versioning and tracks metadata.  
	- Dataset processing pipelines defined in `dvc.yaml` for reproducibility.  

2. **Experimentation & Training**    
	- Training jobs run on GPU machines inside Docker containers—fully reproducible environments.  
	- Model artifacts are automatically registered into the MLflow Model Registry.  

3. **Model Packaging & Serving**
	- Models exported into Triton-compatible formats (ONNX, TorchScript, TensorRT). 
	- Triton Inference Server is deployed via Docker Compose on GPU-enabled nodes.  
	- This setup provides batching, concurrency, and optimized GPU usage without needing Kubernetes.  

4. **API Layer**
	- A lightweight FastAPI service acts as the inference gateway.  
	- Handles preprocessing, postprocessing, and routing requests to Triton via gRPC/HTTP.  

5. **Monitoring & Observability**
	- MLflow for performance metrics.  
	- Triton’s Prometheus endpoint for GPU utilization, latency, and throughput.  
	- Application logs handled via ELK or a OpenSearch stack.  

This is very similar to the infrastructure I built at LPKF, where we had to handle high-resolution microscopy images and video data on-prem with Docker and GPU acceleration.”

### Why did you choose Docker Compose instead of Kubernetes for deployment?

“In our environment, Kubernetes wasn’t necessary because the workloads were predictable, ran on a small number of GPU , and didn’t require multi-node orchestration.

Docker Compose was ideal because:
- It’s lightweight and easy to maintain. 
- Fits well in on-prem Proxmox virtualized environments.  
- Triton, MLflow, FastAPI, Postgres, and supporting services can be defined in a single compose file.  
- No need for complex networking or autoscaling logic. 
- Faster debugging and shorter development cycles.  
For our use case—high-throughput inference running on a fixed number of GPUs—Docker Compose gave us the simplicity we needed while still being production-grade.”

### What are the core components of a modern MLOps infrastructure?

“A mature MLOps infrastructure includes:

1. Data Management  
	- DVC or similar for data versioning  
	- Storage backend like MinIO, Azure Blob, or NAS  
	
2. Experiment Tracking & Model Registry  
	- MLflow to track metrics, parameters, artifacts  
	- Automated model versioning and stage transitions  
	
3. Training Environment  
	- Reproducible Docker containers  
	- GPU-accelerated training jobs  
	- Automated workflow orchestration  

4. Model Serving  
	- Triton Server for high-performance GPU serving  
	- FastAPI for routing and business logic  
	- Docker Compose for service orchestration  
	
5. CI/CD for ML  
	- GitLab CI/CD or GitHub Actions  
	- Automated testing and building of inference containers  
	- Model promotion pipelines  
    
6. Monitoring & Observability  
	- Triton metrics (latency, GPU utilization)  
	- MLflow for model performance tracking  
	- Logging stack for request and error logs  
    
7. Security & Governance  
	- Access controls, secret management  
	- Audit logs  
	- Reproducibility & traceability from data → model → deployment  
    
This reflects exactly how I structure systems in real projects.

### How do you architect reproducible ML pipelines?

“Reproducibility requires controlling three things: data, code, and environment.
Here’s how I approach it:
- **Data**: I version datasets with DVC, including checksums and lineage.  
- **Code**: Git for source control, modular ML code structure, semantic versioning.  
- **Environment**: Training and inference run in the same Docker images, pinned with specific CUDA, PyTorch, and library versions.  
- **Experiments**: MLflow logs all hyperparameters, metrics, and artifacts so any run can be recreated.  
- **Pipelines**: DVC pipelines define deterministic steps from raw data → features → model.  
This way, any model can be reproduced months later, even in a new environment.

### How would you handle large imaging/video data efficiently?

“For large image and video data, the key is to optimize storage, I/O, and preprocessing:

- Chunking and indexing large video files for faster access  
- Using parallel preprocessing in Docker containers  
- Storing preprocessed intermediate datasets versioned in DVC  
- Using efficient data formats like WebP/PNG for images and H.265/MJPEG for videos  
- Ensuring zero-copy GPU pipelines when possible  
- Using Triton preprocessors or custom CUDA kernels for speed  

At LPKF, the data volume was extremely high because of microscopy resolution. Efficient preprocessing and DVC-based dataset organization made a massive difference.

### How do you scale GPU inference without Kubernetes?

Even without Kubernetes, you can scale efficiently using:

- Multiple Triton instances defined in Docker Compose  
- Load-balanced FastAPI gateway routing requests using Nginx
- Triton dynamic batching to boost GPU throughput  
- TensorRT-optimized model formats  
- Running Triton containers on different GPU devices with --gpus device=X  
- Vertical scaling with larger GPU cards on our Proxmox nodes  

This allowed us to achieve high throughput for CV inference workloads without the overhead of managing a K8s cluster.

### How would you design a model registry and promotion workflow?

I implement a 3-stage promotion process using MLflow:
1. **Development Stage**  
	- Newly trained models  
	- Verified only via offline metrics  
    
2. **Staging Stage**  
	- Tested with validation datasets  
	- Load-tested in staging Triton instance  
	- API-level smoke tests  
	- Partial rollout in Docker Compose environment  
	
3. **Production Stage**  
	- Manually approved  
	- Deployed as the active Triton model version  
	- Old versions retained for rollback  
Model lineage is tracked via MLflow + DVC so we always know which data + code produced each version.

### What is your approach to monitoring ML systems in production?

I monitor both system-level and model-level metrics:

1. **System monitoring (from Triton):**
	- GPU utilization  
	- Memory usage  
	- QPS and latency  
	- Dynamic batching efficiency  
	- Request error rates  
      
2. **Model monitoring (from MLflow + custom API logs):**
	- Drift (input distribution vs training distribution)  
	- Confidence scores  
	- Accuracy or proxy business metrics  
	- Failed inference cases  
	- Data quality anomalies  
      
3. **Application monitoring:**
	- FastAPI logs 
	- Response codes 
	- Throughput  

These metrics together give a reliable view of model health and system stability.

### If you had to build this ML infrastructure again from scratch, what would you prioritize first?

I would start with:
1. Data organization and versioning (DVC + storage)  
2. Experiment tracking and reproducibility (MLflow + Docker images)  
3. Inference architecture (Triton + FastAPI + Docker Compose)  
4. Monitoring and logging  
5. CI/CD automation  
Once these foundations are stable, adding feature stores, scheduling, and advanced automation becomes much easier.

### What challenges did you face when building ML infrastructure at LPKF?

The main challenges were:
- Handling extremely large microscopy images efficiently  
- Setting up a reproducible system without any existing ML infrastructure  
- Ensuring GPU inference worked reliably in a non-cloud, on-prem Proxmox cluster  
- Standardizing the workflow across multiple research teams  
- Getting DVC, MLflow, Triton, and FastAPI to work together cleanly via Docker Compose      
Through systematic iteration, documentation, and modular design, we built a stable production pipeline.

### How do you prevent data leakage in an automated ML pipeline?

“I prevent data leakage by enforcing strict data isolation rules in the pipeline: using proper train-validation-test splits, applying all transformations through versioned DVC pipelines, ensuring no future information leaks into training, and validating that preprocessing in serving matches training. I also automate drift checks and schema validation so only clean, non-leaky data passes into training.”

---

### Why use Triton instead of a custom FastAPI inference server?

“Triton provides GPU-optimized, production-ready model serving out of the box. It supports dynamic batching, concurrent execution, multi-model serving, optimized backends like TensorRT, and built-in metrics — all of which are difficult and time-consuming to implement manually with FastAPI. FastAPI is great as a gateway, but Triton is far more efficient for heavy ML inference.”

---

### How would you optimize Triton for high-throughput real-time inference?
 
“I optimize throughput by enabling dynamic batching, using TensorRT or ONNX-optimized models, adjusting `max_batch_size` and `preferred_batch` sizes, running multiple model instances for concurrency, pinning CPU/GPU resources properly, and using gRPC for lower latency compared to HTTP. I also profile performance using Triton’s built-in metrics.”

---

### Explain dynamic batching in Triton.
  
“Dynamic batching lets Triton combine multiple incoming requests into a single larger batch automatically. This maximizes GPU utilization and reduces per-request overhead, dramatically increasing throughput while keeping latency within the configured limits. It’s one of Triton’s biggest performance advantages.”

---

### How to expose a scalable inference API with FastAPI?

“I use FastAPI as a lightweight gateway: async endpoints, connection pooling, and a router that forwards requests to Triton via gRPC. Behind FastAPI, I run multiple worker processes (e.g., with Uvicorn/Gunicorn) in Docker so the API scales horizontally. Triton handles the heavy inference, while FastAPI provides routing, preprocessing, and load balancing.”

### How do you handle model A/B testing and canary deployments for ML models?  

#### Blue/Green Deployment
we run **two identical production environments**:
- **Blue** = Current production
- **Green** = New version of the mode
Switch traffic from Blue → Green only when Green is verified to work.
```bash
           ┌──────────┐
Traffic →  │  Blue    │ (v1 - current)
           └──────────┘
                 │
          Switch traffic
                 ▼
           ┌──────────┐
           │  Green   │ (v2 - new model)
           └──────────┘
```
When to use:
- Major model change
- Infrastructure updates (new Triton config, new Docker images)
- Risk of breaking downstream systems
    
Pos:
- Easy rollback (just switch traffic back)
- Zero downtime

Cons:
	- Requires double resources  
	- Not ideal for gradual rollouts
	
How I would use it with Triton:
- Run `triton_v1` and `triton_v2` as two separate containers in Docker Compose
- FastAPI routes traffic to one of them
- To release: update FastAPI routing to point to `triton_v2`
This is perfect in **on-prem environments** like your Proxmox cluster.
--- 
#### Canary Deployment

Roll out the new model to **a small percentage** of users first.  
Example: 5% get the new model, 95% get the stable one.

```bash
95% traffic → Model v1 (stable)
 5% traffic → Model v2 (new)

95/5 → 80/20 → 50/50 → 0/100
```

When to use:
- You want **gradual rollout**    
- You want to test a new model in production with low risk
- You want real traffic feedback before full release
    
Pros:
- Detect issues early
- Low-risk production testing
- Maintains traffic for old model
    
Cons:
	– Requires traffic routing logic in FastAPI  
	– More complex than Blue/Green
	
How I would use it with Triton: (Ngnix)
- Run both v1 and v2 on Triton (multi-model repository)
- In FastAPI, randomly route X% of requests to v2
- Log outcomes for comparison
- Increase percentage over time
This aligns well with your **FastAPI Gateway → Triton** serving architecture.
---
#### Shadow Testing (a.k.a. Dark Launching)
The new model receives **a copy of real production traffic**, but its output is **not returned to users**.
It runs silently “in the shadows.”
```bash
Incoming Request → Model v1 (returns result)
                  ↘
                   → Model v2 (shadow)   (output ignored)
```
When to use:
- You need to compare model behavior with 0 risk
- For CV/LLM workloads where offline tests are insufficient
- When you need confidence that the new model won’t break expectations
    
Pros:
- Zero user impact
- Full production load
- Best for validating ML behavior
    
Cons:
– Requires duplicating traffic  
– Extra compute usage (twice the inference cost)

How I  would use it with Triton:

- FastAPI receives incoming request
- Sends one request to Triton v1 (response to user)
- Sends a duplicate to Triton v2
- Logs v1 vs v2 outputs to MLflow or a database
This works extremely well in **high-precision imaging systems** like LPKF’s microscopy workflow.



    
## Leadership Questions
### Give an example of standardizing engineering workflow across teams.

“At Telekom Malaysia, I standardized the backend engineering workflow across multiple teams by introducing consistent API guidelines, automated testing, shared CI/CD pipelines, and centralized logging. This reduced duplicate work, improved code quality, and cut operational effort by nearly 50%. The same practices helped align cross-functional teams and made onboarding faster.”

---

### How do you communicate ML system limitations to non-technical stakeholders?

“I explain limitations using clear, business-focused language — not technical jargon. For example, instead of talking about model drift or overfitting, I describe how accuracy can change when the real-world data shifts. I use simple visuals, examples, and concrete scenarios so stakeholders understand the impact on the product and the decisions we need to make. My goal is to align expectations and ensure everyone understands both capabilities and risks.”

---

### How do you mentor junior engineers or contributors?

“I mentor by pairing with junior engineers on real tasks, reviewing their code with constructive feedback, and breaking down complex concepts into simple explanations. I also guide them toward best practices — like reproducible ML pipelines, clean code, and proper version control. I prefer a supportive, hands-on approach that helps them grow confidence and autonomy while learning industry standards.”