---
lab:
  title: 'Laboratório 6: Criando um fluxo do Power Automate'
  learning path: 'Learning Path: Demonstrate the capabilities of Microsoft Power Automate'
  module: 'Module 2: Build a Microsoft Power Automate flow'
---

## Objetivo de aprendizado

Neste exercício, os alunos criarão uma série de fluxos de nuvem diferentes usando o Microsoft Copilot no Power Automate. Você usará diferentes métodos de criação, como o Copilot, do zero para se familiarizar com as diferentes opções disponíveis.

Após a conclusão bem-sucedida deste laboratório, você poderá:

- Usar prompts de linguagem natural para criar fluxos de trabalho
- Configurar gatilhos e ações
- Testar a automação para uso prático.

### Cenário

A Contoso Consulting é uma organização de serviços profissionais especializada em serviços de consultoria de TI e IA. Ao longo do ano, eles promovem muitos eventos diferentes para seus clientes. Alguns deles são eventos no estilo de feiras em que muitos parceiros participam e dão detalhes sobre novos produtos, tendências de mercado e serviços. Outros ocorrem ao longo do ano e são webinars rápidos usados para fornecer detalhes sobre produtos individuais. Além disso, a Contoso está começando a usar agentes automatizados para ajudar os clientes com perguntas.

A Contoso gostaria de usar o Power Automate para criar um fluxo de confirmação de registro que enviará um email automatizado para um cliente quando ele se registrar em um evento. 

Neste exercício, você criará uma série de fluxos do Power Automate com base em critérios específicos.

Antes de iniciar este exercício, você precisa ter concluído os seguintes laboratórios:

- **Laboratório 2 – Criar um modelo de dados**
- **Laboratório 5 – Criar um aplicativo baseado em modelo**

## Exercício 1: Criar fluxo de notificação de Registro de Sessão

Neste primeiro exercício, você criará um fluxo que será executado automaticamente quando um novo Registro de Sessão for criado. Ele obterá os detalhes da sessão, do evento e do contato que registrou e enviará um email para ele com seus detalhes de registro.

### Tarefa 1: Criar um fluxo

Queremos enviar uma confirmação de registro para todos os usuários recém-registrados. Criaremos um fluxo que capturará detalhes de um registro e enviará um email de confirmação para o usuário registrado.

1. Navegue até [https://make.powerautomate.com](https://make.powerautomate.com/).

2. Talvez seja necessário se reautenticar: selecione **Entrar** e siga as instruções, se necessário.

3. Selecione o ambiente **Dev One** no canto superior direito, se ainda não estiver selecionado. (Importante, esqueça de fazer esta etapa).

4. Na navegação à esquerda, selecione **Criar**. (Se solicitado, selecione **Começar**.)

5. Escolha **+ Novo fluxo** e selecione **Fluxo de nuvem automatizado**.

6. Insira **Notificação de Registro** como **Nome do fluxo**.

7. Em **Escolher o gatilho do fluxo**, pesquise por **Dataverse**.

8. Escolha o gatilho **Quando uma linha for adicionada, modificada ou excluída** e selecione **Criar**.

    Se você vir um erro **Parâmetros Inválidos**, isso ocorre porque você não se autenticou. Siga as etapas abaixo para criar uma conexão. 
    - Selecione **Alterar Conexão**.
    - Selecione **Adicionar Nova.*
    - No campo **Nome da Conexão**, insira o MOD **Administrador**. Deixe o **Tipo de autenticação** como **OAuth** e selecione **Entrar**.
    - Depois de conectado, vá para a **Etapa 9.** 

9. Preencha as condições de gatilho do fluxo:

    - Selecionar **Adicionado** para **Alterar tipo**
    - Selecione **Registros de Sessão** para **Nome da tabela.**
    - Selecione **Organização** como **Escopo** na etapa do gatilho, selecione as reticências (**...**) e selecione **Renomear**. 

10. Renomeie a etapa de gatilho como **Quando um Registro de Sessão é adicionado.**

![Captura de tela da configuração do gatilho quando um registro de sessão é adicionado](media/power-automate-01.png)

Essa é uma boa prática, para que você e outros editores de fluxo possam entender a finalidade da etapa sem precisar se aprofundar nos detalhes.


### Tarefa 2: Criar uma etapa para obter os detalhes da Sessão de Evento do Registro.

1. Selecione **+Nova etapa**. 

2. Pesquise **Obter uma linha por ID**. 

3. Selecione a ação **Obter uma linha por ID**.

4. Selecione **Sessões de Evento** como **Nome da tabela**

5. Selecione o campo **ID da Linha**. Observe que ícones aparecem para selecionar **Conteúdo dinâmico** ou **Expressões**.

6. No campo **ID da Linha**, selecione **Sessão de Evento (Valor)** na lista **Conteúdo dinâmico**. Nesta etapa, você está procurando a **Sessão do Evento** para o **Registro de Sessão** que foi criado para disparar esse fluxo.

7. Na ação **Obter uma linha por ID**, selecione as reticências ( **…** ) e escolha **Renomear**. Renomeie esta ação como **Obter a Sessão de Evento**

![Captura de tela da configuração da ação Obter a Sessão de Evento](media/power-automate-02.png)

Em seguida, obteremos os detalhes do evento em que a sessão está.

8. Na etapa **Obter Sessão de Evento**, selecione **+ Inserir Ação.**

9. Pesquise **Obter uma linha por ID**. 

10. Selecione a ação **Obter uma linha por ID**.

11. Selecione **Eventos** como **Nome da tabela**

12. Selecione o campo **ID da Linha**. Observe que ícones aparecem para selecionar **Conteúdo dinâmico** ou **Expressões**.

13. No campo **ID da Linha**, selecione **Evento (Valor)** na lista **Conteúdo dinâmico**. Nesta etapa, você está pesquisando o **Evento** da **Sessão de Evento** do que foi capturado na etapa anterior.

14. Na ação **Obter uma linha por ID**, selecione as reticências ( **…** ) e escolha **Renomear**. Renomeie essa ação para **Obter o evento**.

![Captura de tela da configuração da ação Obter o evento](media/power-automate-03a.png)

Por fim, vamos obter os detalhes da pessoa registrada para a sessão.

15. Em Obter Detalhes do Evento, selecione **Inserir nova Ação**.

16. No campo de pesquisa, insira **Obter uma linha por ID**.

17. Selecione **Obter uma linha por ID**.

18. Selecione **Contatos** em **Nome da tabela**

19. Selecione o campo **ID da Linha**. Observe que será exibida uma janela para selecionar **Conteúdo dinâmico** ou **Expressões**.

20. No campo **ID da Linha**, selecione o campo **Participante (Valor)** do gatilho **Quando um registro de sessão é adicionado** na lista **Conteúdo dinâmico**.

21. Selecione o texto **Obter uma linha por ID** e renomeie a ação como **Obter** **Detalhes do participante**.

![Captura de tela da configuração da ação Obter Detalhes do Participante](media/power-automate-04a.png)

### Tarefa 3: Criar uma etapa para enviar um email para confirmar o registro da sessão

1. Na etapa **Obter Detalhes do Participante**, selecione **Inserir nova Ação**.

2. No campo de pesquisa, insira **Enviar um email**.

3. Selecione **Enviar um email (V2)**.

Você poderá ser solicitado a criar uma conexão com o Outlook, caso contrário, selecione o botão **Entrar** e faça logon com a conta **Administrador do Mod**. 

![Uma captura da tela Criar Conexão](media/power-automate-05.png)

4. Logo acima do campo **Para**, selecione o ícone de **Engrenagem**. No menu exibido, selecione **Usar conteúdo dinâmico**.

![Captura de tela do uso de conteúdo dinâmico](media/power-automate-06.png) 

5. Usando valores dinâmicos, no campo **Para**, selecione **Email** em **Obter Detalhes do Participante**.

![Captura de tela da configuração do campo para o email do participante.](media/power-automate-07.png)

6. No campo **Assunto**, verifique se diz Confirmação de Registro.

7. Insira o seguinte texto no **Corpo do email**:

> **Observação:** O conteúdo dinâmico precisa ser inserido onde os campos são nomeados entre colchetes. É recomendado copiar e colar todo o texto primeiro e, em seguida, adicionar o conteúdo dinâmico nos locais corretos.

  *Prezado {Nome}, obrigado por se registrar em nossa próxima sessão {Nome da Sessão} em {Data do Evento}. {Speaker} será o palestrante nesta sessão. Sua sessão está agendada para durar {Duração (Horas)}. Confira nossa outra sessão em nosso {Nome do Evento}.*

  *Atenciosamente,*

  *Administração de eventos*
  
  *Contoso Consulting*

Em seguida, substituiremos o texto entre colchetes pelos itens descritos abaixo.

8. Realce o texto **{First Name}** . Substitua-o pelo campo **Nome** da etapa **Obter detalhes do participante**.

9. Realce o texto **{Nome da sessão}**. Substitua-o pelo campo **Nome da sessão** da etapa **Obter sessão de evento**.

10. Realce o texto **{Data do evento}**. Substitua-o pelo campo **Data do evento** da etapa **Obter detalhes do evento**.

11. Realce o texto **{Palestrante}**. Substitua-o pelo campo **Palestrante (Valor)** da etapa **Obter sessão de evento**.

12. Realce o texto **{Duração (Horas)}**. Substitua-o pelo campo **Duração (Horas)** da etapa **Obter sessão de evento**.

13. Realce o texto **{Nome do evento}**. Substitua-o pelo campo **Nome do evento** da etapa **Obter detalhes do evento**.

A etapa concluída deve ficar parecida com esta imagem:

![Captura de tela do email concluído](media/power-automate-08.png)

14. Selecione **Salvar**.

Deixe esta guia de fluxo aberta para a próxima tarefa. Seu fluxo deve se parecer com o seguinte:

### Tarefa 4: Inserir alguns dados de amostra

> **Observação:** Se você concluiu o Laboratório 5 – Criar um aplicativo baseado em modelo, ignore essa tarefa e vá diretamente para a Tarefa 5. 

1. Na navegação esquerda, selecione **Aplicativos**.

2. Altere os aplicativos que estão sendo exibidos de **Meus aplicativos** para **Todos**.

3. Passe o mouse sobre o aplicativo de **Gerenciamento de eventos** e selecione o ícone **Reproduzir**.

4. Na navegação esquerda, selecione **Contatos**.

5. Na barra de comandos, selecione o botão **+ Novo**.

6. Na tela **Novo contato**, configure da seguinte maneira:

    - **Nome:** Suzanne

    - **Sobrenome:** Diaz

    - **Cargo:** Engenheira

7. No cabeçalho do formulário, selecione a seta para baixo ao lado de **Tipo de Contato**.

8. Defina o **Tipo de Contato** como **Palestrante**.

![Captura de tela mostrando como definir o campo Tipo de Contato em um formulário.](media/power-automate-09.png)

9. Selecione o botão **Salvar** para salvar o contato e deixá-lo aberto.

10. Selecione o botão **+ Novo**.

11. Na tela **Novo contato**, configure da seguinte maneira:

    - **Nome:** Edgar

    - **Sobrenome:** Swenson

    - **Cargo:** Arquiteto

    - **Email:** Insira seu endereço de email (IMPORTANTE, ou seu fluxo não será executado)

12. No cabeçalho do formulário, selecione a seta para baixo ao lado de **Tipo de Contato**.

13. Defina o **Tipo de Contato** como **Participante**.

14. Selecione o botão **Salvar e Fechar**.

Em seguida, vamos adicionar um novo evento.

15. Na navegação à esquerda, selecione **Eventos**.

16. Na barra de comandos, selecione o botão **+ Novo**.

17. Na tela **Novo evento**, configure da seguinte maneira:

    - **Nome do evento:** Conferência de primavera.

    - **Data do evento:** Data de amanhã.

    - **Máximo de Participantes:** 500

    - **Detalhes do evento:** Conferência de primavera para mostrar os produtos e serviços mais recentes de nossos fornecedores com suporte.

    - **Tipo de Evento:** Conferência

    - **Localização:** Seattle

    - **Registro Necessário:** Sim/True

![Captura de tela do formulário de evento concluído. ](media/power-automate-10.png)

18. Selecione o botão **Salvar e Fechar**.

Em seguida, adicionaremos uma nova sessão ao Evento.

19. Usando a navegação à esquerda, selecione **Sessões de Evento**.

20. Selecione o botão **+ Novo**.

21. Configure a **Sessão de Evento** da seguinte maneira:

    - **Nome da Sessão:** IA responsável

    - **Data da Sessão:** Data de amanhã

    - **Duração:** 1,5 horas

    - **Descrição da sessão:** Com todas as novas soluções de IA, ser responsável é importante. Discutiremos os desafios.

    - **Palestrante:** Suzanne Diaz

    - **Evento:** Conferência de primavera

![Captura de tela do formulário de sessão de evento concluído. ](media/power-automate-11.png)

22. Selecione o botão **Salvar e Fechar (Save and Close)** .

 
### Tarefa 5: Validar e testar o fluxo

1. Se necessário, abra uma nova guia no navegador e navegue até [https://make.powerapps.com](https://make.powerapps.com/). 

2. Selecione o ambiente **Dev One** no canto superior direito, se ainda não estiver selecionado.

3. Selecione **Aplicativos** e abra o **Aplicativo de Gerenciamento de Eventos da Contoso**.

4. Deixando essa guia do navegador aberta, navegue de volta para a guia anterior de seu fluxo.

5. Na barra de comandos, escolha **Teste**. Selecione **Manualmente** e **Testar**.

6. Navegue até a guia do navegador com seu aplicativo baseado em modelo aberto.

Por fim, vamos criar um **Registro de Sessão**.

7. Usando a navegação à esquerda, selecione **Registros de Sessão**.

8. Na **Barra de comandos**, selecione **+ Novo**.

9. Conclua o registro da sessão da seguinte maneira:

    - **Nome:** Registro de E, Swenson.

    - **Data do Registro:** Data de hoje

    - **Participante:** Edgar Swenson

    - **Sessão:** IA responsável

![Captura de tela do formulário de registro de sessão concluído. ](media/power-automate-12.png)

10. Selecione o botão **Salvar e Fechar **.

11. Selecione o botão **Salvar e Fechar**.

12. Vá até a guia do navegador em que o fluxo de teste está em execução. Após um momento, você deverá ver o fluxo em execução. É aqui que você pode detectar quaisquer problemas no fluxo ou confirmar se ele foi executado com êxito.

Após um breve atraso, você verá um email na sua caixa de entrada.

> **Observação:** Ele pode ir para a pasta lixo eletrônico.
