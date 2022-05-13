---
lab:
  title: 'Laboratório: Validar ambiente de laboratório'
  module: 'Module 0: Course introduction'
ms.openlocfilehash: e69074549dddd4494db53a9ccb9ebfb3ae198d48
ms.sourcegitcommit: fc79a9b68a8235b37fd90ef84ba8ae1aa2e581f5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2022
ms.locfileid: "144424697"
---
# <a name="module-0-course-introduction"></a>Módulo 0: Introdução do curso

## <a name="scenario"></a>Cenário

O Bellows College é uma organização educacional que possui um campus com vários edifícios. Atualmente as visitas ao campus são anotadas em papel. As informações não são coletadas de forma consistente e não há meios de analisar os dados sobre as visitas em todo o campus.

A administração do campus quer modernizar o sistema de registro de visitantes, com controle do acesso aos edifícios pelo pessoal de segurança, além de exigência de notificação prévia e registro de todas as visitas pelos anfitriões.

Ao longo deste curso, você vai criar aplicativos e fazer automações para permitir que a administração e a equipe de segurança do Bellows College gerenciem e controlem o acesso aos edifícios no campus.

Neste laboratório do Módulo 0, você irá adquirir um locatário de teste da Power Platform e acessar o centro de administração do Power Platform. No centro de administração, você criará o seu ambiente de **Prática** no qual fará a maior parte do trabalho do laboratório.

## <a name="exercise-1--setup"></a>Exercício 1 – Configuração

### <a name="task-1---acquire-your-microsoft-power-platform-trial-tenant"></a>Tarefa 1 – Adquirir o locatário de teste do Microsoft Power Platform

1.  Copie as **Credenciais do Microsoft 365** do Authorized Lab Hoster.

2.  Navegue até <https://powerapps.microsoft.com> e clique em **Iniciar gratuitamente.**

3.  Em **Vamos começar**, insira o endereço de email das suas credenciais do Microsoft 365 na caixa de texto que diz **Insira seu endereço de email corporativo.**

4.  Será exibido um aviso informando que você tem uma conta na Microsoft. Selecione **Entrar.**

5.  Digite a senha fornecida pelo Authorized Lab Hoster e entre.

6.  Selecione **Sim** para permanecer conectado.

7.  Preencha as informações da sua conta e selecione **Introdução** para se inscrever em sua avaliação do Microsoft Power Platform.

### <a name="task-2--create-environment"></a>Tarefa 2 – Criar ambiente

1.  Acesse <https://admin.powerplatform.microsoft.com> e faça logon com suas credenciais do Microsoft 365 se for solicitado.

2.  Selecione **Ambientes** e clique em **+Novo.**

    1.  Em **Nome**, insira **Prática [Minhas iniciais].** (Exemplo: Prática AJ.)

    2.  Em **Tipo**, selecione **Teste** (não selecione a opção Teste (com base em assinatura)).

    3.  Altere o botão **Criar um banco de dados para este ambiente?** para **Sim.**

    4.  Deixe todas as outras seleções como padrão e clique em **Avançar.**

    5.  Na próxima guia, deixe todas as seleções como padrão e clique em **Salvar.**

3.  Seu ambiente de **Prática** agora deve aparecer na lista Ambientes.

>   O ambiente pode levar alguns minutos para ser provisionado. Se necessário, atualize a página.
