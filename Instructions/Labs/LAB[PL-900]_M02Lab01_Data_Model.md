---
lab:
  title: 'Laboratório 1: Modelagem de dados'
  module: 'Module 2: Introduction to Microsoft Dataverse'
ms.openlocfilehash: 9e26f2eb6b2e6003510c25b5f66e4f43b30a0640
ms.sourcegitcommit: fc79a9b68a8235b37fd90ef84ba8ae1aa2e581f5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2022
ms.locfileid: "144424685"
---
# <a name="module-2-introduction-to-microsoft-dataverse"></a>Módulo 2: Introdução ao Microsoft Dataverse

# <a name="scenario"></a>Cenário

O Bellows College é uma organização educacional que possui um campus com vários edifícios. Atualmente, as visitas ao campus são registradas em diários de papel. As informações não são coletadas de forma consistente e não há meios de analisar os dados sobre as visitas em todo o campus.

A administração do campus quer modernizar o sistema de registro de visitantes, com controle do acesso aos edifícios pelo pessoal de segurança, além de exigência de notificação prévia e registro de todas as visitas pelos anfitriões.

Ao longo deste curso, você vai criar aplicativos e fazer automações para permitir que a administração e a equipe de segurança do Bellows College gerenciem e controlem o acesso aos edifícios no campus.

Neste laboratório, você acessará seu ambiente, criará um banco de dados do Microsoft Dataverse e desenvolverá uma solução para rastrear suas alterações. Você também criará um modelo de dados para oferecer suporte aos seguintes requisitos:

-   R1 – Rastrear os locais (edifícios) das visitas ao campus

-   R2 – Registrar informações básicas para identificar e monitorar os visitantes

-   R3 – Agendar, registrar e gerenciar as visitas

Por fim, você importará dados de amostra para o Microsoft Dataverse.

# <a name="high-level-lab-steps"></a>Macroetapas do laboratório

Para preparar seus ambientes de aprendizagem, você irá:

* criar uma solução e um editor
* adicionar componentes novos e existentes, necessários para atender aos requisitos do aplicativo. Consulte o [documento de modelagem de dados](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/Campus%20Management.png) para ver a descrição dos metadados (tabelas e relacionamentos). Você pode pressionar CTRL+clique ou clicar com o botão direito do mouse no link para abrir o documento de modelagem de dados em uma nova janela.
* criar tabelas de Edifício e Visita
* importar dados de Visita usando uma planilha do Excel

## <a name="prerequisites"></a>Pré-requisitos:

-   Conclusão do **Módulo 0 Laboratório 0 - Validação do ambiente de laboratório**

## <a name="things-to-consider-before-you-begin"></a>Considere estes itens antes de começar:

-   Convenções de nomenclatura – digite os nomes atentamente.

# <a name="exercise-1-create-new-table"></a>Exercício \#1: Criar tabela

**Objetivo:** Neste exercício, você criará a tabela personalizada de Visitas. 

## <a name="task--1-create-visit-table-and-columns"></a>Tarefa \# 1: Criar a tabela Visita e Colunas

A tabela **Visita** conterá informações sobre as visitas ao campus, incluindo o edifício, o visitante, o horário agendado e real de cada visita.

Gostaríamos de atribuir a cada visita um número exclusivo que pode ser facilmente inserido e interpretado por um visitante quando solicitado durante o processo de check-in da visita.

>   Usamos o comportamento **Independente de fuso horário** para registrar informações de data e hora porque o horário de uma visita sempre é local em relação à localização do edifício e não deve mudar quando visualizado em um fuso horário diferente.

1.  Entre em <https://make.powerapps.com> (se ainda não tiver entrado)

2.  No canto superior direito, selecione o ambiente **Prática [minhas iniciais]** se ainda não tiver selecionado.

3.  Usando a navegação à esquerda, expanda o Dataverse e selecione Tabelas.

4.  Clique em **Nova tabela**.

5.  Digite **Visita** no **Nome de exibição**.

6.  Clique em **Criar**. O provisionamento da tabela será iniciado em segundo plano e você pode começar a adicionar outras colunas.

7.  Criar a coluna Início agendado

    1.  Você deve estar na página de colunas da tabela Visita.

    2.  Verifique se a guia **Colunas** está selecionada e clique em **Adicionar coluna**.

    3.  Digite **Início agendado** como **Nome de exibição**.

    4.  Selecione **Data e hora** como **Tipo de dados**.

    5.  Em **Obrigatório**, selecione **Obrigatório**.

    6.  Expanda a seção **Opções avançadas**.

    7.  Em **Comportamento**, selecione **Independente de fuso horário**.

    8.  Clique em **Concluído**.

8.  Criar coluna Término agendado

    1.  Clique em **Adicionar coluna**.

    2.  Digite **Término agendado** para o **Nome de exibição**.

    3.  Selecione **Data e hora** como **Tipo de dados**.

    4.  Em **Obrigatório**, selecione **Obrigatório**.

    5.  Expanda a seção **Opções avançadas**.

    6.  Em **Comportamento**, selecione **Independente de fuso horário**.

    7.  Clique em **Concluído**.

9.  Criar coluna Início real

    1.  Clique em **Adicionar coluna**.

    2.  Digite **Início real** para o **Nome de exibição**.

    3.  Selecione **Data e hora** como **Tipo de dados**.

    4.  Em **Obrigatório**, deixe marcado como **Opcional**.

    5.  Expanda a seção **Opções avançadas**.

    6.  Em **Comportamento**, selecione **Independente de fuso horário**.

    7.  Clique em **Concluído**.

10. Criar coluna Término real

    1.  Clique em **Adicionar coluna**.

    2.  Digite **Término real** para o **Nome de exibição**.

    3.  Selecione **Data e hora** como **Tipo de dados**.

    4.  Em **Obrigatório**, deixe marcado como **Opcional**.

    5.  Expanda a seção **Opções avançadas**.

    6.  Em **Comportamento**, selecione **Independente de fuso horário**.

    7.  Clique em **Concluído**.

11. Criar a coluna Código

    1.  Clique em **Adicionar coluna**.

    2.  Digite **Código** para o **Nome de exibição**.

    3.  Selecione **Numeração automática** como o **Tipo de dados**.
    
    4.  Selecione **Número prefixado de data** no campo **Tipo de numeração automática**.

    5.  Clique em **Concluído**.

12. Criar coluna de pesquisa de Visitante

    1.  Clique em **Adicionar coluna**.

    2.  Digite **Visitante** para o **Nome de exibição**.

    3.  Selecione **Pesquisar** para **Tipo de dados**.

    4.  Selecione **Contato** para a **Tabela relacionada**.

    5.  Clique em **Concluído**.

13. Clique em **Salvar tabela**

# <a name="exercise-2-import-data"></a>Exercício \#2: Importar dados

**Objetivo:** Neste exercício, você importará dados de amostra para o banco de dados do Dataverse.

## <a name="task-1-import-the-visitsxls-file"></a>Tarefa \#1: Importar o arquivo Visits.xls.

Nesta tarefa, você importará uma solução que contém o fluxo do Power Automate necessário para concluir a importação de dados.

1.  Você deve ter o arquivo **Visits.xls** armazenado em seu desktop. Baixe [Visits.xls](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/majorupdate_april2022/Allfiles/Visits.xlsx) se não tiver.

2.  Se ainda não tiver feito isso, entre em <https://make.powerapps.com>.

3.  No canto superior direito, selecione o ambiente **Prática [minhas iniciais]** se ainda não tiver selecionado.

4.  Usando a navegação à esquerda, expanda o **Dataverse** e selecione Tabelas.

5.  Localize e abra a tabela **Visita** criada no exercício anterior.

6.  Usando o menu na parte superior, selecione a seta ao lado de **Dados**, a seta ao lado de **Obter dados** e **Obter dados do Excel**.

7.  No menu exibido, selecione **Obter dados** e, depois, **Obter dados do Excel**.

8.  No menu exibido, selecione o botão **Carregar**.

9.  Localize e selecione o arquivo **Visits.xls** baixado anteriormente. *(Observe que poderão ser necessários um ou dois minutos para que o arquivo seja carregado. Não se preocupe se você receber uma mensagem indicando que há erros de mapeamento, pois nós os corrigiremos a seguir.)*

10. Selecione **Mapear colunas**.

11. Mapeie as colunas conforme indicado abaixo:

    | Colunas no BD Visitas | Valores de origem   |
    |------------------|-----------------|
    | Término Real       | Término real      |
    | Início Real     | Término real    |
    | Código             | Código            |
    | Nome             | Nome            |
    | Fim agendado    | Término agendado   |
    | Início Agendado  | Início agendado |

12. Deixe todo o restante dos campos como **Não definido**.

13. No canto superior direito da tela, selecione **Salvar alterações**.

14. Na tela **Importar dados**, verifique se o status do mapeamento indica que ele foi bem-sucedido e selecione o botão **Importar**.

**Observação:** *Poderão ser necessários alguns minutos para que os dados sejam importados para a tabela. Não se preocupe se você receber algumas mensagens de erro, isso é normal e não afetará o restante do curso.*

## <a name="task-2-verify-data-import"></a>Tarefa \#2: Verificar importação de dados

1.  Após os dados terem sido importados, use a navegação à esquerda da tela para selecionar a tabela **Visita** novamente.

2.  Usando as guias na parte superior, selecione a guia Dados.

3.  Verifique se há registros na tabela.

Parabéns, você criou tabelas e importou dados com êxito.
