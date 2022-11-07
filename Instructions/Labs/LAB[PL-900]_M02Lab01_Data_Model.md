---
lab:
  title: 'Laboratório 1: Modelagem de dados'
  module: 'Module 2: Introduction to Microsoft Dataverse'
---

# <a name="lab-1-data-modeling"></a>Laboratório 1: Modelagem de dados

## <a name="scenario"></a>Cenário

O Bellows College é uma organização educacional que possui um campus com vários edifícios. Atualmente, as visitas ao campus são registradas em diários de papel. As informações não são coletadas de forma consistente e não há meios de analisar os dados sobre as visitas em todo o campus.

A administração do campus quer modernizar o sistema de registro de visitantes, com controle do acesso aos edifícios pelo pessoal de segurança, além de exigência de notificação prévia e registro de todas as visitas pelos anfitriões.

Ao longo deste curso, você vai criar aplicativos e fazer automações para permitir que a administração e a equipe de segurança do Bellows College gerenciem e controlem o acesso aos edifícios no campus.

Neste laboratório, você acessará seu ambiente, criará um banco de dados do Microsoft Dataverse e desenvolverá uma solução para rastrear suas alterações. Você também criará um modelo de dados para oferecer suporte aos seguintes requisitos:

- R1 – Rastrear informações para visitas agendadas no campus

- R2 – Registrar informações básicas para identificar e monitorar os visitantes

- R3 – Agendar, registrar e gerenciar as visitas

Por fim, você importará dados de amostra para o Microsoft Dataverse.

## <a name="high-level-lab-steps"></a>Macroetapas do laboratório

Para preparar seus ambientes de aprendizagem, você irá:

- Consulte o [documento de modelagem de dados](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/Campus%20Management.png) para ver a descrição dos metadados (tabelas e relacionamentos). Você pode pressionar CTRL+clique ou clicar com o botão direito do mouse no link para abrir o documento de modelagem de dados em uma nova janela.
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

### <a name="task-11-load-excel-file-to-onedrive"></a>Tarefa \#1.1: Carregar o arquivo do Excel no OneDrive

1. Você deve ter o arquivo **Visits.xlsx** armazenado em sua máquina virtual em **C:/LabFiles**. Baixe [Visits.xlsx](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/Visits.xlsx) se não tiver.

2. Se ainda não tiver feito isso, entre em [https://make.powerapps.com](https://make.powerapps.com/).

3. No canto superior direito, selecione o ambiente **Prática [minhas iniciais]** se ainda não tiver selecionado.

4. Clique no botão de bolacha no canto superior esquerdo para mudar de aplicativo e selecione **OneDrive**. (Pode demorar um pouco para que o OneDrive seja configurado. A opção Clique no OneDrive estará pronta quando aparecer na tela.)

5. Clique em **Carregar** no menu superior e selecione **Arquivos**.

6. Localize e selecione o arquivo **Visits.xlsx** e clique em **Abrir**.

 **Observação:** esse arquivo está localizado na pasta **Todos os Arquivos** no computador.
 
### <a name="task-12-create-a-dataflow"></a>Tarefa \#1.2: Criar um fluxo de dados

1. Se ainda não tiver feito isso, entre em [https://make.powerapps.com](https://make.powerapps.com/).

2. No canto superior direito, selecione o ambiente **Prática [minhas iniciais]** se ainda não tiver selecionado.

3. Usando a navegação à esquerda, expanda o **Dataverse** e selecione **Tabelas**.

4. Localize e abra a tabela **Visitar** criada no exercício anterior.

5. Usando o menu na parte superior, selecione a seta suspensa ao lado de **Importar** e clique em **Importar dados**.

6. Na caixa de diálogo **Escolher fonte de dados**, selecione **Pasta de trabalho do Excel**.

7. Selecione a opção **Vincular ao Arquivo**. Clique em **Procurar no OneDrive**. Se solicitado, entre com suas credenciais do Microsoft 365.

8. Escolha o arquivo **Visits.xlsx** que foi carregado no OneDrive e clique em **Selecionar**.

9. Clique em **Próximo**.

10. Em **Escolher Dados**, marque a caixa ao lado da pasta de trabalho **Visitas** do Excel.

11. Clique em **Próximo**. Não saia desta página.

12. Clique em **Próximo**.

13. Na seção **Mapear tabelas**, selecione **Carregar em tabela existente** nas **Configurações de carregamento**.

14. No menu suspenso **Tabela de destino**, selecione o nome da tabela que começa com **crXXX_visit** (em que XXX é um conjunto aleatório de letras e números)

15. No **Mapeamento de Colunas**. Mapeie as Colunas para as colunas de destino correspondentes.

| Colunas de destino| Valores de origem |
| - | - |
| crxxx_ActualEnd| término real |
| crxxx_ActualStart| início real |
| crxxx_Code| code |
| crxxx_Name| name |
| crxxx_ScheduledEnd| fim agendado |
| crxxx_ScheduledStart| início agendado |

16. Clique em **Próximo**.

17. Selecione **Atualizar manualmente**.

18. Clique em **Publicar**.

**Observação:** Poderão ser necessários alguns minutos para que os dados sejam importados para a tabela. Não se preocupe se você receber algumas mensagens de erro, isso é normal e não afetará o restante do curso.

### <a name="task-3-verify-data-import"></a>Tarefa \#3: Verificar a importação de dados

1. Após os dados terem sido importados, use a navegação à esquerda da tela para selecionar a tabela **Visita** novamente.

2. Verifique se você vê os dados importados na seção **Colunas e dados de visita**.

Parabéns, você criou com sucesso uma nova tabela e importou dados.
