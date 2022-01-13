---
lab:
    title: 'Laboratório 5: Como criar um portal do Power Apps'
    module: 'Módulo 3: Introdução ao Power Apps'
---

# Módulo 3: Introdução ao Power Apps

## Laboratório 4: Como criar um portal do Power Apps

# Cenário

O Bellows College é uma organização educacional que possui um campus com vários edifícios. Atualmente, as visitas ao campus são registradas em diários de papel. As informações não são coletadas de forma consistente e não há meios de analisar os dados sobre as visitas em todo o campus.

A administração do campus quer fornecer aos visitantes informações sobre os prédios do campus. Os visitantes poderão ver a lista de prédios em um site, que será construído usando um portal do Power Apps.

Neste laboratório, você vai disponibilizar um portal do Power Apps e criar uma página da Web de portais que mostra uma lista com os prédios do campus.

# Macroetapas do laboratório

Seguiremos o esquema abaixo para projetar o portal do Power Apps:

* Provisionar um portal do Power Apps no ambiente do Dataverse
* Criar e configurar uma página da Web para mostrar a lista de prédios
* Criar um novo tema e aplica-lo ao portal

## Pré-requisitos

* Conclusão do **Módulo 0 Laboratório 0 - Validação do ambiente de laboratório**
* Conclusão do **Módulo 2 Laboratório 1 - Introdução ao Microsoft Dataverse**

## Considerações antes de começar

* Os aplicativos de portais do Power Apps são sempre iniciados a partir de um modelo em vez de um aplicativo em branco. O portal já deve ter sido criado no Módulo 0 Laboratório 0. Quando você provisionar um portal, ele já tem páginas, menus e um tema padrão. 

# Exercício \#1: criar uma página da Web do portal

**Objetivo:** neste exercício você vai criar uma nova página da Web que exibe alguns conteúdos estáticos, bem como uma lista de prédios do Dataverse.

## Tarefa 1: navegar até o portal

1.  Acesse <https://make.powerapps.com>.

2.  Confirme se você está no seu ambiente de prática. Se não estiver, troque de ambiente (no canto superior direito).

3.  Clique em **Aplicativos**.

4.  Localize o aplicativo que tem o **Tipo** igual a **Portal**

5.  Clique no nome do aplicativo para abrir o portal

    > Você deve ser redirecionado para a página de aterrissagem do site do portal com uma mensagem de boas-vindas. Navegue pelo portal para ver o que foi criado por padrão quando você provisionou o portal. 

## Tarefa 2: criar uma página da Web

1.  Abra o Estúdio dos portais do Power Apps

    -   Entre em <https://make.powerapps.com> (confira se já está aberto nas suas guias).

    -   Selecione **Aplicativos**.
    
    -   Localize o aplicativo que tem o **Tipo** igual a **Portal**

    -   Clique nas reticencias (**...**) à direita do nome do aplicativo de portais e selecione **Editar**.

    > Agora você está no Estúdio dos portais do Power Apps. É aqui que você pode modificar e criar o conteúdo do portal.

2.  Crie uma página nova.

    -   Na barra de comando, selecione **Nova página**.

    - Selecione **Página de aterrissagem**

3.  No painel de propriedades, em **Exibição**, troque o **Nome** de **Nova página nova (1)** para `Building Directory`.

4.  Em **URL parcial**, troque o valor para `building-directory` e pressione a tecla Tab (para iniciar o salvamento automático).

    > O título da página agora deve ser **Diretório de prédios**.
    
## Tarefa 3: adicionar conteúdos estáticos

1.  Adicione uma seção à página da Web.

    - Na tela (área que exibe a página da Web), selecione um,a seção da página que não é uma coluna.

    -   Na caixa de ferramentas (lado esquerdo), selecione o ícone **Componentes**.

    -   Escolha **Seção com duas colunas** na área **Layout da seção**.

2.  Adicione textos estáticos.

    -   Na tela (área que exibe a página da Web), selecione a coluna à esquerda

    -   Na caixa de ferramentas (lado esquerdo), selecione o ícone **Componentes**.

    -   Selecione **Texto** na área **Componentes do portal**.

    -   Na nova área de texto, insira o seguinte texto:
          ```
          The following is the building directory.
          ```
    -   Selecione a caixa de texto acima daquela que você acabou de editar e clique em **Excluir** na barra de comandos para remover o texto padrão.

3. Adicione uma Imagem.

    -   Na tela (área que exibe a página da Web), selecione a coluna à direita

    -   Na caixa de ferramentas (lado esquerdo), selecione o ícone **Componentes**.

    -   Selecione **Imagem** na área **Componentes do portal**.

    - No painel de propriedades, clique em **Selecionar uma imagem**. Localize e selecione **Pages.png**
    
    -   No painel de propriedades, clique no menu suspenso da seção **Formatação** e troque a **Largura** para 70% (lembre-se de digitar o símbolo %). Faça as alterações no dimensionamento da imagem até atingir o resultado desejado.

4.  Configure os direitos para exibir a lista de prédios 

    -   No menu esquerdo, clique em Configurações (símbolo de engrenagem) e selecione **Ver mais configurações**. Isso abrirá as configurações adicionais em uma nova guia.

    -   No menu esquerdo, role para baixo até **Segurança** e selecione **Permissões de tabela**.

    -   Clique em **Novo** e adicione os seguintes valores:

        -   **Nome**: Mostrar lista de prédios
        -   **Nome da tabela**: Selecione Prédio (bc_building) do menu suspenso no lado direito.
        -   **Site**: Clique na Lupa e selecione o seu site (Bellows College Visitors – [seu nome])
        -   **Tipo de acesso**: Global
        -   **Privilégios**: Leitura
    
    -   No menu superior, selecione **Salvar**.
    
    -   Role para baixo até a seção **Funções da Web** e **Adicione uma função da Web existente**.
    
    -   Clique na lupa, selecione **Usuários Anônimos** e clique em **Adicionar**.
    
    -   No menu superior, selecione **Salvar e fechar**.
    
    -   Volte para a guia anterior.

5.  Clique em **Navegar pelo site** para ver como a página está.  Agora existe uma opção **Diretório de prédios** no menu principal.

    > Você precisa configurar o navegador para aceitar pop-ups.

## Tarefa 4: adicionar um componente de lista

1.  Volte até a guia anterior e continue a partir da etapa 2. Se não for possível, siga as etapas abaixo para retornar a esse local.

    -   Entre em <https://make.powerapps.com> (confira se já está aberto nas suas guias).

    -   Localize o aplicativo que tem o **Tipo** igual a **Portal**

    -   Clique nas reticências (**...**) e escolha **Editar**.
    
    -   Na caixa de ferramentas (lado esquerdo), selecione a opção **Páginas**. 

    -   Localize e selecione a página **Diretório de prédios** criada anteriormente.
    
2.  Adicione uma lista de componentes à página Lista de prédios.

    -   Selecione a seção com as duas colunas.

    -   Na caixa de ferramentas (lado esquerdo), selecione o ícone **Componentes**.

    -   Escolha **Seção com uma coluna** na área **Layout de seção** (uma seção será exibida abaixo da imagem e do texto na página da Web).

    -   Selecione a nova seção de coluna na tela.

    -   Na caixa de ferramentas (lado esquerdo), selecione o ícone **Componentes**.

    -   Escolha **Lista** na área **Componentes do portal** (uma lista será exibida na nova seção).
    
3.  Configure o componente da lista.

    -   Selecione o componente lista na tela.

    -   No painel de propriedades (lado direito), digite `Buildings List` no campo **Nome**

    -   No campo **Tabela**, escolha **Building (bc_building)** na lista suspensa.

    -   Em **Visualizações**, escolha **Prédios ativos**.

    -   Não mexa nas demais as configurações padrão
    
4.  Clique em **Navegar pelo site** para visualizar a página. 

    > A lista de prédios do seu banco de dados Dataverse é exibida na página da Web.

# Exercício \#2: mudar o tema do portal

**Objetivo:** Neste exercício você vai criar um novo tema para alterar o esquema de cores do portal. 

## Tarefa 1: aplicar e editar um tema

1.  Volte até a guia anterior e continue a partir da etapa 2. Se não for possível, siga as etapas abaixo para retornar a esse local.

    -   Entre em <https://make.powerapps.com> (confira se já está aberto nas suas guias).

    -   Localize o aplicativo que tem o **Tipo** igual a **Portal**

    -   Clique nas reticências (**...**) e escolha **Editar**.
    
2.  Aplique e personalize um tema básico.

    -   Na caixa de ferramentas (lado esquerdo), selecione o ícone **Temas**.
    
    - Verifique se a opção de **Habilitar tema básico** está ativada.
    
    -   Em uma das predefinições, clique nas reticências (**...**) e escolha **Personalizar**.
    
    -   É criada uma cópia do tema básico. 
    
    -   No painel de propriedades, troque as cores e analise o impacto das alterações no seu portal.
    
    -   Renomeie o tema.
    
3.  Na barra de comando, clique em **Configuração de sincronização**.

O layout do aplicativo deve ser similar ao exibido abaixo:

![Exemplo de portal](media/9-portallabresult.jpg)

# Desafios

* Crie uma exibição diferente dos Prédios que mostra somente o Nome do prédio. Selecione **Navegar pelo site** no estúdio do portal para ver as alterações.
* Na caixa de ferramentas, clique no ícone **Temas** e edite o CSS do seu tema personalizado.
* Crie uma página com o componente **Formulário** e modifique o componente **Lista** para adicionar ou editar linhas do Dataverse com o formulário.
* Ative as **Permissões da entidade** nas **Configurações** de um componente **Lista**. O que acontece com os dados?
* No estúdio do portal, selecione o ícone Editor de código-fonte `</>` para ver o código-fonte da página. Se você conhecer HTML, faça algumas modificações e visualize os resultados.
