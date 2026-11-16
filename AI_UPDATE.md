# AI_UPDATE.md — Contexto de Trabalho para as IAs

> Atualize este arquivo sempre que houver avanço relevante no projeto. Ele é o ponto de passagem de contexto entre ChatGPT, Claude e Vibe.

## Projeto

**Nome:** RimMod Manager  
**Repositório:** https://github.com/noguchirobert475-tech/Rim-Mod-manager  
**Branch principal:** `main`  
**Estado:** documentação inicial publicada; primeira implementação foi reportada por Claude, mas ainda não foi localizada na branch `main` nem validada neste repositório.

Aplicativo externo para Linux para gerenciar mods do RimWorld. O escopo inicial prevê compatibilidade com instalações GOG executadas por Bottles/Wine, sem depender da Steam.

## Ambiente e compatibilidade

- Plataforma-alvo inicial: Linux.
- Método de instalação a considerar: GOG.
- Camada de execução a considerar: Bottles/Wine.

O aplicativo deve detectar caminhos dinamicamente e também permitir seleção manual. Não registrar neste documento especificações do computador, sistema operacional específico, localização, nome real, contas pessoais ou outros dados privados do usuário. Testes de compatibilidade devem usar ambientes genéricos e dados fictícios sempre que possível.

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

## Tecnologias e ferramentas propostas

- Python >= 3.10.
- PySide6 >= 6.6 e < 7.
- pytest >= 8.
- SQLite para cache e dados locais.
- XML para `ModsConfig.xml`.
- JSON para perfis.
- Logs em diretório compatível com XDG.

As dependências declaradas nos arquivos do projeto devem ser a fonte definitiva; as versões acima foram reportadas na implementação inicial e ainda precisam ser confirmadas na revisão.

## Documentação inicial publicada na branch `main`

- `README.md` — apresentação e visão geral.
- `PROJECT.md` — objetivos, escopo e critérios do MVP.
- `ROADMAP.md` — etapas de desenvolvimento.
- `ARCHITECTURE.md` — arquitetura e estrutura propostas.
- `CONTRIBUTING.md` — fluxo Git, revisão e colaboração entre IAs.
- `CHANGELOG.md` — histórico inicial.

## Primeira implementação reportada por Claude

Claude informou ter criado os seguintes arquivos:

- `main.py`
- `core/__init__.py`
- `core/logging_setup.py`
- `ui/__init__.py`
- `ui/main_window.py`
- `tests/test_logging_setup.py`
- `tests/test_main_window.py`
- `pyproject.toml`
- `requirements.txt`
- `requirements-dev.txt`
- `.gitignore`
- `.gitkeep` em `profiles/`, `backups/` e `database/`

**Atenção: status não verificado.** Na consulta à branch `main` feita em 2026-11-16, `main.py`, `requirements-dev.txt` e `pyproject.toml` não foram encontrados. Portanto, a implementação acima deve ser tratada como trabalho reportado por Claude, não como código já integrado ao repositório. Não presumir que os arquivos estão publicados ou revisados. Confirmar a branch/PR ou receber os arquivos antes de continuar sobre essa base.

### Decisões reportadas

- Python >= 3.10.
- PySide6 >= 6.6 e < 7.
- pytest >= 8.
- Configuração de logs usando diretórios XDG.

### Testes reportados

- Lógica de logging verificada manualmente: quatro checagens informadas como OK.
- `pytest` não executado.
- Aplicativo PySide6 não executado.
- Motivo informado: ambiente sem os pacotes e sem acesso à rede.

Esses resultados são relatos, ainda não foram reproduzidos de forma independente.

### Comandos para validação local

Executar na raiz do projeto, depois que os arquivos da implementação estiverem disponíveis:

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements-dev.txt
pytest
python main.py
```

Se a instalação das dependências falhar, registrar o erro completo; não marcar os testes como aprovados. A execução da interface pode exigir um ambiente gráfico disponível.

## Regras obrigatórias de segurança e privacidade

- Preservar saves e arquivos dos mods.
- Nunca excluir mods automaticamente.
- Não alterar arquivos do jogo durante detecção ou leitura.
- Antes de modificar `ModsConfig.xml`, mostrar as mudanças e pedir confirmação.
- Criar backup antes de qualquer gravação.
- Validar XML e caminhos; se houver erro, preservar o original.
- Não sobrescrever backups silenciosamente.
- Não presumir que todos os usuários têm a mesma instalação ou diretórios.
- Não incluir saves, arquivos privados, tokens, credenciais, dados pessoais ou detalhes identificáveis do ambiente do usuário no GitHub.
- Usar dados fictícios ou anonimizados em exemplos, testes, issues e documentação.

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
7. Não acrescentar informações pessoais do usuário ao repositório.
8. Distinguir claramente código criado localmente, código enviado a uma branch e código integrado à `main`.

## Próxima etapa recomendada

1. Disponibilizar a implementação reportada por Claude em uma branch ou Pull Request.
2. Conferir os arquivos e revisar a segurança do logging e da inicialização da interface.
3. Criar ambiente virtual e instalar as dependências de desenvolvimento.
4. Executar `pytest` e `python main.py`, registrando resultados reais.
5. Corrigir falhas antes de iniciar `core/game_detector.py`.
6. Implementar a detecção do RimWorld somente com operações de leitura e caminhos selecionáveis.

Não editar arquivos reais do RimWorld nesta etapa.

## Como registrar atualizações

Ao atualizar este arquivo, manter as seções de contexto e acrescentar uma entrada no histórico abaixo com:
- data;
- IA responsável;
- resumo da tarefa;
- arquivos alterados;
- testes executados e resultado;
- próximo passo.

Não registrar dados pessoais ou detalhes particulares do computador usado pelo usuário.

## Histórico de atualizações

### 2026-11-16 — ChatGPT
- Criado o arquivo de comunicação compartilhada entre as IAs.
- Registrado o escopo, tecnologias propostas, documentação existente, regras de segurança e próxima etapa.
- Implementação do aplicativo ainda não iniciada.

### 2026-11-16 — ChatGPT
- Revisado o arquivo para remover especificações pessoais do computador e do sistema do usuário.
- Mantidas apenas informações gerais de compatibilidade que fazem parte do escopo do produto.
- Acrescentadas regras explícitas para não publicar dados pessoais no repositório.

### 2026-11-16 — Claude (relato recebido; integração pendente)
- Reportada a criação da estrutura inicial do aplicativo, janela PySide6 e testes básicos.
- Reportadas quatro checagens manuais de logging como OK.
- `pytest` e execução do aplicativo ainda não foram realizados.
- Os arquivos reportados não foram encontrados na branch `main na verificação do ChatGPT; confirmar branch/PR e revisar antes de considerar a implementação integrada.
- Próximo passo reportado: validar a base e depois implementar detecção do RimWorld em modo somente leitura.
