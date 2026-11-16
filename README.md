# GitHub Actions — variáveis e escopos

**Laboratório educacional.** Explora variáveis globais, por job e por step, além de valores persistidos em `GITHUB_ENV`.

[Portfólio](https://github.com/Enzo-Zapparolli) · [Workflow](.github/workflows/pipeline.yml)

## O que observar

- `APP_NAME` está no escopo global do workflow.
- `BUILD_VERSION` existe no job `build_app`.
- `STEP_TEMP` existe apenas no step que a define.
- `BUILD_HASH` é persistido para steps posteriores do mesmo job por `GITHUB_ENV`.
- O segundo job utiliza `needs` e referencia `vars.URL_AMBIENTE` e `secrets.API_TOKEN_PROD`.

## Executar

Na aba **Actions**, selecione **Desafio de Variaveis e Escopos** e use **Run workflow**. Os valores de vars e secrets dependem da configuração do repositório; não estão incluídos no código.

## Escopo

O job chamado `deploy_app` demonstra variáveis e não realiza implantação. As respostas originais da atividade foram preservadas em [docs/README-anterior.md](docs/README-anterior.md).
