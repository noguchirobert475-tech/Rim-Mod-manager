# Arquitetura Inicial

## Princípios

- Separar interface, lógica de negócio e acesso a arquivos.
- Começar com operações locais e offline.
- Não modificar arquivos do jogo durante a descoberta.
- Fazer alterações de configuração de forma atômica sempre que possível.
- Manter backups antes de operações de escrita.
- Não assumir que todos os usuários têm a mesma estrutura de diretórios.

## Tecnologias propostas

- Python 3
- PySide6
- SQLite
- XML
- JSON
- pytest para testes (proposta)

As versões e dependências serão fixadas quando o ambiente de desenvolvimento for definido.

## Estrutura proposta

```text
rimmod-manager/
├── main.py
├── core/
│   ├── game_detector.py
│   ├── mod_scanner.py
│   ├── dependency.py
│   ├── conflict.py
│   ├── load_order.py
│   └── performance.py
├── profiles/
├── backups/
├── database/
├── ui/
│   ├── main_window.py
│   ├── mod_library.py
│   ├── profile_manager.py
│   └── diagnostics.py
├── tests/
├── assets/
├── README.md
├── PROJECT.md
├── ROADMAP.md
├── ARCHITECTURE.md
├── CONTRIBUTING.md
└── CHANGELOG.md
```

A estrutura é uma referência inicial; pastas de dados do usuário não devem ser confundidas com arquivos versionados do projeto.

## Fluxo de configuração

1. Localizar a instalação e o diretório de dados.
2. Ler o arquivo de configuração.
3. Validar XML e identificar os IDs dos mods.
4. Mostrar as mudanças propostas.
5. Criar backup do arquivo atual.
6. Gravar em arquivo temporário, validar e substituir o arquivo original.
7. Informar o resultado e a localização do backup.

## Perfis

Perfis devem armazenar IDs e ordem dos mods, além de metadados necessários. Não devem copiar ou mover os diretórios dos mods. A aplicação de um perfil modifica somente a configuração de mods do jogo, após backup e confirmação.

## Banco de dados

SQLite poderá guardar cache de metadados e histórico local. O banco não deve ser a única cópia de perfis ou backups.

## Limites dos diagnósticos

Dependências podem ser extraídas de metadados declarados pelos próprios mods. Conflitos e impacto de desempenho nem sempre são determinísticos; os resultados devem ser apresentados como avisos fundamentados, não como garantias.
