---
lab:
  title: 'Laboratório 1: Modelagem de dados'
  module: 'Module 2: Introduction to Microsoft Dataverse'
---

# Laboratório 1: Modelagem de dados

**Locatários do WWL – Termos de Uso** Se você estiver recebendo um locatário como parte de uma entrega de treinamento com instrutor, observe que o locatário é disponibilizado com a finalidade de dar suporte aos laboratórios práticos no treinamento com instrutor. Os locatários não devem ser compartilhados ou usados para fins fora dos laboratórios práticos. O locatário usado neste curso é um locatário de avaliação e não pode ser usado ou acessado após o fim da aula e não está qualificado para extensão. Os locatários não podem ser convertidos em uma assinatura paga. Os locatários obtidos como parte deste curso permanecem a propriedade da Microsoft Corporation e reservamos o direito de obter acesso e a qualquer momento. 

## Cenário

O Bellows College é uma organização educacional que possui um campus com vários edifícios. Atualmente, as visitas ao campus são registradas em diários de papel. As informações não são coletadas de forma consistente e não há meios de analisar os dados sobre as visitas em todo o campus.

A administração do campus quer modernizar o sistema de registro de visitantes, com controle do acesso aos edifícios pelo pessoal de segurança, além de exigência de notificação prévia e registro de todas as visitas pelos anfitriões.

Ao longo deste curso, você vai criar aplicativos e fazer automações para permitir que a administração e a equipe de segurança do Bellows College gerenciem e controlem o acesso aos edifícios no campus.

Neste laboratório, você criará um modelo de dados para oferecer suporte aos seguintes requisitos:

- R1 – Rastrear informações para visitas agendadas no campus.

- R2 – Registrar informações básicas para identificar e monitorar os visitantes.

- R3 – Agendar, registrar e gerenciar as visitas.

Por fim, você importará dados de amostra para o Microsoft Dataverse.

Macroetapas do laboratório

Para preparar seus ambientes de aprendizagem, você irá:

- Consulte o [documento de modelagem de dados](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/Campus%20Management.png) para ver a descrição dos metadados (tabelas e relacionamentos). Você pode pressionar Ctrl + clique ou clicar com o botão direito do mouse no link para abrir o documento de modelagem de dados em uma nova janela.
- Criar a tabela Visita
- Importar dados de visitas usando uma planilha do Excel


## Pré-requisitos

- Conclusão do **Módulo 0 Laboratório 0 - Validação do ambiente de laboratório**

Considerações antes de começar

- Convenções de nomenclatura – digite os nomes atentamente.


# Exercício 1: Criar tabela

**Objetivo:** Neste exercício, você criará a tabela personalizada de Visitas.

## Tarefa 1: Criar a tabela Visita e Colunas

A tabela de **Visitas** conterá informações sobre as visitas ao campus, incluindo o visitante, horários agendados e horários reais de cada visita.

Gostaríamos de atribuir a cada visita um número exclusivo que pode ser facilmente inserido e interpretado por um visitante quando solicitado durante o processo de check-in da visita.

1.  Entre em <https://make.powerapps.com> (se ainda não tiver entrado) 

1.  No menu **Ambiente** no canto superior direito, verifique se o ambiente **Prática** está selecionado. 

1.  Na navegação à esquerda, selecione **Tabelas**.

1.  Selecione **+ Nova tabela** e escolha **Definir propriedades avançadas**. 

1.  Para **Nome de exibição**, insira `Visit`

1.  Clique em **Salvar**. 

1.  Na seção **Esquema**, selecione **Colunas**. 


## Criar a coluna Início agendado

1.  Selecione **+ Nova coluna**. 

1.  Para **Nome de exibição**, insira `Scheduled Start`. 

1.  Selecione **Data e hora** como **Tipo de dados**. 

1.  Altere **Obrigatório** para **Requisito de negócios**. 

1.  Expanda **Opções avançadas**. 

1.  No **Ajuste de fuso horário**, selecione **Fuso horário independente**. 

    > **Observação:** Usamos o comportamento **Independente de fuso horário** para registrar informações de data e hora porque o horário de uma visita é sempre local em relação à localização do edifício e não deve mudar quando visualizado de um fuso horário diferente. 

1.  Clique em **Salvar**. 


## Criar coluna Término agendado

1.  Selecione **+ Nova coluna**. 

1.  Para **Nome de exibição**, insira `Scheduled End`.

1.  Selecione **Data e hora** como **Tipo de dados**.

1.  Em **Obrigatório**, selecione **Negócio obrigatório**.

1.  Expanda **Opções avançadas**.

1.  No **Ajuste de fuso horário**, selecione **Fuso horário independente**.

1.  Clique em **Salvar**. 


## Criar coluna Início real

1.  Selecione **+ Nova coluna**. 

1.  Para **Nome de exibição**, insira `Actual Start`.

1.  Selecione **Data e hora** como **Tipo de dados**.

1.  Em **Obrigatório**, deixe marcado como **Opcional**.

1.  Expanda **Opções avançadas**.

1.  No **Ajuste de fuso horário**, selecione **Fuso horário independente**. 

1.  Clique em **Salvar**. 


## Criar coluna Término real

1.  Selecione **+ Nova coluna**.

1.  Para **Nome de exibição**, insira `Actual End`.

1.  Selecione **Data e hora** como **Tipo de dados**.

1.  Em **Obrigatório**, deixe marcado como **Opcional**.

1.  Expanda **Opções avançadas**.

1.  No **Ajuste de fuso horário**, selecione **Fuso horário independente**.

1.  Clique em **Salvar**.


## Criar a coluna Código

1.  Selecione **+ Nova coluna**.

1.  Para **Nome de exibição**, insira `Code`.

1.  Selecione **Numeração automática** como o **Tipo de dados**.

1.  Selecione **Número prefixado de data** no campo **Tipo de numeração automática**.

1.  Clique em **Salvar**. 


## Criar coluna de pesquisa de Visitante

1.  Selecione **+ Nova coluna**.

1.  Para **Nome de exibição**, insira `Visitor`.

1.  Selecione **Pesquisa** > **Pesquisa** para **Tipo de dados**. 

1.  Selecione **Contato** para a **Tabela relacionada**. 

1.  Expanda **Opções avançadas**. 

1.  Insira `visitor_id` em **Nome da relação**. 

1.  Clique em **Salvar**.


# Exercício 2: Importar dados

**Objetivo:** Neste exercício, você importará dados de amostra para o banco de dados do Dataverse.

## Tarefa \#1: Carregar o arquivo do Excel no OneDrive

1.  Você deve ter o arquivo **Visits.xlsx** armazenado em sua máquina virtual em **C:/LabFiles**. Baixe [Visits.xlsx](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/Visits.xlsx) se não tiver.

2.  Se ainda não tiver feito isso, entre em [https://make.powerapps.com](https://make.powerapps.com/). 

3.  No canto superior direito, selecione o ambiente **Prática [minhas iniciais]** se ainda não tiver selecionado.

4.  Selecione o botão de bolacha no canto superior esquerdo para mudar de aplicativo e selecione **OneDrive**. (Pode demorar um pouco para que o OneDrive seja configurado. Selecione **O OneDrive está pronto** quando a opção for exibida na tela.

5.  Selecione **+Adicionar novo** no menu e selecione **Upload de arquivos**.

6.  Localize e selecione o arquivo **Visits.xlsx** e selecione **Abrir**.

    > **Observação:** o arquivo deve estar localizado na pasta **Área de Trabalho** > **Todos os arquivos** em sua máquina virtual.


## Tarefa 2: Criar um fluxo de dados

1.  Entre em <https://make.powerapps.com> (se ainda não tiver entrado) 

2.  No menu **Ambiente** no canto superior direito, verifique se o ambiente **Prática** está selecionado. 

3.  Na navegação à esquerda, selecione **Tabelas**. 

4.  Abra a tabela **Visitar** criada no exercício anterior. 

5.  Usando o menu na parte superior, selecione **Importar** > **Importar dados**.

6.  Na caixa de diálogo **Escolher fonte de dados**, selecione **Pasta de trabalho do Excel**.

7.  Selecione a opção **Vincular ao Arquivo**. Selecione **Procurar no OneDrive**. Se solicitado, entre com suas credenciais do Microsoft 365. Configure o navegador para sempre permitir pop-ups. 

8.  Selecione o arquivo **Visits.xlsx**, que foi carregado no OneDrive na tarefa anterior. 

9.  Selecione **Avançar**. 

10. Na tela**Power Query** > **Escolher dados**, marque a pasta de trabalho **Visitas** do Excel. 

11. Selecione **Avançar**. Não saia desta página.

12. Selecione **Avançar**. 

13. Na seção **Mapear tabelas**, em **Configurações de carregamento**, selecione **Carregar em tabela existente**. 

14. No menu suspenso **Tabela de destino**, selecione a tabela **crXXX_Visit** (em que XXX é um conjunto aleatório de letras e números)

15. Na seção **Mapeamento de Colunas**, mapeie as colunas para as colunas de destino correspondentes:

    | Colunas de destino  | Valores de origem   |
    |:---------------------|:----------------|
    | crxxx_ActualEnd      | término real      |
    | crxxx_ActualStart    | início real    |
    | crxxx_Code           | code            |
    | crxxx_Name           | name            |
    | crxxx_ScheduledEnd   | fim agendado   |
    | crxxx_ScheduledStart | início agendado |

16. Selecione **Avançar**. 

17. Selecione **Atualizar manualmente**. 

18. Selecione **Publicar**. 

    > **Observação:** Poderão ser necessários alguns minutos para que os dados sejam importados para a tabela. Não se preocupe se você receber algumas mensagens de erro, isso é normal e não afetará o restante do curso.


## Tarefa \#3: Verificar a importação de dados

1.  Após os dados terem sido importados, use a navegação à esquerda da tela para selecionar **Tabelas** e abra a tabela **Visita**.

2.  Verifique se você vê os dados importados na seção **Colunas e dados de visita**.

Parabéns, você criou com sucesso uma nova tabela e importou dados.

