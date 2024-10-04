Voici tout votre contenu dans une seule section, prêt à être utilisé sur votre page GitHub :

```md
# Setup WSL, Ollama, Docker, and Stable Diffusion

## Install WSL and Ubuntu
```bash
wsl --install
```

## Connect to a WSL Instance in a New Window
```bash
wsl -d Ubuntu
```

## Install Ollama
[Ollama Download](https://ollama.com/download)

### Add a Model to Ollama
```bash
ollama pull llama2
```

## "Watch" GPU Performance in Linux
```bash
watch -n 0.5 nvidia-smi
```

## Install Docker

### Add Docker's Official GPG Key:
```bash
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc
```

### Add the Repository to Apt Sources:
```bash
echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```

### Install Docker
```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

### Run Open WebUi Docker Container
```bash
docker run -d --network=host -v open-webui:/app/backend/data -e OLLAMA_BASE_URL=http://127.0.0.1:11434 --name open-webui --restart always ghcr.io/open-webui/open-webui:main
```

## Stable Diffusion Install

### Prerequisites: Pyenv
#### Install Pyenv Prerequisites
```bash
sudo apt install -y make build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev xz-utils tk-dev libffi-dev liblzma-dev git
```

#### Install Pyenv
```bash
curl https://pyenv.run | bash
```

#### Install Python 3.10
```bash
pyenv install 3.10
```

#### Make Python 3.10 Global
```bash
pyenv global 3.10
```

### Install Stable Diffusion
```bash
wget -q https://raw.githubusercontent.com/AUTOMATIC1111/stable-diffusion-webui/master/webui.sh
```

#### Make the Script Executable
```bash
chmod +x webui.sh
```

#### Run Stable Diffusion
```bash
./webui.sh --listen --api
```
```

Cela regroupe toutes les instructions dans une seule section pour une utilisation plus simple sur votre page GitHub.
