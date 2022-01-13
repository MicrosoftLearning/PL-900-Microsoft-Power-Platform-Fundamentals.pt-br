---
lab:
    title: 'Laboratório: Validar ambiente de laboratório'
    module: 'Módulo 0: Introdução ao curso'
---

Módulo 0: Introdução ao curso
=================================

Cenário
--------

O Bellows College é uma organização educacional que possui um campus com vários edifícios. Atualmente as visitas ao campus são anotadas em papel. As informações não são coletadas de forma consistente e não há meios de analisar os dados sobre as visitas em todo o campus.

A administração do campus quer modernizar o sistema de registro de visitantes, com controle do acesso aos edifícios pelo pessoal de segurança, além de exigência de notificação prévia e registro de todas as visitas pelos anfitriões.

Ao longo deste curso, você vai criar aplicativos e fazer automações para permitir que a administração e a equipe de segurança do Bellows College gerenciem e controlem o acesso aos edifícios no campus.

Neste laboratório do Módulo 0, você irá adquirir um locatário de teste da Power Platform e acessar o centro de administração do Power Platform. No centro de administração, você criará o seu ambiente de **Prática** no qual fará a maior parte do trabalho do laboratório.

## Exercício 1 – Configuração

### Tarefa 1 – Adquirir o locatário de avaliação da Microsoft Power Platform

1. Copie as **Credenciais do Microsoft 365** do Authorized Lab Hoster.

2. Navegue até <https://powerapps.microsoft.com> e clique em **Comece gratuitamente.**

3. Em **Vamos começar**, insira o endereço de email das suas credenciais do Microsoft 365 na caixa de texto que diz **Insira seu endereço de email corporativo.**

4. Será exibido um aviso informando que você tem uma conta na Microsoft. Selecione **Entrar.**

5. Digite a senha fornecida pelo Authorized Lab Hoster. 

6. Selecione **Sim** para permanecer conectado.

7. Preencha as informações da sua conta e selecione **Introdução** para se inscrever na avaliação da Microsoft Power Platform.  

### Tarefa 2 – Criar o ambiente

1. Acesse <https://admin.powerplatform.microsoft.com> e faça login com as suas credenciais do Microsoft 365 se for solicitado novamente.

2. Selecione **Ambientes** e clique em **+Novo.**

    - Em **Nome**, insira **Prática [Minhas iniciais].** (Exemplo: Prática AJ.)
    
    - Em **Tipo**, selecione **Teste** (não selecione a opção Teste (com base em assinatura)).
    
    - Altere o botão **Criar um banco de dados para este ambiente?** para **Sim.**
    
    - Deixe todas as outras seleções como padrão e clique em **Avançar.**
    
    - Na próxima guia, deixe todas as seleções como padrão e clique em **Salvar.**

3. Seu ambiente de **Prática** agora deve aparecer na lista Ambientes. 

    > O ambiente pode levar alguns minutos para ser provisionado. Se necessário, atualize a página.

# Exercício \#2: Provisionar um portal do Power Apps

**Objetivo:** O provisionamento de um portal do Power Apps pode levar algum tempo. Neste exercício, você criará o portal do Power Apps no seu ambiente para que o processo de provisionamento possa ser iniciado. Você usará este portal em um laboratório posterior.

## Tarefa 1: Criar o portal do Power Apps

1.  Faça login em <https://make.powerapps.com>

2.  Se o **Ambiente** exibido no canto superior direito não for seu ambiente de Prática, clique para selecionar o seu Ambiente.

3.  Na página inicial, clique no painel **Portal a partir do zero** em **Criar seu próprio aplicativo**

    > Se você não vir esta opção, tente diminuir o zoom.

4.  Forneça novos detalhes para o portal

    -   Digite **```Bellows College Visitors```** como o **Nome** do portal

    -   Forneça um URL exclusivo; **algumacoisa**.powerappsportals.com (se o nome já estiver sendo usado, escolha outro)

    -   Selecione um **Idioma** para o portal de base

    -   Clique em **Criar**

    > O processo de provisionamento do Portal será executado em 30 a 45 minutos. Não é necessário esperar, pois esse processo continua enquanto você avança para o próximo módulo.
