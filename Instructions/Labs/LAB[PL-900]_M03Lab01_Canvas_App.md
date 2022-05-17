---
lab:
  title: 'Laboratório 2: Como criar um aplicativo de tela'
  module: 'Module 3: Get started with Power Apps'
ms.openlocfilehash: 24d99d14079d40f74a43ed0de64dd6ae5d7046c7
ms.sourcegitcommit: 0118c25a230425d0ccba16e6c3922053ee07c183
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2022
ms.locfileid: "144810915"
---
# <a name="module-3-get-started-with-power-apps"></a>Módulo 3: Introdução ao Power Apps
## <a name="lab-how-to-build-a-canvas-app"></a>Laboratório: Como criar um aplicativo de tela

# <a name="scenario"></a>Cenário

O Bellows College é uma organização educacional que possui um campus com vários edifícios. Atualmente, as visitas ao campus são registradas em diários de papel. As informações não são coletadas de forma consistente e não há meios de analisar os dados sobre as visitas em todo o campus.

Atualmente, a administração do campus está usando uma planilha do Excel para acompanhar o registro de visitantes. Eles querem modernizar o sistema de registro de visitantes, em que o controle de acesso aos edifícios é feito pelo pessoal de segurança e todas as visitas precisam ser registradas previamente e gravadas pelos anfitriões.

Ao longo deste curso, você vai criar aplicativos e fazer automações para permitir que a administração e a equipe de segurança do Bellows College gerenciem e controlem o acesso aos edifícios no campus.

# <a name="high-level-lab-steps"></a>Macroetapas do laboratório

Seguiremos o esquema abaixo para projetar o aplicativo de tela:

-   Criar um aplicativo de tela com base nos dados na tabela Visita

-   Configurar como as visitas são mostradas na tela de navegação

-   Fazer algumas alterações básicas no aplicativo

-   Testar a funcionalidade do aplicativo

## <a name="prerequisites"></a>Pré-requisitos

-   Conclusão do **Módulo 0 Laboratório 0 - Validação do ambiente de laboratório**

# <a name="exercise-1-create-visits-app"></a>Exercício \#1: Criar Aplicativo de Visitas

**Objetivo:** Neste exercício, você criará um aplicativo de tela conectando a tabela Inicial das Visitas criada anteriormente.

## <a name="task-1-create-a-visits-app"></a>Tarefa \#1: Criar um Aplicativo de Visitas

1.  Navegue até <https://make.powerapps.com>. Talvez seja necessário reautenticar - clique em **Entrar** e siga as instruções, se necessário.

2.  No canto superior direito, selecione o ambiente **Prática [minhas iniciais]** se ainda não tiver selecionado.

3.  Se necessário, clique no ícone **Página Inicial** no lado esquerdo da tela. Na seção **Iniciar em**, selecione **Dataverse**.

4.  Selecione a conexão do Dataverse. 

    >   **Observação:** *Se não houver uma conexão do Dataverse:*
    >   -   Selecione **Nova Conexão**
    >   -   Localize o **Microsoft Dataverse**
    >   -   Clique em **Criar**

5.  Localize e selecione a tabela **Visitas** criada no laboratório anterior.

6.  Selecione o botão **Conectar** no canto inferior direito.

7.  Após o aplicativo ser criado, na tela Boas-vindas ao Power Apps Studio, marque a caixa **Não mostrar isso novamente** e selecione **Ignorar**.

8.  Após a criação ser concluída, ele deve ser semelhante à imagem abaixo.

![Aplicativo de tela criado com base nos dados de Visita.](media/2-canvas-app-from-data.png)

9. No designer de aplicativo, selecione o botão **visualizar aplicativo** (ícone Executar) na barra de comandos. *(Você também pode visualizar o aplicativo pressionando F5 no teclado.)* Dê uma olhada no aplicativo e veja como ele se comporta na configuração inicial pelo usuário.

10. Feche a visualização do aplicativo clicando em **X** no canto superior direito da tela.

Parabéns, você criou com êxito um Power App usando uma tabela do Dataverse. A próxima etapa do processo é personalizar o aplicativo para que ele corresponda à identidade visual da faculdade. A próxima série de etapas ajudará você a fazer personalizações extra no aplicativo.

## <a name="task-2-modify-and-theme-the-newly-created-app"></a>Tarefa \#2: Modificar e criar um tema para o aplicativo recém-criado

Nesta tarefa, você personalizará o texto do cabeçalho em cada uma das três telas do aplicativo (Procurar, Detalhes e Editar) e alterará o tema do aplicativo.

1.  Você está na tela Procurar. Selecione o rótulo **Visitas** na tela.

3.  No lado direito da tela, na guia Propriedades, atualize a propriedade de controle **Texto** para **"Visitas a Bellows College"** .

4. Nas propriedades, altere o **Tamanho da fonte** para **24**.

4.  Clique no fundo em branco para ver o texto atualizado na tela de navegação.

5.  Usando a navegação à esquerda, selecione **DetailScreen1**.

5.  Selecione o rótulo **Visitas** na tela.

6.  No lado direito da tela, na guia Propriedades, atualize a propriedade de controle **Texto** para **"Detalhes da visita"** .

7.  Clique no fundo em branco para ver o texto atualizado na tela Detalhes.

8.  Usando a navegação à esquerda, selecione **EditScreen1** (talvez seja necessário rolar a tela para ver isso no modo de exibição de árvore).

9.  Selecione o rótulo **Visitas** na tela.

10.  No lado direito da tela, na guia Propriedades, substitua o texto Table1 na propriedade de controle **Texto** por **"Editar detalhes"** .

11.  Clique no fundo em branco para ver o texto atualizado na tela Editar.

12. Usando a navegação à esquerda, selecione **BrowseScreen1**.

13. Na barra de ferramentas de comando, selecione o botão **Tema** e, na lista exibida, selecione a cor do tema **Vermelho**.

## <a name="task-3-test-your-visits-app"></a>Tarefa \#3: Testar o aplicativo de Visitas

Nesta tarefa, você testará seu novo aplicativo.

1.  Com o aplicativo aberto no Designer de Aplicativo, selecione **Arquivo**, atualize o nome do aplicativo para **Aplicativo de Visitas** e selecione **Salvar**.

2.  Selecione a seta **voltar** para retornar ao seu aplicativo.

3.  Usando a navegação à esquerda, selecione **BrowseScreen1**.

4.  No designer de aplicativo, selecione o botão **visualizar aplicativo** (ícone Executar) na barra de comandos. *(Você também pode visualizar o aplicativo pressionando F5 no teclado.)*

4.  Quando o aplicativo for aberto, no campo **Pesquisar Itens**, insira o texto **Maria**
     *(observe como os itens na galeria são filtrados com base no que é digitado no campo de pesquisa).*

5.  Assim que o registro **Contoso Suites** para **Clara Barbosa** for exibido, clique na linha do navegador para abrir os detalhes dessa visita. (**Observação**: *se mais de um registro de Maria Campbell do Contoso Suites for exibido, selecione qualquer um deles*)

6.  Para editar o registro, selecione o **Ícone de lápis** no canto superior direito do aplicativo.

7.  Você pode editar o nome da visita aqui e clicar no ícone de marca de seleção no canto superior direito para salvar a alteração.

8.  No canto superior direito da tela, clique no ícone **X** para retornar ao editor do aplicativo de tela.

Parabéns! Você criou e configurou seu primeiro aplicativo de tela.

# <a name="challenges"></a>Desafios

-   Adicione as seguintes colunas aos formulários em DetailScreen1 e EditScreen1: Início real, Término real, Código, Início agendado e Término agendado
