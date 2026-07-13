
# ⚡ Compute Labs
## Praesignis AWS re/Start Programme — Weeks 3 & 4 (15-26 June 2026)

---

## 📖 Introduction

### What is Cloud Computing?
Cloud computing is the delivery of computing services — servers, storage, databases, networking, software — over the internet ("the cloud"). Instead of buying and maintaining physical servers, you rent computing power from a cloud provider like AWS.

### What are AWS Compute Services?
AWS Compute Services provide the processing power needed to run applications in the cloud. Think of it as renting virtual computers instead of buying physical ones. AWS offers different compute options depending on your needs:

| Service | What It Is | Simple Explanation |
|---------|-----------|-------------------|
| **Amazon EC2** | Virtual servers in the cloud | Like renting a computer that lives in AWS's data centre |
| **AWS Lambda** | Serverless functions | Your code runs without you managing any server — AWS handles everything |
| **Amazon ECS** | Container orchestration | Runs Docker containers (packaged applications) at scale |
| **Amazon ECR** | Container image storage | A place to store your Docker images (like a photo album for containers) |
| **AWS Fargate** | Serverless containers | Run containers without managing the underlying servers |
| **Amazon EKS** | Managed Kubernetes | Run Kubernetes (a container management tool) on AWS |
| **AWS Auto Scaling** | Automatic capacity adjustment | Automatically adds/removes servers based on traffic |

### Why Do We Need Compute Services?
- 🏢 **Traditional (On-Premises):** Buy physical servers → expensive, takes weeks to set up, hard to scale
- ☁️ **Cloud (AWS):** Launch virtual servers in minutes → pay only for what you use, scale up/down instantly

### How These Services Connect:
User Request → Load Balancer → EC2 Instances (or Lambda/Containers) ↓ Auto Scaling (adds more if busy) ↓ Connects to databases, storage, etc.


---

## 📖 What is Amazon EC2?

**Amazon Elastic Compute Cloud (EC2)** is a web service that provides resizable compute capacity in the cloud. In simple terms, it's a virtual server that you can launch in minutes.

### Why EC2?
- No need to buy physical hardware
- Launch in minutes (not weeks)
- Choose your operating system (Linux, Windows)
- Scale up (bigger server) or out (more servers) as needed
- Pay only for what you use

### Key Components of EC2:
| Component | What It Is | Real-World Analogy |
|-----------|-----------|-------------------|
| **Instance** | A virtual server | A rented apartment |
| **AMI** | Template with OS + software | The blueprint of the apartment |
| **Instance Type** | CPU + RAM + Storage specs | The size of the apartment (studio vs. 3-bedroom) |
| **Security Group** | Firewall rules | The security gate — who can enter |
| **Key Pair** | SSH login credentials | Your apartment key |
| **EBS Volume** | Storage disk | Your filing cabinet |
| **Elastic IP** | Static public IP | Your permanent address |

---

## 📖 What is AWS Lambda?

**AWS Lambda** is a serverless compute service that lets you run code without provisioning or managing servers. You upload your code, and Lambda runs it only when triggered.

### Why Lambda?
- **No servers to manage** — AWS handles everything
- **Pay per use** — charged only when your code runs (per millisecond)
- **Auto-scales** — handles 1 request or 1 million requests automatically
- **Event-driven** — runs in response to triggers (file upload, API call, schedule)

### How Lambda Works:

Trigger (event) → Lambda Function (your code) → Output (response/action)

Examples:

    User uploads image to S3 → Lambda resizes it → Saves thumbnail
    API request comes in → Lambda processes it → Returns response
    Every day at 9 AM → Lambda runs report → Sends email


### Lambda vs EC2:
| Feature | Lambda | EC2 |
|---------|--------|-----|
| Server management | None (serverless) | You manage the OS |
| Scaling | Automatic | Manual or Auto Scaling |
| Pricing | Per request + duration | Per hour/second |
| Max runtime | 15 minutes | Unlimited |
| Best for | Short tasks, events | Full applications |

---

## 📖 What are Containers?

**Containers** are lightweight, portable packages that contain everything needed to run an application — code, runtime, libraries, and settings. Think of them as a lunchbox that has everything you need for a meal, no matter where you eat it.

### Containers vs Virtual Machines:
| Feature | Container | Virtual Machine (EC2) |
|---------|-----------|----------------------|
| Size | Megabytes | Gigabytes |
| Startup | Seconds | Minutes |
| OS | Shares host OS | Full OS per instance |
| Isolation | Process-level | Hardware-level |
| Best for | Microservices | Full applications |

### AWS Container Services:
| Service | Role | Simple Explanation |
|---------|------|-------------------|
| **ECR** | Registry (storage) | Where you store your container images |
| **ECS** | Orchestration (management) | Tells containers where and how to run |
| **EKS** | Orchestration (Kubernetes) | Same as ECS but uses Kubernetes |
| **Fargate** | Compute (serverless) | Runs containers without managing servers |

### Container Workflow:

    Write your app code
    Create a Dockerfile (instructions to build the container)
    Build the container image
    Push to ECR (store it)
    Deploy with ECS or EKS (run it)
    Fargate provides the compute (no servers to manage)


---

## 📖 What is AWS Auto Scaling?

**AWS Auto Scaling** automatically adjusts the number of EC2 instances based on demand. When traffic is high, it adds more servers. When traffic is low, it removes them. This saves money and ensures your app stays fast.

### How It Works:

Low traffic (2 AM): [Server 1] [Server 2] → 2 instances Normal traffic (9 AM): [Server 1] [Server 2] [Server 3] → 3 instances High traffic (Black Friday): [S1] [S2] [S3] [S4] [S5] [S6] → 6 instances Traffic drops: Auto Scaling removes extra servers → Back to 2


### Key Concepts:
| Concept | What It Means |
|---------|--------------|
| **Minimum** | Fewest instances to always keep running (e.g., 2) |
| **Maximum** | Most instances allowed (e.g., 10) |
| **Desired** | How many you want right now (e.g., 3) |
| **Scaling Policy** | The rule that triggers scaling (e.g., "if CPU > 70%, add 1 instance") |

---

## 📖 AWS Pricing & Billing

### How AWS Charges You:
AWS uses a **pay-as-you-go** model — like a utility bill (electricity, water). You only pay for what you use.

| Pricing Principle | Explanation |
|-------------------|-------------|
| **Pay-as-you-go** | No upfront costs, pay only for resources consumed |
| **Pay less when you reserve** | Commit for 1-3 years = big discounts |
| **Pay less per unit by using more** | Volume discounts (the more you use, the cheaper per unit) |

### AWS Free Tier:
| Type | Duration | Examples |
|------|----------|---------|
| **Always Free** | Forever | Lambda (1M requests/month), DynamoDB (25 GB) |
| **12 Months Free** | First year after sign-up | EC2 (750 hrs/month t2.micro), S3 (5 GB) |
| **Trials** | Short-term | SageMaker, Inspector, GuardDuty |

