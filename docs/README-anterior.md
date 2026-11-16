# lab-github-actions-vars

## Respostas da atividade

### 1. Por que a Secret aparece no log como *** e a variável aparece normalmente?

A Secret aparece mascarada como *** porque o GitHub Actions protege automaticamente valores definidos em `secrets`, evitando que informações sensíveis sejam expostas nos logs. Já as variáveis de repositório (`vars`) não são tratadas como segredos, então seus valores aparecem normalmente.

### 2. O Job deploy_app consegue ler a variável BUILD_VERSION criada no Job build_app? Por quê?

Não. O job `deploy_app` não consegue ler `BUILD_VERSION` porque ela foi definida no escopo do job `build_app`. Em GitHub Actions, jobs diferentes executam em runners diferentes, então variáveis de job não são compartilhadas automaticamente entre jobs.

### 3. O que aconteceu com STEP_TEMP no Passo 2?

A variável `STEP_TEMP` não ficou disponível no Passo 2 porque ela foi criada apenas no escopo do Step 1. Variáveis definidas dentro do `env` de um step só existem naquele step específico.
