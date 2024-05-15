---
lab:
  title: 'Laboratório de bônus: Criar um aplicativo de tela usando o Copilot'
  module: 'Module 3: Get started with Power Apps'
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

4. Na caixa **Descreva o aplicativo que você deseja criar**, insira o texto a seguir. Crie um aplicativo que registra visitas a um campus universitário. 

5. Selecione o botão **Ir**.

O Copilot começará a criar uma estrutura de tabela para dar suporte ao aplicativo. 

> **IMPORTANTE:** Ao usar a IA gerativa, nem sempre você obterá os mesmos resultados exatos. É possível que sua tabela não corresponda exatamente à tabela criada para outro aluno. 

6. Na caixa **Descreva o que alterar**, insira o texto: Adicione duas colunas, Hora de entrada e Hora de saída. Ambos devem ser campos de data e hora.  

7. Selecione o ícone **Avançar** ou pressione **Enter**. 

8. Role para o lado da tabela e verifique se as colunas **Hora de entrada** e **Hora de saída** foram criadas. 

Como estamos registrando os horários de entrada e de saída dos visitantes, não precisamos mais de outros campos de data de visita. 

9. Localize o campo **Data da Visita** (ou campo equivalente) e, na caixa **Descreva o que alterar**, insira o texto Remover o Campo de Data da Visita. 

10. Selecione o botão **Ir**. 

11. Remova quaisquer campos de data adicionais que possam estar presentes além de **Hora de entrada** e **Hora de saída**. 

Inicialmente, um campo como **Motivação** foi formatado com um tipo de dados de texto e adicionado. Vamos fazer o Copilot alterá-lo para um menu suspenso (Múltipla escolha). 

12. Na caixa **Descreva o que alterar**, insira o seguinte texto: Altere o campo Motivação para um menu de escolha com as seguintes opções: Tour pelo campus, Feira de carreiras, Reunião com professor, Aconselhamento estudantil, Outros. 

13. Selecione o botão **Ir**. 

14. Como também queremos capturar o número do prédio, na caixa **Descreva o que alterar**, insira: Adicione uma coluna para o número do prédio. 

15. Selecione o botão **Ir**. 

16. Depois que você estiver contente com sua tabela, selecione o botão **Criar aplicativo**. 

17. Após a criação do aplicativo, na tela **Bem-vindo(a) ao Power Apps Studio**, escolha **Não mostrar isso novamente** e selecione **Ignorar**. 

![Captura de tela do aplicativo que acabou de ser criado](media/bonus-lab-copilot-01.png)

Parabéns, você usou Copilot para criar um aplicativo. 
