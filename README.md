# AWS Bedrock Workshop - Agentic AI Bootcamp

## 📌 À propos du bootcamp

The bootcamp is a hands-on enablement program by our AWS Solutions Architects and Prototyping Architects, where the customer Agentic AI use case gets accelerated through a charge-free co-development and technical knowledge transfer in an on-site, multi-customer classroom setting.

---

## 📅 Plan de travail

### **Day 1** - Foundations & GenAI Essentials

| Sujet | Contenu |
|-------|---------|
| **Welcome** | Welcome from Thierry Pierre, leader of AWS AI/ML FR specialist team |
| **GenAI models** | • AWS GenAI offering<br>• Models available in Bedrock<br>• Model selection criteria<br>• Model evaluation |
| **GenAI patterns** | • Prompt engineering<br>• Multimodality<br>• RAG |
| **GenAI services** | • Bedrock Data Automation<br>• Amazon Quick Suite |

### **Day 2** - Agentic AI Architecture & Orchestration

| Sujet | Contenu |
|-------|---------|
| **Architecting Agentic AI Systems** | • Components of Agentic AI systems<br>• MCP |
| **AI Agent Orchestration** | • Strands Agents<br>• State and sessions<br>• Multi-agents solutions<br>• Model Evaluation and how to approach agents' evaluation and observability |
| **Agentic AI Security** | • Security considerations for GenAI Agentic systems |

### **Day 3** - Bedrock AgentCore Deep Dive & Wrap-up

| Sujet | Contenu |
|-------|---------|
| **Bedrock AgentCore** | • Bedrock AgentCore deep dive<br>• Agents Evaluation and Observability |
| **AI coding tools and best practices** | • Kiro and Spec Driven Development |
| **What Next?** | • What to anticipate over the next two weeks<br>• Meet your PA<br>• Ensure account set up<br>• Work on Customer Business Outcomes |

---

## 🚀 Démarrage rapide

### Prérequis
- Python 3.9 ou supérieur
- pip (gestionnaire de paquets Python)
- Git

### 1️⃣ Créer un environnement virtuel

#### Sur macOS/Linux
```bash
# Créer l'environnement virtuel
python3 -m venv venv

# Activer l'environnement virtuel
source venv/bin/activate
```

#### Sur Windows
```bash
# Créer l'environnement virtuel
python -m venv venv

# Activer l'environnement virtuel
venv\Scripts\activate
```

### 2️⃣ Installer les dépendances

Une fois l'environnement virtuel activé, installez les requirements :

```bash
# Installer les packages principaux
pip install -r requirements.txt

# Si vous travaillez sur les labs AgentCore
cd agentcore
pip install -r requirements-agent.txt
cd ..
```

### 3️⃣ Vérifier l'installation

```bash
# Vérifier que tout est installé correctement
pip list
```

### 4️⃣ Configuration AWS

Avant de commencer, assurez-vous que vos credentials AWS sont configurées. Vous pouvez utiliser l'une des deux méthodes suivantes :

#### Option 1 : Avec `aws configure` (standard)

```bash
aws configure
```

Vous aurez besoin de :
- AWS Access Key ID
- AWS Secret Access Key
- Default region (ex: us-east-1)
- Default output format (json)

#### Option 2 : Avec `aws-vault` (recommandé pour la sécurité)

[aws-vault](https://github.com/99designs/aws-vault) est un outil sécurisé pour gérer vos credentials AWS. Il stocke vos credentials dans le trousseau sécurisé de votre système.

**Installation** :
```bash
# macOS (avec Homebrew)
brew install aws-vault

# Linux
curl https://github.com/99designs/aws-vault/releases/download/v7.2.0/aws-vault-linux-amd64 -o aws-vault
chmod +x aws-vault
sudo mv aws-vault /usr/local/bin

# Windows
choco install aws-vault
```

**Configuration** :
```bash
# Ajouter vos credentials
aws-vault add default

# Vérifier la configuration
aws-vault list
```

**Utilisation** :
```bash
# Exécuter une commande AWS de manière sécurisée
aws-vault exec default -- aws s3 ls

# Ou lancer Jupyter avec les credentials
aws-vault exec default -- jupyter notebook
```

---

## 📂 Structure du projet

```
aws-bedrock-workshop/
├── agentcore/                          # Labs AgentCore (1-7)
│   ├── lab-01-create-an-agent.ipynb
│   ├── lab-02-agentcore-memory.ipynb
│   ├── lab-03-agentcore-gateway.ipynb
│   ├── lab-04-agentcore-runtime.ipynb
│   ├── lab-05-agentcore-evals.ipynb
│   ├── lab-06-frontend.ipynb
│   ├── lab-07-agentcore-policy.ipynb
│   ├── lab_helpers/                    # Utilitaires pour les labs
│   ├── prerequisite/                   # Infrastructure CloudFormation
│   └── scripts/                        # Scripts d'aide
│
├── architecture_patterns/              # Patterns d'architecture GenAI
│   └── 01_text_and_code_generation_w_bedrock.ipynb
│
├── bedrock_data_automation/            # Automation avec Bedrock
│   ├── 01_standard_output_basic_to_advanced.ipynb
│   └── 02_custom_outputs_and_blueprints.ipynb
│
├── guardrails/                         # Sécurité des chatbots
│   └── 01-secure_chatbots.ipynb
│
├── image_and_multimodal/               # Traitement d'images et multimodal
│   ├── 01_nova-canvas-notebook.ipynb
│   ├── 02_nova-reel-notebook.ipynb
│   └── 03_bedrock-titan-multimodal-embeddings.ipynb
│
├── knowledgebases_and_rag/             # Knowledge Bases et RAG
│   ├── 01_create_ingest_documents_test_kb.ipynb
│   └── 02_managed-rag-kb-retrieve-generate-api.ipynb
│
├── speech_to_speech/                   # Text-to-Speech et Speech-to-Text
│   ├── 00_introduction_nova_sonic_console.ipynb
│   ├── 01_core_functionality.ipynb
│   ├── 02_repeatable_patterns.ipynb
│   ├── python-server/
│   └── react-client/
│
├── cleanup/                            # Scripts de nettoyage
│   └── 01_cleanup.ipynb
│
├── requirements.txt                    # Dépendances principales
└── README.md                           # Ce fichier
```

---

## 📖 Commencer les labs

### Démarrer Jupyter Notebook

```bash
# Lancer Jupyter Notebook
jupyter notebook

# Ou lancer Jupyter Lab (plus moderne)
jupyter lab
```

Naviguez ensuite vers le dossier `agentcore/` pour commencer les labs :
- **Lab 1**: Create an Agent
- **Lab 2**: AgentCore Memory
- **Lab 3**: AgentCore Gateway
- **Lab 4**: AgentCore Runtime
- **Lab 5**: AgentCore Evals
- **Lab 6**: Frontend
- **Lab 7**: AgentCore Policy

---

## 🔧 Commandes utiles

```bash
# Désactiver l'environnement virtuel
deactivate

# Mettre à jour pip
pip install --upgrade pip

# Réinstaller les dépendances (si problème)
pip install --force-reinstall -r requirements.txt

# Voir tous les packages installés
pip list

# Créer un fichier des dépendances actuelles
pip freeze > requirements.txt
```

---

## ⚠️ IMPORTANT : Gestion des ressources AWS et des coûts

Ce bootcamp créera des ressources AWS dans votre compte, notamment :
- Infrastructure CloudFormation (stacks)
- Services Bedrock (Agents, Knowledge Bases, etc.)
- Stockage S3
- Tables DynamoDB
- Endpoints SageMaker
- Et autres ressources cloud

### 🔴 CRITICAL : Nettoyage après le bootcamp

**Ces ressources engendrent des coûts !** Vous devez les supprimer après les labs pour éviter des charges inutiles.

```bash
# Utilisez le script de cleanup inclus
cd cleanup
jupyter notebook 01_cleanup.ipynb

# Ou exécutez le script de nettoyage
python cleanup_tagged_resources.py
```

**Checklist de nettoyage** :
- ✅ Arrêtez tous les notebooks Jupyter
- ✅ Exécutez les scripts de cleanup fournis
- ✅ Supprimez les stacks CloudFormation manuellement si nécessaire
- ✅ Vérifiez dans la console AWS que toutes les ressources ont été supprimées
- ✅ Consultez la section `cleanup/` pour plus de détails

**Estimation des coûts** : Les coûts varient selon l'utilisation mais peuvent être importants pour certains services. Soyez vigilant !

---

## 📝 Notes importantes

- ✅ Ce bootcamp est une **expérience pratique** - soyez prêts à coder !
- ✅ Les labs sont **progressifs** - commencez par le Lab 1
- ✅ Vous aurez besoin d'un **compte AWS** avec accès à Bedrock
- ✅ Des **Prototyping Architects** seront disponibles pour vous aider
- ✅ Focus sur les **business outcomes** des clients
- ⚠️ **NETTOYEZ les ressources après chaque lab pour éviter des coûts supplémentaires**

---

## 🆘 Support

Pour des problèmes d'installation ou des questions techniques :
1. Consultez les README spécifiques dans chaque dossier
2. Vérifiez la documentation AWS Bedrock : https://docs.aws.amazon.com/bedrock/
3. Contactez un Solution Architect ou Prototyping Architect du bootcamp

---

## 📚 Ressources supplémentaires

- [AWS Bedrock Documentation](https://docs.aws.amazon.com/bedrock/)
- [AWS GenAI Patterns](https://aws.amazon.com/bedrock/)
- [AgentCore Documentation](https://docs.aws.amazon.com/bedrock/latest/userguide/agents-rag.html)
- [AWS AI/ML Solutions](https://aws.amazon.com/ai/)

---

**Dernière mise à jour**: Février 2026
