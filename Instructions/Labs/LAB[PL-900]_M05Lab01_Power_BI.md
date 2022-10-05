---
lab:
  title: 'Laboratório 5: Como compilar um dashboard simples'
  module: 'Module 5: Get Started with Power BI'
---

## <a name="lab-5-how-to-build-a-simple-dashboard"></a>Laboratório 5: Como compilar um dashboard simples

## <a name="scenario"></a>Cenário

Bellows College is an educational organization with multiple buildings on campus. Campus visitors are currently recorded in paper journals. The information is not captured consistently, and there are no means to collect and analyze data about the visits across the entire campus.

A administração do campus quer modernizar o sistema de registro de visitantes, com controle do acesso aos edifícios pelo pessoal de segurança, além de exigência de notificação prévia e registro de todas as visitas pelos anfitriões.

Ao longo deste curso, você vai criar aplicativos e fazer automações para permitir que a administração e a equipe de segurança do Bellows College gerenciem e controlem o acesso aos edifícios no campus.

Neste laboratório você criará um painel e relatório do Power BI que mostra dados sobre as visitas ao campus.

## <a name="high-level-lab-steps"></a>Macroetapas do laboratório

Vamos seguir as etapas abaixo para projetar e criar um dashboard do Power BI:

-   Criar um relatório com várias visualizações das informações de visitas ao campus

-   Usar uma linguagem de consulta natural ao usuário para criar visualizações adicionais

## <a name="prerequisites"></a>Pré-requisitos

- Conclusão do **Módulo 0 Laboratório 0 - Validação do ambiente de laboratório**
- Conclusão do **Laboratório 1 do Módulo 2 – Modelagem de Dados**

## <a name="things-to-consider-before-you-begin"></a>Considerações antes de começar

-   Quem é o público-alvo do relatório?
-   How will the audience consume the report? Typical device? Location?
-   Existem dados suficientes para visualizar o painel?
-   Quais são as características que você pode usar para analisar os dados sobre as visitas?

## <a name="exercise-1-create-power-bi-report"></a>Exercício 1: criar um relatório do Power BI

**Objetivo:** neste exercício, você criará um relatório do Power BI com base nos dados da planilha do Excel que aproveitamos em um exercício anterior.

### <a name="task-1-prepare-power-bi-service"></a>Tarefa \#1: Preparar o serviço do Power BI

1.  Baixe o [visits.pbix](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/visits.pbix) e salve no computador.

2.  Navegue até <https://app.powerbi.com/> e entre se necessário.

3.  No canto inferior esquerdo da tela, selecione **Obter dados**

4.  Selecione o botão **Obter** em **Arquivos**, na seção **Criar conteúdo**.

5.  Selecione **Arquivo Local**.

6.  Localize e selecione o arquivo **visits.pbix** que você baixou anteriormente.

7.  Depois de carregar os dados, expanda **Meu workspace** e selecione o relatório de **visitas** (o Tipo está definido para **Relatório**).

8.  Click <bpt id="p1">**</bpt>Edit<ept id="p1">**</ept>. If <bpt id="p1">**</bpt>Edit<ept id="p1">**</ept> menu item is not visible click <bpt id="p2">**</bpt>...<ept id="p2">**</ept> and then select <bpt id="p3">**</bpt>Edit<ept id="p3">**</ept>.

Você concluiu a configuração do serviço do Power BI para usar em seus laboratórios.

### <a name="task-2-create-chart-and-time-visualizations"></a>Tarefa \#2: criar gráficos e visualizações de tempo

1.  Pressione o ícone de **Gráfico de pizza** no painel **Visualizações** para inserir um gráfico.

2.  Press the drop-down arrow beside <bpt id="p1">**</bpt>bc_building<ept id="p1">**</ept> in the Fields pane. Drag the <bpt id="p1">**</bpt>Building<ept id="p1">**</ept> field and drop it into <bpt id="p2">**</bpt>Legend<ept id="p2">**</ept> box.

3.  O Bellows College é uma organização educacional que possui um campus com vários edifícios.

4.  Redimensione o gráfico de pizza usando as alças de canto para que todos os componentes do gráfico fiquem visíveis.

5.  Clique fora do gráfico de pizza para desmarcá-lo e selecione o gráfico de colunas no painel **Visualizações**.

6.  Atualmente as visitas ao campus são anotadas em papel.

7.  Arraste o campo **Início** e solte-o na caixa de destino **Eixo x**.

8.  No painel Visualizações, clique em **x** ao lado de **Ano** e **Trimestre** para deixar somente os totais de **Mês** e **Dia** no Eixo.

9.  Redimensione o gráfico conforme desejado usando as alças de canto.

10. Teste a interatividade do relatório:

    1.  Selecione várias partes do gráfico de pizza dos prédios e observe as mudanças no relatório de tempo.

    2.  As informações não são coletadas de forma consistente e não há meios de analisar os dados sobre as visitas em todo o campus.

    3.  Faça pesquisas detalhadas ou agrupadas e selecione várias barras no gráfico de colunas de tempo para observar as mudanças no relatório de pizza.

11. Salve o trabalho em andamento pressionando **Salvar**.

## <a name="exercise-2-create-power-bi-dashboard"></a>Exercício 2: criar um painel do Power BI

### <a name="task-1-create-power-bi-dashboard"></a>Tarefa \#1: criar um painel do Power BI

1.  Abra o relatório criado na tarefa anterior.

2.  Select <bpt id="p1">**</bpt>Pin to a dashboard<ept id="p1">**</ept> on the menu. Depending on the layout you may need to press <bpt id="p1">**</bpt>...<ept id="p1">**</ept> to show additional menu items.

3.  Selecione **Novo painel** na janela de prompt **Fixar no painel**.

4.  Digite **Administração do campus** como **Nome do dashboard** e pressione **Fixar em tempo real**.

5.  A pop-up will prompt you that the dashboard has been created. Select <bpt id="p1">**</bpt>Go to dashboard<ept id="p1">**</ept>.

6.  Teste a interatividade dos gráficos de pizza e barras exibidos.

### <a name="task-2-add-visualizations-using-natural-language"></a>Tarefa \#2: adicionar visualizações usando linguagem natural

1.  No painel **Gerenciamento do campus**, selecione a barra **Faça uma pergunta sobre os dados** no topo.

2.  Enter <bpt id="p1">**</bpt>buildings by number of visits<ept id="p1">**</ept> in Q&amp;A area. A bar chart will be displayed.

3.  Selecione **Fixar visual**.

4.  Selecione **Dashboard existente**, selecione o dashboard **Administração do campus** e pressione **Fixar**.

5.  Clique em **Sair de P e R**.

Your <bpt id="p1">**</bpt>Campus Management<ept id="p1">**</ept> dashboard should be displayed with three visuals on it. You may have to scroll down to see the new Q&amp;A visual.

Seu painel deve se parecer com o seguinte:

![](media/5-powerbi-result.png)