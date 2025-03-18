---
lab:
  title: 'Laboratório 1: Modelagem de dados'
  module: 'Module 2: Identify foundational components of Microsoft Power Platform'
---

# Laboratório 1: Modelagem de dados

**Locatários do WWL – Termos de Uso** Se você estiver recebendo um locatário como parte de uma entrega de treinamento com instrutor, observe que o locatário é disponibilizado com a finalidade de dar suporte aos laboratórios práticos no treinamento com instrutor. Os locatários não devem ser compartilhados ou usados para fins fora dos laboratórios práticos. O locatário usado neste curso é um locatário de avaliação e não pode ser usado ou acessado após o término da aula e não está qualificado para extensão. Os locatários não podem ser convertidos em uma assinatura paga. Os locatários obtidos como parte deste curso permanecem a propriedade da Microsoft Corporation e reservamos o direito de obter acesso e a qualquer momento. 

## Cenário

O Bellows College é uma organização educacional com vários campi e programas. Muitos instrutores e administradores do Bellows College precisam participar de eventos e comprar itens. Historicamente, o controle dessas despesas tem sido um desafio. 

A administração do campus gostaria de modernizar o sistema de relatórios de despesas fornecendo aos funcionários uma forma de relatar despesas digitalmente. 

Ao longo deste curso, você criará aplicativos e realizará automação para permitir que os funcionários do Bellows College gerenciem as despesas.

Por fim, você importará dados de amostra para o Microsoft Dataverse.

## Macroetapas do laboratório

Para preparar seus ambientes de aprendizagem, você irá:

- Criar a tabela Despesas

- Adicionar alguns dados de amostra. 

### Pré-requisitos

- Conclusão do **Módulo 1 Laboratório 0 – Validação do ambiente de laboratório**

Considerações antes de começar

- Convenções de nomenclatura – insira os nomes com cuidado.

## Exercício 1: Criar tabela

**Objetivo:** Neste exercício, você criará uma nova tabela personalizada para Despesas.

### Tarefa 1: Criar a Tabela e as Colunas de Despesas

A tabela **Despesas** conterá informações sobre despesas individuais que um funcionário pode apresentar, incluindo motivo, tipo, data e valor.

1. Entre em https://make.powerapps.com (se ainda não tiver entrado)

1. No menu **Ambiente** no canto superior direito, verifique se o ambiente **Dev One** está selecionado.

1. Na navegação à esquerda, selecione **Tabelas**.

1. Selecione **+ Nova tabela** e selecione **Tabela (propriedades avançadas)** no menu suspenso.

1. Para **Nome de exibição**, insira `Expense`

1. Clique em **Salvar**.

1. Na seção **Esquema**, selecione **Colunas**.

### Criar a coluna Data da Despesa

1. Selecione **+ Nova coluna**.

1. Para **Nome de exibição**, insira `Expense Date`.

1. Selecione **Somente data** para **Tipo de dados**.

1. Altere **Obrigatório** para **Requisito de negócios**.

1. Expanda **Opções avançadas**.

1. Em **Ajuste do fuso horário**, selecione **Somente data**.

    >**Observação:** Usamos o comportamento **Somente data** para registrar informações de data, porque a data das despesas não deve mudar quando visualizada em um fuso horário diferente.

1. Selecione **Salvar**.

### Criar a coluna Tipo de Despesa

1. Selecione **+ Nova coluna**.

1. Para **Nome de exibição**, insira `Expense Type`.

1. Selecione **Escolha** para **Tipo de dados**.

1. Em **Obrigatório**, selecione **Opcional**.

1. Defina **Sincronizar com a Escolha Global** como **Sim (recomendado)**

1. No campo **Sincronizar esta opção com**, selecione **Tipo de despesa**.

1. Defina o campo **Escolha padrão** como **Nenhuma**.

1. Selecione **Salvar**.

### Criar a Coluna Finalidade da Despesa

1. Selecione **+ Nova coluna**.

1. Para **Nome de exibição**, insira `Expense Purpose`.

1. Selecione **Escolha** para **Tipo de dados**.

1. Em **Obrigatório**, selecione **Opcional**.

1. Defina **Sincronizar com a Escolha Global** como **Sim (recomendado)**

1. No campo **Sincronizar esta opção com**, selecione **Finalidade da Despesa**.

1. Defina o campo **Escolha padrão** como **Nenhuma**.

1. Selecione **Salvar**.

### Criar a coluna Descrição do item

1. Selecione **+ Nova coluna**.

1. Para **Nome de exibição**, insira `Item Description`.

1. Selecione **Várias linhas de texto &gt; Texto simples** para **Tipo de dados**.

1. Selecione **Salvar**.

### Criar a coluna Valor da Despesa

1. Selecione **+ Nova coluna**.

1. Para **Nome de exibição**, insira `Expense Amount`.

1. Selecione **Moeda** para **Tipo de dados**.

1. Selecione **Salvar**.

 
## Exercício 2: Inserir dados

**Objetivo:** Neste exercício, você insere manualmente alguns dados de amostra na sua nova tabela. 

### Tarefa 1: Modificar as colunas exibidas

1. Se ainda não tiver feito isso, entre em https://make.powerapps.com

1. Selecione o ambiente **Dev One** no canto superior direito, se ainda não estiver selecionado.

1. Na navegação à esquerda, selecione **Tabelas**.

1. Abra a tabela **Despesa** criada no exercício anterior.

1. Ao lado da coluna **Nome**, selecione **+mais 26**.

1. No menu que aparecerá, selecione as seguintes colunas.

    1. Data da Despesa

    2. Finalidade da Despesa 

    3. Tipo de Despesa

    4. Valor da Despesa

    5. Descrição do Item

1. Selecione o botão **Salvar**.

## Tarefa 2: Adicionar um registro de amostra.

1. Selecione a **Seta** ao lado de **Editar**. No menu que aparecerá, selecione **Editar em nova guia**.

1. Na coluna **Nome**, insira `John Doe`.

1. Na coluna **Data da Despesa**, insira **xxx**.

1. Na coluna **Finalidade da Despesa**, selecione **Conferência**.

1. Na coluna **Tipo de Despesa**, selecione **Viagem**.

1. Na coluna **Valor da Despesa**, insira `750.00`.

1. Na coluna **Descrição do Item**, insira uma breve descrição.

1. Pressione o botão Tab para avançar para a próxima linha e **salvar** o registro.

Parabéns, você criou com êxito uma nova tabela e adicionou dados.


