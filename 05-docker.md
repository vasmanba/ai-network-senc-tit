# 📋 Documentação Técnica de Servidor GNU/Linux
**Padrão de Auditoria e Gestão de Ativos — Docker-CE**
> Gerado automaticamente com base em coleta manual de informações do servidor.

---

## 1. 🖥️ Informações Gerais do Servidor

| Categoria | Descrição | Configuração |
|-----------|-----------|--------------|
| 🏷️ Geral | Nome do Servidor (Hostname) | `ctlinux01` |
| 🖴 Geral | Tipo de Máquina | Máquina Virtual (VM) |
| 🏭 Geral | Fabricante do Hardware | innotek GmbH |
| 📦 Geral | Modelo do Hardware | VirtualBox |
| 🔧 Geral | Plataforma de Virtualização | Oracle VirtualBox |
| 🐧 Geral | Sistema Operacional | Ubuntu 24.04.4 LTS (Noble Numbat) |
| 🔑 Geral | Versão do Kernel Linux | 6.8.0-106-generic |
| 🏗️ Geral | Arquitetura do Sistema | x86-64 (64 bits) |
| 🆔 Geral | ID da Máquina | `05c2865e767d44c4870777b482ba0652` |
| 🔄 Geral | ID do Boot Atual | `1212feaa63a54b48b491ebe52f0f0945` |
| ⏱️ Geral | Tempo Ativo (Uptime) | 33 minutos |
| 👤 Geral | Usuários Conectados | 2 |
| 🔒 Geral | Firmware | VirtualBox (versão: Dez/2006) |

> **💬 Para o Gestor:** Este servidor é uma máquina virtual rodando em VirtualBox. Ele utiliza o sistema operacional Ubuntu, versão estável de longa duração (LTS), que recebe suporte e atualizações de segurança até 2029. O servidor estava ativo há apenas 33 minutos no momento da coleta — o que indica uma reinicialização recente.

---

## 2. ⚙️ Informações de Hardware do Servidor

| Categoria | Descrição | Configuração |
|-----------|-----------|--------------|
| 🧠 Hardware | Memória RAM Total | 3.911 MB (~4 GB) |
| ✅ Hardware | Memória RAM em Uso | 529 MB |
| 💤 Hardware | Memória RAM Disponível | 3.382 MB |
| 🔃 Hardware | Memória Swap Total | 3.914 MB (~4 GB) |
| 💤 Hardware | Memória Swap em Uso | 0 MB (não utilizada) |
| 💽 Hardware | Disco Principal (sda) | 50 GB |
| 🗂️ Hardware | Partição de Boot (/boot) | 2 GB — uso: 198 MB (11%) |
| 🗂️ Hardware | Partição Principal (/) | 48 GB (LVM) — uso: 8,3 GB (19%) |
| 📀 Hardware | Dispositivo de Mídia (sr0) | 1024 MB (ROM) |
| 📊 Hardware | Espaço Livre na Partição Raiz | 37 GB (81% disponível) |
| 📊 Hardware | Espaço Livre na Partição Boot | 1,6 GB (89% disponível) |

> **💬 Para o Gestor:** O servidor possui 4 GB de memória RAM e está usando apenas 13% dela — há bastante folga. O armazenamento em disco ocupa cerca de 19% da capacidade total de 50 GB, com amplo espaço para crescimento. O servidor não está usando memória Swap, o que é um sinal positivo de desempenho.

---

## 3. 🌐 Informações de Rede do Servidor

| Categoria | Descrição | Configuração |
|-----------|-----------|--------------|
| 🌐 Rede | Status da Conexão | Online ✅ |
| 🔌 Rede | Interface Principal | `enp0s3` (Ethernet — Intel Corporation) |
| 🏠 Rede | Endereço IPv4 | `10.24.82.219/24` |
| 🔗 Rede | Endereço IPv6 (link) | `fe80::a00:27ff:fe85:2792/64` |
| 📡 Rede | MAC Address (enp0s3) | `08:00:27:85:27:92` |
| 🚪 Rede | Gateway Padrão (rota de saída) | `10.24.82.1` |
| 🔁 Rede | Interface de Loopback (lo) | `127.0.0.1/8` |
| 🐳 Rede | Interface Docker (docker0) | `172.17.0.1/16` |
| 📡 Rede | MAC Address (docker0) | `f6:a5:2e:2d:85:e1` |
| 🔗 Rede | Interface Virtual Docker (veth) | `veth793681f` — vinculada ao `docker0` |
| 🧭 Rede | Servidor DNS Primário | `8.8.8.8` (Google) |
| 🧭 Rede | Servidor DNS Secundário | `8.8.4.4` (Google) |
| 🔒 Rede | Modo resolv.conf | Stub (resolução local) |
| 🔐 Rede | DNSSEC | Não suportado |

> **💬 Para o Gestor:** O servidor está conectado à rede da organização com o endereço IP `10.24.82.219`. Ele utiliza os servidores de DNS do Google para resolver nomes de sites e serviços. Há também uma rede interna exclusiva para os Containers Docker (`172.17.0.0/16`), separada da rede principal — o que é uma boa prática de segurança e isolamento.

---

## 4. 🔧 Informações de Serviços e Processos

### 4.1 🟢 Serviços Ativos (em execução)

| Categoria | Serviço | Descrição |
|-----------|---------|-----------|
| ⚙️ Serviço | `containerd.service` | Motor de execução de Containers |
| ⚙️ Serviço | `docker.service` | Motor Docker — gerenciamento de Containers |
| 📦 Serviço | `portainer.service` | Interface Web para gerenciar Containers Docker |
| 🔐 Serviço | `ssh.service` | Acesso remoto seguro ao servidor (OpenSSH) |
| 📅 Serviço | `cron.service` | Agendador de tarefas automáticas |
| 💬 Serviço | `dbus.service` | Barramento de mensagens do sistema |
| 🛡️ Serviço | `polkit.service` | Gerenciador de autorizações do sistema |
| 📝 Serviço | `rsyslog.service` | Serviço de registro de logs do sistema |
| 🔄 Serviço | `systemd-networkd.service` | Configuração de rede |
| 🧭 Serviço | `systemd-resolved.service` | Resolução de nomes (DNS) |
| ⏰ Serviço | `systemd-timesyncd.service` | Sincronização de horário (NTP) |
| 🔌 Serviço | `systemd-udevd.service` | Gerenciador de dispositivos |
| 👤 Serviço | `systemd-logind.service` | Gerenciamento de login de usuários |
| 📖 Serviço | `systemd-journald.service` | Registro de logs do sistema (Journal) |
| 🖥️ Serviço | `getty@tty1.service` | Terminal local (console físico) |
| 📡 Serviço | `ModemManager.service` | Gerenciador de modems |
| 🔋 Serviço | `upower.service` | Gerenciamento de energia |
| 💾 Serviço | `udisks2.service` | Gerenciamento de discos |
| 🔗 Serviço | `multipathd.service` | Controlador de múltiplos caminhos de disco |
| 🔄 Serviço | `unattended-upgrades.service` | Atualizações automáticas de segurança |
| 🔧 Serviço | `fwupd.service` | Atualizações de Firmware |
| 👤 Serviço | `user@1000.service` | Sessão do usuário ativo (UID 1000) |

### 4.2 🔓 Portas Abertas e em Escuta

| Categoria | Porta | Protocolo | Descrição |
|-----------|-------|-----------|-----------|
| 🔌 Porta | `22` | TCP | SSH — Acesso Remoto Seguro |
| 🔌 Porta | `9000` | TCP | Portainer — Interface Web de Containers |
| 🔌 Porta | `53` | TCP/UDP | DNS — Resolução de Nomes (local) |

> **💬 Para o Gestor:** O servidor está rodando os serviços essenciais para gerenciar Containers Docker. O **Portainer** (porta 9000) é uma interface visual — acessível via navegador — que permite gerenciar os Containers sem precisar digitar comandos. O acesso remoto via **SSH** (porta 22) permite que a equipe de TI administre o servidor a distância com segurança. Todos os 22 serviços listados estão ativos e funcionando normalmente.

---

## 5. 🔄 Informações de Softwares e Atualizações Disponíveis

| Categoria | Pacote | Versão Disponível |
|-----------|--------|-------------------|
| 🐳 Atualização | `docker-ce` | 5:29.4.0 (de 5:29.2.1) |
| 🐳 Atualização | `docker-ce-cli` | 5:29.4.0 (de 5:29.2.1) |
| 🐳 Atualização | `docker-buildx-plugin` | 0.33.0 (de 0.31.1) |
| 🐳 Atualização | `docker-compose-plugin` | 5.1.1 (de 5.1.0) |
| 🐳 Atualização | `docker-ce-rootless-extras` | 5:29.4.0 |
| 📦 Atualização | `containerd.io` | 2.2.2 (de 2.2.1) |
| 🐧 Atualização | `linux-generic` (Kernel) | 6.8.0-107 (de 6.8.0-106) |
| 🐧 Atualização | `linux-image-generic` | 6.8.0-107 |
| 🐧 Atualização | `linux-headers-generic` | 6.8.0-107 |
| 🔐 Atualização | `openssl` | 3.0.13-0ubuntu3.9 |
| 🔐 Atualização | `libssl3t64` | 3.0.13-0ubuntu3.9 |
| 🔐 Atualização | `python3-openssl` | 23.2.0-1ubuntu0.1 |
| 🔐 Atualização | `python3-jwt` | 2.7.0-1ubuntu0.1 |
| 🔐 Atualização | `libarchive13t64` | 3.7.2-2ubuntu0.6 |
| 🔐 Atualização | `python3-pyasn1` | 0.4.8-4ubuntu0.2 |
| 🌐 Atualização | `bind9-dnsutils` | 1:9.18.39-0ubuntu0.24.04.3 |
| 🌐 Atualização | `bind9-host` | 1:9.18.39-0ubuntu0.24.04.3 |
| 🌐 Atualização | `bind9-libs` | 1:9.18.39-0ubuntu0.24.04.3 |
| ⚙️ Atualização | `systemd` | 255.4-1ubuntu8.15 |
| ⚙️ Atualização | `systemd-resolved` | 255.4-1ubuntu8.15 |
| ⚙️ Atualização | `systemd-timesyncd` | 255.4-1ubuntu8.15 |
| ⚙️ Atualização | `systemd-sysv` | 255.4-1ubuntu8.15 |
| ⚙️ Atualização | `libsystemd0` | 255.4-1ubuntu8.15 |
| ⚙️ Atualização | `libpam-systemd` | 255.4-1ubuntu8.15 |
| ⚙️ Atualização | `libnss-systemd` | 255.4-1ubuntu8.15 |
| ⚙️ Atualização | `netplan.io` | 1.1.2-8ubuntu1~24.04.2 |
| ⚙️ Atualização | `coreutils` | 9.4-3ubuntu6.2 |
| ⚙️ Atualização | `tzdata` | 2026a (de 2025b) |
| 🔧 Atualização | `binutils` | 2.42-4ubuntu2.10 |
| 🔧 Atualização | `fwupd` | 1.9.34 |
| 🔧 Atualização | `nftables` | 1.0.9-1ubuntu0.1 |
| 🔧 Atualização | `sosreport` | 4.10.2 |
| 🔧 Atualização | `lshw` | 02.19.git.2021.06.19.996aaad9c7-2ubuntu0.24.04.1 |

> **💬 Para o Gestor:** Existem **33 pacotes de software** aguardando atualização neste servidor, incluindo o próprio **Docker** (ferramenta de Containers) e o **Kernel** do sistema operacional. Algumas dessas atualizações são de **segurança crítica** — especialmente as relacionadas ao `openssl` (responsável por criptografar conexões) e ao `libssl`. Recomenda-se agendar uma janela de manutenção para aplicar essas atualizações, pois manter o sistema desatualizado aumenta o risco de vulnerabilidades e falhas.

---

*📅 Documentação gerada em: Abril/2026 | Servidor: `ctlinux01` | OS: Ubuntu 24.04.4 LTS*
