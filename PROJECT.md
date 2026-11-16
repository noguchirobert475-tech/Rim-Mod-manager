# Visão do Projeto

## Nome

RimMod Manager

## Problema

Gerenciar mods do RimWorld pode exigir alternar entre pastas, arquivos de configuração e ferramentas diferentes. O objetivo é reunir as tarefas comuns em um aplicativo Linux simples, com foco em segurança e clareza.

## Público e ambiente inicial

- Usuário de Linux.
- RimWorld instalado pela GOG.
- Execução do jogo por Bottles/Wine.
- Sem dependência da Steam.

O suporte a outros métodos de instalação poderá ser acrescentado depois.

## Escopo funcional

### Primeira entrega (MVP)

1. Detectar ou permitir selecionar manualmente a instalação do jogo.
2. Identificar diretórios de mods.
3. Ler e exibir os mods presentes.
4. Ler e salvar `ModsConfig.xml`, preservando um backup antes de alterações.
5. Criar, listar, selecionar e restaurar perfis de mods.
6. Criar e restaurar backups.

### Etapas posteriores

- Pesquisa, filtros e metadados de mods.
- Diagnóstico de dependências ausentes.
- Avisos de conflitos conhecidos.
- Ferramenta assistida para ordem de carregamento.
- Análise informativa de possíveis gargalos.
- Relatórios e exportação de diagnósticos.

## Fora do escopo inicial

- Baixar ou atualizar mods automaticamente.
- Excluir mods automaticamente.
- Alterar saves.
- Prometer detectar todos os conflitos ou prever com precisão o desempenho.
- Exigir Steam ou acesso a serviços externos.

## Requisitos de segurança

- Nunca apagar mods ou saves automaticamente.
- Fazer backup antes de modificar configurações.
- Validar caminhos antes de escrever arquivos.
- Não sobrescrever backups sem confirmação.
- Mostrar claramente o que será alterado.
- Permitir cancelamento antes de aplicar mudanças.
- Tratar arquivos XML inválidos sem destruir o original.

## Critérios de sucesso do MVP

- Detectar uma instalação GOG em prefixo Bottles ou aceitar caminho manual.
- Listar mods encontrados sem modificar seus arquivos.
- Importar e exportar perfis.
- Ler e atualizar a configuração de mods com backup e validação.
- Funcionar sem Steam e sem conexão com a internet para as funções locais básicas.
