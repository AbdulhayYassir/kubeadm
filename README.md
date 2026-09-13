# 🚀 Local Kubernetes Cluster Setup on Ubuntu VMs (kubeadm & containerd)

A comprehensive guide and automated workflow to build a production-grade, multi-node Kubernetes cluster locally using VirtualBox VMs, static networking, and Netplan, completely isolated from any external router requirements.

---

## 🛠️ Architecture Overview
* **Control Plane (`controlplane`):** Manages cluster state, API server, and orchestration.
* **Worker Nodes (`node01`, `node02`):** Run containerized application workloads.
* **Container Runtime:** `containerd` configured with `SystemdCgroup = true`.
* **Kubernetes Version:** `v1.32.13` (synchronized across all nodes).

---

## ⚙️ Automated Setup Script
Run the following script on **all** nodes (Master and Worker nodes) to configure the kernel modules, system parameters, container runtime, and Kubernetes components (`kubeadm`, `kubelet`, `kubectl` v1.32):

```bash
#!/bin/bash
set -e

echo "[1/4] Loading required kernel modules..."
sudo tee /etc/modules-load.d/k8s.conf <<EOF "="==" "[2/4] "[3/4] "[4/4] ## 'deb 's/SystemdCgroup="false/SystemdCgroup" (`node01`, (v1.32)..." **On --- --dearmor --print-join-command --system -fsSL -i -o -p -y /' /etc/apt/keyrings /etc/apt/keyrings/kubernetes-apt-keyring.gpg /etc/apt/sources.list.d/kubernetes.list /etc/containerd /etc/containerd/config.toml /etc/sysctl.d/k8s.conf 1. 2. <<EOF <MASTER_IP Cluster Configuring Containerd..." EOF Installing Joining Kubernetes Kubernetes..." Master Node Node**, Nodes Worker [signed-by="/etc/apt/keyrings/kubernetes-apt-keyring.gpg]" ``` ```bash `node02`)**, `sudo`: and apt-get apt-mark apt-transport-https br_netfilter ca-certificates cluster command command: components config configuring containerd create curl default each echo enable execute for generate gpg hold [https://pkgs.k8s.io/core:/stable:/v1.32/deb/](https://pkgs.k8s.io/core:/stable:/v1.32/deb/) [https://pkgs.k8s.io/core:/stable:/v1.32/deb/Release.key](https://pkgs.k8s.io/core:/stable:/v1.32/deb/Release.key) install join join!="=="" kubeadm kubectl kubelet mkdir modprobe net.bridge.bridge-nf-call-ip6tables="1" net.bridge.bridge-nf-call-iptables="1" net.ipv4.ip_forward="1" net.netfilter.nf_conntrack_max="131072" output overlay parameters provisioned ready restart sed successfully sudo sysctl systemctl tee the to token true/g' update with | 🔗>:6443 --token <token> --discovery-token-ca-cert-hash sha256:<hash>
