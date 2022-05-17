---
lab:
  title: 'Laboratório 3: Como criar um aplicativo baseado em modelo'
  module: 'Module 3: Get started with Power Apps'
ms.openlocfilehash: 56a807c49479c245f95e3af9566450651bcc3ebb
ms.sourcegitcommit: 99acd470de1164d438d7c4794faa28d6489c39db
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2022
ms.locfileid: "144812443"
---
# <a name="module-3-get-started-with-power-apps"></a>Módulo 3: Introdução ao Power Apps
## <a name="lab-how-to-build-a-model-driven-app"></a>Laboratório: Como criar um aplicativo baseado em modelo

# <a name="scenario"></a>Cenário

O Bellows College é uma organização educacional que possui um campus com vários edifícios. Atualmente as visitas ao campus são anotadas em papel. As informações não são coletadas de forma consistente e não há meios de analisar os dados sobre as visitas em todo o campus.

A administração do campus quer modernizar o sistema de registro de visitantes, com controle do acesso aos edifícios pelo pessoal de segurança, além de exigência de notificação prévia e registro de todas as visitas pelos anfitriões.

Ao longo deste curso, você vai criar aplicativos e fazer automações para permitir que a administração e a equipe de segurança do Bellows College gerenciem e controlem o acesso aos edifícios no campus.

Neste laboratório, você criará um aplicativo baseado em modelo do Power Apps para permitir que a equipe de apoio gerencie os registros de visitação de todo o campus.

# <a name="high-level-lab-steps"></a>Macroetapas do laboratório

Você fará o seguinte para criar o aplicativo baseado em modelo:

-   Crie um novo aplicativo baseado em modelo denominado Gerenciamento de campus

-   Editar a navegação do aplicativo para fazer referência às tabelas necessárias

-   Personalize os formulários e as exibições das tabelas necessárias para o aplicativo

Vamos trabalhar com os seguintes componentes:

-   **Exibições**: As exibições permitem que o usuário exiba os dados atuais na tabela do formulário.

-   **Formulários**: É onde o usuário cria/atualiza novas linhas nas tabelas.

Ambos serão integrados ao aplicativo baseado em modelo para oferecer uma melhor experiência do usuário.

## <a name="prerequisites"></a>Pré-requisitos

-   Conclusão do **Módulo de Laboratório 0 – Validar ambiente de laboratório**

-   Conclusão do **Módulo de Laboratório 2 – Modelagem de dados**

-   Conclusão do **Módulo de Laboratório 3 – Como criar um aplicativo de tela**

## <a name="things-to-consider-before-you-begin"></a>Considerações antes de começar

-   Que mudanças precisamos fazer para melhorar a experiência do usuário?

-   O que precisamos incluir em um aplicativo baseado em modelo de acordo com o modelo de dados que criamos?

-   Quais personalizações podem ser feitas no mapa do site de um aplicativo baseado em modelo?

# <a name="exercise-1-customize-views-and-forms"></a>Exercício 1: Personalizar exibições e formulários

**Objetivo:** Neste exercício, você vai personalizar as exibições e os formulários das tabelas personalizadas que serão usadas no aplicativo baseado em modelo.

## <a name="task-1-edit-visit-form"></a>Tarefa 1: Editar o formulário de visitas

1.  Entre para <https://make.powerapps.com> se você ainda não tiver entrado.

2.  No canto superior direito, selecione o ambiente **Prática [minhas iniciais]** se ainda não tiver selecionado.

3.  Usando a navegação à esquerda, expanda **Dataverse**, selecione **Tabelas** e clique para abrir a tabela **Visita**.
>   Se você não vir a tabela Visitas, verifique se está no ambiente correto (etapa 2).

4.  Selecione a guia **Formulários** e clique para abrir o formulário Informações com o tipo de formulário **Principal**.
>   **IMPORTANTE:** *Como, por padrão, todos os formulários são denominados Informações, verifique se o formulário selecionado tem um Tipo de formulário* **Principal** *e não outro.*
Por padrão, o formulário tem dois campos: Nome (campo principal) e proprietário.

5.  No lado direito da tela no painel Propriedades, selecione o campo **Nome de Exibição** e altere-o para **Informações Principais**.

6.  Usando o menu na parte superior da tela, selecione **+ Campo de formulário** e adicione os seguintes campos abaixo do campo **Proprietário** arrastando as colunas para o formulário ou apenas clicando nos nomes das colunas:

    1.  **Visitante**

    2.  **Início agendado**

    3.  **Fim agendado**

    4.  **Início real**

    5.  **Término real**

7.  Arraste a coluna **Código** e solte-a no cabeçalho do formulário.

    >   O cabeçalho é a área superior direita do formulário. Pode ser necessário recolher o painel Propriedades do lado direito da tela para ver o campo no formulário.

8.  Com o campo **Código** ainda selecionado, marque a caixa de seleção **Somente leitura** no painel Propriedades no lado direito da tela.

9.  Selecione o campo **Proprietário**. No painel Propriedades, altere o **Rótulo** para **Anfitrião**

10.  Clique em **Salvar** na parte superior direita e espere salvar para concluir.

11.  Clique em **Publicar** na parte superior direita e espere publicar para concluir.

12.  Se a visualização de edição foi aberta em uma nova guia ou janela do navegador, feche-a. Caso contrário, clique em **Voltar** na parte superior esquerda da tela. Agora você deve estar de volta à guia Formulários das tabelas de Visitas.

## <a name="task-2-edit-active-visits-view"></a>Tarefa \#2: Editar a exibição Visitas ativas

Nesta tarefa, vamos modificar a exibição Visitas ativas e criar uma nova exibição para as visitas de hoje.

1.  Selecione a guia **Exibições** e clique para abrir a exibição **Visitas ativas**.

2.  Inclua os campos a seguir à exibição ao clicar ou arrastar e soltar os campos:

    1.  **Código**

    2.  **Visitante**

    3.  **Início agendado**

    4.  **Fim agendado**

3.  Clique na coluna **Criado em** e selecione **Remover**. O campo **Criado em** será removido da exibição.

4.  Redimensione as larguras das colunas para ajustar os dados.

5.  Clique em **Salvar** e espere as alterações serem salvas.

6.  Clique em **Publicar** e espere a conclusão da publicação.

## <a name="task-3-create-new-view-for-todays-visits"></a>Tarefa \#3: Criar exibição para as visitas do dia

Agora, vamos clonar a exibição e criar uma nova para as visitas de hoje.

1.  Clique na **seta da lista suspensa** ao lado do botão Salvar (cuidado para não pressionar o botão) e selecione **Salvar como**.

2.  Altere o nome para **Visitas de hoje** e pressione **Salvar**.

3.  Clique no link **Editar filtros** no painel Propriedades.

2.  Clique em **Adicionar** e selecione **Incluir linha**.

3.  Selecione **Início agendado** como um campo, depois selecione **Hoje** como a condição na lista suspensa.

4.  Clique em **...** na linha **Status** e clique em **Excluir** para excluir essa condição de filtro.

5.  Pressione **Ok** para salvar a condição. A exibição agora é filtrada para mostrar somente registros em que a data de Início agendado é hoje.

6.  Inclua os campos **Início real** e **Fim real** à exibição.

> **Observação:** como não filtramos mais no status de exibição, obteremos todas as visitas de hoje incluindo as concluídas. Esses campos ajudarão a diferenciar as visitas concluídas e as visitas em andamento.

7.  Clique em **Salvar**.

8.  Clique em **Publicar** e espere a conclusão da publicação.

# <a name="exercise-2-create-model-driven-application"></a>Exercício 2: Criar aplicativo baseado em modelo

**Objetivo:** Neste exercício, você vai criar o aplicativo baseado em modelo, personalizar o mapa do site e testar o aplicativo.

>   Para simplificar e economizar tempo, não abordaremos algumas das colunas de Visita neste laboratório. 

## <a name="task-1-create-application"></a>Tarefa 1: Criar aplicativo

1.  Entre em <https://make.powerapps.com> (se ainda não tiver entrado).

2.  No canto superior direito, selecione o ambiente **Prática [minhas iniciais]** se ainda não tiver selecionado.

3.  Criar o aplicativo baseado em modelo:

    1.  Selecione **Aplicativo em branco** na seção **Iniciar em** da tela Página Inicial.

    2.  Em **Aplicativo em branco baseado no Dataverse**, selecione **Criar**.

    3.  Selecione a experiência **Designer de aplicativo moderno**.
    
    4.  Selecione **Criar**.
    
    5.  Insira **Administração do campus Bellows** como nome e selecione **Criar**.

4.  Quando o novo aplicativo baseado em modelo for carregado, selecione o botão **+ Adicionar Página**.

5.  Na tela Adicionar Página, escolha **Exibição e formulário baseados em tabela** e selecione o botão **Avançar**.

6.  Adicione as seguintes tabelas:

    1.  Visite

    2.  Contact

7.  Depois de selecionar as duas tabelas, selecione **Adicionar**.

8.  Usando os ícones de navegação no lado esquerdo da tela, selecione **Navegação**.

9.  No painel de navegação, selecione **Grupo 1** abaixo, na Barra de navegação.

10.  No lado direito da tela, na seção **Exibir Opções**, altere a propriedade **Título** para **Segurança**.

## <a name="task-2-edit-your-app"></a>Tarefa \#2: Editar o aplicativo
Agora que todos os componentes necessários foram adicionados ao aplicativo baseado em modelo, organizaremos os itens.

1.  No Painel de Navegação, no grupo de segurança, selecione **SubArea1**.

2.  Selecione as **Reticências** e, no menu exibido, selecione para remover **SubArea1**.

3.  Use a navegação à esquerda da tela e selecione **Páginas**.

4.  Localize e expanda **Visitas** no painel Páginas.

5.  Selecione **Formulário de visita**.

6.  No lado direito da tela, selecione **Gerenciar formulários**.

7.  Selecione o formulário **Informações principais** e clique em **Salvar**.

8.  Em **Visitas** no painel de Páginas, selecione **Visualizar visita**.

9.  No lado direito da tela, selecione **Gerenciar exibições**.

10. Selecione os formulários **Visitas de hoje** e **Visitas ativas** e selecione **Salvar**.

11. Selecione **Salvar**.

12. Depois de **Salvar**, selecione o botão **Publicar** para publicar as alterações.

## <a name="task-3-test-application"></a>Tarefa \#3: Testar o aplicativo

1.  Iniciar o aplicativo

    1.  Selecione **Executar** para abrir o aplicativo em uma nova janela.

2.  Criar um novo contato

    1.  O aplicativo abrirá a exibição **Meus Contatos Ativos** Se isso não acontecer, selecione Visitas à esquerda. 

    2.  Clique em **Novo** no menu superior.

    3.  Informe o **Nome** como `John` e **Sobrenome** como `Doe`.

    4.  Informe seu email pessoal como **e-mail**. Isso será usado em um laboratório futuro em que você receberá um email. 

    5.  Clique em **Salvar e Fechar**.

    6.  Agora, você verá o contato criado na exibição **Contatos ativos**.

4.  Criar uma nova visita

    1.  Selecione **Visitas** no mapa do site.

    2.  Clique em **Nova**.

    3.  Preencha os campos da seguinte maneira

        1.  **Nome**: `New test visit`

        2.  **Visitante**: selecione João Silva

        3.  **Início agendado**: selecione a data de amanhã e 14h como hora de início

        4.  **Fim agendado**: selecione a data de amanhã e 15h30 como hora de término

    4.  Clique em **Salvar e Fechar**. A visita será criada e você poderá vê-la na Exibição de visitas ativas.

    5.  Altere a exibição para **Visitas de hoje**. Você não verá mais a nova visita na exibição, pois ela foi agendada para amanhã.

5.  Você pode adicionar mais registros de teste.

    O aplicativo em execução deve ser parecido com o seguinte:

![](media/3-model-driven-app.png)

Parabéns! Você criou e configurou seu primeiro aplicativo controlado por modelos.

# <a name="challenges"></a>Desafios

-   Selecionar exibições e formulários específicos para Contatos
