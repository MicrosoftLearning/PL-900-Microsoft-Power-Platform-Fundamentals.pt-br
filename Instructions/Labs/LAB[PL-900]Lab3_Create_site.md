---
lab:
  title: 'Laboratório 3: Criar um site do Power Pages'
  learning path: 'Learning Path: Demonstrate the capabilities of Microsoft Power Pages'
  module: 'Module 2: Create a Microsoft Power Pages site'
---
## Objetivo de aprendizado

Neste exercício, os alunos usarão o Copilot para criar um site do Power Pages. Após o site ser criado, você usará o Estúdio de Design do Power Pages para executar tarefas como adicionar e modificar conteúdo, bem como alterar temas.

### Cenário

Ao longo do ano, a Contoso Consulting promove muitos tipos de eventos diferentes. Eles vão de eventos pessoais a webinars, treinamentos com instrutor e muito mais. Eles estão buscando usar o Microsoft Power Platform para gerenciar os diferentes eventos que promovem. Eles querem usar o Power Pages para criar um site de gerenciamento de eventos que exibirá os diferentes eventos que promovem.

Após a conclusão bem-sucedida deste laboratório, você poderá:

-   Usar o Copilot para criar um site de Gerenciamento de Eventos.
-   Adicionar novo conteúdo ao site.
-   Visualizar o novo site do Power Pages em diferentes tipos de dispositivos.

**Detalhes do laboratório:**

Antes de iniciar este exercício, você precisa ter concluído o seguinte laboratório:

- **Laboratório 2 – Criar um modelo de dados**

> **Importante:** Este laboratório usa IA para criar os componentes. Como os resultados da IA podem variar, é importante observar que os seus resultados podem ser diferentes (mas semelhantes) do que é definido no laboratório. Os conceitos básicos descritos no laboratório serão os mesmos, independentemente do que foi criado ou de como foi nomeado. Se as tabelas e colunas não corresponderem exatamente, talvez seja necessário ajustar-se ao que for criado para você.

O tempo estimado para concluir este exercício é de **30 a 45**minutos.

**Antes de começar:** Se esta for a primeira vez que você acessa o portal do criador do Power Pages, talvez seja necessário configurar algumas coisas.  Se for esse o caso, siga as instruções abaixo.  Caso contrário, você pode prosseguir para a **Tarefa 1**.  

1.  Se necessário, navegue até [Microsoft Power Pages](https://make.powerpages.microsoft.com).
1.  Na tela **Boas-vindas ao Power Pages**, selecione o botão **Introdução**.

    ![Captura da tela de boas-vindas do Power Pages.](media/get-started.png)

1. Na tela **Conte-nos um pouco sobre você**, selecione o botão **Ignorar**.

    ![Captura da tela de boas-vindas do Power Pages.](media/about-you.png)

## Tarefa 1: Usar o Copilot para criar um site do Power Pages.

1.  Se necessário, navegue até <https://make.powerpages.microsoft.com>
1.  Na home page do **Estúdio de design do Power Pages**, insira o seguinte texto: “*Crie um site para gerenciar eventos que nossa organização promove.”*
1.  Selecione o botão **Enviar**.
1.  Na tela **Verifique os detalhes básicos do site**, configure da seguinte maneira:
    - **Dê um nome ao site:** `Contoso Event Management`
    - **Crie um endereço web:** Aceite o endereço padrão fornecido
    - **Idioma do site:** Inglês

    ![Captura de tela mostrando detalhes básicos do site](media/9a5bc928349720c1da2f112bf1baf562.png)

1.  Selecione o botão **Avançar**.
1.  Na tela **Escolha um layout**, examine o layout sugerido. Se quiser sugestões de layout adicionais, selecione **Tente novamente** para que o **Copilot** sugira outro layout.
1.  Após identificar o modelo que deseja usar, selecione **Avançar**.
1.  Na seção **Adicionar páginas comuns**, selecione as seguintes páginas:
    - Sobre nós
    - Entre em contato conosco.
    - Perguntas frequentes
    - Selecione as páginas adicionais que desejar.
1.  Depois de selecionar as páginas, selecione **Concluído**.

    O novo site será criado em segundo plano, o que pode levar vários minutos.

1.  Após o site ser criado, abra-o (caso ainda não tenha sido levado para lá).

    > **Observação:** Às vezes, quando o site é carregado pela primeira vez, você pode ver uma mensagem de objeto Liquid não encontrado. Se isso acontecer, atualize (F5) a janela do navegador para recarregar o site. O site deve aparecer.

## Tarefa 2: Modificar o conteúdo do site

Agora que o site inicial foi criado, você pode usar o estúdio de design para modificá-lo adicionando páginas, texto, imagens, formulários e muito mais.

1.  Na **Navegação principal**, selecione **Início** para abrir a página **Início**.
1.  Passe o mouse sobre o texto do **Site Contoso Event Management** no cabeçalho do site e selecione **Editar cabeçalho do site**.
1.  Altere o **Título do site** para **Contoso Consulting**.
1.  Selecione o botão **Carregar imagem**.
1.  Na tela **Adicionar uma imagem**, selecione **Carregar imagem**, escolha o **Logotipo da Contoso** nos arquivos da aula e escolha **Abrir**.
1.  Com a imagem do **Logotipo da Contoso** selecionada, selecione **OK**.
1.  Depois de concluir as alterações, selecione o **X** para sair da tela **Editar cabeçalho do site**.
1.  Para alterar a imagem de plano de fundo do site, clique em qualquer lugar nela.
1.  No menu exibido, escolha **Editar plano de fundo**.
1. Selecione o botão **Alterar Imagem**.
1. Selecione **Biblioteca de mídia** e escolha **Carregar Imagem**.
1. Selecione a imagem **Site_Background** nos arquivos de aula e escolha **Abrir**.
1. Com Site_Background selecionado, escolha **OK**.
1. Selecione o texto **Boas-vindas aos Eventos da Contoso** e altere o texto para **Contoso Consulting**.
1. Na barra de ferramentas, selecione o botão **Design** * (Pincel)*.
1. Selecione a seta ao lado da propriedade **Sombra de Texto** e defina **Deslocamento de H** como **2**.
1. Selecione o **X** para fechar a janela **Design de Texto**.
1. Selecione o texto abaixo de Contoso Consulting, *(pode dizer algo semelhante a Seu parceiro no Gerenciamento de Eventos)* e altere-o para **Seu parceiro para hoje e o futuro**.

    Agora que fizemos algumas alterações básicas na home page, vamos atualizar o tema do site para corresponder melhor à identidade visual da Contoso.

1.  Usando a navegação à esquerda, selecione o botão **Estilo**.
1.  Selecione o tema **Azul Brilhante**.
1.  Em **cores da marca**, selecione o círculo de cores **Cinza**.
1.  Altere a cor **Hex** **: 101E2B**
1.  Selecione **OK**.
1.  Selecione o círculo **Branco** e altere a cor para código **Hex** **e8e8e8**
1.  Selecione **OK**
1.  Selecione o círculo **Preto** e altere a cor para **Branco**. (ffffff)
1.  Selecione **OK**.
1. Faça as alterações adicionais desejadas no tema. Quando terminar a alteração de temas, selecione o botão **Salvar**.

## Tarefa 3: Conectar o site aos dados corporativos

Uma das principais vantagens do Power Pages é a capacidade de conectar um Power Pages a seus dados corporativos que estão no Dataverse. Antes de trazer os dados, precisamos criar alguns elementos que serão usados.

1.  Usando a navegação à esquerda, selecione o ícone **Dados**.
1.  No campo de **Pesquisa**, insira **Evento**.
1.  Selecione a tabela **Evento**.

    Primeiro, vamos criar um formulário que será usado quando quisermos adicionar um novo evento.

1.  Selecione a guia **Formulários** e escolha **+ Novo Formulário**.
1.  Defina **Nome do formulário** como `Create Event` e selecione o botão **Criar** .
1.  Não faremos nenhuma modificação no layout. Selecione o botão **Salvar e Fechar**.
1.  Pressione a **Seta Voltar** para voltar ao designer.

    Em seguida, vamos criar um formulário que será usado para exibir e editar eventos existentes

1.  Selecione o botão **+ Novo Formulário**.
1.  Nomeie o formulário **Exibir Evento** e selecione o botão **Criar**.
1.  Na **Barra de comandos**, selecione **Adicionar componente** e selecione **Subgrade**.
1.  Configure a Subgrade da seguinte maneira:
    -   **Mostrar Registros Relacionados:** Sim
    -   **Tabela:** Sessões de evento
    -   **Padrão:** Sessões Ativas
1.  Selecione **Concluído**.
1.  Selecione o botão **Salvar e Fechar**.
1.  Selecione o botão **Voltar** para retornar ao **Estúdio de Design**.

## Tarefa 4: Criar os formulários de página da Web necessários

Agora que definimos formulários para a tabela Evento, vamos criar páginas que incluam esses formulários para que os usuários do site possam trabalhar com registros de Eventos. Vamos criar páginas para exibir, criar e editar eventos.

1.  Usando a navegação à esquerda, selecione o ícone **Páginas**.
1.  Selecione o botão **+ Página**.
1.  No **Copilot**, digite o texto a seguir: *`Add a new blank page.`* Selecione o botão **Enviar**.
1.  Selecione o botão **Manter**.
1.  Na parte superior da nova página, selecione o botão **Adicionar uma Seção**.
1.  Selecione **1 Coluna**.
1.  Em **Escolher um componente para adicionar a esta seção**, selecione **Formulário**.
1.  Selecione **+ Novo formulário**.
1.  Na tela **Adicionar um formulário**, configure da seguinte maneira:
    - **Escolha uma tabela:** Evento
    - **Selecione um formulário:** Criar Evento
    - **Nomeie sua cópia do formulário selecionado:** Criar Evento
1. Selecione a guia **Dados** e verifique se **Dados deste formulário** está definido como **Criar um registro**.
1. Selecione a guia **Ao enviar**. No campo **Exibir esta mensagem**, insira *`Your event has been successfully submitted.`*
1. Selecione o botão **OK**.

    Vamos remover seções adicionais da página, pois não precisamos delas.

1. Selecione a **Seção ** abaixo do **Formulário** que você acabou de adicionar. Na barra de ferramentas exibida, selecione Mais **(…)** e escolha **Excluir**.
1. Repita a etapa anterior para remover as duas seções restantes da página.

    Depois de concluído, os únicos itens que devem permanecer são o formulário que você criou e o rodapé na parte inferior da página.

1. Em **Navegação principal** à esquerda, selecione as Reticências ao lado da **Nova Página** que você criou.
1. No menu exibido, selecione **Configurações da Página**.
1. Configure as definições da página da seguinte maneira:
    - **Nome:** Novo Evento
    - **URL Parcial:** New-Events
1. Selecione o botão **OK**.

    Em seguida, adicionaremos uma página adicional que pode ser usada para exibir um evento individual.

1.  Verifique se você ainda tem **Páginas** selecionado e clique no botão **+ Página**.
1.  Na tela **Descreva uma página para criá-la**, insira: *`Add a Blank Page named View Event.`* Selecione o botão **Enviar**.
1.  Selecione o botão **Manter** para aceitar a nova página.
1.  Na parte superior da nova página, selecione o botão **Adicionar uma Seção**.
1.  Selecione **1 Coluna**.
1.  Em **Escolher um componente para adicionar a esta seção**, selecione **Formulário**.
1.  Selecione **+ Novo formulário**.
1.  Na tela **Adicionar um formulário**, configure da seguinte maneira:
    - **Escolha uma tabela:** Evento
    - **Selecione um formulário:** Exibir Evento
    - **Nomeie sua cópia do formulário selecionado:** Exibir Evento
1.  Selecione a guia **Dados** e defina o campo **Dados para este formulário** como **É somente leitura**.
1. Selecione o botão **OK**.

    Vamos remover seções adicionais da página, pois não precisamos delas.

1. Selecione a **Seção ** abaixo do **Formulário** que você acabou de adicionar. Na barra de ferramentas exibida, selecione Mais **(…)** e escolha **Excluir**.
1. Repita a etapa anterior para remover a seção restante da página.
1. Em **Navegação principal** à esquerda, selecione as **Reticências** ao lado da nova página que você criou.
1. No menu exibido, selecione **Configurações da Página**.
1. Configure as definições da página da seguinte maneira:
    - **Nome:** Exibir Evento
    - **URL Parcial:** View-Events
1. Selecione o botão **OK**.

    Por fim, vamos criar mais um formulário de página da Web que podemos usar para editar um evento.

1.  Verifique se você ainda tem **Páginas** selecionado e clique no botão **+ Página**.
1.  Na tela **Descreva uma página para criá-la**, insira: *`Add a Blank Page named Edit Event.`* Selecione o botão **Enviar**.
1.  Selecione o botão **Manter** para aceitar a nova página.
1.  Na parte superior da nova página, selecione o botão **Adicionar uma Seção**.
1.  Selecione **1 Coluna**.
1.  Em **Escolher um componente para adicionar a esta seção**, selecione **Formulário**.
1.  Selecione **+ Novo formulário**.
1.  Na tela **Adicionar um formulário**, configure da seguinte maneira:
    - **Escolha uma tabela:** Evento
    - **Selecione um formulário:** Criar Evento
    - **Nomeie sua cópia do formulário selecionado:** Editar Evento
1.  Selecione a guia **Dados** e defina **Dados para este formulário** como **Atualiza um registro existente**.
1. Selecione o botão **OK**.

    Vamos remover seções adicionais da página, pois não precisamos delas.

1. Selecione a **Seção ** abaixo do **Formulário** que você acabou de adicionar. Na barra de ferramentas exibida, selecione Mais **(…)** e escolha **Excluir**.
1. Repita a etapa anterior para remover as seções restantes da página.
1. Selecione o botão **OK**.

## Tarefa 5: Criar uma página que exibe uma lista de eventos

Agora que definimos os formulários necessários que usaremos para gerenciar registros, criaremos uma exibição de página para exibir esses registros.

1.  Selecione o botão **+ Página**.

1.  Na tela **Descreva uma página para criá-la**, insira: *`Add a blank page called events.`* Selecione o botão **Enviar**.
1.  Selecione **Manter** para aceitar a nova página.
1.  Na parte superior da nova página, selecione o botão **Adicionar uma Seção**.
1.  Selecione **1 Coluna**.
1.  Em **Escolher um componente para adicionar a esta seção**, selecione o botão **Mais** *(…)*. No grupo **Dados conectados**, selecione **Lista**.
1.  Na tela **Adicionar uma lista**, selecione a guia **Configurar** e configure da seguinte maneira:
    - **Escolha uma Tabela:** Evento
    - **Selecionar as exibições de dados:** Eventos Ativos, Eventos Inativos
    - **Dê um nome à lista:** `Events`
1.  Selecione a guia **Ações** e configure da seguinte maneira:
    - **Criar um registro:** Ativado
        - **Tipo de Destino:** Formulário
        - **Formulário:** Criar Evento
        - **Exibir rótulo:** `Create New Event`
    - **Detalhes da exibição:** Ativado
        - **Tipo de Destino:** Formulário
        - **Formulário:** Exibir Evento
        - **Exibir rótulo:** `See Event Details`
    - **Editar registro:** Ativado
        - **Tipo de Destino:** Formulário
        - **Formulário:** Editar Evento
        - **Exibir rótulo:** `Edit Event`
1. Selecione **Concluído**.

## Tarefa 6: Atualizar permissões

Para garantir que os usuários vejam apenas dados relevantes para eles, as organizações podem especificar permissões de tabela. Nesta tarefa, vamos criar permissões muito básicas que dão acesso a qualquer pessoa.

1.  Em **Navegação Principal**, selecione a página **Eventos**.
1.  Selecione a lista **Eventos** e clique no botão **+ Nova permissão**.
1.  Configure a permissão da seguinte maneira:
    -   **Nome:** Eventos
    -   **Tabela:** Evento
    -   **Tipo de Acesso:** Acesso global
1.  Defina a **Permissão** como **Leitura**.
1.  Selecione **Adicionar funções** e escolha as funções **Administradores**, **Usuários Anônimos** e **Usuários Autenticados**.
1.  Selecione o botão **Salvar**.
1.  Se uma tela que diz **Os dados podem ser vistos por qualquer pessoa** aparecer, selecione **Salvar**.

    Vamos repetir esse processo para as páginas de formulário do evento. Começaremos com a página **Novo Evento**

1.  Em **Navegação Principal**, selecione a página **Novo Evento**.
1.  Selecione o botão **Atualizar permissão**.
1.  Configure a permissão da seguinte maneira:
    -   **Nome:** Criar eventos
    -   **Tabela:** Evento
    -   **Tipo de Acesso:** Acesso global
1.  Defina a **Permissão** como **Leitura** e **Criar**.
1.  Selecione **Adicionar funções** e escolha as funções **Administradores**, **Usuários Anônimos** e **Usuários Autenticados**.
1.  Selecione o botão **Salvar** e selecione **Salvar** novamente na tela pop-up.

    Em seguida, vamos definir para a tela **Editar Evento**.

1.  Em **Navegação Principal**, selecione a página **Editar Evento**.
1.  Selecione o botão **Atualizar permissão**.
1.  Configure a permissão da seguinte maneira:
    -   **Nome:** Criar eventos
    -   **Tabela:** Evento
    -   **Tipo de Acesso:** Acesso global
1.  Defina a **Permissão** como **Leitura** e **Atualizar**.
1.  Selecione **Adicionar funções** e escolha as funções **Administradores**, **Usuários Anônimos** e **Usuários Autenticados**.
1.  Selecione o botão **Salvar** e selecione **Salvar** novamente na tela pop-up.

## Tarefa 7: Atualizar a navegação do site

Agora que temos nossas páginas e itens formatados da maneira desejada, vamos ajustar a navegação do site adequadamente.

1.  Em **Navegação Principal**, selecione as **Reticências** ao lado da página **Evento**.

1.  No menu exibido, selecione **Mover para cima**.
1.  Repita a etapa até a página **Evento** localizada abaixo da página **Contato**.
1.  Verifique se a página **Novo Evento** está localizada diretamente abaixo da página **Eventos**. *(Se não estiver, mova a página Novo Evento até que esteja.)*
1.  Na página **Novo Evento**, selecione o botão **Reticências**.
1.  No menu exibido, selecione **Tornar em subpasta**.
1.  Selecione as Reticências ao lado de **Exibir Evento** e selecione **Mover para Outras Páginas**.
1.  Selecione as Reticências ao lado de **Editar Evento** e selecione **Mover para Outras Páginas**.
1.  Na **Barra de comandos**, selecione o botão **Sincronizar**.

## Tarefa 8: Visualizar e refinar o site

Depois que o site for criado, você desejará revisá-lo para garantir que atenda às suas necessidades e requisitos de negócios para que possa determinar os refinamentos necessários. Os sites podem ser visualizados nos modos Desktop e Móvel

1.  No estúdio de design, selecione o botão **Início**.
1.  Clique em **Visualizar** na barra de comandos.
1.  Selecione **Desktop** para visualizar o site em um navegador.
1.  Durante a exibição no modo **Desktop**, examine os seguintes aspectos do seu site, como:
    -   Layout e navegação.
    -   Elementos de identidade visual, como cores, fontes e logotipos.
1.  Quando terminar de testar o site, feche a **Guia do navegador** para voltar ao editor do site.

    Em seguida, visualizaremos o site como ele seria exibido em dispositivos móveis.

1.  Selecione o botão **Visualizar** novamente.
1.  Leia o **Código QR** exibido com seu dispositivo móvel.
1.  O site será aberto em seu dispositivo móvel *(Observação: você pode ser solicitado a fazer logon. Se for o caso, forneça suas credenciais de logon.)*
1.  Assim como fez no modo Desktop, examine os seguintes aspectos do seu site, como:
    - Layout e navegação.
    - Elementos de identidade visual, como cores, fontes e logotipos.
1. Quando terminar de testar, feche a guia do navegador para voltar ao site.
