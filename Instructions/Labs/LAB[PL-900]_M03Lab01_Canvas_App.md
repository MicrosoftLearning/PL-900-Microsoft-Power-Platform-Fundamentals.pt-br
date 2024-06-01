---
lab:
  title: 'Laboratório 2: Como criar um aplicativo de tela'
  module: 'Module 3: Describe how to build applications with Microsoft Power Apps'
---

# Laboratório 2: Como criar um aplicativo de tela

**Locatários do WWL – Termos de Uso** Se você estiver recebendo um locatário como parte de uma entrega de treinamento com instrutor, observe que o locatário é disponibilizado com a finalidade de dar suporte aos laboratórios práticos no treinamento com instrutor. Os locatários não devem ser compartilhados ou usados para fins fora dos laboratórios práticos. O locatário usado neste curso é um locatário de avaliação e não pode ser usado ou acessado após o término da aula e não está qualificado para extensão. Os locatários não podem ser convertidos em uma assinatura paga. Os locatários obtidos como parte deste curso permanecem a propriedade da Microsoft Corporation e reservamos o direito de obter acesso e a qualquer momento. 

## Cenário

O Bellows College é uma organização educacional com vários campi e programas. Muitos instrutores e administradores do Bellows College precisam participar de eventos e comprar itens. Historicamente, o controle dessas despesas tem sido um desafio. 

A administração do campus gostaria de modernizar o sistema de relatórios de despesas fornecendo aos funcionários uma forma de relatar despesas digitalmente. 

Ao longo deste curso, você criará aplicativos e executará a automação para permitir que os funcionários do Bellows College gerenciem as despesas. 


## Macroetapas do laboratório

Seguiremos o esquema abaixo para projetar o aplicativo de tela:

- Criar um aplicativo de tela de relatório de despesas 

- Configurar como os relatórios de despesas são mostrados na tela de navegação

- Fazer algumas alterações básicas no aplicativo

- Testar a funcionalidade do aplicativo

## Pré-requisitos

- Conclusão do **Módulo 1 Laboratório 0 – Validação do ambiente de laboratório**

## Exercício 1: Criar um aplicativo de Tela de Relatórios de Despesas

### Objetivo: Neste exercício, você criará um aplicativo de tela conectando-se a uma tabela de Relatórios de Despesas.

### Tarefa 1: Criar o aplicativo de Relatórios de Despesas

1. Navegue até https://make.powerapps.com

1. Talvez seja necessário autenticar novamente – selecione **Entrar** e siga as instruções, se necessário.

1. Selecione o ambiente **Dev One** na parte superior direita, se ele ainda não estiver selecionado.

1. Selecione **+ Criar** no painel de navegação à esquerda da tela. Na seção **Iniciar em**, selecione **Dataverse**.

1. Selecione a conexão do Dataverse.

    >**Observação**: Se uma conexão do Dataverse não existir:

    >   - Selecione **+Nova Conexão**

    >   - Localize o **Microsoft Dataverse**

    >   - Escolha **Criar**

    >   - **Entre** e selecione **Permitir acesso**

1. Localize e selecione a tabela **Relatórios de despesas**.

1. Selecione o botão **Conectar** no canto inferior direito.

1. Após a criação do aplicativo, na tela Boas-vindas ao Power Apps Studio, escolha **Não mostrar isso novamente** e selecione **Ignorar**.

1. No designer de aplicativo, selecione o botão **Visualizar aplicativo** (ícone Reproduzir) na barra de comandos. (Você também pode visualizar o aplicativo pressionando F5). Dê uma olhada no aplicativo e veja como ele se comporta na configuração inicial pelo usuário.

1. Feche a visualização do aplicativo clicando em **X** no canto superior direito da tela.

Parabéns, você criou com êxito um Power App usando uma tabela do Dataverse. A próxima etapa no processo é adaptar o aplicativo para corresponder à identidade visual de suas organizações. A próxima série de etapas ajudará você a fazer personalizações extra no aplicativo.

### Tarefa 2: Modificar e criar um tema para o aplicativo recém-criado

Nesta tarefa, você personalizará o texto do cabeçalho em cada uma das três telas do aplicativo (Procurar, Detalhes e Editar) e alterará o tema do aplicativo.

1. Você está na tela Procurar. Selecione o rótulo **Relatórios de despesas** na tela.

1. No lado direito da tela, na guia Propriedades, atualize a propriedade de controle **Texto** para Meus relatórios de despesas

1. Na guia **Propriedades**, altere o **Tamanho da fonte** para **24**.

1. Selecione o fundo em branco da tela para ver o texto atualizado na tela de navegação.

1. Usando o **Modo de exibição de árvore** no painel de navegação à esquerda, selecione **DetailScreen1**.

1. Selecione o rótulo **Relatórios de despesas** na tela.

1. No lado direito da tela, na guia **Propriedades**, atualize a propriedade de controle **Texto** para Detalhes do relatório

1. Clique no fundo em branco da tela para ver o texto atualizado na tela Detalhes.

1. Usando o **Modo de exibição de árvore** no painel de navegação à esquerda, selecione **EditScreen1** (talvez seja necessário rolar a tela para ver isso no modo de exibição de árvore).

1. Selecione o rótulo **Relatórios de despesas** na tela.

1. No lado direito da tela, na guia **Propriedades**, substitua o texto na propriedade de controle **Texto** por Editar detalhes

1. Clique no fundo em branco da tela para ver o texto atualizado na tela Editar.

1. Usando o **Modo de exibição de árvore** no painel de navegação à esquerda, selecione **BrowseScreen1**.

1. Na barra de ferramentas de comando, selecione o botão **Tema** e, na lista exibida, selecione a cor do tema **Vermelho**.

### Tarefa 3: Testar o seu aplicativo de relatórios de despesas

Nesta tarefa, você testará seu novo aplicativo.

1. Com o seu aplicativo aberto no Designer de Aplicativos, selecione **Configurações** (talvez seja necessário selecionar … para o Ícone de Configuração a ser exibido), na seção **Geral**, atualize o nome do aplicativo para o Aplicativo de Relatório de Despesas, selecione o **X** para fechar a tela de configurações e, em seguida, selecione **Salvar**.

1. Usando a navegação à esquerda, selecione **BrowseScreen1**.

1. No designer de aplicativo, selecione o botão **Visualizar aplicativo** (ícone Reproduzir) na barra de comandos. (Você também pode visualizar o aplicativo pressionando F5).

1. Depois que o aplicativo for aberto, no campo **Pesquisar itens**, insira o texto Viagem (observe como os itens na galeria são filtrados com base no que é digitado no campo de pesquisa).

1. Depois que o registro **Viagem para a Power Platform Conference** for exibido, selecione uma linha para navegar e abrir a tela Detalhes dessa Despesa.
 
    >**Observação**: Se mais de um registro da viagem para a Power Platform Conference for exibido, selecione qualquer um deles.

1. Para editar o registro, selecione o **Ícone de lápis** no canto superior direito do aplicativo.

1. Você pode editar o **Nome do relatório** aqui e selecionar o ícone **Marca de seleção** na parte superior direita para salvar a alteração.

1. No canto superior direito da tela, selecione o ícone **X** para fechar o modo de pré-visualização e retornar ao editor do aplicativo de tela.

Parabéns! Você criou e configurou seu primeiro aplicativo de tela.

 
