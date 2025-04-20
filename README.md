# Desafio-uso-do-Azure

Criar uma máquina virtual do Windows no Portal do Azure
Artigo
30/01/2025
27 colaboradores
Neste artigo
Entrar no Azure
Criar máquina virtual
Conectar-se à máquina virtual
Instalar servidor Web
Mostrar mais 3
Aplica-se a: ✔️ VMs do Windows

As máquinas virtuais (VM) do Azure podem ser criadas por meio do Portal do Azure. Esse método fornece uma interface de usuário baseada em navegador para criar as VMS seus recursos relacionados. Esse início rápido mostra como usar o portal do Azure para implantar uma máquina virtual (VM) no Azure que executa o Windows Server 2022 Datacenter. Para ver a VM em ação, você habilita o protocolo RDP na VM e instala o servidor Web do IIS.

Se você não tiver uma assinatura do Azure, crie uma conta gratuita antes de começar.

 Importante

As etapas descritas nesse início rápido se destinam exclusivamente à educação e não têm como objetivo as implantações em um ambiente de produção.

Entrar no Azure
Entre no portal do Azure.

Criar máquina virtual
Digite máquinas virtuais na pesquisa.

Em Serviços, selecione Máquinas virtuais.

Na página Máquinas virtuais, clique em Criar e selecione Máquina virtual do Azure. A página Criar uma máquina virtual é aberta.

Em Detalhes da instância, insira myVM no Nome da máquina virtual e escolha Windows Server 2022 Datacenter: Azure Edition - x64 Gen 2 na Imagem. Deixe os outros padrões.

Captura de tela da seção Detalhes da instância, onde você fornece um nome para a máquina virtual e seleciona a região, a imagem e o tamanho dela.

 Observação

Alguns usuários agora verão a opção de criar VMs em várias zonas. Para saber mais sobre essa nova capacidade, confira Criar máquinas virtuais em uma zona de disponibilidade. Captura de tela mostrando que existe a opção de criar máquinas virtuais em várias zonas de disponibilidade.

Em Conta de administrador, forneça um nome de usuário, como azureuser e uma senha. A senha deve ter no mínimo 12 caracteres e atender a requisitos de complexidade definidos.

Captura de tela da seção Conta de administrador, onde você fornece o nome de usuário e a senha do administrador.

Em Regras de porta de entrada, escolha Permitir portas selecionadas e, em seguida, selecione RDP (3389) e HTTP (80) na lista suspensa.

Captura de tela da seção de regras de porta de entrada, na qual você seleciona as portas nas quais as conexões de entrada são permitidas

Deixe os padrões restantes e, em seguida, selecione o botão Examinar + criar na parte inferior da página.

Captura de tela mostrando o botão Examinar + criar na parte inferior da página.

Após a execução da validação, selecione o botão Criar na parte inferior da página. Captura de tela mostrando que a validação foi aprovada. Clique no botão Criar para criar a VM.

Após a conclusão da implantação, selecione Ir para o recurso.

Captura de tela mostrando a próxima etapa de ir para o recurso.

Conectar-se à máquina virtual
Inicie uma conexão da área de trabalho remota para a máquina virtual. Estas instruções ensinam a se conectar aàsua VM de um computador com Windows. Em um Mac, você precisa de um cliente RDP, como este Cliente de Área de Trabalho Remota da Mac App Store.

Selecione Conectar>RDP na página de visão geral de sua máquina virtual.

Captura de tela da página de visão geral da máquina virtual mostrando o local do botão Conectar.

Na guia Conectar-se ao RDP, mantenha as opções padrão para se conectar por endereço IP pela porta 3389 e clique em Baixar arquivo RDP.

Abra o arquivo RDP baixado e clique em Conectar quando solicitado.

Na janela Segurança do Windows, selecione Mais opções e Usar uma conta diferente. Digite o nome de usuário como localhost\nome de usuário, insira a senha que você criou para a máquina virtual e clique em OK.

Você pode receber um aviso do certificado durante o processo de logon. Clique em Sim ou em Continuar para criar a conexão.

Instalar servidor Web
Para ver a VM em ação, instale o servidor Web do IIS. Abra um prompt do PowerShell na VM e execute o seguinte comando:

PowerShell

Copiar
Install-WindowsFeature -name Web-Server -IncludeManagementTools
Quando terminar, feche a conexão RDP com a VM.

Exibir a página de boas-vindas do IIS
No portal, selecione a VM e, na visão geral da VM, passe o mouse sobre o endereço IP para mostrar Copiar para área de transferência. Copie o endereço IP e cole-o em uma guia do navegador. A página de boas-vinda do IIS padrão será aberta e deve ter esta aparência:

Captura de tela do site padrão do IIS em um navegador

Limpar os recursos
Excluir recursos
Quando o grupo de recursos, a máquina virtual e todos os recursos relacionados não forem mais necessários, exclua-os.

Na página Visão geral da VM, selecione o link Grupo de recursos.
Selecione Excluir grupo de recursos na parte superior da página do grupo de recursos.
Uma página abrirá um aviso de que você está prestes a excluir recursos. Digite o nome do grupo de recursos e selecione Excluir para concluir a exclusão dos recursos e do grupo de recursos.
Desligamento automático
Se a VM ainda for necessária, o Azure fornecerá um recurso de desligamento automático para máquinas virtuais a fim de ajudar a gerenciar custos e garantir que você não seja cobrado por recursos não utilizados.

Na seção Operações da VM, selecione a opção Desligamento automático.
Uma página será aberta na qual você poderá configurar o tempo para o desligamento automático. Selecione a opção Ativado para habilitar e, em seguida, defina uma hora que seja adequada para você.
Depois de definir a hora, selecione Salvar na parte superior para habilitar a configuração de Desligamento automático.
