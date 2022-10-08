---
lab:
  title: '‘Laboratório 4: Saiba como construir uma solução automatizada'
  module: 'Module 4: Get Started with Power Automate'
---

# <a name="lab-4-how-to-build-an-automated-solution"></a>‘Laboratório 4: Saiba como construir uma solução automatizada

## <a name="scenario"></a>Cenário

Bellows College is an educational organization with multiple buildings on campus. Campus visitors are currently recorded in paper journals. The information is not captured consistently, and there are no means to collect and analyze data about the visits across the entire campus.

A administração do campus quer modernizar o sistema de registro de visitantes, com controle do acesso aos edifícios pelo pessoal de segurança, além de exigência de notificação prévia e registro de todas as visitas pelos anfitriões.

Ao longo deste curso, você vai criar aplicativos e fazer automações para permitir que a administração e a equipe de segurança do Bellows College gerenciem e controlem o acesso aos edifícios no campus.

Neste laboratório, você criará um fluxo do Power Automate para enviar um email a um visitante quando uma visita for agendada.

## <a name="high-level-lab-steps"></a>Macroetapas do laboratório

Os pré-requisitos seguintes foram identificados para que o projeto seja concluído:

- Os contatos precisam ser notificados por email quando uma visita for agendada.

## <a name="prerequisites"></a>Pré-requisitos

- Conclusão do **Módulo 0 Laboratório 0 - Validação do ambiente de laboratório**
- Conclusão do **Laboratório 1 do Módulo 2 – Modelagem de Dados**
- Conclusão do **Laboratório 3 do Módulo 2 – Como criar um aplicativo controlado por modelo**
- Contato de Davi Barros criado com um endereço de email pessoal preenchido

## <a name="exercise-1-create-visit-notification-flow"></a>Exercício 1: Criar fluxo de Notificação de visita

<bpt id="p1">**</bpt>Objective:<ept id="p1">**</ept> In this exercise, you will create a Power Automate flow that implements the requirement. The visitor should be sent an email that includes the unique code assigned to the visit when a visit is created.

### <a name="task-1-create-a-flow"></a>Tarefa \#1: Criar um fluxo

1.  Navigate to <ph id="ph1">&lt;https://make.powerapps.com&gt;</ph>. You may need to reauthenticate - click <bpt id="p1">**</bpt>Sign in<ept id="p1">**</ept> and follow instructions if needed.

2.  No canto superior direito, selecione o ambiente **Prática [minhas iniciais]** se ainda não tiver selecionado.

3.  Na barra de navegação à esquerda, selecione **Fluxos**.

4.  Se solicitado, selecione **Começar**.

5.  Clique em **Novo fluxo** e selecione **Fluxo de nuvem automatizado**.

6.  Insira "Notificação de Visita" em **Nome do fluxo**.

7.  Em **Escolher o gatilho do fluxo**, pesquise por **Dataverse**.

8.  Selecione o gatilho **Quando uma linha for adicionada, modificada ou excluída** e, em seguida, clique em **Criar**.

9.  Preencha as condições de gatilho do fluxo:

    1.  Selecionar **Adicionado** para **Alterar tipo**

    2.  Selecione **Visitas** em **Nome da tabela**

    3.  Selecione **Organização** em **Escopo**

    4.  On the trigger step, click the ellipsis (<bpt id="p1">**</bpt>...<ept id="p1">**</ept>) and click <bpt id="p2">**</bpt>Rename<ept id="p2">**</ept>. Rename this trigger <bpt id="p1">**</bpt>"When a visit is added"<ept id="p1">**</ept>. This is a good practice, so you and other flow editors can understand the purpose of the step without having to dive into the details.

### <a name="task-2-create-a-step-to-get-the-visitor-row"></a>Tarefa \#2: Criar uma etapa para obter a linha de visitantes

1.  O Bellows College é uma organização educacional que possui um campus com vários edifícios.

2.  Pesquise por **Dataverse**.

3.  Selecione a ação **Obter uma linha por ID**.

4.  Selecione **Contatos** em **Nome da tabela**

5.  Atualmente as visitas ao campus são anotadas em papel.

6.  As informações não são coletadas de forma consistente e não há meios de analisar os dados sobre as visitas em todo o campus.

7.  On this action, click the ellipsis (<bpt id="p1">**</bpt>...<ept id="p1">**</ept>) and click <bpt id="p2">**</bpt>Rename<ept id="p2">**</ept>.
        Rename this action <bpt id="p1">**</bpt>"Get the Visitor"<ept id="p1">**</ept>. This is a good practice, so you and other flow editors can understand the purpose of the step without having to dive into the details.

### <a name="task-3-create-a-step-to-send-an-email-to-the-visitor"></a>Tarefa \#3: Criar uma etapa para enviar um email ao visitante

1.  Click <bpt id="p1">**</bpt>+ New step<ept id="p1">**</ept>. This is the step that will send an email to the visitor.

2.  Pesquise por *email*, selecione o conector do **Office 365 Outlook** e a ação **Enviar um email (V2)** .

3.  Se precisar aceitar termos e condições para usar esta ação, clique em **Aceitar**.

4.  Selecione **Adicionar conteúdo dinâmico** no campo **Para**. 
    
5.  Selecione **Email** na lista de conteúdo dinâmico.
        > Notice that it is beneath the **Get the visitor** header. This means you
        are selecting the Email that is related to the Visitor that you looked
        up in the previous step.

6.  Insira **Sua visita agendada ao Bellows College** no campo **Assunto**.

7.  Insira o seguinte texto no **Corpo do email**:

>   Dynamic content needs to be placed where fields are named in brackets. It is recommended to copy &amp; paste all text first and then add dynamic content in the correct places.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
   Dear {First Name},

   You are currently scheduled to visit Bellows Campus from {Scheduled Start} until {Scheduled End}.

   Best regards,

   Campus Administration
   Bellows College
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

8.  Highlight the <bpt id="p1">**</bpt>{First Name}<ept id="p1">**</ept> text. Replace it with the <bpt id="p1">**</bpt>First Name<ept id="p1">**</ept> field from the <bpt id="p2">**</bpt>Get the Visitor<ept id="p2">**</ept> step.

9.  Highlight the <bpt id="p1">**</bpt>{Scheduled Start}<ept id="p1">**</ept> text. Replace it with the <bpt id="p1">**</bpt>Scheduled Start<ept id="p1">**</ept> field <bpt id="p2">**</bpt>When a visit is added<ept id="p2">**</ept> step.

10.  Highlight the <bpt id="p1">**</bpt>{Scheduled End}<ept id="p1">**</ept> text. Replace it with the <bpt id="p1">**</bpt>Scheduled End<ept id="p1">**</ept> field from the <bpt id="p2">**</bpt>When a visit is added<ept id="p2">**</ept> step.

11.  Clique em **Salvar**.

Leave this flow tab open for the next task. You flow should look approximately like the following:

![Exemplo de etapas de fluxo.](media/4-Flow.png)

### <a name="task-4-validate-and-test-the-flow"></a>Tarefa \#4: Validar e testar o fluxo

1.  Abra uma nova guia no navegador e navegue para <https://make.powerapps.com>.

2.  No canto superior direito, selecione o ambiente **Prática [minhas iniciais]** se ainda não tiver selecionado.

3.  Clique em **Aplicativos** e selecione o aplicativo baseado em modelo **Administração de campus Bellows** criado anteriormente.

3.  Deixando essa guia do navegador aberta, navegue de volta para a guia anterior de seu fluxo.

4.  On the command bar, click <bpt id="p1">**</bpt>Test<ept id="p1">**</ept>. Select <bpt id="p1">**</bpt>Manually<ept id="p1">**</ept> and then click <bpt id="p2">**</bpt>Test<ept id="p2">**</ept>.

5.  Navegue até a guia do navegador com seu aplicativo baseado em modelo aberto. 

6.  Usando a navegação à esquerda, selecione **Visitas**

6. Pressione o botão **+ Novo** para adicionar um novo registro de **Visita**.

7. Preencha o registro da Visita da seguinte forma:

    -   **Nome:** Visit de teste

    -   **Visitante:** John Doe

    -   **Início agendado:** Amanhã às 8h

    -   **Término agendado:** Amanhã às 9h

8. Selecione o botão **Salvar e Fechar (Save and Close)** .

9. Navigate to the browser tab with your flow test running. After a short delay, you should see the flow running. This is where you can catch any issues in the flow or confirm that it ran successfully.

After a short delay, you should see an email in your inbox, since you populated John Doe's email as your personal email. Note that it may go to your Junk Email folder.

## <a name="challenges"></a>Desafios

- Play around with the formatting on the email. How can you make it more professional looking?