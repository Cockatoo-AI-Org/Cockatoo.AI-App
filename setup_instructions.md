
# WSL Setup Instructions

## 1. Install WSL and Ubuntu
```bash
wsl --install
```

## 2. Connect to a WSL Instance in a New Window
```bash
wsl -d Ubuntu
```

# Ollama Installation and Model Setup

## 1. Download and Install Ollama
[Ollama Download](https://ollama.com/download)

## 2. Add a Model to Ollama
```bash
ollama pull llama2
```

# Monitoring GPU Performance

## 1. Watch GPU Performance in Linux
```bash
watch -n 0.5 nvidia-smi
```

# Docker Installation

## 1. Add Docker's Official GPG Key
```bash
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc
```

## 2. Add the Repository to Apt Sources
```bash
echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```

## 3. Install Docker
```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

# Running Open WebUI Docker Container

## 1. Run the Container
```bash
docker run -d --network=host -v open-webui:/app/backend/data -e OLLAMA_BASE_URL=http://127.0.0.1:11434 --name open-webui --restart always ghcr.io/open-webui/open-webui:main
```

# Stable Diffusion Installation

## 1. Install Prerequisites for Pyenv
```bash
sudo apt install -y make build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev xz-utils tk-dev libffi-dev liblzma-dev git
```

## 2. Install Pyenv
```bash
curl https://pyenv.run | bash
```

## 3. Install Python 3.10 Using Pyenv
```bash
pyenv install 3.10
pyenv global 3.10
```

# Extra: Stable Diffusion Installation

## 1. Download and Setup Stable Diffusion WebUI
```bash
wget -q https://raw.githubusercontent.com/AUTOMATIC1111/stable-diffusion-webui/master/webui.sh
chmod +x webui.sh
./webui.sh --listen --api
```
