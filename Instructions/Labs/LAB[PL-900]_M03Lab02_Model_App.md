---
lab:
  title: 'Laboratório 3: Como criar um aplicativo baseado em modelo'
  module: 'Module 3: Get started with Power Apps'
---

# Laboratório 3: Como criar um aplicativo baseado em modelo

**Locatários do WWL – Termos de Uso** Se você estiver recebendo um locatário como parte de uma entrega de treinamento com instrutor, observe que o locatário é disponibilizado com a finalidade de dar suporte aos laboratórios práticos no treinamento com instrutor. Os locatários não devem ser compartilhados ou usados para fins fora dos laboratórios práticos. O locatário usado neste curso é um locatário de avaliação e não pode ser usado ou acessado após o fim da aula e não está qualificado para extensão. Os locatários não podem ser convertidos em uma assinatura paga. Os locatários obtidos como parte deste curso permanecem a propriedade da Microsoft Corporation e reservamos o direito de obter acesso e a qualquer momento. 

## Cenário

O Bellows College é uma organização educacional que possui um campus com vários edifícios. Atualmente as visitas ao campus são anotadas em papel. As informações não são coletadas de forma consistente e não há meios de analisar os dados sobre as visitas em todo o campus.

A administração do campus quer modernizar o sistema de registro de visitantes, com controle do acesso aos edifícios pelo pessoal de segurança, além de exigência de notificação prévia e registro de todas as visitas pelos anfitriões.

Ao longo deste curso, você vai criar aplicativos e fazer automações para permitir que a administração e a equipe de segurança do Bellows College gerenciem e controlem o acesso aos edifícios no campus.

Neste laboratório, você criará um aplicativo baseado em modelo do Power Apps para permitir que a equipe de apoio gerencie os registros de visitação de todo o campus.

Macroetapas do laboratório

Você fará o seguinte para criar o aplicativo baseado em modelo:

- Crie um novo aplicativo baseado em modelo denominado Gerenciamento de Campus do Bellows

- Editar a navegação do aplicativo para fazer referência às tabelas necessárias

- Personalize os formulários e as exibições das tabelas necessárias para o aplicativo

Vamos trabalhar com os seguintes componentes:

- **Exibições**: As exibições permitem que o usuário exiba os dados atuais na tabela do formulário.

- **Formulários**: É onde o usuário cria/atualiza novas linhas nas tabelas.

Ambos serão integrados ao aplicativo baseado em modelo para oferecer uma melhor experiência do usuário.

Pré-requisitos

- Conclusão do **Módulo 0 Laboratório 0 - Validação do ambiente de laboratório**

- Conclusão do **Laboratório 1 do Módulo 2 – Modelagem de Dados**

Considerações antes de começar

- Que mudanças precisamos fazer para melhorar a experiência do usuário?

- O que precisamos incluir em um aplicativo baseado em modelo de acordo com o modelo de dados que criamos?

- Quais personalizações podem ser feitas no mapa do site de um aplicativo baseado em modelo?

Exercício 1: Personalizar exibições e formulários

**Objetivo:** Neste exercício, você vai personalizar as exibições e os formulários das tabelas personalizadas que serão usadas no aplicativo baseado em modelo.

Tarefa 1: Editar o formulário de visitas

1. Entre em [https://make.powerapps.com](https://make.powerapps.com/) se você ainda não tiver entrado.

2. No canto superior direito, selecione o ambiente **Prática [minhas iniciais]** se ainda não tiver selecionado.

3. Usando a navegação à esquerda, selecione **Tabelas** e clique para abrir a tabela **Visita**.

Se você não vir a tabela Visitas, verifique se está no ambiente correto (etapa 2).

4. Na seção **Experiências de dados**, selecione **Formulários** e clique para abrir o formulário Informações com o tipo de formulário **Principal**. (**Importante:** selecione aquele com o tipo de formulário **Main**.) 

**IMPORTANTE:** Como, por padrão, todos os formulários são denominados Informações, verifique se o formulário selecionado tem um Tipo de formulário **Principal** e não outro. Por padrão, o formulário tem dois campos: Nome e Proprietário.

1. No lado direito da tela no painel Propriedades, selecione o campo **Nome de Exibição** e altere-o para **Informações Principais**.

2. Selecione **Colunas da Tabela** no painel de navegação à esquerda e adicione os seguintes campos abaixo do campo **Proprietário** arrastando as colunas para o formulário ou simplesmente clicando nos nomes das colunas:

    1. **Visitante**

    2. **Início agendado**

    3. **Fim agendado**

    4. **Início real**

    5. **Término real**

3. Arraste a coluna **Código** e solte-a no cabeçalho do formulário.

O cabeçalho é a área superior direita do formulário. Pode ser necessário recolher o painel Propriedades do lado direito da tela para ver o campo no formulário.

1. Com o campo **Código** ainda selecionado, marque a caixa de seleção **Somente leitura** no painel Propriedades no lado direito da tela.

2. Selecione o campo **Proprietário**. No painel Propriedades, altere o **Rótulo** para **Anfitrião**

3. Clique no botão **Salvar e publicar** na parte superior direita e espere salvar e publicar para concluir.

4. Se a visualização de edição foi aberta em uma nova guia ou janela do navegador, feche-a. Caso contrário, clique em **Voltar** na parte superior esquerda da tela. Agora você deve estar de volta aos Formulários das tabelas de Visitas.

5. Usando a trilha de navegação no canto superior esquerdo (Tabelas>Visitas>Formulários). Selecione **Visita** para retornar à tela principal da tabela **Visita**.

Tarefa 2: Editar a exibição Visitas ativas

Nesta tarefa, vamos modificar a exibição Visitas ativas e criar uma nova exibição para as visitas de hoje.

1. Na seção **Experiências de dados**, selecione **Exibições** e clique para abrir a exibição **Visitas ativas**.

2. Inclua os campos a seguir à exibição ao clicar ou arrastar e soltar os campos:

    1. **Código**

    2. **Visitante**

    3. **Início agendado**

    4. **Fim agendado**

3. Clique na coluna **Criado em** e selecione **Remover**. O campo **Criado em** será removido da exibição.

4. Redimensione as larguras das colunas para ajustar os dados.

5. Em **Classificar por ...** selecione o X para remover o **Nome** e, em vez disso, selecione **Início Agendado**.

6. Selecione **Início Agendado** para alterar a ordem de classificação para **Mais Recente para Mais Antigo**.

7. Clique em **Salvar** e espere as alterações serem salvas.

8. Clique em **Publicar** e espere a conclusão da publicação.

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

1. Clique em **Salvar** e espere as alterações serem salvas.

2. Clique em **Publicar** e espere a conclusão da publicação.

Exercício 2: Criar aplicativo baseado em modelo

**Objetivo:** neste exercício, você criará o aplicativo baseado em modelo, personalizará o mapa do site e testará o aplicativo.

Para simplificar e economizar tempo, não abordaremos algumas das colunas Visita neste laboratório.

Tarefa 1: Criar aplicativo

1. Entre em [https://make.powerapps.com](https://make.powerapps.com/) (se ainda não tiver entrado).

2. No canto superior direito, selecione o ambiente **Prática [minhas iniciais]** se ainda não tiver selecionado.

3. Se necessário, clique no ícone **Página Inicial** no lado esquerdo da tela.

4. Criar o aplicativo baseado em modelo:

    1. Selecione **Aplicativo em branco** na seção **Iniciar em** da tela Página Inicial.

    2. Em **Aplicativo em branco baseado no Dataverse**, selecione **Criar**.

    3. Insira **Administração do campus Bellows** como nome e selecione **Criar**.

5. Quando o novo aplicativo baseado em modelo for carregado, selecione o botão **+ Adicionar Página**.

6. Na tela **Adicionar Página**, escolha **Tabela do Dataverse** e selecione o botão **Avançar**.

7. Adicione as seguintes tabelas:

    1. Visite

    2. Contact

8. Depois de selecionar as duas tabelas, selecione **Adicionar**.

9. Usando os ícones de navegação no lado esquerdo da tela, selecione **Navegação**.

10. No painel de navegação, selecione **Grupo 1** abaixo, na Barra de navegação. Talvez seja necessário expandir o menu à esquerda.

11. No lado direito da tela, na seção **Exibir Opções**, altere a propriedade **Título** para **Segurança**.

12. No Painel de Navegação, no grupo de segurança, selecione **SubArea1**.

13. Selecione as **Reticências** e, no menu exibido, selecione **Remover da navegação**.

14. Selecione **Salvar** espere as alterações serem salvas.

15. Depois de **Salvar**, selecione o botão **Publicar** para publicar as alterações.

Tarefa nº 2: Testar app

1. Iniciar o aplicativo

    1. Selecione o botão **Reproduzir**, o novo app será carregado em uma nova guia.

2. Criar um novo contato

    1. O aplicativo abrirá a exibição **Meus Contatos Ativos** Se isso não acontecer, selecione Contatos à esquerda.

    2. Clique em **+ Novo** no menu superior.

    3. Informe o **Nome** como João e o **Sobrenome** como Silva.

    4. Informe seu email pessoal como **e-mail**. Isso será usado em um laboratório futuro em que você receberá um email.

    5. Clique em **Salvar &amp; Fechar**.

    6. Agora, você verá o contato criado na exibição **Meus Contatos Ativos**.

3. Criar uma nova visita

    1. Selecione **Visitas** na navegação esquerda do mapa do site.

    2. Clique em **+ Novo**.

    3. Preencha os campos da seguinte maneira

        1. **Nome**: Nova visita de teste

        2. **Visitante**: selecione João Silva

        3. **Início agendado**: selecione a data de amanhã e 14h como hora de início

        4. **Fim agendado**: selecione a data de amanhã e 15h30 como hora de término

- Clique em **Salvar &amp; Fechar**. A visita será criada e você poderá vê-la na Exibição de visitas ativas.

- Altere o modo de exibição para **Visitas de Hoje** usando a lista suspensa ao lado de **Visitas Ativas**. Você não verá mais a nova visita na exibição, pois ela foi agendada para amanhã.

1. Você pode adicionar mais registros de teste.

O aplicativo em execução deve ser parecido com o seguinte:

![](media/3-model-driven-app.png)

Parabéns! Você criou e configurou seu primeiro aplicativo controlado por modelos.

## Desafios

- Selecionar exibições e formulários específicos para Contatos.
