---
lab:
  title: 'Laboratório 1: Criar uma solução'
  learning path: 'Learning Path: Manage the Microsoft Power Platform environment'
  module: 'Module 1: Describe Microsoft Dataverse'
---

## Objetivo de aprendizado

Neste exercício, você criará uma solução do Power Platform para armazenar os diferentes componentes que criar. No Power Platform, as soluções são usadas para agrupar diferentes componentes e fornecer transportabilidade. A solução criada neste exercício será usada durante todo o restante do curso.

### Cenário

A Contoso Consulting é uma organização de serviços profissionais especializada em serviços de consultoria de TI e IA. Ao longo do ano, eles promovem muitos eventos diferentes para seus clientes. Alguns deles são eventos no estilo de feiras em que muitos parceiros participam e dão detalhes sobre novos produtos, tendências de mercado e serviços. Outros ocorrem ao longo do ano e são webinars rápidos usados para fornecer detalhes sobre produtos individuais.

A Contoso gostaria de usar o Power Platform para criar uma solução de gerenciamento de eventos que possa ser usada para gerenciar os diferentes eventos que promovem ao longo do ano.

Neste exercício, você criará uma solução que será usada para o Gerenciamento do Ciclo de Vida do Aplicativo e agrupará todos os diferentes aplicativos, sites e fluxos que criamos juntos para que possam ser facilmente gerenciados e transportados.

O tempo estimado para concluir este exercício é de **15 a 20**minutos.

Após a conclusão bem-sucedida deste laboratório, você poderá:

- Criar uma solução de gerenciamento de eventos
- Adicionar as tabelas de Conta e Contato existentes à solução.
- Criar uma nova tabela chamada Eventos de dentro da solução.

## Tarefa 1: Criar uma solução de gerenciamento de eventos

1.  Abra o [Power Apps Maker Portal](https://make.powerapps.com).
2.  Navegue até **Soluções**.
3.  Na barra de comandos, selecione **Nova solução**.
4.  Na tela da nova solução, configure da seguinte maneira:
    - **Nome de exibição:** Gerenciamento de eventos
    - **Nome:** Gerenciamento de eventos
5.  Em **Editor**, selecione **+ Novo editor**
6.  Configure o novo editor da maneira a seguir
    - **Nome de exibição:** EventMSLEventMSLearnarn
    - **Nome:** EverntMSLearn
    - **Prefixo:** mslearn
    - **Prefixo do valor de escolha:** Mantenha o padrão

![Uma captura de tela da caixa de diálogo Criar Editor.](media/61fa62c324d424f7c73c8291a0724130.png)

7.  Selecione o botão **Salvar** para salvar o editor.
8.  No campo **Editor**, selecione o editor **EventMSlearn** que você acabou de criar.
9.  Selecione **Definir sua solução preferencial**.

![Uma captura da solução concluída](media/f968526926661bfa401f10742e6f376f.png)

10.  Selecione **Criar**.

## Tarefa 2: Adicionar componentes existentes a uma solução.

Agora que criamos uma solução para armazenar nossos componentes, vamos adicionar algumas tabelas existentes a ela. Vamos adicionar as tabelas Conta e Contato, para que elas possam ser usadas facilmente em nossos diferentes aplicativos, fluxos e sites de Gerenciamento de Eventos. Primeiro, vamos adicionar a tabela Conta à solução.

1.  Se necessário, vá para a solução **Gerenciamento de Eventos** que você criou na tarefa anterior.
2.  Na **Barra de comandos**, selecione **Adicionar existente**.
3.  No menu exibido, selecione **Tabela**.
4.  Selecione a tabela **Conta** e, depois, **Avançar**.
5.  Na tela **Selecionar Tabelas**, selecione **Incluir todos os objetos**.
6.  Selecione **Adicionar**

Agora que temos a tabela Conta, vamos adicionar a tabela de contatos.

7.  Na **Barra de comandos**, selecione o botão **existente** novamente **.**
8.  No menu exibido, selecione **Tabela**.
9.  Selecione a tabela **Contato** e selecione **Avançar.**
10.  Na tela **Selecionar Tabelas**, selecione **Incluir todos os objetos**
11.  Selecione **Adicionar**

![Uma captura de tela mostrando as tabelas Conta e Contato na solução.](media/a53817e242fca7371765583d9e565c36.png)

Parabéns, você criou com êxito uma nova solução usando o Microsoft Power Platform. Continuaremos usando a solução para adicionar componentes adicionais a ela.
