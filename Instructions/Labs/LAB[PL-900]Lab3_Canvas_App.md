---
lab:
  title: 'Laboratório 3: Criar um aplicativo de tela'
  learning path: 'Learning Path: Demonstrate the capabilities of Microsoft Power Apps'
  module: 'Module 2: Build a canvas app'
---
## Objetivo de aprendizado

Neste exercício, você usará o Copilot para criar um aplicativo de tela que os funcionários podem usar para solicitar e gerenciar solicitações de folga e retirada de equipamentos. Após o aplicativo ser criado, você usará o Copilot e o designer do Power Apps para alterá-lo.

Após a conclusão bem-sucedida deste laboratório, você poderá:

- Usar o Copilot para ajudar na criação de um modelo de dados para dar suporte ao seu aplicativo.
- Modificar um aplicativo de tela.

### Cenário

A Contoso Consulting é uma organização de serviços profissionais especializada em serviços de consultoria de TI e IA. Eles querem criar um aplicativo de folga que os funcionários possam usar para solicitar folgas.

### Detalhes do laboratório

Antes de iniciar este exercício, você precisa ter concluído o seguinte laboratório:

- **Laboratório 2 – Criar um modelo de dados**

> **Importante** Este laboratório usa IA para criar os componentes. Como os resultados da IA podem variar, é importante observar que os seus resultados podem ser diferentes (mas semelhantes) do que é definido no laboratório. Os conceitos básicos descritos no laboratório serão os mesmos, independentemente do que foi criado ou de como foi nomeado. Se as tabelas e colunas não corresponderem exatamente, talvez seja necessário ajustar-se ao que for criado para você.

O tempo estimado para concluir este exercício é de **60 a 75**minutos.

## Tarefa 1: Entrar no Power Apps e explorar a interface

1.  Abra um navegador da Web e acesse o portal do criador do [Power Apps](https://make.powerapps.com/).
1.  Usando a navegação à esquerda, selecione **Criar**.
1.  Em **Criar seus aplicativos**, escolha **Começar com o Copilot**.
1.  Na tela **Descreva as tabelas que você deseja que o Copilot crie**, digite: *` I want to store time off requests sent by employees. The table should identify the start and end times of the request.`*
1.  Selecione o botão **Opções da tabela**. No menu exibido, selecione **Uma Tabela**.

    ![Captura de tela de introdução com a tela do Copilot](media/60a2ec72988f48c91df7c370532cb331.png)

1.  Selecione o botão **Gerar**.

    O Copilot deve ter criado uma tabela **Solicitação de Folga**. Em seguida, adicionaremos mais colunas à tabela.

    **Observação**: Se necessário, adicione o nome da tabela ao prompt.

1.  No painel do **Copilot**, insira: *`Add a choice column called Time Off Reason.`*
1.  No painel do **Copilot**, adicione individualmente os seguintes prompts:
    - *`Add a choice column named Time off Type.`*
    - *`Add a Date column called Submission Date.`*
    - *`Add a choice column to the Time Off request table called Approval Status.`*
    - *`Add a multi-line text column called Request Details.`*

    Sua tabela de folga deve ser semelhante à imagem:

    ![Captura de tela da tabela Solicitação de Folga preenchida ](media/2ac256daafe1853e5367852467690c76.png)

    Em seguida, vamos adicionar a tabela de usuário ao modelo de dados para que possamos associar solicitações de folga a usuários específicos.

1.  Na **Barra de comandos**, selecione **+ Tabela existente**.
1.  Alterne de **Recomendado** para **Todas as Tabelas**.
1.  No campo **Pesquisar**, insira **Usuário**.
1.  Selecione a tabela **Usuário** e clique no botão **Adicionar Selecionado**.
1.  Na **Barra de comandos**, selecione **Criar relações**.
1.  Configure a relação da seguinte maneira:

    -   **Um:** Usuário
    -   **Muitos:** Solicitação de Folga
    -   **Nome de exibição**: `Requesting Employee`
  
1.  Selecione **Concluído**.

    O modelo de dados concluído deve ficar parecido com esta imagem:

    ![Captura de tela do modelo de dados concluído ](media/daa74d51e2ceada8e1e8b004cae9942a.png)

1.  Selecione o botão **Salvar e abrir o aplicativo**.

> [!NOTE]
> Pode demorar alguns minutos para que o aplicativo seja criado.

## Tarefa 2: Personalizar o novo aplicativo

Agora que o aplicativo foi criado, faremos algumas modificações para atender melhor às nossas necessidades. Vamos começar fazendo algumas modificações na tela de boas-vindas.

1.  Com o novo aplicativo aberto, selecione o espaço reservado **Imagem** acima do texto **Solicitações de Folga**.
1.  No menu que aparecerá, selecione **Editar** \> **Carregar**.
1.  Escolha a imagem **Folga** na pasta de arquivos de classe e selecione **Abrir**.
1.  Em seguida, selecione o espaço reservado **Imagem** acima de **Usuários**.
1.  No menu que aparecerá, selecione **Editar** \> **Carregar**.
1.  Escolha a imagem **Funcionário** na pasta de arquivos de classe e selecione **Abrir**.

    Em seguida, vamos ajustar o tamanho das imagens para facilitar a leitura dos usuários. Além disso, vamos ajustar o texto exibido para cada item.

1.  Na **Barra de comandos**, selecione o botão **Propriedades**. (*Localizado à direita do botão Edição.*)
1.  Selecione a imagem **Folga** que você adicionou anteriormente.
1.  No painel **Propriedades**, configure a imagem da seguinte maneira:
    
    -   **Posição da Imagem:** Preencher
    -   **Largura:** 300
    -   **Altura:** 300
      
1.  Repita a etapa anterior para definir a **Altura** e a **Largura** da imagem **Funcionário** para **300** x **300**.
1.  Selecione o texto abaixo de **Solicitações de Folga**.
1.  No painel **Propriedades**, selecione o campo **Texto** e altere o texto para: *`Create, View, and Manage you time off requests.`*
1.  Selecione o texto **Tela de Boas-vindas** no **Cabeçalho**.
1.  No painel **Propriedades** à direita, selecione o campo **Logotipo**.
1.  No menu exibido, selecione **Carregar**.
1. Selecione o **Logotipo da Contoso** em seus arquivos de classe e selecione **Abrir**.
1. No painel **Propriedades**, no grupo de temas e **Estilo**, selecione o ícone de cor de **Preenchimento**.
1. Selecione a guia **Personalizado**
1. Altere a cor **Hex** para: `101E2B`
1. Verifique se você ainda tem o **Cabeçalho** selecionado e altere o **Título** para `Contoso Employee Hub`.
1. Na **Barra de comandos**, selecione o botão **Salvar** e salve o aplicativo.
1. Na tela **Salvar**, defina o **Nome** como `Contoso Employee Hub` e selecione **Salvar.**

    Seu aplicativo será semelhante à imagem.

    ![Captura da tela de boas-vindas do aplicativo de tela.](media/533c80cc861941b6a353b56bfc0dbc0f.png)

## Tarefa 3: Adicionar uma nova tela ao aplicativo.

Enquanto você está criando o aplicativo, um de seus gerentes pergunta se os funcionários também podem usar esse aplicativo para retirar equipamentos. A Contoso já está armazenando informações de retirada de equipamentos no Dataverse, portanto, é apenas uma questão de disponibilizar as informações no aplicativo.

1.  Com o aplicativo ainda aberto, expanda o painel do **Copilot** (se necessário). No Copilot, digite o seguinte: *`Add a new screen called Equipment Checkout.`*
1.  Selecione **Enviar**.
1.  Selecione o botão **Manter** para aceitar a nova tela.
1.  Uma tela chamada **Retirada de Equipamento** é adicionada ao seu aplicativo.
1.  Na tela **Retirada de Equipamento**, clique em **Com o layout** e escolha o layout de **Barra lateral**.
1.  Expanda os diferentes contêineres até que **SideBarContainer** esteja visível.

    ![Captura de tela do modo de exibição de árvore ](media/cde6257402b7a8786e679ab64ee0f882.png)

1.  Clique com o botão direito do mouse em **SidebarContainer** e renomeie como **EquipContainer1**.
1.  Com o contêiner **EquipContainer1** selecionado, clique no botão **Abrir Menu de Inserção**.
1.  Na janela **Pesquisar**, insira **Galeria** e selecione **Galeria vertical**.
1.  Quando você for solicitado a fornecer uma fonte de dados no campo **Pesquisar**, insira **Equipamentos** e selecione a tabela **Equipamentos**.
1. Em **Modo de Exibição de Árvore** no lado esquerdo da tela, selecione o controle **Gallery1** que você acabou de adicionar.
1. Clique com o botão direito do mouse no nome da Galeria, escolha **Renomear** e renomeie como `Equipment List`.
1. Passe o mouse sobre a galeria **Lista de Equipamentos** na barra de ferramentas que aparece acima da galeria e selecione **Layout**.
1. Selecione a opção **Layout de título e subtítulo**.
1. Com a galeria **Lista de Equipamentos** selecionada, no painel **Propriedades**, configure da seguinte maneira:

    -   **Width**: `360`
    -   **Altura flexível:** Ativado
    -   **Altura mínima:** `287`

    Em seguida, adicionaremos um contêiner adicional ao contêiner **EquipmentContiner1** para armazenar um controle de pesquisa que usaremos para filtrar o conteúdo da galeria **Lista de Equipamentos**.

1.  No modo de exibição **Árvore**, selecione **EquipContainer1**.
1.  Passe o mouse sobre o contêiner e selecione o ícone do **Copilot**.
1.  Digite o seguinte texto: *`Insert a Horizontal container.`*

    ![Captura de tela da inserção de uma galeria em um contêiner.](media/b9b784ea5625469c8785650b977f32d1.png)

1.  Selecione o botão **Manter**.
1.  Um novo contêiner será adicionado à parte inferior do contêiner **EquipContainer1**.
1.  No **Modo de Exibição de Árvore**, clique, segure e arraste o novo contêiner e coloque-o acima da galeria **Lista de Equipamentos**.
1.  Renomeie o contêiner como `EquipSearchContainer`.
1.  Com a galeria **EquipSearchContainer** selecionada, no painel **Propriedades**, configure da seguinte maneira:
    
    -   **Largura mínima:** `0`
    -   **Altura flexível:** Desativado
    -   **Height**: `44`
    
1.  Com **EquipSearchContainer** selecionado, selecione o botão **Abrir menu de inserção**.
1. No campo **Pesquisar**, insira **Texto** e selecione **Entrada de texto**.
1. Renomeie o campo **Entrada de texto** como `EquipSearchInput`.
1. Com **EquipSearchInput** selecionado, no painel **Propriedades**, configure da seguinte maneira:

    -   **Padrão:** Em branco (nada)
    -   **Texto da dica:** Pesquisar
    -   **Fonte:** Open Sans
    -   **Tamanho da fonte:** 14
    -   **Preenchimento** (os valores abaixo podem já estar lá.)
        -   **Superior:** 5
        -   **Inferior:** 5
        -   **Esquerda:** 12
        -   **Direita:** 5
    -   **Altura:** 44
    -   **Largura flexível:** Ativado
    -   **Largura mínima:** 0

        ![Captura de tela das propriedades de Entrada de Pesquisa.](media/b0e092b4795edf58dad1153209639051.png)

1. No **Modo de Exibição de Árvore**, selecione o **EquipSearchContainer.**
1. Passe o mouse sobre o contêiner, selecione o ícone do **Copilot** e insira *`Add a Search Icon.`*
1. Selecione **Manter**.

    > **Observação:** se o Copilot adicionar o ícone errado, remova-o e insira a lupa manualmente.

1. Com o ícone de **Pesquisa** selecionado, no painel **Propriedades**, configure o controle da seguinte maneira:

    -   **Preenchimento**
        -   **Superior:** 10
        -   **Inferior:** 10
        -   **Esquerda:** 10
        -   **Direita:** 10
    -   **Altura:** 44
    -   **Largura:** 44

    ![Captura de tela das propriedades do Ícone de pesquisa.](media/cb3305731a09bca0bbf166d55d9822a4.png)

1. Usando o **Modo de exibição árvore** à esquerda, selecione **EquipSearchContainer**.

    Por fim, vamos configurar a **Lista de Equipamentos ** para preencher seus dados com base no texto inserido no campo de controle de pesquisa.

1.  Selecione a galeria **Lista de Equipamentos** que criamos anteriormente.
1.  Na propriedade **Itens**, insira a seguinte fórmula: `Search([@'Equipments'], EquipSearchInput.Text, 'Equipment Name',Category)`

    ![Captura de tela da Fórmula PowerFx de Itens.](media/powerfx-formula.png)

1. Na **Barra de comandos**, selecione o botão **Salvar** e salve seu aplicativo.

> **Importante:** se você copiou e associou a fórmula na barra de fórmulas, é possível que '' esteja incorreto para o Nome do Equipamento e o Equipamento. Se você estiver recebendo um erro de fórmula, tente removê-las e inseri-las novamente.

## Tarefa 4: Crie um contêiner para exibir operações de registro.

Quando um usuário seleciona um registro na lista Equipamentos, queremos abrir o registro em outro contêiner para permitir que ele edite o registro selecionado.

1.  Selecione o **MainContainer** e renomeie-o como `DetailsContainer`.
1.  No **DetailsContainer**, selecione o botão **Inserir**.
1.  No campo **Pesquisar**, insira **Contêiner** e escolha **Contêiner Vertical**.
1.  Clique com o botão direito do mouse e **Renomeie** o contêiner como `RecordDetails`.
1.  No contêiner **RecordDetails**, selecione o botão **Inserir**.
1.  No menu **Inserir**, **Editar formulário**.
1.  Na tela selecionar fonte de dados, selecione **Equipamentos**. *(Pode levar até 30 segundos para que os dados sejam preenchidos.)*
1.  Clique com o botão direito do mouse no formulário que você acabou de adicionar e **Renomeie** como `EquipmentForm`.
1.  No painel **Propriedades**, selecione a guia **Avançado** e defina a propriedade **Item** como: `'Equipment List'.Selected` *(Isso preencherá o formulário com o registro selecionado no momento.)*
1. Selecione a guia **Exibir** e configure o formulário da seguinte maneira:

    -   **Colunas:** 2
    -   **Modo padrão:** Editar

    Agora, vamos adicionar outro contêiner que será usado para controlar as operações no formulário.

1.  Verifique se você tem **DetailsContainer** selecionado.
1.  Selecione o ícone do **Copilot** exibido. Digite o seguinte: *`Insert a horizontal container.`*
1.  Selecione **Manter**.
1.  Clique com o botão direito do mouse no contêiner e **Renomeie**-o como `SelectedRecord1`
1.  Usando a exibição de **Árvore**, mova o contêiner **SelectedRecord1** acima do contêiner **RecordDetails**.
1.  Configure o contêiner **SelectedRecord1** da seguinte maneira:
    
    -   **Largura mínima:** 250
    -   **Altura flexível:** Desativado
    -   **Height**: 50
    
1.  Com o contêiner **SelectedRecord1** selecionado, selecione o botão **Inserir**.
1.  Selecione **Rótulo de Texto**.
1.  Renomeie o rótulo como `SelectedRecordTitle`.
1. Configure o **SelectedRecordTitle** da seguinte maneira:

    1.  **Preenchimento**
        1.  **Superior:** 5
        2.  **Inferior:** 5
        3.  **Esquerda:** 30
        4.  **Direita:** 5
    2.  **Largura flexível:** Ativado
    3.  **Largura mínima:** 150
    4.  **Altura:** 40
       
1. Selecione o contêiner **SecondRecord1**, selecione o botão **Inserir**.
1. No campo **Pesquisar**, insira **Salvar** e selecione o ícone **Salvar**.
1. Configure o botão **Salvar** da seguinte maneira:

    -   **Altura:** 40
    -   **Width**: 40
      
1. Selecione a propriedade **OnSelect** e insira a seguinte fórmula: `SubmitForm(EquipmentForm)`.

    ![Captura de tela da Fórmula OnSelect PowerFx.](media/e5b22c91a437e6918269d65e2616afc8.png)

## Tarefa 5: Modificar o cabeçalho na página

A última etapa da criação desta tela é preencher o contêiner do leitor com dados.

1.  Selecione **HeaderContainer** na parte superior do aplicativo.
1.  Selecione o botão **Inserir**.
1.  Selecione **Rótulo de texto**.
1.  Configure o controle **Rótulo de texto** da seguinte maneira:
   
    -   **Text**: `Equipment Checkout`
    -   **Fonte:** Open Sans
    -   **Tamanho da Fonte:** 16
    -   **Peso da fonte:** Seminegrito
    -  **Preenchimento**
        -   **Superior:** 16
        -   **Inferior:** 16
        -   **Esquerda:** 16
        -   **Direita:** 16
    -   **Altura:** 40
    -   **Largura flexível:** Ativado

        ![Captura de tela das propriedades do rótulo de texto.](media/088cafeec651b099fa49ac1f151cd228.png)

1.  Selecione o **HeaderContainer**, escolha **Inserir** e selecione o ícone **Página Inicial**.
1.  Defina a propriedade **OnSelect** do botão de início como: `Back()`

    ![Captura de tela do comando navegação Voltar.](media/38d0e5367ee41da58ac9902f8056b1af.png)

## Tarefa 6: Concluir a configuração da tela de boas-vindas

Após a revisão, decidimos que não precisamos ter a capacidade de criar usuários neste aplicativo, portanto, vamos alterar a Tela de Boas-Vindas para permitir que você acesse a retirada de equipamentos.

1.  Usando o **Modo de Exibição de Árvore**, selecione a **Tela de boas-vindas**.
1.  Selecione a **Imagem** acima de **Usuários**.
1.  No menu que aparecerá, selecione **Editar** e escolha **Carregar**.
1.  Localize a imagem do **Equipamento** na pasta do aluno e escolha **Abrir**.
1.  Defina a propriedade **OnSelect** da imagem como: `Navigate('Equipment Checkout')`
1.  Selecione o texto **Usuários** e defina a propriedade **Texto** como `Equipment`.
1.  Selecione o **Texto** abaixo de **Equipamento** e altere a propriedade **Texto** para: `Check out equipment and edit reservations`.

    ![Uma captura de tela de um conteúdo gerado por IA do computador pode estar incorreta.](media/561d1e8cd023541761b6523138c2fde8.png)

1. Clique no botão **Salvar** para salvar seu aplicativo.

## Tarefa 7: Testar o aplicativo

1.  Na **Barra de comandos**, selecione o botão **Reproduzir**.
1.  Selecione a imagem **Equipamento**.
1.  No campo de **Pesquisa**, insira **Eletrônico**. (*Observe como a lista é filtrada*)
1.  Selecione o registro **Laptop**.
1.  Altere a **Categoria** para **Móveis**.
1.  Selecione o botão **Salvar**.
1.  Observe como a categoria **Laptop** muda para **Móveis**.
1.  Selecione o botão **Início**.
1.  Selecione o **X roxo** para sair do modo de **Visualização**.

## Tarefa 8: Salvar e publicar o aplicativo

**Meta:** Salve e publique o aplicativo para torná-lo acessível em navegadores da Web, dispositivos móveis ou plataformas inseridas, como SharePoint ou Teams.

1.  No Power Apps Studio, selecione o botão **Salvar**.
1.  Selecione o botão **Publicar**.
1.  Selecione **Publicar esta versão.**

