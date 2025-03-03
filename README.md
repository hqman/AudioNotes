# AudioNotes

## A Structured Note-Taking System for Audio and Video Based on FunASR and Qwen2

Quickly extracts content from audio and video files, and uses large language models to organize it into structured markdown notes for easy reading.

FunASR: https://github.com/modelscope/FunASR

Qwen2: https://ollama.com/library/qwen2

## Demonstration

### Audio/Video Recognition and Organization

![image](docs/1.jpg)

### Conversation with Audio/Video Content

![image](docs/2.jpg)

## Usage Instructions

### ① Install Ollama

Download and install the Ollama package for your system

https://ollama.com/download

### ② Pull the Model

Using `Alibaba's Qwen2 7b` as an example: https://ollama.com/library/qwen2

```bash
ollama pull qwen2:7b
```

### ③ Deploy the Service

There are two deployment methods: Docker deployment or local deployment

#### Docker Deployment (Recommended) 🐳

```bash
curl -fsSL https://github.com/harry0703/AudioNotes/raw/main/docker-compose.yml -o docker-compose.yml
docker-compose up
```
After Docker starts, visit http://localhost:15433/

> Login account is admin, password is admin (can be modified in the docker-compose.yml file)

#### Local Deployment 📦

Requires an accessible PostgreSQL database

```bash
conda create -n AudioNotes python=3.10 -y
conda activate AudioNotes
git clone https://github.com/harry0703/AudioNotes.git
cd AudioNotes
pip install -r requirements.txt
```

Rename `.env.example` to `.env` and modify the relevant configuration information

```bash
chainlit run main.py
```
After the service starts, visit http://localhost:8000/

> Login account is admin, password is admin (can be modified in the .env file)