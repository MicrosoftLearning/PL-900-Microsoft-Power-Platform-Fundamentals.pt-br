---
lab:
  title: 'Laboratório 5: Como compilar um dashboard simples'
  module: 'Module 5: Describe the capabilities of Microsoft Power BI'
---

## Laboratório 5: Como compilar um dashboard simples

**Locatários do WWL – Termos de Uso** Se você estiver recebendo um locatário como parte de uma entrega de treinamento com instrutor, observe que o locatário é disponibilizado com a finalidade de dar suporte aos laboratórios práticos no treinamento com instrutor. Os locatários não devem ser compartilhados ou usados para fins fora dos laboratórios práticos. O locatário usado neste curso é um locatário de avaliação e não pode ser usado ou acessado após o término da aula e não está qualificado para extensão. Os locatários não podem ser convertidos em uma assinatura paga. Os locatários obtidos como parte deste curso permanecem a propriedade da Microsoft Corporation e reservamos o direito de obter acesso e a qualquer momento. 

## Cenário

O Bellows College é uma organização educacional que possui um campus com vários edifícios. Atualmente as visitas ao campus são anotadas em papel. As informações não são coletadas de forma consistente e não há meios de analisar os dados sobre as visitas em todo o campus.

A administração do campus quer modernizar o sistema de registro de visitantes, com controle do acesso aos edifícios pelo pessoal de segurança, além de exigência de notificação prévia e registro de todas as visitas pelos anfitriões.

Neste laboratório você criará um painel e relatório do Power BI que mostra dados sobre as visitas ao campus.

**Etapas do laboratório de alto nível**

Vamos seguir as etapas abaixo para projetar e criar um dashboard do Power BI:

- Criar um relatório com várias visualizações das informações de visitas ao campus

- Usar uma linguagem de consulta natural ao usuário para criar visualizações adicionais

### Pré-requisitos

- Conclusão do **Módulo 1 Laboratório 0 – Validação do ambiente de laboratório**

**Coisas a considerar antes de começar**

- Quem é o público-alvo do relatório?

- Como o público-alvo usará o relatório? Qual é o dispositivo usual? Qual é o local?

- Existem dados suficientes para visualizar o painel?

- Quais são as características que você pode usar para analisar os dados sobre as visitas?

## Exercício nº 1: criar um relatório do Power BI

**Objetivo:** neste exercício, você criará um relatório do Power BI com base nos dados da planilha do Excel que aproveitamos em um exercício anterior.

### Tarefa 1: preparar o serviço do Power BI

1. Você terá um arquivo visits.pbix armazenado na sua máquina virtual na pasta AllFiles na Área de Trabalho. Baixe [visits.pbix](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/visits.pbix) e salve-o no computador, caso ainda não tenha feito isso.

1. Abra uma nova guia, acesse `https://app.powerbi.com` e se conecte, se necessário.

1. Selecione **Meu workspace** na navegação à esquerda.

1. Selecione **Carregar** e **Procurar**.

1. Localize e selecione o arquivo **visits.pbix** que você baixou anteriormente.

1. Uma vez concluído o carregamento de dados, selecione o relatório de **visitas**.

    >**Observação:** o Tipo está definido como **Relatório**. Não selecione o Modelo Semântico.

1. Selecione **Editar**.

Se o item de menu **Editar** não estiver visível, selecione as reticências **...** e clique em **Editar**.

Você concluiu a configuração do serviço do Power BI para usar em seus laboratórios.

### Tarefa 2: criar visualizações de gráfico e de tempo

1. Escolha o ícone de **Gráfico de pizza** no painel **Visualizações** para inserir um gráfico.

1. Expanda **bc_Visit** no painel **Dados**. Arraste o campo **Prédio** e solte-o dentro da caixa **Legenda**.

1. Arraste o campo **Visita** e solte-o na caixa **Valores**.

1. Redimensione o gráfico de pizza usando as alças de canto para que todos os componentes do gráfico fiquem visíveis.

1. Clique no relatório, fora do gráfico de pizza, para desmarcá-lo e selecione o ícone do **Gráfico de colunas empilhadas** no painel **Visualizações**.

1. Expanda **bc_Visit** no painel **Dados** caso ele ainda não esteja expandido. Arraste o campo **Visita** e solte-o na caixa **Eixo y**.

1. Arraste o campo **Início** e solte-o na caixa **Eixo x**.

1. No painel **Visualizações**, selecione o **x** ao lado de **Ano** e **Trimestre** para deixar somente os totais de **Mês** e **Dia** no eixo X.

1. Redimensione o gráfico conforme desejado usando as alças de canto.

1. Teste a interatividade do relatório:

    - Escolha diferentes fatias de prédios no gráfico de pizza e observe as alterações no gráfico de colunas empilhadas.

    - Selecione o Gráfico de colunas empilhadas. Escolha a seta para cima para **Fazer drill up**. Selecione a seta para baixo para ativar o modo de **Busca detalhada** e escolha uma coluna para fazer uma busca detalhada do próximo nível (dias).

    - Faça drill up e drill down e selecione várias barras no Gráfico de colunas empilhadas para observar as alterações no relatório de pizza.

1. Salve o trabalho em andamento selecionando **Salvar este relatório**.

## Exercício 2: criar um painel do Power BI

### Tarefa 1: criar um dashboard do Power BI

1. Abra o relatório criado na tarefa anterior.

1. Selecione **Fixar no painel** no menu. Dependendo do layout, talvez seja necessário selecionar o menu de reticências **...** para mostrar mais opções.

1. Selecione **Novo painel** na janela de prompt **Fixar no painel**.

1. Insira `Campus Management` como **Nome do dashboard** e selecione **Fixar em tempo real**.

1. Um pop-up informará que o painel foi criado. Selecione **Ir para o dashboard**.

1. Teste a interatividade dos gráficos de pizza e barras exibidos.

### Tarefa 2: adicionar visualizações usando linguagem natural

1. No painel **Gerenciamento do campus**, selecione a barra **Faça uma pergunta sobre os dados** no topo.

1. Entre `buildings by number of visits` na área de perguntas e respostas. Uma gráfico de barras será exibido.

1. Selecione **Fixar visual**.

1. Selecione **Dashboard existente**, escolha o dashboard **Administração do campus** e selecione **Fixar**.

1. Selecione **Sair de P&amp;R**.

O dashboard **Administração do campus** deve ser exibido contendo três visuais. Role a tela para baixo para ver o novo visual de P e R.

Seu painel deve se parecer com o seguinte:

[![Captura de tela do painel recém-criado](media/lab-5-power-bi-01.png)](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Instructions/Labs/media/5-powerbi-result.png)

 
