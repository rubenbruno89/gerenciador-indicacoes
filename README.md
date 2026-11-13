# Gerenciador de Indicações de Clientes

Sistema em um único arquivo HTML para cadastrar clientes, gerar um código de indicação a partir do nome e registrar quem indicou quem. Os dados ficam em um banco SQLite (`.db`), com salvamento automático no navegador e opções para exportar e importar.

## Acesso

Use um destes endereços:

- https://gerenciador-indicacoes.shardweb.app/
- https://rubenbruno89.github.io/gerenciador-indicacoes/

Também é possível baixar o arquivo `indicacoes.html` e abri-lo diretamente no navegador.

## Funcionalidades

- Cadastro de clientes com nome, telefone, e-mail e observações
- Código gerado automaticamente a partir do nome
- Registro de quem indicou cada cliente
- Contagem de indicações e ranking dos maiores indicadores
- Busca, edição, exclusão e visualização de detalhes
- Salvamento automático no navegador, usando IndexedDB
- Exportação e importação do arquivo `.db`
- Exportação para CSV, compatível com o Excel

## Tecnologias

- HTML, CSS e JavaScript
- [sql.js](https://github.com/sql-js/sql.js) para usar SQLite no navegador
- IndexedDB para manter os dados ao fechar a página

Não é necessário instalar nada. O sistema funciona no navegador.

## Como usar

1. Acesse um dos links acima ou baixe o arquivo `index.html`.
2. Use o Chrome, Edge ou Firefox.
3. Na primeira abertura, é necessária conexão com a internet para carregar a biblioteca SQLite.
4. Cadastre os clientes e acompanhe as indicações.

## Como o código é gerado

O código usa até 5 letras do primeiro nome, a inicial do último sobrenome e 3 números aleatórios. Acentos são removidos, e palavras como `da`, `de`, `do`, `das`, `dos` e `e` são ignoradas. O sistema não permite códigos duplicados.

| Nome | Exemplo de código |
|---|---|
| Maria Souza | `MARIAS482` |
| João da Silva | `JOAOS731` |
| Ana Paula Ribeiro | `ANAR205` |
| Carlos | `CARLO918` |

Clique no código na tabela para copiá-lo.

## Armazenamento e backup

Os dados são salvos automaticamente neste navegador. Para fazer backup ou transferir para outro computador:

- **Exportar .db:** baixa um arquivo SQLite real, que também pode ser aberto no DB Browser for SQLite.
- **Importar .db:** carrega um arquivo exportado anteriormente e substitui os dados atuais.
- **Exportar CSV:** gera uma planilha para consulta no Excel.

Faça exportações periódicas. Se os dados do navegador forem limpos, as informações salvas automaticamente podem ser perdidas.

## Estrutura do banco

Tabela `clientes`:

| Campo | Descrição |
|---|---|
| `id` | Identificador automático |
| `nome` | Nome do cliente |
| `telefone` | Telefone |
| `email` | E-mail |
| `codigo` | Código único de indicação |
| `indicado_por` | Código de quem indicou |
| `observacoes` | Observações |
| `data_cadastro` | Data e hora do cadastro |

## Observações

- Os dados ficam apenas no navegador em que o sistema foi usado.
- A internet é necessária na primeira abertura para carregar o SQLite.
- A importação de um `.db` substitui todos os dados atuais.
- O arquivo contém dados pessoais. Guarde os backups em local seguro e não os compartilhe publicamente.

## Licença

Defina a licença desejada antes de publicar o repositório.
