# n8n Guide

```bash
docker compose up -y
```

# Cloudflare Tunnels:
```bash
docker run -d --network host cloudflare/cloudflared:latest tunnel --no-autoupdate run --token <TOKEN>
```

It's recommended that you use a Linux server or WSL2


# Installing Docker:

## Step 1: Update Packages and Install Prerequisites
```bash
sudo apt update
sudo apt install -y ca-certificates curl
```


## Step 2: Add Docker's Official GPG Key
```bash
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc
```


## Step 3: Add the Docker Repository to APT Sources
```bash
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

## Step 4: Install Docker Engine
```bash
sudo apt update
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```


## Step 5: Verify the Installation
```bash
sudo docker run hello-world
```

## Optional: Run Docker Without Sudo
```bash
sudo usermod -aG docker $USER

# Note: you need to re-login
```

