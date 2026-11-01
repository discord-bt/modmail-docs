# ModMail

Bot de atendimento por mensagens privadas para Discord, mantido por **pyyrho**. Cada conversa abre um canal reservado à equipe, que responde pelo servidor sem precisar chamar o membro no próprio perfil.

Este repositório reúne a apresentação e o guia de uso do ModMail. O código-fonte e a hospedagem do bot são privados; esta página não distribui plugins ou uma versão para executar por conta própria.

## Recursos

### `atendimento`

Quando alguém envia uma DM ao bot, ele cria um canal `modmail-nome` na categoria configurada e encaminha a mensagem. As próximas mensagens seguem para esse canal enquanto o atendimento estiver aberto na sessão atual. Anexos são encaminhados como links.

Os cargos de staff configurados recebem acesso ao canal. O membro conversa somente pela DM e não recebe acesso ao canal interno. A equipe responde escrevendo normalmente no canal; o bot envia a resposta pela própria conta, sem acrescentar o nome do atendente.

| Ação | Função |
| --- | --- |
| Enviar uma DM ao bot | Abre um atendimento ou continua uma conversa registrada. |
| Escrever no canal do atendimento | Encaminha a resposta da staff ao membro. |
| Enviar anexos | Encaminha os links dos arquivos para o outro lado da conversa. |

Somente membros com um dos cargos autorizados pela configuração do bot podem responder ou encerrar atendimentos. Administrador, sozinho, não substitui esse vínculo no código. Mensagens que começam com o prefixo são tratadas como comandos e não são encaminhadas como respostas.

### `comandos`

| Comando | Função |
| --- | --- |
| `.fechar` | Exclui o canal do atendimento e encerra o atendimento. |
| `.threads` | Lista os atendimentos abertos na sessão atual. |

O prefixo padrão é `.` e pode ser alterado pela administração. Os comandos são textuais; esta versão não possui comandos de barra nem painel de configuração.

Encerrar um atendimento apaga o canal. O bot não exporta transcrições nem envia uma mensagem de encerramento ao membro. Guarde manualmente o que precisar antes de usar `.fechar`.

## Adicionar ao servidor

A ativação deve ser combinada com o mantenedor. Esta página não oferece um convite público de instalação. O responsável configura a aplicação para a comunidade, a categoria de atendimento e os cargos autorizados.

Não é necessário baixar arquivos deste repositório para conversar com um bot já instalado.

## Primeiro atendimento

1. Abra o perfil do ModMail no servidor em que ele atende.
2. Envie uma mensagem privada explicando o que precisa.
3. Aguarde a resposta da equipe pela mesma conversa.
4. Se necessário, envie imagens ou arquivos junto da mensagem.

Para a equipe, basta responder no canal criado dentro da categoria de atendimento. Mensagens comuns nesse canal são encaminhadas ao membro; use os comandos apenas para administrar a conversa.

## Permissões e funcionamento

Os canais de atendimento ficam restritos à equipe configurada, ao bot e às pessoas com permissões administrativas que permitem visualizá-los. A conversa é privada em relação aos demais membros, mas pode ser lida pela equipe de atendimento.

O ModMail precisa conseguir criar e excluir canais, enviar mensagens, ler o histórico, inserir links e adicionar reações. Os membros da equipe precisam estar vinculados a um dos cargos autorizados.

A lista de atendimentos é reiniciada quando o bot reinicia. Os canais anteriores continuam no servidor, mas uma nova mensagem privada pode abrir outro atendimento. O fechamento exclui o canal e não gera uma transcrição automática.

## Dúvidas e sugestões

Procure a equipe do servidor para dúvidas sobre um atendimento. Para sugestões sobre o bot, descreva o comportamento esperado e o que aconteceu, sem compartilhar conversas privadas ou credenciais.
