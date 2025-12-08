
# MLOps Engineer

- [[#Tell me About Yourself|Tell me About Yourself]]
	- [[#Tell me About Yourself#Long version|Long version]]
	- [[#Tell me About Yourself#1-Minute Version|1-Minute Version]]
	- [[#Tell me About Yourself#20-Second Version|20-Second Version]]
- [[#ML Infrastructure & Architecture|ML Infrastructure & Architecture]]
	- [[#ML Infrastructure & Architecture#1. End-to-End ML Infrastructure (Your Real Setup) (DVC + MLflow + Training + Triton + FastAPI)|1. End-to-End ML Infrastructure (Your Real Setup) (DVC + MLflow + Training + Triton + FastAPI)]]
	- [[#ML Infrastructure & Architecture#2. ML Serving (Triton + FastAPI)|2. ML Serving (Triton + FastAPI)]]
	- [[#ML Infrastructure & Architecture#3. Training & Dataset Versioning Architecture (DVC + MLflow)|3. Training & Dataset Versioning Architecture (DVC + MLflow)]]
	- [[#ML Infrastructure & Architecture#4. On-Prem GPU Deployment (Proxmox + Docker + Triton)|4. On-Prem GPU Deployment (Proxmox + Docker + Triton)]]
	- [[#ML Infrastructure & Architecture#5. High-Throughput Inference Pipeline (Batching + FastAPI)|5. High-Throughput Inference Pipeline (Batching + FastAPI)]]
- [[#Questions and Answers|Questions and Answers]]
	- [[#Questions and Answers#1️. How would you design an end-to-end ML infrastructure for a computer vision pipeline?|1️. How would you design an end-to-end ML infrastructure for a computer vision pipeline?]]

## Tell me About Yourself

### Long version

“Sure. I’m an MLOps Engineer with over eight years of experience spanning MLOps, machine learning, backend engineering, and large-scale data systems. What makes my background unique is that I’ve consistently worked at the intersection of ML, software engineering, and platform building—so my strength is operationalizing AI systems end-to-end, not just developing models.

Most recently, I’ve been working at LPKF, where I had the opportunity to build the entire ML infrastructure from the ground up. When I joined, there was no existing ML pipeline, so I designed and implemented everything from data versioning with DVC to experiment tracking and model registry with MLflow. I also set up GPU-accelerated model serving using NVIDIA Triton and deployed it in an on-prem Proxmox cluster and Azure Cloud VM using data center GPUs such as A10, T4, H100 . This included designing the data flow architecture for high-resolution images and videos (terabytes of data) coming from BioTec imaging systems, and ensuring reproducible training and scalable inference. This experience really strengthened my ability to design ML systems that are reliable, maintainable, and production-ready.

Before that, I spent six years at Telekom Malaysia, where I held multiple roles—from Machine Learning Engineer to Lead Backend Engineer. I built real-time analytics engines for sensor data for building management systems, and also developed video analytics systems for people-counting and behavior analysis, and later led the backend engineering team. One of my achievements there was developing API microservices and data pipelines that reduced helpdesk operational workload by 50%. I also worked on FinTech systems like digital wallet backends, KYC pipelines, and PCI-DSS compliant key management systems. These roles gave me a strong foundation in distributed systems, API design, security, and data processing at scale.

I hold a master’s degree in Data Analytics from the University of Hildesheim, where I researched knowledge distillation for improving LLM efficiency. I’ve also completed several nanodegrees in LLMOps, DevOps, Full-Stack Development, and Computer Vision, which reflect my commitment to continuous learning.

Outside of work, I founded the Alex Snow School in Myanmar, a STEM and AI learning community with over 13,000 members. I also build open-source projects, including a BBC-audio RAG system with Whisper and Gemini, and an AI-driven career conversation tool.

Overall, I bring a blend of ML engineering, MLOps architecture, backend development, and real-world system deployment. I’m passionate about building scalable ML platforms that make model development faster, more reproducible, and more impactful.”


### 1-Minute Version

“Sure. I’m an MLOps Engineer with over 8 years of experience across ML engineering, backend development, and large-scale data systems. Most recently at LPKF, I built the entire ML infrastructure from scratch. I set up MLflow for experiment tracking and model registry, DVC for data versioning, and deployed GPU-accelerated models using NVIDIA Triton Server orchestrated through Docker and Docker Compose on our on-prem Proxmox environment and Azure Cloud VM. I also designed the data architecture for processing high-resolution image and video microscopy data, ensuring reproducible training workflows and scalable inference performance.

Before that, I spent six years at Telekom Malaysia in roles ranging from ML Engineer to Lead Backend Engineer. I developed real-time analytics systems, video analytics pipelines, and later led backend teams building microservices and ETL workflows that reduced internal operational workload by 50%. I also worked on FinTech systems—such as KYC verification flows and PCI-DSS–compliant key management services.

I hold a Master’s in Data Analytics, specialize in MLOps and LLMOps, and build open-source projects like a BBC-audio RAG system and an AI-driven career conversation tool. Overall, I bring strong hands-on experience in MLOps, ML engineering, and backend architecture—especially around deploying, serving, and operationalizing ML models with Docker-based GPU environments.”

### 20-Second Version

“I’m an MLOps Engineer with 8+ years across ML, backend engineering, and large-scale data systems. At LPKF, I built the full ML infrastructure—MLflow, DVC, and GPU inference using Triton Server deployed with Docker Compose on-prem. Before that, I led backend engineering at Telekom Malaysia, delivering high-impact microservices, analytics pipelines, and FinTech systems. I specialize in building scalable, reliable AI and ML platforms.

## ML Infrastructure & Architecture

### 1. End-to-End ML Infrastructure (Your Real Setup) (DVC + MLflow + Training + Triton + FastAPI)

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
### 1️. How would you design an end-to-end ML infrastructure for a computer vision pipeline?

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

5. Monitoring & Observability
	- MLflow for performance metrics.  
	- Triton’s Prometheus endpoint for GPU utilization, latency, and throughput.  
	- Application logs handled via ELK or a OpenSearch stack.  

This is very similar to the infrastructure I built at LPKF, where we had to handle high-resolution microscopy images and video data on-prem with Docker and GPU acceleration.”

