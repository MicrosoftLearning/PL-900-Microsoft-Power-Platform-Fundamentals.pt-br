---
lab:
  title: '‘Laboratório 4: Saiba como construir uma solução automatizada'
  module: 'Module 4: Get Started with Power Automate'
---

# ‘Laboratório 4: Saiba como construir uma solução automatizada

**Locatários do WWL – Termos de Uso** Se você estiver recebendo um locatário como parte de uma entrega de treinamento com instrutor, observe que o locatário é disponibilizado com a finalidade de dar suporte aos laboratórios práticos no treinamento com instrutor. Os locatários não devem ser compartilhados ou usados para fins fora dos laboratórios práticos. O locatário usado neste curso é um locatário de avaliação e não pode ser usado ou acessado após o fim da aula e não está qualificado para extensão. Os locatários não podem ser convertidos em uma assinatura paga. Os locatários obtidos como parte deste curso permanecem a propriedade da Microsoft Corporation e reservamos o direito de obter acesso e a qualquer momento. 

## Cenário

O Bellows College é uma organização educacional que possui um campus com vários edifícios. Atualmente as visitas ao campus são anotadas em papel. As informações não são coletadas de forma consistente e não há meios de analisar os dados sobre as visitas em todo o campus.

A administração do campus quer modernizar o sistema de registro de visitantes, com controle do acesso aos edifícios pelo pessoal de segurança, além de exigência de notificação prévia e registro de todas as visitas pelos anfitriões.

Ao longo deste curso, você vai criar aplicativos e fazer automações para permitir que a administração e a equipe de segurança do Bellows College gerenciem e controlem o acesso aos edifícios no campus.

Neste laboratório, você criará um fluxo do Power Automate para enviar um email a um visitante quando uma visita for agendada.

## Macroetapas do laboratório

Os pré-requisitos seguintes foram identificados para que o projeto seja concluído:

- Os contatos precisam ser notificados por email quando uma visita for agendada.

## Pré-requisitos

- Conclusão do **Módulo 0 Laboratório 0 - Validação do ambiente de laboratório**
- Conclusão do **Laboratório 1 do Módulo 2 – Modelagem de Dados**
- Conclusão do **Laboratório 3 do Módulo 2 – Como criar um aplicativo controlado por modelo**
- Contato de Davi Barros criado com um endereço de email pessoal preenchido.

## Exercício 1: Criar fluxo de Notificação de visita

**Objetivo:** Neste exercício será criado um fluxo no Power Automate que implementa o requisito. O visitante deve receber um email incluindo o código exclusivo atribuído à visita quando ela é criada.

### Tarefa \#1: Criar um fluxo

1.  Navegue até <https://make.powerapps.com>. Talvez seja necessário se reautenticar: selecione **Entrar** e siga as instruções, se necessário.

2.  No canto superior direito, selecione o ambiente **Prática [minhas iniciais]** se ainda não tiver selecionado.

3.  Na barra de navegação à esquerda, selecione **Fluxos**.

4.  Se solicitado, selecione **Começar**.

5.  Escolha **+ Novo fluxo** e selecione **Fluxo de nuvem automatizado**.

6.  Insira `Visit Notification` em **Nome do fluxo**.

7.  Em **Escolher o gatilho do fluxo**, procure `Dataverse`

8.  Escolha o gatilho **Quando uma linha for adicionada, modificada ou excluída** e selecione **Criar**.

9.  Preencha as condições de gatilho do fluxo:

    1.  Selecionar **Adicionado** para **Alterar tipo**

    2.  Selecione **Visitas** em **Nome da tabela**

    3.  Selecione **Organização** em **Escopo**

    4.  Na etapa de gatilho, selecione as reticências ( **…** ) e escolha **Renomear**. Renomeie a etapa de gatilho como `When a Visit is added` 

        Essas ações são importantes para que todos com permissão para editar o fluxo entendam o propósito da etapa sem precisar de maiores detalhes.


### Tarefa \#2: Criar uma etapa para obter a linha de visitantes

1.  Selecione **+ Nova Etapa**. Essa etapa vai recuperar as informações do Visitante, incluindo o endereço de email.

2.  Pesquise por `Dataverse`

3.  Selecione a ação **Obter uma linha por ID**.

4.  Selecione **Contatos** em **Nome da tabela**

5.  Selecione o campo **ID da Linha**. Observe que será exibida uma janela para selecionar **Conteúdo dinâmico** ou **Expressões**.

6.  No campo **ID da linha**, selecione **Visitante (Valor)** na lista **Conteúdo dinâmico**. Nesta etapa, busque o contato da linha de Visita que foi criada para acionar esse fluxo. Como o endereço de email faz parte da tabela de Contato, você precisará dessas informações para enviar o email ao visitante.

7.  Na ação **Obter uma linha por ID**, selecione as reticências ( **…** ) e escolha **Renomear**. Renomeie essa ação como `Get the Visitor`
 
    Essas ações são importantes para que todos com permissão para editar o fluxo entendam o propósito da etapa sem precisar de maiores detalhes.


### Tarefa \#3: Criar uma etapa para enviar um email ao visitante

1.  Selecione **+ Nova Etapa**. É nessa a etapa que um email será enviado para o visitante.

2.  Procure `mail` e selecione a ação **Enviar um email (V2)** no conector do **Office 365 Outlook**.

3.  Caso precise aceitar os termos e as condições para usar essa ação, selecione **Aceitar**.

4.  Selecione **Adicionar conteúdo dinâmico** no campo **Para**. 
    
5.  Selecione **Email** na lista de conteúdo dinâmico.

    > Observe que está abaixo do cabeçalho **Criar visitante**. Isso significa que você está selecionando o email relacionado ao Visitante que foi consultado na etapa anterior.

7.  No campo **Assunto**, insira `Your scheduled visit to Bellows College`

8.  Insira o seguinte texto no **Corpo do email**:

    > O conteúdo dinâmico precisa ser inserido onde os campos são nomeados entre colchetes. É recomendado copiar e colar todo o texto primeiro e, em seguida, adicionar o conteúdo dinâmico nos locais corretos.

    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    Dear {First Name},

    You are currently scheduled to visit Bellows Campus from {Scheduled Start} until {Scheduled End}.

    Best regards,

    Campus Administration
    Bellows College
    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

8.  Realce o texto **{First Name}** . Substitua-o pelo campo **Nome** da etapa **Obter o visitante**.

9.  Realce o texto **{Scheduled Start}** . Substitua-o pelo campo **Início do agendamento** na etapa **Quando a visita será adicionada**.

10.  Realce o texto **{Scheduled End}** . Substitua-o pelo campo **Final do agendamento** na etapa **Quando uma visita será adicionada**.

11.  Selecione **Salvar**.

Deixe esta guia de fluxo aberta para a próxima tarefa. Seu fluxo deve ser parecido com o seguinte:

![Exemplo de etapas de fluxo.](media/4-Flow.png)


### Tarefa \#4: Validar e testar o fluxo

1.  Abra uma nova guia no navegador e navegue para <https://make.powerapps.com>.

2.  No canto superior direito, selecione o ambiente **Prática [minhas iniciais]** se ainda não tiver selecionado.

3.  Escolha **Aplicativos** e abra o aplicativo baseado em modelo **Administração de Campus do Bellows** criado anteriormente.

3.  Deixando essa guia do navegador aberta, navegue de volta para a guia anterior de seu fluxo.

4.  Na barra de comandos, escolha **Teste**. Selecione **Manualmente** e **Testar**.

5.  Navegue até a guia do navegador com seu aplicativo baseado em modelo aberto. 

6.  Usando a navegação de mapa do site à esquerda, selecione **Visitas**.

6.  Escolha o botão **+ Novo** para adicionar um novo registro de **Visita**.

7.  Preencha o registro da Visita da seguinte forma:

    -   **Nome:** `Test Visit`

    -   **Visitante:** John Doe

    -   **Início agendado:** Amanhã às 8h

    -   **Término agendado:** Amanhã às 9h

8.  Selecione o botão **Salvar e Fechar**.

9.  Vá até a guia do navegador em que o fluxo de teste está em execução. Após um momento, você deverá ver o fluxo em execução. É aqui que você pode detectar quaisquer problemas no fluxo ou confirmar se ele foi executado com êxito.

    Após um pequeno atraso, você deverá ver um email em sua caixa de entrada, uma vez que preencheu o email de John Doe com seu email pessoal. Observe que ele pode ir para sua pasta de lixo eletrônico.


## Desafio

- Experimente a formatação no email. Como você pode torná-lo mais profissional?


