---
lab:
  title: 'Laboratório 5: Como compilar um dashboard simples'
  module: 'Module 5: Get Started with Power BI'
ms.openlocfilehash: 8d104c42de9d4114c668a63a4d8d30cbbcc4b39e
ms.sourcegitcommit: 36c8fda9cdc6f448416d7000e38c1606bea87d2e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2022
ms.locfileid: "144812929"
---
# <a name="module-5-get-started-with-power-bi"></a>Módulo 5: Introdução ao Power BI
## <a name="lab-how-to-build-a-simple-dashboard"></a>Laboratório: Como compilar um dashboard simples

# <a name="scenario"></a>Cenário

O Bellows College é uma organização educacional que possui um campus com vários edifícios. Atualmente as visitas ao campus são anotadas em papel. As informações não são coletadas de forma consistente e não há meios de analisar os dados sobre as visitas em todo o campus.

A administração do campus quer modernizar o sistema de registro de visitantes, com controle do acesso aos edifícios pelo pessoal de segurança, além de exigência de notificação prévia e registro de todas as visitas pelos anfitriões.

Ao longo deste curso, você vai criar aplicativos e fazer automações para permitir que a administração e a equipe de segurança do Bellows College gerenciem e controlem o acesso aos edifícios no campus.

Neste laboratório você vai criar um painel do Power BI que mostra dados sobre as visitas ao campus.

# <a name="high-level-lab-steps"></a>Macroetapas do laboratório

Vamos seguir as etapas abaixo para projetar e criar um dashboard do Power BI:

-   Conectar ao Dataverse

-   Alterar os dados para incluir descrições amigáveis nas linhas relacionadas (pesquisas)

-   Criar e publicar um relatório com várias visualizações das informações de visitas ao campus

-   Usar uma linguagem de consulta natural ao usuário para criar visualizações adicionais

-   Criar uma visão do painel do Power BI para dispositivos móveis

## <a name="prerequisites"></a>Pré-requisitos

-   Conclusão do **Módulo 0 Laboratório 0 - Validação do ambiente de laboratório**

-   Conclusão do **Módulo 2 Laboratório 1 - Introdução ao Microsoft Dataverse**

## <a name="things-to-consider-before-you-begin"></a>Considerações antes de começar

-   Quem é o público-alvo do relatório?

-   Como o público-alvo usará o relatório? Qual é o dispositivo usual? Qual é o local?

-   Existem dados suficientes para visualizar o painel?

-   Quais são as características que você pode usar para analisar os dados sobre as visitas?

# <a name="exercise-1-create-power-bi-report"></a>Exercício 1: criar um relatório do Power BI

**Objetivo:** neste exercício, você criará um relatório do Power BI com base nos dados da planilha do Excel que aproveitamos em um exercício anterior.

## <a name="task-1-prepare-power-bi-service"></a>Tarefa \#1: Preparar o serviço do Power BI

1.  Baixe o [visits.pbix](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/visits.pbix) e salve no computador.

2.  Navegue até <https://app.powerbi.com/> e entre se necessário.

3.  No canto inferior esquerdo da tela, selecione **Obter dados**

4.  Selecione o botão **Obter** em **Arquivos**, na seção **Criar conteúdo**.

5.  Selecione **Arquivo Local**.

6.  Localize e selecione o arquivo **visits.pbix** que você baixou anteriormente.

7.  Depois de carregar os dados, selecione o relatório **visitas** (observe que Tipo está definido como **Relatório**).

8.  Clique em **Editar**. Se o item de menu **Editar** não estiver visível, clique em **...** e selecione **Editar**.

Você concluiu a configuração do serviço do Power BI para usar em seus laboratórios. 

## <a name="task-2-create-chart-and-time-visualizations"></a>Tarefa \#2: criar gráficos e visualizações de tempo

1.  Pressione o ícone de **Gráfico de pizza** no painel **Visualizações** para inserir um gráfico.

2.  Pressione a seta suspensa ao lado de **bc_name** no painel de Campos. Arraste o campo **Prédio** e solte dentro da caixa **Legenda**.

3.  Pressione a seta ao lado de **bc_Visit** no painel Campos. Arraste o campo **Visita** e solte-o na caixa **Valores**.

4.  Redimensione o gráfico de pizza usando as alças de canto para que todos os componentes do gráfico fiquem visíveis.

5.  Clique fora do gráfico de pizza para desmarcá-lo e selecione o gráfico de colunas no painel **Visualizações**.

6.  Pressione a seta ao lado de **bc_Visit** no painel Campos. Arraste o campo **Visita** e solte-o na caixa **Valores**.

7.  Arraste o campo **Início** e solte dentro da caixa **Eixo**.

8.  No painel Visualizações, clique em **x** ao lado de **Ano** e **Trimestre** para deixar somente os totais de **Mês** e **Dia** no Eixo.

9.  Redimensione o gráfico conforme desejado usando as alças de canto.

10. Teste a interatividade do relatório:

    1.  Selecione várias partes do gráfico de pizza dos prédios e observe as mudanças no relatório de tempo.

    2.  Clique no gráfico de colunas. Pressione a seta para baixo para ativar o modo de **Fazer busca detalhada** (ou clique com o botão direito do mouse no gráfico e selecione **Fazer busca detalhada**) e clique na coluna a ser detalhada até o próximo nível (dias). 
    
    3.  Faça pesquisas detalhadas ou agrupadas e selecione várias barras no gráfico de colunas de tempo para observar as mudanças no relatório de pizza.

11. Salve o trabalho em andamento pressionando **Salvar**.

# <a name="exercise-2-create-power-bi-dashboard"></a>Exercício \#2: criar um painel do Power BI

## <a name="task-1-create-power-bi-dashboard"></a>Tarefa \#1: criar um painel do Power BI

1.  Abra o relatório criado na tarefa anterior.

2.  Selecione **Fixar no painel** no menu. Dependendo do layout, você precisa pressionar **...** para exibir os itens de menu adicionais.

3.  Selecione **Novo painel** na janela de prompt **Fixar no painel**.

4.  Digite **Administração do campus** como **Nome do dashboard** e pressione **Fixar em tempo real**.

5.  Selecione **Meu espaço de trabalho** no topo, depois selecione o painel **Gerenciamento do campus [Seu sobrenome]** .

6.  Um pop-up informará que o painel foi criado. Selecione **Ir para o dashboard**.

7.  Teste a interatividade dos gráficos de pizza e barras exibidos.

## <a name="task-2-add-visualizations-using-natural-language"></a>Tarefa \#2: adicionar visualizações usando linguagem natural

1.  No painel **Gerenciamento do campus**, selecione a barra **Faça uma pergunta sobre os dados** no topo.

2.  Digite **prédios por número de visitas** na área de P e R (Perguntas e Respostas) Uma gráfico de barras será exibido.

3.  Selecione **Fixar visual**.

4.  Selecione **Dashboard existente**, selecione o dashboard **Administração do campus** e pressione **Fixar**.

5.  Clique em **Sair de P e R**.

O dashboard **Administração do campus** deve ser exibido contendo três visuais. Role a tela para baixo para ver o novo visual de P e R.

Seu painel deve se parecer com o seguinte:

![](media/5-powerbi-result.png)
