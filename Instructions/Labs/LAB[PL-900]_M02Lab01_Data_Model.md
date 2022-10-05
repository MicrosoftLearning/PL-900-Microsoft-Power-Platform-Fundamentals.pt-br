---
lab:
  title: 'Laboratório 1: Modelagem de dados'
  module: 'Module 2: Introduction to Microsoft Dataverse'
---

# <a name="lab-1-data-modeling"></a>Laboratório 1: Modelagem de dados

## <a name="scenario"></a>Cenário

Bellows College is an educational organization with multiple buildings on campus. Campus visits are currently recorded in paper journals. The information is not captured consistently, and there are no means to collect and analyze data about the visits across the entire campus.

A administração do campus quer modernizar o sistema de registro de visitantes, com controle do acesso aos edifícios pelo pessoal de segurança, além de exigência de notificação prévia e registro de todas as visitas pelos anfitriões.

Ao longo deste curso, você vai criar aplicativos e fazer automações para permitir que a administração e a equipe de segurança do Bellows College gerenciem e controlem o acesso aos edifícios no campus.

In this lab you will access your environment, create a Microsoft Dataverse database, and create a solution to track your changes. You will also create a data model to support the following requirements:

- R1 – Rastrear informações para visitas agendadas no campus

- R2 – Registrar informações básicas para identificar e monitorar os visitantes

- R3 – Agendar, registrar e gerenciar as visitas

Por fim, você importará dados de amostra para o Microsoft Dataverse.

## <a name="high-level-lab-steps"></a>Macroetapas do laboratório

Para preparar seus ambientes de aprendizagem, você irá:

- Refer to the <bpt id="p1">[</bpt>data model document<ept id="p1">](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/Campus%20Management.png)</ept> for the metadata description (tables and relationships). You can hold CTRL+click or right click the link to open the data model document in a new window.
- Criar a tabela de Visitas
- importar dados de Visita usando uma planilha do Excel

## <a name="prerequisites"></a>Pré-requisitos

- Conclusão do **Módulo 0 Laboratório 0 - Validação do ambiente de laboratório**

## <a name="things-to-consider-before-you-begin"></a>Considerações antes de começar

- Convenções de nomenclatura – digite os nomes atentamente.

## <a name="exercise-1-create-new-table"></a>Exercício 1: Criar tabela

**Objetivo:** Neste exercício, você criará a tabela personalizada de Visitas.

### <a name="task-1-create-visit-table-and-columns"></a>Tarefa \#1: Criar a tabela Visita e Colunas

A tabela de **Visitas** conterá informações sobre as visitas ao campus, incluindo o visitante, horários agendados e horários reais de cada visita.

Gostaríamos de atribuir a cada visita um número exclusivo que pode ser facilmente inserido e interpretado por um visitante quando solicitado durante o processo de check-in da visita.

> Usamos o comportamento **Independente de fuso horário** para registrar informações de data e hora porque o horário de uma visita é sempre local em relação à localização do edifício e não deve mudar quando visualizado de um fuso horário diferente.

1. Entre em [https://make.powerapps.com](https://make.powerapps.com/) (se ainda não tiver entrado)

1. No canto superior direito, selecione o ambiente **Prática [minhas iniciais]** se ainda não tiver selecionado.

1. Usando a navegação à esquerda, expanda o **Dataverse** e selecione **Tabelas**.

1. Clique em **+ Nova tabela**.

1. Digite **Visita** no **Nome de exibição**.

1. Clique em **Salvar**.

1. Na seção **Esquema**, selecione **Colunas**.

1. Criar a coluna Início agendado

    - Selecione **+ Nova coluna**.

    - Digite **Início agendado** como **Nome de exibição**.

    - Selecione **Data e hora** como **Tipo de dados**.

    - Em **Obrigatório**, selecione **Negócio obrigatório**.

    - Expanda **Opções avançadas**.

    - No **Ajuste de fuso horário**, selecione **Fuso horário independente**.

    - Clique em **Save** (Salvar).

1. Criar coluna Término agendado

    - Clique em **+ Nova coluna**.

    - Digite **Término agendado** para o **Nome de exibição**.

    - Selecione **Data e hora** como **Tipo de dados**.

    - Em **Obrigatório**, selecione **Negócio obrigatório**.

    - Expanda **Opções avançadas**.

    - No **Ajuste de fuso horário**, selecione **Fuso horário independente**.

    - Clique em **Save** (Salvar).

1. Criar coluna Início real

    - Clique em **+ Nova coluna**.

    - Digite **Início real** para o **Nome de exibição**.

    - Selecione **Data e hora** como **Tipo de dados**.

    - Em **Obrigatório**, deixe marcado como **Opcional**.

    - Expanda **Opções avançadas**.

    - No **Ajuste de fuso horário**, selecione **Fuso horário independente**.

    - Clique em **Save** (Salvar).

1. Criar coluna Término real

    - Clique em **+ Nova coluna**.

    - Digite **Término real** para o **Nome de exibição**.

    - Selecione **Data e hora** como **Tipo de dados**.

    - Em **Obrigatório**, deixe marcado como **Opcional**.

    - Expanda **Opções avançadas**.

    - No **Ajuste de fuso horário**, selecione **Fuso horário independente**.

    - Clique em **Save** (Salvar).

1. Criar a coluna Código

    - Clique em **+ Nova coluna**.

    - Digite **Código** para o **Nome de exibição**.

    - Selecione **Numeração automática** como o **Tipo de dados**.

    - Selecione **Número prefixado de data** no campo **Tipo de numeração automática**.

    - Clique em **Save** (Salvar).

1. Criar coluna de pesquisa de Visitante

    - Clique em **+ Nova coluna**.

    - Digite **Visitante** para o **Nome de exibição**.

    - Selecione **Pesquisar** para **Tipo de dados**.

    - Selecione **Contato** para a **Tabela relacionada**.

    - Expanda **Opções avançadas**.

    - Insira **identificação_visitante** em **Nome da relação**.

    - Clique em **Save** (Salvar).

## <a name="exercise-2-import-data"></a>Exercício 2: Importar dados

**Objetivo:** Neste exercício, você importará dados de amostra para o banco de dados do Dataverse.

### <a name="task-1-import-the-visitsxlsx-file"></a>Tarefa \#1: Importar o arquivo Visits.xlsx

Nesta tarefa, você importará dados de Visita de um arquivo do Excel.

1. You should have the <bpt id="p1">**</bpt>Visits.xlsx<ept id="p1">**</ept> file stored on your Desktop. Download <bpt id="p1">[</bpt>Visits.xlsx<ept id="p1">](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/Visits.xlsx)</ept> if you do not.

2. Se ainda não tiver feito isso, entre em [https://make.powerapps.com](https://make.powerapps.com/).

3. No canto superior direito, selecione o ambiente **Prática [minhas iniciais]** se ainda não tiver selecionado.

4. Usando a navegação à esquerda, expanda o **Dataverse** e selecione **Tabelas**.

5. Localize e abra a tabela **Visitar** criada no exercício anterior.

6. Usando o menu na parte superior, selecione a seta suspensa ao lado de **Importar** e **Importar dados do Excel**.

7. No menu exibido, selecione o botão **Carregar**.

8. O Bellows College é uma organização educacional que possui um campus com vários edifícios.

9. Clique em **Colunas do mapa** (talvez seja necessário rolar para a direita para ver a opção Colunas do mapa).

10. Mapeie as colunas conforme indicado abaixo:

| Colunas da visita| Valores de origem |
| - | - |
| Término Real| término real |
| Início Real| início real |
| Código| code |
| Nome| name |
| Fim agendado| fim agendado |
| Início Agendado| início agendado |

11. Deixe todo o restante dos campos como **Não definido**.

12. No canto superior direito da tela, clique em **Salvar alterações**.

13. Na tela **Importar dados**, verifique se o status do mapeamento indica "Mapeamento bem-sucedido".

14. Clique em **Importar** no canto superior direito para concluir a importação de dados.

Atualmente, as visitas ao campus são registradas em diários de papel.

15. Clique em **X** para fechar o painel de importação de dados.

### <a name="task-2-verify-data-import"></a>Tarefa \#2: Verificar importação de dados

1. Após os dados terem sido importados, use a navegação à esquerda da tela para selecionar a tabela **Visita** novamente.

2. Verifique se você vê os dados importados na seção **Colunas e dados de visita**.

Parabéns, você criou com sucesso uma nova tabela e importou dados.