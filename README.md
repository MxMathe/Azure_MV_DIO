**Grupo de Recursos no Azure**

Criação e Utilização:

Selecionar o tipo de assinatura, nome e região

Criado na hora de provisionar qualquer serviço.

Sempre pertence a uma região (location), o que impacta na latência e na disponibilidade.

Permite organizar projetos, ambientes (teste, produção) ou aplicações inteiras.

Facilita o gerenciamento, monitoramento, automação e até exclusão de todos os recursos juntos.

🔐 IAM (Controle de Acesso)

O IAM (Identity and Access Management) controla quem pode acessar o grupo e o que pode fazer.

Funciona com base em RBAC (Controle de Acesso Baseado em Função).

Permite atribuir funções como:

Leitor: só visualiza.

Colaborador: pode gerenciar recursos, mas não gerenciar permissões.

Proprietário: controle total, inclusive de permissões.

Também suporta grupos, usuários e identidades gerenciadas.

🔍 Visualizador de Recursos

Ferramenta que permite visualizar, de forma hierárquica e detalhada, como todos os recursos estão relacionados dentro do grupo.

Útil para entender dependências, topologias e estrutura dos recursos.

🔔 Eventos (Logs e Monitoramento)

Permite acompanhar tudo que ocorre no grupo de recursos, como:

Criação, modificação e exclusão de recursos.

Falhas, alertas e atividades administrativas.

É integrado ao Azure Monitor, Activity Log e pode gerar alertas automáticos.

🛠️ Demais Opções no Grupo de Recursos:

Tags: Marcação de recursos para organização e custos.

Locks (Bloqueios): Impede deleção ou alterações acidentais (CanNotDelete e ReadOnly).

Políticas (Azure Policy): Define regras e compliance, como restrição de regiões ou tipos de máquinas.

Custos: Acompanhar custos e orçamentos do grupo específico.

Exportação de Template (ARM): Exporta a infraestrutura como código para reuso ou automação.

**Rede Virtual (VNet)**

A Rede Virtual (VNet) é como uma rede local, mas dentro do Azure.

Permite interconectar recursos como VMs, bancos e aplicações.

Dá controle sobre sub-redes, endereços IP, tabelas de rotas e firewalls.

Pode ser conectada a redes locais via VPN ou ExpressRoute.

✔️ Criação e Ligação ao Grupo de Recursos:

Selecionar projeto, nome da rede e região. Opcionais: Configurações de segurança, ip, rotulos.

A VNet é criada dentro de um Grupo de Recursos, vinculada a uma região.

Ao criar, você define:

Espaço de endereçamento (CIDR).

Sub-redes internas.

Regras de segurança (NSG).

Todos os recursos que precisam se comunicar na mesma rede devem estar dentro dessa VNet (ou interconectados por outras VNets).





**Criação de Máquina Virtual no Azure**

🔹 Aba: Básico

Assinatura: Seleciona sua conta de cobrança.

Grupo de Recursos: Onde a VM será criada (pode criar um novo ou usar existente).

Nome da VM: Identificação da sua VM.

Região: Local físico (impacta na latência e disponibilidade).

Disponibilidade:

Nenhuma (simples)

Zona de disponibilidade (alta disponibilidade física)

Conjunto de disponibilidade (resistência a falhas)

Imagem: Escolhe o sistema operacional (Windows, Ubuntu, Red Hat, etc.).

Tipo de Azure Spot: (Opcional) Usa máquinas sobras do Azure com desconto, mas podem ser interrompidas.

Tamanho: Define CPU, memória e preço (ex.: B2s, D2s, etc.).

Usuário de administrador: Nome e senha ou chave SSH (Linux).

Portas públicas: Define se abre RDP (Windows) ou SSH (Linux) para acesso externo.

Licenciamento: Se já possui licença local (para Windows, pode reduzir custo).

🔹 Aba: Discos

Tipo de disco do SO:

SSD Premium (mais rápido e caro)

SSD padrão (equilíbrio)

HDD (mais barato e mais lento)

Disco temporário: Automático.

Discos adicionais: Pode adicionar depois.

🔹 Aba: Rede

Rede Virtual: Escolhe uma existente ou cria uma nova.

Sub-rede: Divide a rede virtual em blocos.

IP público: Se deseja acesso externo.

Grupo de segurança de rede (NSG):

Básico: Abre portas específicas (ex.: RDP, SSH).

Avançado: Permite criar regras personalizadas.

Regras de entrada: Permite acesso via portas específicas.

🔹 Aba: Gerenciamento

Monitoramento:

Ativar ou não o Azure Monitor e Logs.

Backup: Pode habilitar backup automático.

Identidade: Permite ativar identidade gerenciada para acesso a outros recursos do Azure sem senhas.

Auto desligamento: Configura para desligar automaticamente em certo horário (economia).

🔹 Aba: Avançado (opcional)

Script de inicialização: Rodar comandos na primeira inicialização.

Extensões: Instalar agentes, antivírus, diagnóstico, etc.

🔹 Aba: Tags

Adiciona chaves/valores para organizar recursos (ex.: ambiente=produção).

🔹 Aba: Revisar + Criar

O Azure faz uma validação de todas as opções.

Exibe o custo estimado por hora.

Clique em Criar para provisionar a máquina.

*Criação com Predefinição e Soluções Relacionadas*

➡️ Muito mais rápida.

Você escolhe uma imagem pronta com configurações otimizadas, como:

Máquinas para desenvolvimento (com Visual Studio já instalado).

Servidores web (IIS, Apache, NGINX prontos).

Soluções de bancos de dados, SAP, servidores de jogo, etc.

O assistente já pré-preenche grande parte das opções (tamanho, SO, discos, rede) baseado na solução escolhida.

Você basicamente define grupo de recursos, credenciais e localização, e prossegue para criar.

**Pool de Hosts (Hosts Dedicados)**

Um Pool de Hosts permite que tenha um servidor físico dedicado no datacenter da Microsoft, onde se pode criar VMs isoladas de clientes externos.

✔️ Benefícios:

Compliance mais rigoroso.

Isolamento físico.

Controle de licenciamento de software.

✅ Processo:

Criar o Pool de Hosts, definindo:

Região.

Tipo de hardware.

Grupo de recursos.

Depois, ao criar uma VM, você escolhe o host dedicado em vez da infraestrutura compartilhada.

**Aplicativos de Função (Azure Functions)**

Serviço serverless que executa códigos sob demanda, sem se preocupar com servidores.

Funciona com eventos: quando algo acontece (ex.: novo arquivo, chamada HTTP, cron), ele executa uma função.

✔️ Na criação:
Grupo de Recursos: Selecionar ou criar.

Nome: Nome único global.

Região: Onde ficará hospedado.

Plano de Hospedagem:

Plano de Consumo: Paga só pelo uso.

Plano Premium/Dedicado: Escalabilidade maior.

Stack: Linguagem (C#, Python, JavaScript, etc.).

Armazenamento: Cria uma conta de armazenamento vinculada para logs e arquivos temporários.
