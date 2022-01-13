---
lab:
    title: 'Laboratório 1: Modelagem de dados'
    module: 'Módulo 2: Introdução ao Microsoft Dataverse'
---

# Módulo 2: Introdução ao Microsoft Dataverse

# Cenário

O Bellows College é uma organização educacional que possui um campus com vários edifícios. Atualmente, as visitas ao campus são registradas em diários de papel. As informações não são coletadas de forma consistente e não há meios de analisar os dados sobre as visitas em todo o campus. 

A administração do campus quer modernizar o sistema de registro de visitantes, com controle do acesso aos edifícios pelo pessoal de segurança, além de exigência de notificação prévia e registro de todas as visitas pelos anfitriões.

Ao longo deste curso, você vai criar aplicativos e fazer automações para permitir que a administração e a equipe de segurança do Bellows College gerenciem e controlem o acesso aos edifícios no campus. 

Neste laboratório, você acessará seu ambiente, criará um banco de dados do Microsoft Dataverse e desenvolverá uma solução para rastrear suas alterações. Você também criará um modelo de dados para oferecer suporte aos seguintes requisitos:

-   R1 – Rastrear os locais (edifícios) das visitas ao campus
-   R2 – Registrar informações básicas para identificar e monitorar os visitantes 
-   R3 – Agendar, registrar e gerenciar as visitas 

Por fim, você importará dados de amostra para o Microsoft Dataverse.

# Macroetapas do laboratório

Para preparar seus ambientes de aprendizagem, você irá:

* criar uma solução e um editor
* adicionar componentes novos e existentes, necessários para atender aos requisitos do aplicativo. Consulte o [documento de modelagem de dados](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/Campus%20Management.png) para ver a descrição dos metadados (tabelas e relacionamentos). Você pode pressionar CTRL+clique ou clicar com o botão direito do mouse no link para abrir o documento de modelagem de dados em uma nova janela.

A sua solução conterá várias tabelas após a conclusão de todas as personalizações:

-   Contato
-   Edifício
-   Visita

## Pré-requisitos:

* Conclusão do **Módulo 0 Laboratório 0 - Validação do ambiente de laboratório**

## Considere estes itens antes de começar:

* Convenção de nomenclatura

* Tipos de dados, restrições (por exemplo, comprimento máximo de um nome)

* Formato de data e hora para facilitar a localização

# Exercício \#1: Criar uma solução

## Tarefa 1: Criar uma solução e um editor

1.  Criar uma solução

    -   Acesse <https://make.powerapps.com>. Talvez seja necessário reautenticar - clique em **Entrar** e siga as instruções, se necessário.

    -   Selecione o seu ambiente clicando em **Ambiente**, no canto superior direito da tela, e escolhendo o seu ambiente no menu suspenso.

    -   No menu esquerdo, selecione **Soluções** e clique em **Nova solução**.

    -   Digite **[Seu sobrenome] Gerenciamento de Campus** no campo **Nome de exibição**.

2.  Criar um editor

    -   Na seção **Editor**, selecione **+ Editor**

    -   Na janela exibida, digite **Bellows College** no campo **Nome de exibição**. 

    -   Insira **BellowsCollege** no campo **Nome**.
    
    -   Digite **bc** no campo **Prefixo**

    -   Clique em **Salvar**
    
    -   Na janela pop-up, clique em **Concluído**.

3.  Conclua a criação da solução.

    -   Agora, clique no menu suspenso **Editor** e selecione o editor **Bellows College**
        que você acabou de criar.

    -   Valide se a **Versão** está definida como **1.0.0.0** 
    
    -   Clique em **Criar**.

# Exercício \#2: Adicionar tabelas existentes e criar novas tabelas

**Objetivo:** Neste exercício, você adicionará a tabela Contato padrão e criará novas tabelas personalizadas para Edifícios e Visitas na solução. 

## Tarefa 1: Adicionar tabelas existentes

1.  Clique para abrir a solução **Gerenciamento de Campus** que você acabou de criar.

2.  Clique em **Adicionar existente** e selecione **Tabela**.

3.  Localize o **Contato** e selecione-o.

4.  Clique em **Próximo**.

5.  Em Contato, clique em **Selecionar componentes**.

6.  Selecione a guia **Exibições** e, em seguida, a exibição **Contatos ativos**. Clique em
    **Adicionar**.
    
7.  Clique em **Selecionar componentes** novamente.

8.  Selecione a guia **Formulários** e, em seguida, o formulário **Contato**.
    
9.  Clique em **Adicionar**.

    > Você deve ter **1 exibição** e **1 formulário** selecionados. 
    
10.  Clique em **Adicionar** novamente. A tabela Contato com a Exibição e o Formulário selecionados será adicionada à solução recém-criada.

> Sua solução agora deve ter uma tabela: Contato.
    
## Tarefa 2: Criar a tabela Edifício

1.  Você ainda deve estar com o navegador aberto na solução Gerenciamento de Campus. Se não estiver, abra a solução Gerenciamento de Campus seguindo estas etapas:

    * Faça login em <https://make.powerapps.com> (se ainda não tiver feito)
    
    * Selecione **Soluções** e clique para abrir a solução **[Seu sobrenome] Gerenciamento de Campus**
          que você acabou de criar.
          
2.  Criar a tabela Edifício

    -   Clique em **Novo** e selecione **Tabela**.
    
    -   Digite **Edifício** no campo **Nome de exibição** 
    
    -   Clique em **Salvar**. O provisionamento da tabela será iniciado em segundo plano e você pode começar a adicionar outras tabelas e colunas.

## Tarefa 3: Criar a tabela Visita e Colunas

A tabela **Visita** conterá informações sobre as visitas ao campus, incluindo o edifício, o visitante, o horário agendado e real de cada visita. 

Gostaríamos de atribuir a cada visita um número exclusivo que pode ser facilmente inserido e interpretado por um visitante quando solicitado durante o processo de check-in da visita.

> Usamos o comportamento **Independente de fuso horário** para registrar informações de data e hora porque o horário de uma visita é sempre local em relação à localização do edifício e não deve mudar quando visualizado de um fuso horário diferente. 

1.  Você ainda deve estar com o navegador aberto na solução Gerenciamento de Campus. Se não estiver, abra a solução Gerenciamento de Campus seguindo estas etapas:

    * Faça login em <https://make.powerapps.com> (se ainda não tiver feito)
    
    * Selecione **Soluções** e clique para abrir a solução **[Seu sobrenome] Gerenciamento de Campus**
          que você acabou de criar.

2. Criar a tabela Visita

   * Clique em **Novo** e selecione **Tabela**.
   
   * Digite **Visita** no campo **Nome de exibição** 
   
   * Clique em **Salvar**. O provisionamento da tabela será iniciado em segundo plano e você pode começar a adicionar outras colunas.

3. Criar a coluna Início agendado

   * Selecione a tabela **Visita**

   * Verifique se a guia **Colunas** está selecionada e clique em **Adicionar coluna**.
   
   * Digite **Início agendado** no campo **Nome de exibição**.
   
   * Selecione **Data e hora** no campo **Tipo de dados**.
   
   * Em **Obrigatório**, selecione **Obrigatório**.
   
   * Expanda a seção **Opções avançadas**.
   
   * Em **Comportamento**, selecione **Independente de fuso horário**.
   
   * Clique em **Concluído**.

4.  Criar coluna Término agendado

    * Clique em **Adicionar coluna**.
    
    * Digite **Término agendado** no campo **Nome de exibição**.
    
    * Selecione **Data e hora** no campo **Tipo de dados**.
    
    * Em **Obrigatório**, selecione **Obrigatório**.
    
    * Expanda a seção **Opções avançadas**.
    
    * Em **Comportamento**, selecione **Independente de fuso horário**.
    
    * Clique em **Concluído**.
    
5.  Criar coluna Início real

    * Clique em **Adicionar coluna**.
    
    * Digite **Início real** no campo **Nome de exibição**.
    
    * Selecione **Data e hora** no campo **Tipo de dados**.
    
    * Em **Obrigatório**, deixe marcado como **Opcional**.
    
    * Expanda a seção **Opções avançadas**.
    
    * Em **Comportamento**, selecione **Independente de fuso horário**.
    
    * Clique em **Concluído**.
    
6.  Criar coluna Término real

    * Clique em **Adicionar coluna**.
    
    * Digite **Término real** no campo **Nome de exibição**.
    
    * Selecione **Data e hora** no campo **Tipo de dados**.
    
    * Em **Obrigatório**, deixe marcado como **Opcional**.
    
    * Expanda a seção **Opções avançadas**.
    
    * Em **Comportamento**, selecione **Independente de fuso horário**.
    
    * Clique em **Concluído**.
    
7.  Criar a coluna Código

    * Clique em **Adicionar coluna**.
    
    * Digite **Código** no campo **Nome de exibição**.
    
    * Selecione **Numeração automática** no campo **Tipo de dados**.
    
    * Selecione **Número prefixado de data** no campo **Tipo de numeração automática**.
    
    * Clique em **Concluído**.
    
8.  Clique em **Salvar tabela**

# Exercício \#3: Criar relacionamentos

**Objetivo:** Neste exercício, você adicionará relacionamentos entre as tabelas.

## Tarefa 1: Criar relacionamentos

1.  Verifique se você ainda está visualizando a tabela **Visita** da solução **Gerenciamento de Campus**. Se não estiver, navegue até ela.

2.  Criar o relacionamento Visita ao contato

    * Selecione a guia **Relacionamentos**.
    
    * Clique em **Adicionar relacionamento** e selecione **Muitos para muitos**
    
    * Selecione **Contato** para **Relacionado (Um)** 
    
    * Digite **Visitante** no campo **Nome de exibição da coluna de pesquisa** 
    
    * Clique em **Concluído**.
    
3.  Criar o relacionamento Visita ao edifício

    * Clique em **Adicionar relacionamento** e selecione **Muitos para muitos**
    
    * Selecione **Edifício** para **Relacionado (Um)** 
    
    * Clique em **Concluído**.
    
4.  Clique em **Salvar tabela**.

5.  Selecione **Voltar para soluções** na parte superior esquerda.

6.  Selecione **Publicar todas as personalizações.**

# Exercício \#4: Importar dados

**Objetivo:** Neste exercício, você importará dados de amostra para o banco de dados do Dataverse.

## Tarefa 1: Importar solução

Nesta tarefa, você importará uma solução que contém o fluxo do Power Automate necessário para concluir a importação de dados.

1. Você deve ter o arquivo **DataImport_managed.zip** armazenado no seu Desktop. Se ainda não tiver baixado, baixe a [Solução de importação de dados](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/DataImport_managed.zip?raw=true).

2. Faça login em <https://make.powerapps.com>.

3. No canto superior direito, selecione o ambiente **Prática [Minhas iniciais]**, se ainda tiver selecionado.

4. No painel de navegação esquerdo, selecione **Soluções**.

5. Clique em **Importar** e, em seguida, em **Procurar**. Procure e selecione **DataImport_managed.zip** no seu Desktop e pressione **Próximo**.

>   Você pode receber a seguinte mensagem:
>
>   Estão faltando dependências. Instale as soluções a seguir antes de instalar esta...
>
>   Essa mensagem indica que o modelo de dados não está completo, o
>   prefixo do editor não é **bc** ou os nomes das tabelas **Building** e **Visits**
>   são diferentes dos nomes listados nas etapas acima.

6. Pressione **Próximo**. Você deverá restabelecer as conexões. 

7. Expanda o menu suspenso **Selecionar uma conexão** e selecione **+ Nova conexão**.

8. A nova janela ou guia do navegador será aberta. Selecione **Criar** quando solicitado para fazer a conexão. Se necessário, faça login para concluir a criação da conexão.

9. Feche a guia atual para voltar à guia anterior **Importar uma solução**.

10. Verifique se a conexão que você acabou de criar está selecionada. Se a sua conexão não aparecer, clique em **Atualizar** para atualizar a lista de conexões. 

11. Pressione **Importar**.

12. Aguarde até que a importação seja concluída.

## Tarefa 2: Importar dados  

1. Abra a solução **Importação de dados**.

2. Verifique o **Status** do fluxo **Importar dados**.

3. Se **Status** estiver **Desativado**, selecione **[...]** ao lado de **Importar dados** e, em seguida, selecione **Ativar**.

   > **Importante:** Se você receber uma mensagem de erro, verifique se as tabelas e colunas criadas correspondem às instruções acima.

4. Abra o componente **Importar dados**. Uma nova guia abrirá o Power Automate. 

5. Clique em **Introdução** se aparecer uma mensagem pop-up. 

6. Clique em **Executar** e, em seguida, clique em **Executar fluxo** quando solicitado.

7. Clique em **Concluído**.

8. Aguarde até que a instância do fluxo conclua a execução. Você pode atualizar a tabela **Histórico de execução de 28 dias** para ver quando o fluxo foi executado. 

    > O objetivo deste fluxo era gerar dados de exemplo para os próximos laboratórios. Na próxima tarefa, você verificará se a importação de dados foi bem-sucedida. 

## Tarefa 3: Verificar importação de dados

1. Navegue de volta até a guia Power Apps anterior. No pop-up, clique em **Concluído**. 

2. Na barra de navegação à esquerda, selecione **Soluções** e abra a solução **Gerenciamento de Campus**.

2. Clique para abrir a tabela **Visita** e, em seguida, selecione a guia **Dados**.

3. No canto superior direito, clique em **Visitas ativas** para exibir o seletor de visualização e, em seguida, selecione **Todas as colunas**. Essa seleção mudará a visualização que está sendo usada para exibir os dados da Visita. 

    > Se as **Visitas ativas** não forem exibidas devido à resolução menor, você deverá ver um ícone de olho no mesmo local.

    > Se a importação for bem-sucedida, você deverá ver uma lista de linhas de visita.

4. Clique em qualquer valor na coluna **Edifício** e confirme se o formulário Edifício abre em uma janela separada. 

5. Feche a janela aberta recentemente.

6. Clique em qualquer valor na coluna **Visitante** (pode ser necessário rolar a tela para a direita) e confirme se o formulário Contato abre em uma janela separada.

7. Feche a janela aberta recentemente.

# Desafios

* Você consideraria usar a atividade *compromisso* como parte da solução? O que isso mudaria?
* Como você poderia fazer com que o término agendado ocorresse após o início agendado? 
* Como você poderia adicionar suporte para várias reuniões durante uma única visita?
* Como você poderia proteger o acesso ao edifício não apenas para contatos externos, mas também para membros da equipe interna?
* Como você poderia fazer com que visitas a certos edifícios exijam aprovação da administração? O que mudaria o processo de aprovação no modelo de dados?

