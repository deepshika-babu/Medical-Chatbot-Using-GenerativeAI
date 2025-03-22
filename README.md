# Medical-Chatbot-Using-Generative-AI
This application leverages the power of artificial intelligence to provide users with general health-related information and assistance. ***It is not a substitute for professional medical advice, diagnosis, or treatment.***

# Tech Stack
The project is built using the following technologies:
- **Python:** The primary programming language for the backend logic.
- **LangChain:** Used for managing the conversational flow and chaining various AI tasks.
- **Flask:** Provides the web framework to create and run the chatbot as a web application.
- **GPT (Generative Pre-trained Transformer):** The underlying language model for natural language understanding and generation.
- **Pinecone:** Facilitates vector database management for semantic search and information retrieval.

# Features
- **User-friendly interface:** Simple and intuitive chat interface for users.
- **Health-related queries:** Offers general health information based on user questions.
- **Semantic search:** Powered by Pinecone for efficient and relevant information retrieval.
- **Conversational AI:** Natural and context-aware responses enabled by GPT and LangChain.


# How to run?

Clone the repository

```bash
https://github.com/deepshika-babu/Medical-Chatbot-Using-GenerativeAI.git
```
### STEP 01- Create a conda environment after opening the repository

```bash
conda create -n medibot python=3.10 -y
```

```bash
conda activate medibot
```


### STEP 02- install the requirements
```bash
pip install -r requirements.txt
```


### Create a `.env` file in the root directory and add your Pinecone & openai credentials as follows:

```ini
PINECONE_API_KEY = "xxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
OPENAI_API_KEY = "xxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
```


```bash
# run the following command to store embeddings to pinecone
python store_index.py
```
Finally, run the Flask app
```bash
python app.py
```

Now,

    Open your browser and navigate to http://127.0.0.1:8080 to interact with the chatbot.


### Techstack Used:

- Python
- LangChain
- Flask
- GPT
- Pinecone


# AWS-CICD-Deployment-with-Github-Actions

### 1. Login to AWS console.
### 2. Create IAM user for deployment

	With specific access

	1. EC2 access : It is virtual machine

	2. ECR: Elastic Container registry to save your docker image in aws


	#Description: About the deployment

	1. Build docker image of the source code

	2. Push your docker image to ECR

	3. Launch Your EC2 

	4. Pull Your image from ECR in EC2

	5. Lauch your docker image in EC2

	#Policy:

	1. AmazonEC2ContainerRegistryFullAccess

	2. AmazonEC2FullAccess

	
### 3. Create ECR repo to store/save docker image
    Save the URI: Example-"970547337635.dkr.ecr.ap-south-1.amazonaws.com/medicalchatbot"

	
### 4. Create EC2 machine (Ubuntu) 

### 5. Open EC2 and Install docker in EC2 Machine:
Execute the following commands after connecting to AWS CLI
	
	#optional

	sudo apt-get update -y

	sudo apt-get upgrade
	
	#required

	curl -fsSL https://get.docker.com -o get-docker.sh

	sudo sh get-docker.sh

	sudo usermod -aG docker ubuntu

	newgrp docker
	
### 6. Configure EC2 as self-hosted runner:
Open Github

    Go to Setting > Actions > Runner > New Self hosted runner > Choose os > then run commands shown one by one in the AWS CLI


### 7. Add Setup github secrets for the following keys:

   - AWS_ACCESS_KEY_ID
   - AWS_SECRET_ACCESS_KEY
   - AWS_DEFAULT_REGION
   - ECR_REPO
   - PINECONE_API_KEY
   - OPENAI_API_KEY