# Guia de Contribuição

## Antes de começar

- Leia README.md, PROJECT.md e ARCHITECTURE.md.
- Verifique issues e tarefas existentes para evitar trabalho duplicado.
- Não presuma caminhos de instalação ou mods presentes.
- Não inclua dados pessoais, saves, logs privados ou arquivos do jogo no repositório.

## Fluxo Git

1. Atualize sua cópia da branch `main`.
2. Crie uma branch curta por tarefa, por exemplo `feat/mod-scanner` ou `fix/xml-validation`.
3. Faça mudanças pequenas e focadas.
4. Execute os testes aplicáveis.
5. Abra um Pull Request explicando objetivo, alterações, testes e riscos.
6. Aguarde revisão antes de integrar à `main`.

## Trabalho com múltiplas IAs

- Cada IA deve receber uma tarefa delimitada e o contexto dos arquivos relevantes.
- Evite que duas IAs editem o mesmo arquivo simultaneamente.
- Antes de reutilizar código gerado, revise-o e execute testes.
- Não aceite mudanças apenas porque foram sugeridas por uma IA.
- Registre decisões arquiteturais importantes na documentação.

## Padrões de código

- Use nomes claros e consistentes.
- Prefira funções pequenas e módulos com responsabilidade única.
- Trate erros de arquivos e permissões explicitamente.
- Não use caminhos absolutos específicos de uma máquina.
- Não faça operações destrutivas silenciosas.
- Adicione testes para parsing XML, perfis, backups e detecção de caminhos.

## Commits

Use mensagens curtas e descritivas, por exemplo:

- `docs: add initial project plan`
- `feat: scan local mod directories`
- `fix: preserve config when XML is invalid`
- `test: cover profile serialization`

## Segurança

Nunca envie tokens, senhas, cookies, saves ou arquivos privados. Toda alteração em arquivos do jogo deve ser explícita, validada e protegida por backup.
