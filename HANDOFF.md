# Handoff

Última atualização: 2026-11-24.  
**Ponto de retomada imediato:** inicializar o Git conforme a preferência do dono e validar o acesso a pastas no WSL com Docker, sem tocar em projetos existentes.

## 1. Projeto

Orquestrador de agentes com escritório virtual e salas permanentes por projeto.

## 2. Repositório

Pasta local `/home/caminhao/coding/orquestrador-ia`. Git ainda não inicializado; remoto não configurado nem consultado.

## 3. Stack

Docker e interface no navegador foram definidos. Linguagens, frameworks e banco ainda não foram escolhidos.

## 4. Como rodar

Ainda não existe aplicação executável. WSL é o primeiro ambiente de validação; acesso a caminhos Windows e Linux precisa ser verificado.

## 5. Planos

Ver [plano](docs/plano.md). Primeiro validar acesso a pastas e Git real em ambiente descartável; conexões de IA ficam para o final.

## 6. Onde parou

Escopo e plano iniciais documentados. Nenhum código foi escrito.

## 7. O que falta

Inicialização Git, viabilidade técnica, implementação, testes, backups e conectores reais.

## 8. Desafios e riscos

Seleção de pastas pelo navegador não disponibiliza automaticamente caminhos ao Docker. O auxiliar local proposto ainda precisa ser validado. Sessões e limites variam entre conectores; compactação não renova cotas. Persistência não substitui backup.

## 9. Decisões abertas do dono

Destino e formato de backup; exceção à regra de um subagente por vez para execução paralela real; decisões de produto surgidas na validação. Stack não foi definida.

## 10. Regras e convenções

Seguir as regras gerais fornecidas pelo usuário, incluindo autorizações explícitas para push e merge na master, handoffs, revisão, testes e versionamento. A versão planejada fica documentada na develop; tag definitiva somente após merge autorizado na master.

## 11. Onde estão os detalhes

[Especificação](docs/especificacao.md), [plano](docs/plano.md) e [revisão](docs/revisao-planejamento.md).
