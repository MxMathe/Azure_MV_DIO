**🗂️ Grupo de Recursos no Azure**

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
