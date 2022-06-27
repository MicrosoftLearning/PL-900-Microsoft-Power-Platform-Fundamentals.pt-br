---
lab:
  title: 'Laboratório 1: Modelagem de dados'
  module: 'Module 2: Introduction to Microsoft Dataverse'
ms.openlocfilehash: 9edefbdf214d5a0f2e0693ffdf024dfc05c032c5
ms.sourcegitcommit: dbffa13e13419f5b9aadc894eb95fd16215b2ebf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2022
ms.locfileid: "146458357"
---
# <a name="module-2-introduction-to-microsoft-dataverse"></a>Módulo 2: Introdução ao Microsoft Dataverse

# <a name="scenario"></a>Cenário

O Bellows College é uma organização educacional que possui um campus com vários edifícios. Atualmente, as visitas ao campus são registradas em diários de papel. As informações não são coletadas de forma consistente e não há meios de analisar os dados sobre as visitas em todo o campus.

A administração do campus quer modernizar o sistema de registro de visitantes, com controle do acesso aos edifícios pelo pessoal de segurança, além de exigência de notificação prévia e registro de todas as visitas pelos anfitriões.

Ao longo deste curso, você vai criar aplicativos e fazer automações para permitir que a administração e a equipe de segurança do Bellows College gerenciem e controlem o acesso aos edifícios no campus.

Neste laboratório, você acessará seu ambiente, criará um banco de dados do Microsoft Dataverse e desenvolverá uma solução para rastrear suas alterações. Você também criará um modelo de dados para oferecer suporte aos seguintes requisitos:

-   R1 – Rastrear informações para visitas agendadas no campus

-   R2 – Registrar informações básicas para identificar e monitorar os visitantes

-   R3 – Agendar, registrar e gerenciar as visitas

Por fim, você importará dados de amostra para o Microsoft Dataverse.

# <a name="high-level-lab-steps"></a>Macroetapas do laboratório

Para preparar seus ambientes de aprendizagem, você irá:

* criar uma solução e um editor
* adicionar componentes novos e existentes, necessários para atender aos requisitos do aplicativo. Consulte o [documento de modelagem de dados](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/Campus%20Management.png) para ver a descrição dos metadados (tabelas e relacionamentos). Você pode pressionar CTRL+clique ou clicar com o botão direito do mouse no link para abrir o documento de modelagem de dados em uma nova janela.
* Criar a tabela de Visitas
* importar dados de Visita usando uma planilha do Excel

## <a name="prerequisites"></a>Pré-requisitos:

-   Conclusão do **Módulo 0 Laboratório 0 - Validação do ambiente de laboratório**

## <a name="things-to-consider-before-you-begin"></a>Considere estes itens antes de começar:

-   Convenções de nomenclatura – digite os nomes atentamente.

# <a name="exercise-1-create-new-table"></a>Exercício \#1: Criar tabela

**Objetivo:** Neste exercício, você criará a tabela personalizada de Visitas. 

## <a name="task--1-create-visit-table-and-columns"></a>Tarefa \# 1: Criar a tabela Visita e Colunas

A tabela de **Visitas** conterá informações sobre as visitas ao campus, incluindo o visitante, horários agendados e horários reais de cada visita.

Gostaríamos de atribuir a cada visita um número exclusivo que pode ser facilmente inserido e interpretado por um visitante quando solicitado durante o processo de check-in da visita.

>   Usamos o comportamento **Independente de fuso horário** para registrar informações de data e hora porque o horário de uma visita sempre é local em relação à localização do edifício e não deve mudar quando visualizado em um fuso horário diferente.

1. Entre em [https://make.powerapps.com](https://make.powerapps.com/) (se ainda não tiver entrado)

2. No canto superior direito, selecione o ambiente **Prática [minhas iniciais]** se ainda não tiver selecionado.

3. Usando a navegação à esquerda, expanda o Dataverse e selecione Tabelas.

4. Clique em **Nova tabela**.

5. Digite **Visita** no **Nome de exibição**.

6. Clique em **Salvar**. O provisionamento da tabela será iniciado em segundo plano e você pode começar a adicionar outras colunas.

7. Depois que a tabela for criada, na seção **Esquema**, selecione **Colunas**. 

8. Selecione **Nova coluna** e a configure da seguinte maneira: 

    - Digite **Início agendado** como **Nome de exibição**.

    - Selecione **Data e hora** como **Tipo de dados**.

    - Em **Obrigatório**, selecione **Negócio obrigatório**.

    - Expanda a seção **Opções avançadas**.

    - Em **Comportamento**, selecione **Independente de fuso horário**.

    - Clique em **Save** (Salvar).

9. Criar coluna Término agendado 

    - Clique em **Adicionar coluna**.

    - Digite **Término agendado** para o **Nome de exibição**.

    - Selecione **Data e hora** como **Tipo de dados**.

    - Em **Obrigatório**, selecione **Negócio obrigatório**.

    - Expanda a seção **Opções avançadas**.

    - Em **Comportamento**, selecione **Independente de fuso horário**.

    - Clique em **Save** (Salvar).

10. Criar coluna Início real

    - Clique em **Adicionar coluna**.

    - Digite **Início real** para o **Nome de exibição**.

    - Selecione **Data e hora** como **Tipo de dados**.

    - Em **Obrigatório**, deixe marcado como **Opcional**.

    - Expanda a seção **Opções avançadas**.

    - Em **Comportamento**, selecione **Independente de fuso horário**.

    - Clique em **Save** (Salvar).

11. Criar coluna Término real

    - Clique em **Adicionar coluna**.

    - Digite **Término real** para o **Nome de exibição**.

    - Selecione **Data e hora** como **Tipo de dados**.

    - Em **Obrigatório**, deixe marcado como **Opcional**.

    - Expanda a seção **Opções avançadas**.

    - Em **Comportamento**, selecione **Independente de fuso horário**.

    - Clique em **Save** (Salvar).

12. Criar a coluna Código

    - Clique em **Adicionar coluna**.

    - Digite **Código** para o **Nome de exibição**.

    - Selecione **Numeração automática** como o **Tipo de dados**.

    - Selecione **Número prefixado de data** no campo **Tipo de numeração automática**.

    - Clique em **Save** (Salvar).

13. Criar coluna de pesquisa de Visitante

    - Clique em **Adicionar coluna**.

    - Digite **Visitante** para o **Nome de exibição**.

    - Selecione **Pesquisar** para **Tipo de dados**.

    - Selecione **Contato** para a **Tabela relacionada**.

    - Expanda a seção **Opções avançadas**.

    - Insira **identificação_visitante** em **Nome da relação**.

    - Clique em **Save** (Salvar).

 

Exercício 2: Importar dados

**Objetivo:** Neste exercício, você importará dados de amostra para o banco de dados do Dataverse.

Tarefa 1: Importar o arquivo Visits.xls.

Nesta tarefa, você importará dados de Visita de um arquivo do Excel.

1. Você deve ter o arquivo **Visits.xls** armazenado em seu desktop. Baixe [Visits.xls](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/Visits.xlsx) se não tiver.

2. Se ainda não tiver feito isso, entre em [https://make.powerapps.com](https://make.powerapps.com/).

3. No canto superior direito, selecione o ambiente **Prática [minhas iniciais]** se ainda não tiver selecionado.

4. Usando a navegação à esquerda, expanda o **Dataverse** e selecione Tabelas.

Você poderá ver essa opção em Dados > Tabelas na tela.

5. Localize e abra a tabela **Visitar** criada no exercício anterior.

6. Usando o menu na parte superior, selecione a seta suspensa ao lado de **Importar** e **Importar dados do Excel**.

7. No menu exibido, selecione o botão **Carregar**.

8. Localize e selecione o arquivo **Visits.xls** baixado anteriormente. Observe que poderão ser necessários um ou dois minutos para que o arquivo seja carregado. Não se preocupe se você receber uma mensagem indicando que há erros de mapeamento, pois nós os corrigiremos a seguir.

9. Selecione **Mapear colunas**.

10. Mapeie as colunas conforme indicado abaixo:

| Colunas no BD Visitas| Valores de origem |
| - |
| Término Real| Término real |
| Início Real| Término real |
| Código| Código |
| Nome| Nome |
| Fim agendado| Término agendado |
| Início Agendado| Início agendado |


11. Deixe todo o restante dos campos como **Não definido**.

12. No canto superior direito da tela, selecione **Salvar alterações**.

13. Na tela **Importar dados**, verifique se o status do mapeamento indica "Mapeamento bem-sucedido".

14. Selecione **Importar** no canto superior direito para concluir a importação de dados.

**Observação:** Poderão ser necessários alguns minutos para que os dados sejam importados para a tabela. Não se preocupe se você receber algumas mensagens de erro, isso é normal e não afetará o restante do curso.

Tarefa 2: Verificar importação de dados

1. Após os dados terem sido importados, use a navegação à esquerda da tela para selecionar a tabela **Visita** novamente.

2. Verifique se você vê os dados importados na seção **Colunas e dados de visita**. 

Parabéns, você criou com sucesso uma nova tabela e importou dados.
