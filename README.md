Penulis: [Naufal](https://x.com/0xfal)

> [!NOTE]
> **WHAT IS Abstract?**\
> .

# Tutorial Abstract Testnet Node

## 1. Needs

### 1.1 Computer

You can use either VPS or your local PC with requirements:

| ✅ Linux | ✅ macOS | ✅ Windows (Native / WSL) |
| ------------- | ------------- | ------------- |

| Part | Minimum | Recommended |
| ------------- | ------------- | ------------- |
| CPU | TBD | TBD |
| RAM | TBD | TBD |
| SSD | TBD | TBD |

This tutorial was created using Linux (Ubuntu), for other operating systems it may be slightly different.

## 2. Dependencies

### 2.1 Install Docker Engine
```
# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```

```
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin docker-compose
```

## 3. Run Node

### 3.2 Setup Repository

```
git clone https://github.com/Abstract-Foundation/abstract-node
cd abstract-node/external-node
```

### 3.3 Running an Abstract Node Locally

```
docker-compose --file testnet-external-node.yml up -d
```

# Help

## How to check my node logs?

Change `<container name>` to `external-node-external-node-1`
```
docker logs -f --tail 100 <container name>
```
Alternatives `<container name>` : `external-node-prometheus-1` , `external-node-postgres-1` , `external-node-grafana-1`

## How to monitor my node status?

Local Grafana Dashboard : `http://<LOCALHOST or YOUR_VPS_IP>:3000/d/0/external-node`

Change the `<LOCALHOST or YOUR_VPS_IP>` as yours.

---

Reach us if you have more questions:\
ZuperHunt's [Discord server](https://discord.gg/ZuperHunt) | [X(Twitter)](https://twitter.com/ZuperHunt)

# Acknowledgements

* [Abstract Node](https://docs.abs.xyz/node/node_running)
