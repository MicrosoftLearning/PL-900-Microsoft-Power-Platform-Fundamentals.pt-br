---
lab:
  title: '‘Laboratório 4: Saiba como construir uma solução automatizada'
  module: 'Module 4: Get Started with Power Automate'
---

# ‘Laboratório 4: Saiba como construir uma solução automatizada

**Locatários do WWL – Termos de Uso** Se você estiver recebendo um locatário como parte de uma entrega de treinamento com instrutor, observe que o locatário é disponibilizado com a finalidade de dar suporte aos laboratórios práticos no treinamento com instrutor. Os locatários não devem ser compartilhados ou usados para fins fora dos laboratórios práticos. O locatário usado neste curso é um locatário de avaliação e não pode ser usado ou acessado após o término da aula e não está qualificado para extensão. Os locatários não podem ser convertidos em uma assinatura paga. Os locatários obtidos como parte deste curso permanecem a propriedade da Microsoft Corporation e reservamos o direito de obter acesso e a qualquer momento. 

## Cenário

O Bellows College é uma organização educacional com vários campi e programas. Muitos instrutores e administradores do Bellows College precisam participar de eventos e comprar itens. Historicamente, o controle dessas despesas tem sido um desafio. 

A administração do campus gostaria de modernizar o sistema de relatórios de despesas fornecendo aos funcionários uma forma de relatar despesas digitalmente. 

Ao longo deste curso, você criará aplicativos e realizará automação para permitir que os funcionários do Bellows College gerenciem as despesas. 

Neste laboratório, você criará um fluxo do Power Automate para enviar por email uma cópia do relatório de despesas quando eles criarem um novo Relatório de Despesas.

## Macroetapas do laboratório

Os pré-requisitos seguintes foram identificados para que o projeto seja concluído:

- Os funcionários precisam receber um email quando um Relatório de Despesas é enviado. 

### Pré-requisitos

- Conclusão do **Módulo 1 Laboratório 0 – Validação do ambiente de laboratório**

## Exercício 1: Criar o fluxo de notificação do relatório de despesas

**Objetivo:** Neste exercício será criado um fluxo no Power Automate que implementa o requisito. 

### Tarefa 1: Criar um fluxo

1. Navegue até https://make.powerapps.com

1. Talvez seja necessário se reautenticar: selecione **Entrar** e siga as instruções, se necessário.

1. Selecione o ambiente **Dev One** no canto superior direito, se ainda não estiver selecionado.

1. Na barra de navegação à esquerda, selecione **Fluxos**.

1. Se solicitado, selecione **Começar**.

1. Escolha **+ Novo fluxo** e selecione **Fluxo de nuvem automatizado**.

1. Insira a Notificação de Despesas para **Nome do fluxo**.

1. Em **Escolha o gatilho do seu fluxo**, pesquise por Dataverse

1. Escolha o gatilho **Quando uma linha for adicionada, modificada ou excluída** e selecione **Criar**.

1. Preencha as condições de gatilho do fluxo:

    1. Selecionar **Adicionado** para **Alterar tipo**
    
    1. Selecione **Relatórios de Despesas** para **Nome da tabela**

    1. Selecione **Organização** em **Escopo**

    1. Na etapa de gatilho, selecione as reticências ( **…** ) e escolha **Renomear**. Renomeie a etapa de gatilho como `When an Expense Report is added` 

Essa é uma boa prática, para que você e outros editores de fluxo possam entender a finalidade da etapa sem precisar se aprofundar nos detalhes.

### Tarefa 2: Criar uma etapa para obter a linha do relatório de despesas

1. Selecione **+Nova etapa**. Esta etapa recuperará as informações do Relatório de despesas, incluindo o endereço de email.

1. Pesquisar Dataverse

1. Selecione a ação **Obter uma linha por ID**.

1. Selecione **Usuários** como **Nome da tabela**

1. Selecione o campo **ID da Linha**. Observe que será exibida uma janela para selecionar **Conteúdo dinâmico** ou **Expressões**.

1. No campo **ID da Linha**, selecione **Proprietário (Valor)** na lista **Conteúdo dinâmico**. Nesta etapa, você está procurando o Proprietário da linha do Relatório de Despesas que foi criada para disparar esse fluxo. 

1. Na ação **Obter uma linha por ID**, selecione as reticências ( **…** ) e escolha **Renomear**. Renomeie essa ação para Obter o proprietário

Essa é uma boa prática, para que você e outros editores de fluxo possam entender a finalidade da etapa sem precisar se aprofundar nos detalhes.

### Tarefa 3: Criar uma etapa para enviar um email para confirmar o envio de um relatório de despesas

1. Selecione **+Nova etapa**. Esta é a etapa que enviará um email para a pessoa que enviou um relatório de despesas.

1. Pesquise emails, selecione a ação **Enviar um email (V2)** no conector do **Office 365 Outlook**.

1. Caso precise aceitar os termos e as condições para usar essa ação, selecione **Aceitar**.

1. Selecione o campo **Para** e insira seu endereço de email pessoal. (Há muitas maneiras de preencher dinamicamente um endereço de email, mas, para este exercício, vamos atribuí-lo manualmente).  

1. No campo **Assunto**, insira Seu relatório de despesas foi enviado

1. Insira o seguinte texto no **Corpo do email**:

O conteúdo dinâmico precisa ser inserido onde os campos são nomeados entre colchetes. É recomendado copiar e colar todo o texto primeiro e, em seguida, adicionar o conteúdo dinâmico nos locais corretos.

    Dear {First Name},
    
    Thank you for submitting your expense report for the total amount of {Report Total Amount} with a due date of {Report Due Date}.
    
     
    Best regards,
    Campus Administration
    Bellows College

1. Realce o texto **{First Name}** . Substitua-o pelo campo **Nome** da etapa **Obter proprietário**.

1. Destaque o texto **{Report Total Amount}**. Substitua pelo campo **Valor Total do Relatório** da etapa **Quando um relatório de despesas for enviado**.

1. Realce o texto **{Report Due Date}**. Substitua pelo campo **Data de Vencimento do Relatório** da etapa **Quando um relatório de despesas é enviado**.

1. Selecione **Salvar**.

Deixe esta guia de fluxo aberta para a próxima tarefa. Seu fluxo deve se parecer com o seguinte:

![Captura de tela do fluxo que acabou de ser criado](media/lab-4-create-an-automated-solution-01.png)

### Tarefa 4: Validar e testar o fluxo

1. Abra uma nova guia no navegador e navegue até https://make.powerapps.com

1. Selecione o ambiente **Dev One** no canto superior direito, se ainda não estiver selecionado.

1. Selecione **Aplicativos** e abra o **Aplicativo de Acompanhamento de Despesas**.

1. Deixando essa guia do navegador aberta, navegue de volta para a guia anterior de seu fluxo.

1. Na barra de comandos, escolha **Teste**. Selecione **Manualmente** e **Testar**.

1. Navegue até a guia do navegador com seu aplicativo baseado em modelo aberto.

1. Usando a navegação do mapa do site à esquerda, selecione **Relatório de Despesas**.

1. Selecione o botão **+Novo** para adicionar um novo registro de **Relatório de Despesas**.

1. Preencha o registro **Relatório de Despesas** da seguinte forma:

    - **Nome do Relatório:** Relatório de Teste

    - **Data de conclusão do relatório: ** Amanhã 

1. Selecione o botão **Salvar e Fechar**.

1. Vá até a guia do navegador em que o fluxo de teste está em execução. Após um momento, você deverá ver o fluxo em execução. É aqui que você pode detectar quaisquer problemas no fluxo ou confirmar se ele foi executado com êxito.

Após um breve atraso, você verá um email na sua caixa de entrada. 

>**Observação:** Ele pode ir para a pasta lixo eletrônico.
