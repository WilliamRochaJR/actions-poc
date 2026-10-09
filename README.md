# GitHub Actions POC

Repositório de estudo para aprender GitHub Actions de forma incremental.

## Pré-requisitos

- Git instalado.
- Uma conta no GitHub.
- Este repositório publicado no GitHub.

## Git

O repositório foi iniciado na branch `main`. Alguns comandos úteis durante o
estudo são:

```bash
git status
git log --oneline
git add .
git commit -m "descrição da alteração"
```

Para publicar o repositório pela primeira vez, crie um repositório vazio no
GitHub e execute:

```bash
git remote add origin URL_DO_REPOSITORIO
git push -u origin main
```

## Primeira GitHub Action

O workflow está em [`.github/workflows/hello.yml`](.github/workflows/hello.yml).
O GitHub procura workflows dentro da pasta `.github/workflows`.

Ele pode ser iniciado de duas maneiras:

- automaticamente, quando há um `push` na branch `main`;
- manualmente, pelo botão **Run workflow** na aba **Actions** do GitHub.

### Estrutura do workflow

- `name`: nome exibido na aba Actions.
- `on`: eventos que iniciam a execução.
- `jobs`: trabalhos executados pelo workflow.
- `runs-on`: sistema operacional da máquina temporária usada pelo job.
- `steps`: etapas executadas em sequência.
- `uses`: reutiliza uma action pronta. `actions/checkout@v4` baixa o código.
- `run`: executa um comando no terminal do runner.

O exemplo também imprime variáveis padrão fornecidas pelo GitHub, como nome do
repositório, referência da branch, hash do commit e evento que iniciou o job.

Após publicar, abra **Actions > Primeira Action** para acompanhar os logs de
cada etapa.

## Roteiro

1. ✅ Criar o primeiro workflow manual e executá-lo em `push`.
2. Executar o workflow em `pull_request`.
3. Adicionar um projeto simples com testes.
4. Configurar cache de dependências.
5. Gerar e publicar artefatos.
6. Explorar variáveis, secrets e ambientes.

Cada etapa será registrada em um commit separado para facilitar o estudo do histórico.
