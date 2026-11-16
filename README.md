# RimMod Manager

Gerenciador externo de mods para RimWorld no Linux, com foco inicial em instalações GOG executadas pelo Bottles (Wine).

## Objetivos

- Detectar a instalação do RimWorld e suas pastas de mods.
- Ler e editar com segurança a configuração de mods (`ModsConfig.xml`).
- Organizar mods em perfis independentes.
- Identificar dependências ausentes e conflitos conhecidos.
- Auxiliar na análise da ordem de carregamento.
- Criar e restaurar backups sem apagar mods automaticamente.
- Oferecer diagnósticos e informações úteis sobre carregamento e desempenho.

## Plataforma e tecnologias previstas

- Linux
- Python 3
- PySide6 para a interface gráfica
- SQLite para dados locais
- XML para configurações do jogo
- JSON para perfis e metadados auxiliares

As tecnologias são uma proposta inicial e podem ser revistas antes da implementação.

## Estado do projeto

**Fase: planejamento e estrutura inicial.** Ainda não há funcionalidades implementadas.

Consulte [PROJECT.md](PROJECT.md), [ROADMAP.md](ROADMAP.md) e [ARCHITECTURE.md](ARCHITECTURE.md).

## Segurança dos dados

O programa deverá preservar saves e mods. Nenhuma remoção ou alteração destrutiva deverá ocorrer sem confirmação explícita. Backups e restauração serão tratados como funcionalidades essenciais.

## Colaboração

Leia [CONTRIBUTING.md](CONTRIBUTING.md) antes de contribuir. Mudanças devem ser pequenas, revisáveis e acompanhadas de testes quando aplicável.

## Aviso

Projeto independente e não afiliado à Ludeon Studios.
