# Especificação inicial

## Produto

App acessível no navegador, executado em Docker, com escritório virtual em pixel art isométrica. Navegação pela visão do prédio e por menu lateral.

O usuário organiza andares por empresa ou gerência. Cada andar aponta para uma pasta principal; suas salas de projeto correspondem a pastas dentro dela. O térreo Miscelânea aceita projetos avulsos e salas de conversa ou pesquisa sem pasta. A janela Organizar prédio cadastra pastas, cria andares e reorganiza salas. Mover uma sala não move arquivos automaticamente.

## Salas e agentes

Cada sala é permanente e guarda seu próprio contexto, tarefas, funcionários, mensagens e handoffs. Ela começa vazia. Ao criar uma tarefa, o orquestrador propõe equipe e subtarefas; o usuário confirma antes do início e aprova novos subagentes durante a execução. Funcionários permanecem na sala após participar; subagentes ficam vinculados a quem os criou.

Uma sala pode conter várias sessões internas sucessivas por agente. Ao trocar de sessão, o histórico da sala continua disponível. A execução paralela real depende de resolver a regra atual do usuário de um subagente por vez e das capacidades dos conectores.

## Tarefas e comunicação

Tarefa tem título, descrição, prioridade e dependências opcionais. O usuário arrasta o cartão até um funcionário. Estados: pendente, em andamento, aguardando, entregue e concluída. Aguardando pode ocorrer durante o trabalho; só o usuário conclui após revisar a entrega.

O painel da tarefa mostra responsável, andamento, dependências e entregas. O painel do funcionário mostra estado, tarefa, atividade, mensagens, entregas e equipe; comandos e logs ficam em seção expansível. Controles: mensagem, pausa, retomada e pedido de handoff, conforme suporte do conector.

Há chat por sala para falar com todos ou marcar um funcionário. Mensagens entre agentes passam pelo orquestrador. A caixa de entrada reúne perguntas, aprovações, entregas e alertas; o prédio mostra avisos por sala e notificações do navegador são opcionais.

## Memória e entrega

A sala preserva contexto, decisões, histórico e handoffs versionados em armazenamento persistente. Compactação é manual; o app avisa sobre limite de contexto quando o conector fornecer essa informação. Ao compactar, solicita handoffs, atualiza o contexto e prepara a retomada. Se um agente não responder, salva o que estiver disponível e marca a operação como incompleta. Compactação não renova limite de uso da assinatura.

Revisão reúne alterações, testes, handoff, pendências e itens não verificados. O usuário conclui ou devolve a tarefa para correção com comentários. Backups são necessários; formato e destino ainda não foram decididos.

## Git e versões

Usar Git real, inicialmente validado em repositórios descartáveis. Exibir status, histórico, branches, commits, integração na develop e conflitos. Aplicar as regras do usuário: branches feature/ ou fix/ a partir da develop atualizada; commits separados com caminhos explícitos e Conventional Commits em português; merge de trabalho em develop com --no-ff e atualização do handoff. Os demais detalhes seguem as regras fornecidas pelo usuário.

Conflitos pausam a integração; o usuário pode resolver manualmente, cancelar o merge ou aprovar a solução proposta pelo agente antes de aplicá-la. Merge de develop em master exige pedido explícito; push exige pedido explícito. Na develop, registrar apenas a versão planejada MAJOR.MINOR.PATCH. Após merge autorizado em master, criar a tag definitiva vMAJOR.MINOR.PATCH; enviar a tag exige pedido explícito de push.

## Primeira versão e limites

Usar agentes simulados; conexões reais de Claude e Codex serão avaliadas depois. Validar primeiro no WSL; Linux e Windows também são objetivos. Um auxiliar local foi proposto para seleção de pastas e configuração de acesso Docker, mas sua arquitetura, viabilidade e instalação precisam de validação. Dados persistentes exigem estratégia de backup.
