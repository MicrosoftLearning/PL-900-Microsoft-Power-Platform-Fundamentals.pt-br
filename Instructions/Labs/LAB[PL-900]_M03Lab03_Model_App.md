---
lab:
  title: 'Laboratório 3: Como criar um aplicativo baseado em modelo'
  module: 'Module 3: Get started with Power Apps'
ms.openlocfilehash: ed98e1f2c2ff900f84b98910e0ef2d14d130f462
ms.sourcegitcommit: dbffa13e13419f5b9aadc894eb95fd16215b2ebf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2022
ms.locfileid: "146458369"
---
# <a name="module-3-get-started-with-power-apps"></a>Módulo 3: Introdução ao Power Apps
## <a name="lab-how-to-build-a-model-driven-app"></a>Laboratório: Como criar um aplicativo baseado em modelo

# <a name="scenario"></a>Cenário

O Bellows College é uma organização educacional que possui um campus com vários edifícios. Atualmente as visitas ao campus são anotadas em papel. As informações não são coletadas de forma consistente e não há meios de analisar os dados sobre as visitas em todo o campus.

A administração do campus quer modernizar o sistema de registro de visitantes, com controle do acesso aos edifícios pelo pessoal de segurança, além de exigência de notificação prévia e registro de todas as visitas pelos anfitriões.

Ao longo deste curso, você vai criar aplicativos e fazer automações para permitir que a administração e a equipe de segurança do Bellows College gerenciem e controlem o acesso aos edifícios no campus.

Neste laboratório, você criará um aplicativo baseado em modelo do Power Apps para permitir que a equipe de apoio gerencie os registros de visitação de todo o campus.

Macroetapas do laboratório

Você fará o seguinte para criar o aplicativo baseado em modelo:

- Crie um novo aplicativo baseado em modelo denominado Gerenciamento de campus

- Editar a navegação do aplicativo para fazer referência às tabelas necessárias

- Personalize os formulários e as exibições das tabelas necessárias para o aplicativo

Vamos trabalhar com os seguintes componentes:

- **Exibições**: As exibições permitem que o usuário exiba os dados atuais na tabela do formulário.

- **Formulários**: É onde o usuário cria/atualiza novas linhas nas tabelas.

Ambos serão integrados ao aplicativo baseado em modelo para oferecer uma melhor experiência do usuário.

Pré-requisitos

- Conclusão do **Módulo de Laboratório 0 – Validar ambiente de laboratório**

- Conclusão do **Módulo de Laboratório 2 – Modelagem de dados**

- Conclusão do **Módulo de Laboratório 3 – Como criar um aplicativo de tela**

Considerações antes de começar

- Que mudanças precisamos fazer para melhorar a experiência do usuário?

- O que precisamos incluir em um aplicativo baseado em modelo de acordo com o modelo de dados que criamos?

- Quais personalizações podem ser feitas no mapa do site de um aplicativo baseado em modelo?

Exercício nº 1: Personalizar exibições e formulários

**Objetivo:** Neste exercício, você vai personalizar as exibições e os formulários das tabelas personalizadas que serão usadas no aplicativo baseado em modelo.

Tarefa 1: Editar o formulário de visitas

1. Entre em [https://make.powerapps.com](https://make.powerapps.com/) se você ainda não tiver entrado.

2. No canto superior direito, selecione o ambiente **Prática [minhas iniciais]** se ainda não tiver selecionado.

3. Usando a navegação à esquerda, expanda **Dataverse**, selecione **Tabelas** e clique para abrir a tabela **Visita**.

Se você não vir a tabela Visitas, verifique se está no ambiente correto (etapa 2).

4. Nas seções Experiências de Dados, selecione **Formulários** e clique para abrir o formulário Informações com o tipo de formulário **Principal**.

**IMPORTANTE:** Como, por padrão, todos os formulários são denominados Informações, verifique se o formulário selecionado tem um Tipo de formulário **Principal** e não outro. Por padrão, o formulário tem dois campos: Nome (campo principal) e proprietário.

5. No lado direito da tela no painel Propriedades, selecione o campo **Nome de Exibição** e altere-o para **Informações Principais**.

6. Usando o menu na parte superior da tela, selecione **+ Campo de formulário** e adicione os seguintes campos abaixo do campo **Proprietário** arrastando as colunas para o formulário ou apenas clicando nos nomes das colunas:

    0. **Visitante**

    1. **Início agendado**

    2. **Fim agendado**

    3. **Início real**

    4. **Término real**

7. Arraste a coluna **Código** e solte-a no cabeçalho do formulário.

O cabeçalho é a área superior direita do formulário. Pode ser necessário recolher o painel Propriedades do lado direito da tela para ver o campo no formulário.

8. Com o campo **Código** ainda selecionado, marque a caixa de seleção **Somente leitura** no painel Propriedades no lado direito da tela.

9. Selecione o campo **Proprietário**. No painel Propriedades, altere o **Rótulo** para **Anfitrião**

10. Clique em **Salvar** na parte superior direita e espere salvar para concluir.

11. Clique em **Publicar** na parte superior direita e espere publicar para concluir.

12. Se a visualização de edição foi aberta em uma nova guia ou janela do navegador, feche-a. Caso contrário, clique em **Voltar** na parte superior esquerda da tela. Agora você deve estar de volta à guia Formulários das tabelas de Visitas.

13. Usando a trilha de navegação no canto superior esquerdo (Tabelas>Visitas>Formulários). Selecione **Visita** para retornar à tela principal da tabela **Visita**. 

Tarefa 2: Editar a exibição Visitas ativas

Nesta tarefa, vamos modificar a exibição Visitas ativas e criar uma nova exibição para as visitas de hoje.

1. Na seção Experiências de dados, selecione **Exibições** e clique para abrir a exibição **Visitas Ativas**.

2. Inclua os campos a seguir à exibição ao clicar ou arrastar e soltar os campos:

    0. **Código**

    1. **Visitante**

    2. **Início agendado**

    3. **Fim agendado**

3. Clique na coluna **Criado em** e selecione **Remover**. O campo **Criado em** será removido da exibição.

4. Redimensione as larguras das colunas para ajustar os dados.

5. Clique em **Salvar** e espere as alterações serem salvas.

6. Clique em **Publicar** e espere a conclusão da publicação.

Tarefa 3: Criar uma exibição para as visitas de hoje

Agora, vamos clonar a exibição e criar uma para as visitas de hoje.

IMPORTANTE: Verifique se você não fechou a exibição Visitas Ativas, pois vamos usá-la para criar o modo de exibição de visitas de hoje. 

1. Clique na **seta da lista suspensa** ao lado do botão Salvar (cuidado para não pressionar o botão) e selecione **Salvar como**.

2. Altere o nome para **Visitas de Hoje** e pressione **Salvar**.

3. Clique no link **Editar filtros** no painel Propriedades.

4. Clique em **Adicionar** e selecione **Incluir linha**.

5. Selecione **Início agendado** como um campo, depois selecione **Hoje** como a condição na lista suspensa.

6. Clique em **...** na linha **Status** e em **Excluir** para excluir essa condição de filtro.

7. Pressione **Ok** para salvar a condição. A exibição agora é filtrada para mostrar somente registros em que a data de Início agendado é hoje.

8. Inclua os campos **Início real** e **Fim real** à exibição.

**Observação:** como não filtramos mais no status de exibição, obteremos todas as visitas de hoje incluindo as concluídas. Esses campos ajudarão a diferenciar as visitas concluídas e as visitas em andamento.

1. Clique em **Salvar**.

2. Clique em **Publicar** e espere a conclusão da publicação.

Exercício 2: Criar aplicativo baseado em modelo

**Objetivo:** Neste exercício, você vai criar o aplicativo baseado em modelo, personalizar o mapa do site e testar o aplicativo.

Para simplificar e economizar tempo, não abordaremos algumas das colunas Visita neste laboratório.

Tarefa 1: Criar aplicativo

1. Entre em [https://make.powerapps.com](https://make.powerapps.com/) (se ainda não tiver entrado).

2. No canto superior direito, selecione o ambiente **Prática [minhas iniciais]** se ainda não tiver selecionado.

3. Criar o aplicativo baseado em modelo:

    0. Selecione **Aplicativo em branco** na seção **Iniciar em** da tela Página Inicial.

    1. Em **Aplicativo em branco baseado no Dataverse**, selecione **Criar**.

    2. Insira **Administração do campus Bellows** como nome e selecione **Criar**.

4. Quando o novo aplicativo baseado em modelo for carregado, selecione o botão **+ Adicionar Página**.

5. Na tela Adicionar Página, escolha **Exibição e formulário baseados em tabela** e selecione o botão **Avançar**.

6. Adicione as seguintes tabelas:

    0. Visite

    1. Contact

7. Depois de selecionar as duas tabelas, selecione **Adicionar**.

8. Usando os ícones de navegação no lado esquerdo da tela, selecione **Navegação**.

9. No painel de navegação, selecione **Grupo 1** abaixo, na Barra de navegação.

10. No lado direito da tela, na seção **Exibir Opções**, altere a propriedade **Título** para **Segurança**.

Tarefa 2: Editar o aplicativo

Agora que todos os componentes necessários foram adicionados ao aplicativo baseado em modelo, organizaremos os itens.

1. No Painel de Navegação, no grupo de segurança, selecione **SubArea1**.

2. Selecione as **Reticências** e, no menu exibido, selecione para remover **SubArea1**.

3. Use a navegação à esquerda da tela e selecione **Páginas**.

4. Localize e expanda **Visitas** no painel Páginas.

5. Selecione **Formulário de visita**.

6. No lado direito da tela, selecione **Adicionar formulário**.

7. Selecione o formulário **Informações principais**.

8. Em **Visitas** no painel de Páginas, selecione **Visualizar visita**.

9. No lado direito da tela, selecione **Adicionar exibição**.

10. Selecione o modo de exibição **Visitas de Hoje**.

11. Selecione **Adicionar exibição** outra vez. 

12. Selecione a exibição **Visitas Ativas**. 

13. Selecione **Salvar**.

14. Depois de **Salvar**, selecione o botão **Publicar** para publicar as alterações.

Tarefa 3: Testar o aplicativo

1. Iniciar o aplicativo

    0. Selecione **Executar** para abrir o aplicativo em uma nova janela.

2. Criar um novo contato

    0. O aplicativo abrirá a exibição **Meus Contatos Ativos** Se isso não acontecer, selecione Visitas à esquerda.

    1. Clique em **Novo** no menu superior.

    2. Informe o **Nome** como João e o **Sobrenome** como Silva.

    3. Informe seu email pessoal como **e-mail**. Isso será usado em um laboratório futuro em que você receberá um email.

    4. Clique em **Salvar e Fechar**.

    5. Agora, você verá o contato criado na exibição **Contatos ativos**.

3. Criar uma nova visita

    0. Selecione **Visitas** no mapa do site.

    1. Clique em **Nova**.

    2. Preencha os campos da seguinte maneira

        0. **Nome**: Nova visita de teste

        1. **Visitante**: selecione João Silva

        2. **Início agendado**: selecione a data de amanhã e 14h como hora de início

        3. **Fim agendado**: selecione a data de amanhã e 15h30 como hora de término

- Clique em **Salvar e Fechar**. A visita será criada e você poderá vê-la na Exibição de visitas ativas.

- Altere a exibição para **Visitas de Hoje**. Você não verá mais a nova visita na exibição, pois ela foi agendada para amanhã.

4. Você pode adicionar mais registros de teste.

O aplicativo em execução deve ser parecido com o seguinte:

![](media/3-model-driven-app.png)

Parabéns! Você criou e configurou seu primeiro aplicativo controlado por modelos.

# <a name="challenges"></a>Desafios

-   Selecionar exibições e formulários específicos para Contatos
