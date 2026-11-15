# GitHub Actions · Laboratório 04

O [workflow Lint e build Docker](.github/workflows/docker.yml) verifica a aplicação Express e gera uma imagem Docker. O job `build_docker` depende de `lint` e verifica a aplicação em execução por HTTP na porta 8080.

| Branch | Comportamento |
| --- | --- |
| `demo/lint-falha` | O ESLint rejeita `require` sem a declaração de ambiente Node. O passo `check-lint` registra a falha e o job de build fica pulado. |
| `main` | A declaração `/* eslint-env node */` corrige a falha. O lint libera o build, seguido da validação HTTP. |

O escopo do exercício vai até o build da imagem. O workflow também admite publicação no Docker Hub quando as credenciais estão configuradas.
