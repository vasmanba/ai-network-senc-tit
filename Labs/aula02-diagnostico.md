## 📄 Documentação do Servidor (Ubuntu)

| Categoria            | Informação                     |
|---------------------|-------------------------------|
| 🖥️ Hostname        | wslinux01                     |
| 💻 Tipo             | Máquina Virtual (VM)          |
| 🧩 Virtualização    | Oracle VirtualBox             |
| 🏷️ Sistema Operacional | Ubuntu 24.04.4 LTS        |
| ⚙️ Kernel          | Linux 6.8.0-106-generic      |
| 🧱 Arquitetura      | x86_64 (64 bits)             |
| 🏭 Fabricante       | innotek GmbH                 |
| 🖲️ Modelo          | VirtualBox                   |
| ⏱️ Data/Hora (UTC) | Mon Mar 30 21:45:57 UTC 2026 |


🖥️ Sistema
hostnamectl
lsb_release -a
uptime
whoami
⚙️ Hardware / VM
lscpu
lsmem
lsblk
df -h
free -h
sudo lshw -short
🌐 Rede
ip a
ip r
ss -tuln
hostname -I
📦 Software / Pacotes
dpkg -l
snap list
🔧 Serviços
systemctl list-units --type=service --state=running
systemctl list-unit-files --type=service
🔐 Segurança
sudo ufw status
last
who
💾 Armazenamento detalhado
lsblk -f
mount | column -t
📊 Processos / desempenho
top
htop   # (se instalado)
ps aux --sort=-%mem | head
🧾 Logs importantes
journalctl -xe
dmesg | tail
💡 Dica profissional (automatizar inventário)

Você pode gerar um relatório único:

(
echo "### SISTEMA"; hostnamectl; lsb_release -a;
echo "### HARDWARE"; lscpu; free -h; lsblk;
echo "### REDE"; ip a; ss -tuln;
echo "### SERVIÇOS"; systemctl list-units --type=service --state=running;
) > inventario.txtex