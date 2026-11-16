# AI_UPDATE.md — Contexto de Trabalho para as IAs

> Atualize este arquivo sempre que houver avanço relevante no projeto. Ele é o ponto de passagem de contexto entre ChatGPT, Claude e Vibe.

## Projeto

**Nome:** RimMod Manager  
**Repositório:** https://github.com/noguchirobert475-tech/Rim-Mod-manager  
**Branch principal:** `main`  
**Estado:** planejamento e documentação inicial; implementação ainda não iniciada.

Aplicativo externo para Linux para gerenciar mods do RimWorld, com foco inicial em instalação GOG executada pelo Bottles/Wine. Não deve depender da Steam.

## Ambiente inicial de referência

- Sistema: AnduinOS.
- Jogo: RimWorld GOG 1.6.4633 rev1245.
- Execução: Bottles Flatpak.
- Hardware de referência: 7,5 GiB de RAM e Intel HD Graphics 4000.

Esses dados servem para orientar testes e compatibilidade, não devem ser tratados como caminhos fixos ou requisitos universais.

## Objetivo e escopo

### MVP planejado

1. Detectar a instalação do RimWorld ou permitir selecionar o caminho manualmente.
2. Localizar diretórios de mods.
3. Ler e listar mods encontrados.
4. Ler e editar `ModsConfig.xml`, sempre com backup antes de gravar.
5. Criar, listar e aplicar perfis de mods.
6. Criar e restaurar backups.

### Funcionalidades posteriores

- Pesquisa, filtros e metadados de mods.
- Diagnóstico de dependências ausentes.
- Avisos sobre conflitos conhecidos.
- Assistente para ordem de carregamento.
- Análise informativa de possíveis gargalos de carregamento/desempenho.

### Fora do escopo inicial

- Excluir mods automaticamente.
- Modificar saves.
- Baixar ou atualizar mods automaticamente.
- Exigir Steam ou conexão com a internet para funções locais básicas.

## Tecnologias propostas

- Python 3
- PySide6 para interface gráfica
- SQLite para cache e dados locais
- XML para `ModsConfig.xml`
- JSON para perfis
- pytest para testes (proposta)

As versões e escolhas ainda precisam ser confirmadas antes da implementação.

## Documentação já criada na branch `main`

- `README.md` — apresentação e visão geral.
- `PROJECT.md` — objetivos, escopo e critérios do MVP.
- `ROADMAP.md` — etapas de desenvolvimento.
- `ARCHITECTURE.md` — arquitetura e estrutura propostas.
- `CONTRIBUTING.md` — fluxo Git, revisão e colaboração entre IAs.
- `CHANGELOG.md` — histórico inicial.

Nenhuma funcionalidade do aplicativo foi implementada até o momento.

## Regras obrigatórias de segurança

- Preservar saves e arquivos dos mods.
- Nunca excluir mods automaticamente.
- Não alterar arquivos do jogo durante detecção ou leitura.
- Antes de modificar `ModsConfig.xml`, mostrar as mudanças e pedir confirmação.
- Criar backup antes de qualquer gravação.
- Validar XML e caminhos; se houver erro, preservar o original.
- Não sobrescrever backups silenciosamente.
- Não presumir que todos os usuários têm a mesma instalação ou diretórios.
- Não incluir saves, arquivos privados, tokens ou dados pessoais no GitHub.

## Organização do trabalho entre as IAs

Os papéis abaixo são uma proposta inicial, não uma obrigação rígida:

- **ChatGPT:** arquitetura, planejamento, integração, documentação e revisão.
- **Claude:** implementação de lógica e módulos, conforme tarefas delimitadas.
- **Vibe:** interface, experiência visual e apoio em testes.

Cada IA deve:
1. Ler este arquivo e os documentos relevantes antes de trabalhar.
2. Trabalhar em uma tarefa pequena e claramente delimitada.
3. Evitar editar simultaneamente os mesmos arquivos que outra IA.
4. Não presumir que uma sugestão ou código gerado já foi testado.
5. Informar arquivos alterados, decisões, testes executados e pendências.
6. Atualizar este arquivo ao concluir sua parte, ou fornecer o texto da atualização para ser integrado.

## Próxima etapa recomendada

**Etapa 1 — Base do aplicativo:**
1. Definir a versão mínima de Python e dependências.
2. Criar a estrutura de diretórios do projeto.
3. Criar um ponto de entrada mínimo.
4. Inicializar uma janela PySide6 simples.
5. Configurar testes e logs básicos.

Não começar ainda a editar arquivos reais do RimWorld. A primeira implementação deve operar em ambiente de teste e priorizar leitura.

## Como registrar atualizações

Ao atualizar este arquivo, manter as seções de contexto e acrescentar uma entrada no histórico abaixo com:
- data;
- IA responsável;
- resumo da tarefa;
- arquivos alterados;
- testes executados e resultado;
- próximo passo.

## Histórico de atualizações

### 2026-11-16 — ChatGPT
- Criado o arquivo de comunicação compartilhada entre as IAs.
- Registrado o escopo, ambiente de referência, documentação existente, regras de segurança e próxima etapa.
- Implementação do aplicativo ainda não iniciada.
