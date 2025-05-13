# Desafio de Projeto  - Configurando Recursos e Dimensionamentos em Máquinas Virtuais na Azure

**1. Acessar o Portal do Azure:**

  * Abra seu navegador da web e vá para o [Portal do Azure](https://www.google.com/search?q=https://portal.azure.com/).
  * Faça login com sua conta da Azure (se você não tiver uma, precisará criar uma).

**2. Criar um Recurso de Máquina Virtual:**

  * No menu do portal (canto superior esquerdo), clique em "**Criar um recurso**" (o ícone de "+").
  * Na barra de pesquisa, digite "**Máquina virtual**" e pressione Enter.
  * Selecione "**Máquina virtual**" nos resultados da pesquisa e clique em "**Criar**".

**3. Configurar os Detalhes Básicos da VM:**

Na guia "**Básico**", você precisará fornecer as seguintes informações:

  * **Assinatura:** Selecione a assinatura do Azure que você deseja usar.
  * **Grupo de recursos:** Escolha um grupo de recursos existente ou crie um novo. Um grupo de recursos é um contêiner lógico para recursos relacionados no Azure. Para criar um novo, clique em "**Criar novo**", insira um nome e clique em "**OK**".
  * **Nome da máquina virtual:** Digite um nome para sua VM. Este nome será usado para identificar a VM no Azure.
  * **Região:** Selecione a região do Azure onde você deseja implantar a VM. Escolha uma região que esteja geograficamente próxima de seus usuários para obter melhor desempenho.
  * **Opções de disponibilidade:**
      * **Nenhuma redundância de infraestrutura necessária:** Adequado para cargas de trabalho de desenvolvimento e teste que não exigem alta disponibilidade.
      * **Conjuntos de disponibilidade:** Fornece redundância para proteger sua aplicação contra falhas de hardware dentro de um data center.
      * **Zonas de disponibilidade:** Fornece redundância e proteção contra falhas de data center inteiros dentro de uma região.
      * **Conjuntos de escala de máquinas virtuais:** Permite criar e gerenciar um grupo de VMs idênticas com balanceamento de carga automático.
  * **Imagem:** Selecione o sistema operacional que você deseja instalar na VM. Você pode escolher entre várias distribuições do Linux, diferentes versões do Windows Server e imagens personalizadas.
  * **Tamanho:** Selecione o tamanho da VM, que define os recursos de computação (CPUs virtuais, memória, armazenamento temporário) alocados à VM. Diferentes tamanhos são otimizados para diferentes tipos de cargas de trabalho. Você pode ver mais detalhes sobre os tamanhos clicando em "**Ver todos os tamanhos**".
  * **Tipo de autenticação:**
      * **Senha:** Crie um nome de usuário e uma senha para acessar a VM.
      * **Chave pública SSH:** Se você estiver usando um sistema operacional Linux, pode usar um par de chaves SSH para autenticação mais segura. Se você não tiver um par de chaves, pode pedir ao Azure para criar um para você.
  * **Nome de usuário:** Digite o nome de usuário para a conta de administrador na VM.
  * **Senha** (se a autenticação por senha for selecionada): Crie e confirme uma senha segura.
  * **Chave pública SSH** (se a autenticação por chave pública SSH for selecionada): Cole sua chave pública SSH ou escolha um par de chaves armazenado no Azure.
  * **Portas de entrada públicas (firewall):** Configure as regras de firewall para permitir o tráfego de entrada para sua VM. Por padrão, a porta SSH (22 para Linux) e a porta RDP (3389 para Windows) são frequentemente abertas para permitir o acesso remoto. Você pode adicionar outras portas conforme necessário (por exemplo, porta 80 para tráfego HTTP, porta 443 para tráfego HTTPS).

**4. Configurar os Discos (Guia "Discos"):**

  * **Tipo de disco do SO:** Escolha o tipo de disco para o sistema operacional. Os SSDs Premium oferecem o melhor desempenho, mas são mais caros. Os SSDs Standard são uma opção mais econômica para cargas de trabalho menos exigentes. Os HDDs Standard são adequados para dados não críticos.
  * **Tipo de criptografia:** Você pode optar por criptografar o disco do SO e os discos de dados.
  * **Criar e anexar um novo disco:** Você pode adicionar discos de dados adicionais à sua VM para armazenar seus dados de aplicativos. Clique em "**Criar e anexar um novo disco**" para configurar um novo disco. Você precisará especificar o nome, tamanho e tipo do disco.

**5. Configurar a Rede (Guia "Rede"):**

  * **Rede virtual:** Selecione uma rede virtual existente ou crie uma nova. Uma rede virtual permite que seus recursos do Azure se comuniquem entre si de forma isolada.
  * **Sub-rede:** Selecione uma sub-rede dentro da rede virtual.
  * **Endereço IP público:**
      * **Nenhum:** A VM não terá um endereço IP público diretamente acessível da internet.
      * **Dinâmico:** Um endereço IP público será atribuído à VM dinamicamente e pode mudar quando a VM for reiniciada.
      * **Estático:** Um endereço IP público fixo será atribuído à VM.
  * **Nome do rótulo DNS (opcional):** Se você escolher um endereço IP público dinâmico ou estático, você pode criar um rótulo DNS para associar um nome de domínio amigável ao endereço IP.
  * **Grupo de segurança de rede (firewall):** Selecione um grupo de segurança de rede (NSG) existente ou crie um novo. Um NSG controla o tráfego de rede de entrada e saída para sua VM. As regras de porta que você configurou na guia "Básico" serão adicionadas a este NSG.

**6. Gerenciamento (Guia "Gerenciamento"):**

  * **Diagnóstico de inicialização:** Habilite o diagnóstico de inicialização para ajudar a solucionar problemas de inicialização da VM. Você pode escolher entre o armazenamento gerenciado (recomendado) ou uma conta de armazenamento personalizada.
  * **Diagnóstico do SO do convidado:** Coleta métricas e logs do sistema operacional convidado.
  * **Identidade gerenciada:** Permite que sua VM se autentique em serviços do Azure compatíveis sem precisar de credenciais codificadas.
  * **Desligamento automático:** Configure um horário para desligar automaticamente a VM, o que pode ajudar a reduzir custos para cargas de trabalho não contínuas.
  * **Backup:** Configure backups para proteger os dados da sua VM.

**7. Configurações Avançadas (Guia "Avançado"):**

Esta seção oferece opções de configuração mais avançadas, como extensões, dados personalizados e configurações de proximidade. Geralmente, você não precisará alterar essas configurações para uma VM básica.

**8. Etiquetas (Guia "Etiquetas"):**

As etiquetas são pares de chave-valor que você pode atribuir aos seus recursos do Azure para organização e relatórios.

**9. Revisar + criar:**

  * Revise todas as configurações que você configurou. O Azure validará sua configuração e mostrará quaisquer problemas.
  * Se tudo estiver correto, clique em "**Criar**".

**10. Implantação:**

  * O Azure iniciará o processo de implantação da sua máquina virtual. Isso pode levar alguns minutos.
  * Você pode monitorar o progresso da implantação na seção de notificações do portal.

**11. Conectar-se à sua VM:**

  * Após a conclusão da implantação, vá para o seu grupo de recursos e selecione sua máquina virtual.
  * Na página de visão geral da VM, você encontrará o endereço IP público (se você configurou um).
  * **Para Windows:** Use a Conexão de Área de Trabalho Remota (RDP) com o endereço IP público, nome de usuário e senha que você criou.
  * **Para Linux:** Use um cliente SSH (como PuTTY no Windows ou o terminal no macOS e Linux) com o endereço IP público e as credenciais (senha ou chave privada SSH).
