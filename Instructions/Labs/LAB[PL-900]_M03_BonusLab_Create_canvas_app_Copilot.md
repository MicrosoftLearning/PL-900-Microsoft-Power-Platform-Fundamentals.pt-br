---
lab:
  title: 'Laboratório de bônus: Criar um aplicativo de tela usando o Copilot'
  module: 'Module 3: Describe how to build applications with Microsoft Power Apps'
---

# Laboratório de bônus: Criar um aplicativo de tela usando o Copilot

**Locatários do WWL – Termos de Uso** Se você estiver recebendo um locatário como parte de uma entrega de treinamento com instrutor, observe que o locatário é disponibilizado com a finalidade de dar suporte aos laboratórios práticos no treinamento com instrutor. Os locatários não devem ser compartilhados ou usados para fins fora dos laboratórios práticos. O locatário usado neste curso é um locatário de avaliação e não pode ser usado ou acessado após o término da aula e não está qualificado para extensão. Os locatários não podem ser convertidos em uma assinatura paga. Os locatários obtidos como parte deste curso permanecem a propriedade da Microsoft Corporation e reservamos o direito de obter acesso e a qualquer momento. 

## Cenário

O Bellows College é uma organização educacional que possui um campus com vários edifícios. Atualmente as visitas ao campus são anotadas em papel. As informações não são coletadas de forma consistente e não há meios de analisar os dados sobre as visitas em todo o campus.

A administração do campus quer modernizar o sistema de registro de visitantes, com controle do acesso aos edifícios pelo pessoal de segurança, além de exigência de notificação prévia e registro de todas as visitas pelos anfitriões.

Neste laboratório, você usará o Copilot para criar um novo aplicativo de tela para registrar visitas. 

## Macroetapas do laboratório

Seguiremos o esquema abaixo para projetar o aplicativo de tela:

- Descreva o aplicativo que você deseja criar

- Usar o Copilot para modificar a estrutura de tabela de suporte

 ## Pré-requisitos

- Conclusão do **Módulo 1 Laboratório 0 – Validação do ambiente de laboratório**

## Exercício 1: Use o Copilot para criar um aplicativo de visitas à faculdade.

**Objetivo:** Neste exercício, você criará um aplicativo de tela conectando-se a uma tabela de visitas ao Campus.

### Tarefa \#1: Criar o aplicativo inicial

1. Navegue até https://make.powerapps.com

2. Talvez seja necessário autenticar novamente – selecione **Entrar** e siga as instruções, se necessário.

3. Selecione o ambiente **Dev One** na parte superior direita, se ele ainda não estiver selecionado.

4. Na caixa **Use palavras cotidianas para descrever o que seu aplicativo deve coletar, rastrear, listar ou gerenciar.**, insira o seguinte texto. `Create an application that logs visits to a college campus`. 

5. Selecione o botão **Ir**.

O Copilot começará a criar uma estrutura de tabela para dar suporte ao aplicativo. 

> **IMPORTANTE:** Ao usar a IA gerativa, nem sempre você obterá os mesmos resultados exatos. É possível que sua tabela não corresponda exatamente à tabela criada para outro aluno. 

6. No lado direito, selecione a estrutura da tabela na janela do Copilot e, em seguida, selecione **Opções de tabela**.

7. Selecione a opção **Uma tabela** e, em seguida, selecione **Aplicar**.
 
    ![Captura de tela da estrutura da tabela recém-criada](media/bonus-lab-tablestr.png)


> Para ver a estrutura da tabela, escolha a tabela e clique no botão **Exibir dados** 

8. Na caixa **O que você gostaria de fazer em seguida?**, insira o texto: Adicione duas colunas, Hora de entrada e Hora de saída na tabela. Ambos devem ser campos de data e hora. 

9. Selecione o ícone **Avançar** ou pressione **Enter**. 

10. Role para o lado da tabela e verifique se as colunas **Hora de entrada** e **Hora de saída** foram criadas. 

Como estamos registrando os horários de entrada e de saída dos visitantes, não precisamos mais de outros campos de data de visita. 

11. Localize o campo **Data da Visita** (ou campo equivalente) e, na caixa **O que você quer fazer em seguida?**, insira o texto: Remover o Campo de Data da Visita (ou campo equivalente). 

>Se necessário, atualize o nome do campo a ser removido do nome da tabela relevante.

12. Selecione o botão **Ir**. 

13. Remova quaisquer campos de data adicionais que possam estar presentes além de **Hora de entrada** e **Hora de saída**. 

Inicialmente, um campo como **Motivação** foi formatado com um tipo de dados de texto e adicionado. Vamos fazer o Copilot alterá-lo para um menu suspenso (Múltipla escolha). 

14. Na caixa **O que você quer fazer em seguida?**, insira o seguinte texto: Altere o campo Motivação para um menu de escolha com as seguintes opções: Tour pelo campus, Feira de carreiras, Reunião com professor, Aconselhamento estudantil, Outros. 

15. Selecione o botão **Ir**. 

16. Como também queremos capturar o número do prédio, na caixa **O que você quer fazer em seguida?**, insira: Adicione uma coluna para o prédio. 

17. Selecione o botão **Ir**. 

18. Quando estiver contente com a tabela, clique no botão **Salvar e abrir aplicativo**. 

19. Se necessário, na tela **Concluiu o trabalho?**, clique em **Não perguntar novamente** e clique no botão **Salvar e abrir aplicativo**. 

![Captura de tela do aplicativo que acabou de ser criado](media/bonus-lab-copilot-02.png)

Parabéns, você usou Copilot para criar um aplicativo. 
