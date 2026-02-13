# AWS Bedrock Workshop - Agentic AI Bootcamp

## 📌 About the Bootcamp

The bootcamp is a hands-on enablement program by our AWS Solutions Architects and Prototyping Architects, where the customer Agentic AI use case gets accelerated through a charge-free co-development and technical knowledge transfer in an on-site, multi-customer classroom setting.

slidies are in docs/
---

## 📅 Agenda

### **Day 1** - Foundations & GenAI Essentials

| Topic | Content |
|-------|---------|
| **Welcome** | Welcome from Thierry Pierre, leader of AWS AI/ML FR specialist team |
| **GenAI models** | • AWS GenAI offering<br>• Models available in Bedrock<br>• Model selection criteria<br>• Model evaluation |
| **GenAI patterns** | • Prompt engineering<br>• Multimodality<br>• RAG |
| **GenAI services** | • Bedrock Data Automation<br>• Amazon Quick Suite |

### **Day 2** - Agentic AI Architecture & Orchestration

| Topic | Content |
|-------|---------|
| **Architecting Agentic AI Systems** | • Components of Agentic AI systems<br>• MCP |
| **AI Agent Orchestration** | • Strands Agents<br>• State and sessions<br>• Multi-agents solutions<br>• Model Evaluation and how to approach agents' evaluation and observability |
| **Agentic AI Security** | • Security considerations for GenAI Agentic systems |

### **Day 3** - Bedrock AgentCore Deep Dive & Wrap-up

| Topic | Content |
|-------|---------|
| **Bedrock AgentCore** | • Bedrock AgentCore deep dive<br>• Agents Evaluation and Observability |
| **AI coding tools and best practices** | • Kiro and Spec Driven Development |
| **What Next?** | • What to anticipate over the next two weeks<br>• Meet your PA<br>• Ensure account set up<br>• Work on Customer Business Outcomes |

---

## 🚀 Quick Start

### Prerequisites
- Python 3.9 or higher
- pip (Python package manager)
- Git

### 1️⃣ Create a Virtual Environment

#### On macOS/Linux
```bash
# Create the virtual environment
python3 -m venv venv

# Activate the virtual environment
source venv/bin/activate
```

#### On Windows
```bash
# Create the virtual environment
python -m venv venv

# Activate the virtual environment
venv\Scripts\activate
```

### 2️⃣ Install Dependencies

Once the virtual environment is activated, install the requirements:

```bash
# Install main packages
pip install -r requirements.txt

# If you're working on AgentCore labs
cd agentcore
pip install -r requirements-agent.txt
cd ..
```

### 3️⃣ Verify Installation

```bash
# Verify that everything is installed correctly
pip list
```

### 4️⃣ AWS Configuration

Before getting started, make sure your AWS credentials are configured. You can use one of the two methods below:

#### Option 1: With `aws configure` (standard)

```bash
aws configure
```

You will need:
- AWS Access Key ID
- AWS Secret Access Key
- Default region (e.g., us-east-1)
- Default output format (json)

#### Option 2: With `aws-vault` (recommended for security)

[aws-vault](https://github.com/99designs/aws-vault) is a secure tool for managing your AWS credentials. It stores your credentials in your system's secure keychain.

**Installation**:
```bash
# macOS (with Homebrew)
brew install aws-vault

# Linux
curl https://github.com/99designs/aws-vault/releases/download/v7.2.0/aws-vault-linux-amd64 -o aws-vault
chmod +x aws-vault
sudo mv aws-vault /usr/local/bin

# Windows
choco install aws-vault
```

**Configuration**:
```bash
# Add your credentials
aws-vault add default

# Verify configuration
aws-vault list
```

**Usage**:
```bash
# Execute an AWS command securely
aws-vault exec default -- aws s3 ls

# Or launch Jupyter with credentials
aws-vault exec default -- jupyter notebook
```

---

## 📂 Project Structure

```
aws-bedrock-workshop/
├── agentcore/                          # AgentCore Labs (1-7)
│   ├── lab-01-create-an-agent.ipynb
│   ├── lab-02-agentcore-memory.ipynb
│   ├── lab-03-agentcore-gateway.ipynb
│   ├── lab-04-agentcore-runtime.ipynb
│   ├── lab-05-agentcore-evals.ipynb
│   ├── lab-06-frontend.ipynb
│   ├── lab-07-agentcore-policy.ipynb
│   ├── lab_helpers/                    # Lab utilities
│   ├── prerequisite/                   # CloudFormation infrastructure
│   └── scripts/                        # Helper scripts
│
├── architecture_patterns/              # GenAI architecture patterns
│   └── 01_text_and_code_generation_w_bedrock.ipynb
│
├── bedrock_data_automation/            # Bedrock automation
│   ├── 01_standard_output_basic_to_advanced.ipynb
│   └── 02_custom_outputs_and_blueprints.ipynb
│
├── guardrails/                         # Chatbot security
│   └── 01-secure_chatbots.ipynb
│
├── image_and_multimodal/               # Image and multimodal processing
│   ├── 01_nova-canvas-notebook.ipynb
│   ├── 02_nova-reel-notebook.ipynb
│   └── 03_bedrock-titan-multimodal-embeddings.ipynb
│
├── knowledgebases_and_rag/             # Knowledge Bases and RAG
│   ├── 01_create_ingest_documents_test_kb.ipynb
│   └── 02_managed-rag-kb-retrieve-generate-api.ipynb
│
├── speech_to_speech/                   # Text-to-Speech and Speech-to-Text
│   ├── 00_introduction_nova_sonic_console.ipynb
│   ├── 01_core_functionality.ipynb
│   ├── 02_repeatable_patterns.ipynb
│   ├── python-server/
│   └── react-client/
│
├── strands_agents/                     # Strands Agents Implementation Examples
│   ├── 01-first-agent/
│   ├── 02-connecting-with-aws-services/
│   ├── 03-using-mcp-tools/
│   ├── 04-agent-as-tool/
│   ├── 05-agent-workflows/
│   ├── 06-graph-agent/
│   └── 07-swarm-agent/
│
├── util/                               # Utility modules and helpers
│   ├── __init__.py
│   ├── model_constants.py              # Model configuration constants
│   ├── model_selector.py               # Model selection utilities
│   ├── strands_retry.py                # Retry logic for agent calls
│   └── tagging.py                      # AWS resource tagging utilities
│
├── cleanup/                            # Cleanup scripts
│   └── 01_cleanup.ipynb
│
├── requirements.txt                    # Main dependencies
├── Agent.md                            # Agents comprehensive guide
└── README.md                           # This file
```

---

## 📖 Starting the Labs

### Launch Jupyter Notebook

```bash
# Launch Jupyter Notebook
jupyter notebook

# Or launch Jupyter Lab (more modern)
jupyter lab
```

Then navigate to the `agentcore/` folder to start the labs:
- **Lab 1**: Create an Agent
- **Lab 2**: AgentCore Memory
- **Lab 3**: AgentCore Gateway
- **Lab 4**: AgentCore Runtime
- **Lab 5**: AgentCore Evals
- **Lab 6**: Frontend
- **Lab 7**: AgentCore Policy

For more details on Agents, see [Agent.md](Agent.md).

---

## 🔧 Useful Commands

```bash
# Deactivate the virtual environment
deactivate

# Update pip
pip install --upgrade pip

# Reinstall dependencies (if issue)
pip install --force-reinstall -r requirements.txt

# List all installed packages
pip list

# Create a file with current dependencies
pip freeze > requirements.txt
```

---

## ⚠️ IMPORTANT: AWS Resources Management and Cost Control

This bootcamp will create AWS resources in your account, including:
- CloudFormation infrastructure (stacks)
- Bedrock services (Agents, Knowledge Bases, etc.)
- S3 storage
- DynamoDB tables
- SageMaker endpoints
- And other cloud resources

### 🔴 CRITICAL: Cleanup After Bootcamp

**These resources incur costs!** You must delete them after the labs to avoid unnecessary charges.

```bash
# Use the included cleanup script
cd cleanup
jupyter notebook 01_cleanup.ipynb

# Or run the cleanup script
python cleanup_tagged_resources.py
```

**Cleanup Checklist**:
- ✅ Stop all Jupyter notebooks
- ✅ Run the provided cleanup scripts
- ✅ Delete CloudFormation stacks manually if necessary
- ✅ Verify in AWS console that all resources have been deleted
- ✅ Consult the `cleanup/` section for more details

**Cost Estimate**: Costs vary depending on usage but can be significant for certain services. Be cautious!

---

## 📝 Important Notes

- ✅ This bootcamp is a **hands-on experience** - be ready to code!
- ✅ Labs are **progressive** - start with Lab 1
- ✅ You'll need an **AWS account** with Bedrock access
- ✅ **Prototyping Architects** will be available to help you
- ✅ Focus on **customer business outcomes**
- ⚠️ **CLEAN UP resources after each lab to avoid extra costs**

---

## 🆘 Support

For installation issues or technical questions:
1. Check the specific README files in each folder
2. Review AWS Bedrock documentation: https://docs.aws.amazon.com/bedrock/
3. Contact a Solution Architect or Prototyping Architect from the bootcamp

---

## 📚 Additional Resources

- [AWS Bedrock Documentation](https://docs.aws.amazon.com/bedrock/)
- [AWS GenAI Patterns](https://aws.amazon.com/bedrock/)
- [AgentCore Documentation](https://docs.aws.amazon.com/bedrock/latest/userguide/agents-rag.html)
- [AWS AI/ML Solutions](https://aws.amazon.com/ai/)
- [Generative AI with Large Language Models](https://www.coursera.org/learn/generative-ai-with-llms)

---

**Last Update**: February 2026
