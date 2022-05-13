---
lab:
  title: 'Laboratório 3: Como criar um aplicativo de tela'
  module: 'Module 3: Get started with Power Apps'
ms.openlocfilehash: 0ac0874e80deb74b8a4cf0c8075adf6c9b14e375
ms.sourcegitcommit: fc79a9b68a8235b37fd90ef84ba8ae1aa2e581f5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2022
ms.locfileid: "144424757"
---
# <a name="module-3-get-started-with-power-apps"></a>Módulo 3: Introdução ao Power Apps
## <a name="lab-1-how-to-build-a-canvas-app"></a>Laboratório 1: Como criar um aplicativo de tela

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

3.  Se necessário, clique no ícone **Página Inicial** no lado direito da tela. Na seção **Iniciar em**, selecione **Dataverse**.

4.  Selecione a conexão do Dataverse. 

>   **Observação:** *Se não houver uma conexão do Dataverse:*
>   -   Selecione **Nova Conexão**
>   -   Localize o **Microsoft Dataverse**
>   -   Clique em **Criar**

5.  Localize e selecione a tabela **Visitas** criada no laboratório anterior.

6.  Selecione o botão **Conectar**.

7.  Após o aplicativo ser criado, na tela Boas-vindas ao Power Apps Studio, marque a caixa **Não mostrar isso novamente** e selecione **Ignorar**.

8.  Após a criação ser concluída, ele deve ser semelhante à imagem abaixo.

![Aplicativo de tela criado com base nos dados de Visita.](media/2-canvas-app-from-data.png)

Parabéns, você criou com êxito um Power App usando uma tabela do Dataverse. A próxima etapa do processo é personalizar o aplicativo para que ele corresponda à identidade visual da faculdade. A próxima série de etapas ajudará você a fazer personalizações extra no aplicativo.

## <a name="task-2-modify-and-theme-the-newly-created-app"></a>Tarefa \#2: Modificar e criar um tema para o aplicativo recém-criado

1.  Selecione o nome do aplicativo **Visitas**.

3.  No lado direito da tela, na guia Propriedades, atualize a propriedade de controle **Texto** para **"Visitas a Bellows College"** .

4. Nas propriedades, altere o **Tamanho da fonte** para **24**.

4.  Usando a navegação à esquerda, selecione **DetailsScreen1**.

5.  Selecione o título **Visitas**.

6.  No lado direito da tela, na guia Propriedades, atualize a propriedade de controle **Texto** para **"Detalhes da visita"** .

7.  Usando a navegação à esquerda, selecione **EditScreen1**.

8.  Selecione o título **Visitas**.

9.  No lado direito da tela, na guia Propriedades, substitua o texto Table1 na propriedade de controle **Texto** por **"Editar detalhes"** .

10. Usando a navegação à esquerda, selecione **BrowseScreen1**.

11. Na barra de ferramentas de comando, selecione o botão **Tema** e, na lista exibida, selecione a cor do tema **Vermelho**.

## <a name="task-3-test-your-visits-app"></a>Tarefa \#3: Testar o aplicativo de Visitas

Nesta tarefa, você vai configurar um formulário para editar informações sobre Visitas individuais.

1.  Com o aplicativo aberto no Designer de Aplicativo, selecione **Arquivo**, atualize o nome do aplicativo para **Aplicativo de Visitas** e selecione **Salvar**.

2.  Depois que o aplicativo for salvo, use a seta para **trás** para voltar ao aplicativo.

3.  No designer de aplicativo, selecione o botão **visualizar aplicativo** (ícone Executar) na barra de comandos. *(Você também pode visualizar o aplicativo pressionando F5 no teclado.)*

4.  Quando o aplicativo for aberto, no campo **Pesquisar Itens**, insira o texto **Maria**
     *(observe como os itens na galeria são filtrados com base no que é digitado no campo de pesquisa).*

5.  Quando o registro do **Contoso Suites** de **Maria Campbell** for exibido, clique na **seta para a direita** nesse registro para navegar até a tela **Detalhes da Visita**. (**Observação**: *se mais de um registro de Maria Campbell do Contoso Suites for exibido, selecione qualquer um deles*)

6.  Para editar o registro, selecione o **Ícone de lápis** no canto superior direito do aplicativo.

7.  Na parte superior da tela, clique no ícone **X** para voltar à tela **Detalhes da Propriedade**

8.  Clique na **seta para a esquerda** para voltar à tela Procurar.

9. Selecione **Arquivo** e, então, **Salvar**.

10. Selecione **Publicar**.

# <a name="challenges"></a>Desafios

-   Adicione as seguintes colunas aos formulários em DetailScreen1 e EditScreen1: Início real, Término real, Código, Início agendado e Término agendado
