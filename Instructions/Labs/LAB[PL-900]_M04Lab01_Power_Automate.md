---
lab:
  title: 'Laboratório 6: Saiba como construir uma solução automatizada'
  module: 'Module 4: Get Started with Power Automate'
ms.openlocfilehash: c37bbf2975aa1964493e93716d0b3aeb32030c99
ms.sourcegitcommit: fc79a9b68a8235b37fd90ef84ba8ae1aa2e581f5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2022
ms.locfileid: "144424626"
---
# <a name="module-4-get-started-with-power-automate"></a>Módulo 4: Introdução ao Power Automate
## <a name="lab-how-to-build-an-automated-solution"></a>Laboratório: Saiba como construir uma solução automatizada

## <a name="scenario"></a>Cenário

O Bellows College é uma organização educacional que possui um campus com vários edifícios. Atualmente as visitas ao campus são anotadas em papel. As informações não são coletadas de forma consistente e não há meios de analisar os dados sobre as visitas em todo o campus.

A administração do campus quer modernizar o sistema de registro de visitantes, com controle do acesso aos edifícios pelo pessoal de segurança, além de exigência de notificação prévia e registro de todas as visitas pelos anfitriões.

Ao longo deste curso, você vai criar aplicativos e fazer automações para permitir que a administração e a equipe de segurança do Bellows College gerenciem e controlem o acesso aos edifícios no campus.

Neste laboratório, você criará fluxos do Power Automate para automatizar várias partes do gerenciamento do campus.

# <a name="high-level-lab-steps"></a>Macroetapas do laboratório

Os pré-requisitos seguintes foram identificados para que o projeto seja concluído:

-   A equipe de segurança precisa receber notificações de visitantes que ultrapassam os horários programados.

## <a name="prerequisites"></a>Pré-requisitos

-   Conclusão do **Módulo 0 Laboratório 0 - Validação do ambiente de laboratório**

-   Conclusão do **Módulo 2 Laboratório 1 - Introdução ao Microsoft Dataverse**

-   Contato John Doe criado com um endereço de email pessoal

## <a name="things-to-consider-before-you-begin"></a>Considerações antes de começar

-   Como medir o tempo de permanência excedente e aplicar políticas rígidas?

# <a name="exercise-1-create-visit-notification-flow"></a>Exercício \#1: Criar fluxo de Notificação de visita

**Objetivo:** Neste exercício será criado um fluxo no Power Automate que implementa o requisito. O visitante deverá receber um email com o código exclusivo atribuído à visita.

## <a name="task-1-create-a-flow"></a>Tarefa \#1: Criar um fluxo

1.  Navegue até <https://make.powerapps.com>. Talvez seja necessário reautenticar - clique em **Entrar** e siga as instruções, se necessário.

2.  No canto superior direito, selecione o ambiente **Prática [minhas iniciais]** se ainda não tiver selecionado.

2.  Na barra de navegação à esquerda, selecione **Fluxos**.

4.  Se solicitado, selecione **Começar**.

5.  Clique em **Novo fluxo** e selecione **Fluxo de nuvem automatizado**.

6.  Em **Escolher o gatilho do fluxo**, pesquise por **Dataverse**.

7.  Selecione o gatilho **Quando uma linha for adicionada, modificada ou excluída** e, em seguida, clique em **Criar**.

8.  Preencha as condições de gatilho do fluxo:

    1.  Selecionar **Adicionado** para **Alterar tipo**

    2.  Selecione **Visitas** em **Nome da tabela**

    3.  Selecione **Organização** em **Escopo**

    4.  Na etapa de ativação, clique nas reticências ( **...** ) e clique em **Renomear**.
        Renomeie esse gatilho **"Quando uma visita é criada"** . Essas ações são importantes para que todos com permissão para editar o fluxo entendam o propósito da etapa sem precisar de maiores detalhes.

## <a name="task-2-create-a-step-to-get-the-visitor-row"></a>Tarefa \#2: Criar uma etapa para obter a linha de visitantes

1.  Selecione **Nova Etapa**. Esta etapa é necessária para recuperar as informações dos visitantes, inclusive o endereço de email.

2.  Pesquise por **Dataverse**.

3.  Selecione a ação **Obter uma linha por ID**.

4.  Selecione **Contatos** em **Nome da tabela**

5.  No campo **ID da linha**, selecione **Visitante (Valor)** na lista de conteúdo dinâmico.

6.  Neste momento, clique nas reticências ( **...** ) e clique em **Renomear**.
        Renomeie esta ação **"Criar visitante"** . Essas ações são importantes para que todos com permissão para editar o fluxo entendam o propósito da etapa sem precisar de maiores detalhes.

## <a name="task-3-create-a-step-to-send-an-email-to-the-visitor"></a>Tarefa \#3: Criar uma etapa para enviar um email ao visitante

1.  Clique em **Nova etapa**. Essa é a etapa que criará e enviará o email ao visitante.

2.  Pesquise por *email*, selecione o conector do **Office 365 Outlook** e a ação **Enviar um email (V2)** .

3.  Se precisar aceitar termos e condições para usar esta ação, clique em **Aceitar**.

4.  Selecione **Adicionar conteúdo dinâmico** no campo **Para**. 
    
5.  Selecione **Email** na lista de conteúdo dinâmico.
        > Notice that it is beneath the **Get the visitor** header. This means you
        are selecting the Email that is related to the Visitor that you looked
        up in the previous step.

5.  Insira **Sua visita agendada ao Bellows College** no campo **Assunto**.

6.  Insira o seguinte texto no **Corpo do email**:

>   O conteúdo dinâmico precisa ser inserido onde os campos são nomeados entre colchetes. É recomendado copiar e colar todo o texto primeiro e, em seguida, adicionar o conteúdo dinâmico nos locais corretos.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
   Dear {First Name},

   You are currently scheduled to visit Bellows Campus from {Scheduled Start} until {Scheduled End}.

   Best regards,

   Campus Administration
   Bellows College
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

7.  Realce o texto **{Nome}** . Substitua-o pelo campo **Nome** da etapa **Obter o visitante**.

8.  Realce o texto **{Início agendado}** . Substitua-o pelo campo **Início agendado** da etapa **Obter o visitante**.

9.  Realce o texto **{Término agendado}** . Substitua-o pelo campo **Término agendado** da etapa **Obter o visitante**.

10.  Selecione o nome do fluxo na parte superior e renomeie-o como `Visit
        Notification`.

11.  Clique em **Salvar**.

Deixe esta guia de fluxo aberta para a próxima tarefa. Seu fluxo deve ser parecido com o seguinte:

![Exemplo de etapas de fluxo.](media/4-Flow.png)

## <a name="task-2-validate-and-test-the-flow"></a>Tarefa \#2: Validar e testar o fluxo

1.  Abra uma nova guia no navegador e navegue para <https://make.powerapps.com>.

2.  No canto superior direito, selecione o ambiente **Prática [minhas iniciais]** se ainda não tiver selecionado.

3.  Clique em **Aplicativos** e selecione o aplicativo **Baseado em modelo de Administração de campus** criado anteriormente.

3.  Deixe esta guia aberta, volte para a guia anterior com o fluxo.

4.  Na barra de comandos, clique em **Testar**. Selecione **Manualmente** e, em seguida, **Salvar e Testar**.

5.  Usando a navegação à esquerda, selecione **Visitas**

6. Pressione o botão **+ Novo** para adicionar um novo registro de **Visita**.

7. Preencha o registro da Visita da seguinte forma:

    -   **Nome:** Visit de teste

    -   **Visitante:** John Doe

    -   **Início agendado:** Amanhã às 8h

    -   **Término agendado:** Amanhã às 9h

8. Selecione o botão **Salvar e Fechar (Save and Close)** .

Após um pequeno atraso, você deverá ver um email em sua caixa de entrada, uma vez que preencheu o email de John Doe com seu email pessoal. 

# <a name="challenges"></a>Desafios

-   Brincar com a formatação no email. Como você pode torná-lo mais profissional? 
