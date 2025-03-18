---
lab:
  title: 'Laboratório 3: Como criar um aplicativo baseado em modelo'
  module: 'Module 3: Describe how to build applications with Microsoft Power Apps'
---

# Laboratório 3: Como criar um aplicativo baseado em modelo

**Locatários do WWL – Termos de Uso** Se você estiver recebendo um locatário como parte de uma entrega de treinamento com instrutor, observe que o locatário é disponibilizado com a finalidade de dar suporte aos laboratórios práticos no treinamento com instrutor. Os locatários não devem ser compartilhados ou usados para fins fora dos laboratórios práticos. O locatário usado neste curso é um locatário de avaliação e não pode ser usado ou acessado após o término da aula e não está qualificado para extensão. Os locatários não podem ser convertidos em uma assinatura paga. Os locatários obtidos como parte deste curso permanecem a propriedade da Microsoft Corporation e reservamos o direito de obter acesso e a qualquer momento. 

## Cenário

O Bellows College é uma organização educacional com vários campi e programas. Muitos instrutores e administradores do Bellows College precisam participar de eventos e comprar itens. Historicamente, o controle dessas despesas tem sido um desafio.

A administração do campus gostaria de modernizar o sistema de relatórios de despesas fornecendo aos funcionários uma forma de relatar despesas digitalmente.

Ao longo deste curso, você criará aplicativos e executará a automação para permitir que os funcionários do Bellows College gerenciem as despesas.

## Macroetapas do laboratório

Você fará o seguinte para criar o aplicativo baseado em modelo:

- Criar um novo aplicativo baseado em modelo chamado Gerenciamento de Despesas do Bellows.

- Editar a navegação do aplicativo para fazer referência às tabelas necessárias.

- Personalizar os formulários e as exibições das tabelas necessárias para o aplicativo.

Vamos trabalhar com os seguintes componentes:

- **Exibições**: As exibições permitem que o usuário exiba os dados atuais na tabela do formulário.

- **Formulários**: É onde o usuário cria/atualiza novas linhas nas tabelas.

Ambos serão integrados ao aplicativo baseado em modelo para oferecer uma melhor experiência do usuário.

### Pré-requisitos

- Conclusão do **Módulo 1 Laboratório 0 – Validação do ambiente de laboratório**

**Coisas a considerar antes de começar**

- Que mudanças precisamos fazer para melhorar a experiência do usuário?

- O que precisamos incluir em um aplicativo baseado em modelo de acordo com o modelo de dados que criamos?

- Quais personalizações podem ser feitas no mapa do site de um aplicativo baseado em modelo?

## Exercício 1: Personalizar exibições e formulários

**Objetivo:** Neste exercício, você vai personalizar as exibições e os formulários das tabelas personalizadas que serão usadas no aplicativo baseado em modelo.

### Tarefa 1: editar o Formulário do Relatório de Despesas

1. Se você ainda não tiver entrado, entre em https://make.powerapps.com

1. Selecione o ambiente **Dev One** no canto superior direito, se ainda não estiver selecionado.

1. Usando a navegação à esquerda, selecione **Tabelas** e abra a tabela **Relatório de Despesas**.

    >Se não vir a tabela Relatório de despesas, verifique se está no ambiente correto (Etapa 2).

1. Na seção **Experiências de dados**, selecione **Formulários** e abra o formulário **Informações** com o tipo de formulário **Principal**. (**Importante:** selecione o formulário com o tipo de formulário **Principal**).

    >**IMPORTANTE:** Como, por padrão, todos os formulários são denominados Informações, verifique se o formulário selecionado tem um Tipo de formulário **Principal** e não outro. Por padrão, o formulário tem dois campos: Nome e Proprietário.

1. No lado direito da tela, no painel **Propriedades**, selecione o campo **Nome de exibição** e altere-o para Informações do Relatório

1. Selecione **Colunas da tabela** no painel de navegação à esquerda e adicione os seguintes campos abaixo do campo **Proprietário** arrastando as colunas para o formulário ou simplesmente clicando nos nomes das colunas:

    - **Descrição**

    - **Finalidade do relatório**

    - **Data de conclusão do relatório**

    - **Valor Total do Relatório**

1. Arraste a coluna **Razão do Status** e solte-a no cabeçalho do formulário.

    >O cabeçalho é a área superior direita do formulário. Pode ser necessário recolher o painel Propriedades do lado direito da tela para ver o campo no formulário.

1. Selecione o campo **Proprietário**. No painel Propriedades, altere o **Rótulo** para Solicitante.

1. Selecione o botão **Salvar e publicar** no canto superior direito e aguarde a conclusão do salvamento e da publicação.

1. Se a exibição Edição foi aberta em uma nova guia ou janela do navegador, feche-a. Caso contrário, selecione **🡠 Voltar** no canto superior esquerdo da tela. Agora você deve voltar à tabela Formulários do **Relatório de Despesas**.

1. Usando a barra de rolagem no canto superior esquerdo (**Tabelas** > **Relatório de Despesas** > **Formulários**). Selecione **Relatório de Despesas** para retornar à tela de propriedades da Tabela do **Relatório de Despesas**.

## Tarefa 2: editar a exibição de Relatórios de Despesas Ativas

Nesta tarefa, modificaremos o modo de exibição padrão dos Relatórios de Despesas Ativas e criaremos uma nova exibição para os relatórios de despesas com vencimento hoje.

1. Na seção **Experiências de dados**, selecione **Exibições** e abra a exibição **Relatórios de Despesas Ativas**.

1. Inclua os campos a seguir à exibição ao clicar ou arrastar e soltar os campos:

    - **Finalidade do relatório**

    - **Data de conclusão do relatório**

    - **Valor Total do Relatório**

1. Selecione o menu suspenso na coluna **Criado em** e escolha **Remover**. O campo **Criado em** será removido da exibição.

1. Redimensione as larguras das colunas como desejar para ajustar os dados.

1. Em **Classificar por ...** clique no X para remover o **Nome do relatório** e, em vez disso, selecione **Valor Total do Relatório**.

1. Selecione **Valor Total do Relatório** para alterar a ordem de classificação para **Do maior para o menor**.

1. Selecione o botão **Salvar e publicar** no canto superior direito e aguarde a conclusão da publicação.

### Tarefa 3: criar um novo modo de exibição para os Relatórios com vencimento hoje

Agora, vamos clonar a exibição para criar uma nova exibição para os relatórios com vencimento hoje.

>    **IMPORTANTE:** Certifique-se de não fechar a exibição Relatórios de Despesas Ativas, pois a utilizaremos para criar o modo de exibição de Relatórios previstos para hoje.

1. Selecione **Salvar como**.

1. Altere o **Nome** para os Relatórios de despesas com vencimento hoje e selecione **Salvar**.

1. Escolha **Editar filtros** no painel Propriedades.

1. Selecione **+ Adicionar** e **Adicionar linha**.

1. Selecione **Data de vencimento do relatório** como campo e, em seguida, altere **Igual a** para **Hoje** como condição no menu suspenso.

1. Selecione as **…** **Mais comandos** na linha **Status** e escolha **Excluir** para excluir essa condição de filtro.

1. Escolha **OK** para salvar a condição. O modo de exibição agora é filtrado para mostrar apenas os registros em que a **Data de conclusão do relatório** é hoje.

1. Adicione o campo **Valor do Reembolso** à exibição.

1. Selecione o botão **Salvar e publicar** no canto superior direito e aguarde a conclusão da publicação.

## Exercício 2: criar o aplicativo baseado em modelo

**Objetivo:** neste exercício, você criará o aplicativo baseado em modelo, personalizará o mapa do site e testará o aplicativo.

Para simplificar e ganhar tempo, não abordaremos todas as colunas do Relatório de Despesas neste laboratório.

### Tarefa 1: criar o aplicativo

1. Se você ainda não tiver entrado, entre em https://make.powerapps.com

1. Selecione o ambiente **Dev One** na parte superior direita, se ele ainda não estiver selecionado.

1. Selecione **+ Criar** no painel de navegação à esquerda.

1. Criar o aplicativo baseado em modelo:

    - Escolha **Aplicativo em branco** na seção **Iniciar em** da tela **Criar seu aplicativo**.

    - Em **Aplicativo em branco baseado no Dataverse**, selecione **Criar**.

    - Insira `Employee Expense Management` em **Nome** e escolha **Criar**.

1. Quando o novo aplicativo baseado em modelo for carregado, selecione o botão **+ Adicionar página**.

1. Na tela **Adicionar página**, escolha **Tabela do Dataverse**.

1. Escolha as seguintes tabelas:

    - Relatório de Despesas

    - Contato

1. Quando tiver as duas tabelas, selecione **Adicionar**.

1. Usando os ícones de navegação no lado esquerdo da tela, selecione **Navegação**.

1. No painel de navegação, selecione **Novo Grupo** abaixo do item Navegação. Talvez seja necessário expandir o menu à esquerda.

1. No lado direito da tela, na seção **Opções de exibição**, altere a propriedade **Título** para Relatórios.

1. Selecione **Salvar** espere as alterações serem salvas.

1. Depois de **Salvar**, selecione o botão **Publicar** para publicar as alterações. Aguarde a conclusão da publicação.

## Tarefa 2: testar o aplicativo

**Iniciar o aplicativo**

1. Selecione o botão **Reproduzir**, e o novo aplicativo baseado em modelo será carregado em uma nova guia.

**Criar um Contato**

1. O aplicativo abrirá a exibição **Meus Contatos Ativos** Se isso não acontecer, selecione **Contatos** no painel de navegação à esquerda.

1. Escolha **+ Novo** na barra de comandos.

1. Insira **Nome** como `John` e **Sobrenome** como `Doe`.

1. Informe seu email pessoal como **e-mail**. Isso será usado em um laboratório futuro, em que você receberá um email.

1. Selecione **Salvar &amp; Fechar**.

1. Agora, você verá o contato criado na exibição **Meus Contatos Ativos**.

**Criar um novo Relatório de Despesas**

1. Selecione **Relatórios de Despesas** na navegação à esquerda (também conhecido como mapa do site).

1. Selecione **+ Novo**.

1. Insira os campos da seguinte maneira:

    - **Nome do relatório**: `New Test Report`

    - **Finalidade do Relatório**: selecione **Conferência**

    - **Data de conclusão do relatório**: Selecione a data de hoje.

1. Selecione **Salvar &amp; Fechar**. Isso criará o novo Relatório de Teste e você poderá vê-lo na exibição **Relatórios de Despesas Ativas **.

1. Altere o modo de exibição para **Relatórios de Despesas com Vencimento Hoje** usando o menu suspenso ao lado de **Relatórios de Despesas Ativas**. 

1. Você poderá adicionar mais alguns registros de teste.

O aplicativo baseado em modelo em execução será parecido com o seguinte:

![Captura de tela do aplicativo orientado por modelos recém-criado.](media/lab-3-create-a-model-app-01.png)

Parabéns! Você criou e configurou seu primeiro aplicativo controlado por modelos.
