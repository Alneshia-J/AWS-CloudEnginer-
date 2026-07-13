### What I Did:
- Launched an Amazon EC2 instance from the AWS Console
- Selected an AMI (Amazon Machine Image) and instance type
- Configured security groups and key pairs
- Connected to the instance via SSH

### How I Did It:
1. Navigated to EC2 Dashboard in AWS Console
2. Clicked **Launch Instance**
3. Selected **Amazon Linux 2 AMI**
4. Chose instance type: `t2.micro` (Free Tier eligible)
5. Configured security group to allow SSH (port 22)
6. Created and downloaded a key pair (.pem file)
7. Launched the instance and waited for "Running" status
8. Connected via terminal: `ssh -i mykey.pem ec2-user@<public-ip>`

### Key Concepts Learned:
| Concept | Description |
|---------|-------------|
| **AMI** | Template containing the OS and software for your instance |
| **Instance Type** | Determines CPU, memory, storage (e.g., t2.micro = 1 vCPU, 1 GB RAM) |
| **Security Group** | Virtual firewall controlling inbound/outbound traffic |
| **Key Pair** | SSH keys for secure remote access |
| **Elastic IP** | Static public IP address that doesn't change on stop/start |

### Commands Used:
```bash
# Connect to EC2 instance
ssh -i "mykey.pem" ec2-user@<public-ip-address>

# Verify connection
whoami          # ec2-user
hostname        # ip-xxx-xxx-xxx-xxx
uname -a        # Linux kernel info

