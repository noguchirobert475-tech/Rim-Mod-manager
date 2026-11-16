# Roteiro de Desenvolvimento

As etapas são sequenciais; cada uma deve ser revisada antes de avançar.

## Etapa 0 — Planejamento

- [x] Criar documentação inicial.
- [ ] Confirmar arquitetura e convenções.
- [ ] Definir versão mínima do Python e dependências.
- [ ] Definir estratégia de testes.

## Etapa 1 — Base do aplicativo

- [ ] Criar estrutura Python do projeto.
- [ ] Inicializar interface PySide6.
- [ ] Criar configuração local do aplicativo.
- [ ] Adicionar logs e tratamento de erros.

## Etapa 2 — Detecção e leitura

- [ ] Permitir selecionar manualmente a instalação.
- [ ] Detectar caminhos comuns de Bottles/GOG sem presumir um caminho único.
- [ ] Identificar diretórios de mods.
- [ ] Ler metadados básicos dos mods.
- [ ] Ler `ModsConfig.xml` sem modificá-lo.

## Etapa 3 — Perfis e segurança

- [ ] Criar e alternar perfis.
- [ ] Salvar perfis em JSON.
- [ ] Fazer backup antes de aplicar configurações.
- [ ] Restaurar backups com validação e confirmação.

## Etapa 4 — Diagnósticos

- [ ] Detectar dependências declaradas ausentes.
- [ ] Sinalizar incompatibilidades conhecidas.
- [ ] Explicar limitações e incertezas dos diagnósticos.
- [ ] Sugerir ordem de carregamento sem aplicá-la silenciosamente.

## Etapa 5 — Análise e acabamento

- [ ] Relatórios de carregamento e possíveis gargalos.
- [ ] Melhorias de interface e acessibilidade.
- [ ] Testes em diferentes instalações Linux.
- [ ] Documentação de instalação e uso.

## Regra de conclusão

Uma tarefa só deve ser marcada como concluída quando houver implementação revisada e, quando aplicável, testes reproduzíveis.
