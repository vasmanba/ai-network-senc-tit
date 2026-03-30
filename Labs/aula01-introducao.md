1) Importar a imagem .ova

📁 Arquivo: Downloads\UbuntuServer-OnPremises.ova

▶️ Abra o VirtualBox<br>
📂 Clique em Arquivo → Importar Appliance<br>
📍 Clique em Selecionar arquivo<br>
📁 Vá até Downloads e escolha:<br>
UbuntuServer-OnPremises.ova<br>
▶️ Clique em Avançar<br>
⚙️ (Opcional) Revise:<br>
    Nome da VM<br>
    CPU / RAM (não altere se não tiver instrução)<br>
✅ Clique em Importar<br>

⏳ Aguarde o processo terminar.

🌐 2) Configurar rede em modo Bridge (Ponte)
🖥️ No VirtualBox, selecione a VM importada
⚙️ Clique em Configurações
🌐 Vá na aba Rede
🔌 Em Adaptador 1:
✔️ Marcar: Habilitar Placa de Rede
🔄 Conectado a: → Placa em modo Bridge
📡 Nome (adaptador):
Escolha a placa Ethernet (cabeada) do laboratório
(ex: Intel Ethernet, Realtek PCIe, etc.)
⚠️ Importante:
NÃO selecionar Wi-Fi
Deve ser a rede física cabeada da máquina
✅ Clique em OK
🚀 3) Iniciar a máquina virtual
▶️ Selecione a VM
▶️ Clique em Iniciar

⏳ Aguarde o boot do sistema.

🔎 4) Identificar o IP da VM

Após login no Ubuntu Server:

🔐 Faça login com usuário/senha fornecidos pelo professor
⌨️ Execute:
ip a
🔍 Procure algo como:
inet 192.168.x.x

👉 Esse é o IP da VM na rede do laboratório.

🔐 5) Testar acesso SSH

No Windows 11 (host):

💻 Abra o Prompt de Comando ou PowerShell
⌨️ Execute:
ssh usuario@IP_DA_VM

📌 Exemplo:

ssh aluno@192.168.0.25
🔑 Confirme:
Digite yes na primeira conexão
Informe a senha
🧪 6) Validação rápida

Se tudo estiver correto:

✅ VM recebe IP da mesma rede do laboratório
✅ Ping funciona:
ping 192.168.x.x
✅ SSH conecta normalmente
⚠️ Problemas comuns (diagnóstico rápido)

🔸 Sem IP (ou 169.254.x.x):

Bridge configurada na placa errada
Cabo de rede desconectado

🔸 SSH não conecta:

Verificar serviço:
sudo systemctl status ssh
Se necessário:
sudo systemctl start ssh

🔸 Rede não aparece:

Testar outro adaptador na configuração Bridge
✔️ Resultado esperado
VM importada corretamente
Rede em Bridge ativa via Ethernet
IP válido na rede local
Acesso remoto via SSH funcional

---

🧩 1) Importar a imagem .ova

📁 Arquivo: Downloads\UbuntuServer-Container.ova

▶️ Abra o VirtualBox
📂 Arquivo → Importar Appliance
📍 Selecionar arquivo → escolha UbuntuServer-Container.ova
▶️ Avançar
⚙️ Revisar (não alterar ainda)
✅ Importar

⏳ Aguarde finalizar.

⚙️ 2) Ajuste inicial de hardware (após importar)

Com 32 GB RAM + i7-14700K, há margem para otimização.

🖥️ Selecione a VM → Configurações
🧠 Sistema → Processador
🔢 CPUs: 4 a 6
⚠️ Não ultrapassar 50% dos núcleos lógicos
🧠 Sistema → Placa-mãe
🧮 RAM: 8192 MB (8 GB)
(pode subir para 12 GB se usar containers pesados)
⚡ Sistema → Aceleração
✔️ VT-x/AMD-V: habilitado
✔️ Paginação aninhada: habilitado
💾 Armazenamento
Tipo: já definido pela OVA
✔️ Marcar “Usar cache de I/O do host”
🖥️ Vídeo
VRAM: 16–32 MB (server não precisa mais)

✅ Clique OK

🌐 3) Configurar rede Bridge (Ponte)
⚙️ Configurações → Rede
🔌 Adaptador 1:
✔️ Habilitar placa de rede
🔄 Conectado a: Placa em modo Bridge
📡 Nome:
Selecionar placa Ethernet (cabeada)
Ex: Intel Ethernet / Realtek PCIe

⚠️ Regras críticas:

❌ Não usar Wi-Fi
✔️ Deve ser rede física do laboratório
✅ OK
🚀 4) Iniciar a VM
▶️ Selecionar VM
▶️ Iniciar

⏳ Aguarde o boot.

🔎 5) Obter IP da máquina

Login no Ubuntu:

ip a

🔍 Identifique:

inet 192.168.x.x

👉 Esse IP vem do DHCP da rede do laboratório (Bridge)

🔐 6) Acesso remoto via SSH

No host (Windows):

ssh usuario@IP_DA_VM

📌 Exemplo:

ssh aluno@192.168.0.50
🧪 7) Validação rápida

✔️ Testar conectividade:

ping 192.168.x.x

✔️ Testar SSH:

Conecta sem erro
Solicita senha
🚀 8) Otimizações de desempenho (recomendado)
🔧 Dentro do Ubuntu Server
Atualizar sistema
sudo apt update && sudo apt upgrade -y
🔌 Verificar serviços ativos
systemctl list-units --type=service --state=running

Desativar serviços desnecessários:

sudo systemctl disable nome_servico
🐳 Se for usar containers (Docker)
Limitar uso de recursos

Exemplo:

docker run -d --cpus="2" --memory="2g" nginx
⚡ Ajustes de kernel (rede e I/O)

Editar:

sudo nano /etc/sysctl.conf

Adicionar:

net.core.somaxconn = 1024
net.ipv4.tcp_tw_reuse = 1

Aplicar:

sudo sysctl -p
💾 Ajuste de swap (melhora desempenho)
sudo nano /etc/sysctl.conf

Adicionar:

vm.swappiness=10

Aplicar:

sudo sysctl -p
📊 Monitoramento

Instalar ferramentas:

sudo apt install htop iotop -y

Uso:

htop
⚠️ Troubleshooting (rápido)

🔸 Sem IP

Bridge na placa errada
Cabo desconectado

🔸 SSH falha

sudo systemctl status ssh
sudo systemctl start ssh

🔸 Desempenho ruim

Reduz CPUs ou RAM (overcommit)
Verificar uso com htop
✔️ Resultado final esperado
VM importada corretamente
Recursos otimizados (CPU/RAM ajustados)
Rede em Bridge via Ethernet funcional
IP válido da rede local
Acesso SSH operacional
Ambiente pronto para práticas de IA e containers

---

🖥️ Sugestão de IP para Servidores Ubuntu Server

Critério técnico adotado:

Evitar conflito com DHCP (normalmente começa em faixas mais baixas ou médias)
Utilizar faixa alta para servidores (padrão comum em redes corporativas)
| 🖥️ Servidor        | 🌐 Endereço IP   | 🎭 Máscara        | 🚪 Gateway     | 🔎 DNS          |
|---------------------|-----------------|------------------|----------------|-----------------|
| 🗄️ Server 01        | 10.24.82.100    | 255.255.255.0    | 10.24.82.1     | 10.24.40.190    |
| 🗄️ Server 02        | 10.24.82.101    | 255.255.255.0    | 10.24.82.1     | 10.24.40.190    |

---

