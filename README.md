# Olá, sou o José Ferrão 👋

Estou a aprender desenvolvimento full stack a construir projetos completos: do código aos testes, ao CI e à infraestrutura na cloud.

## Projetos

### 🧾 [faturapt](https://github.com/JoseFerrao20/faturapt)

[![PyPI](https://img.shields.io/pypi/v/faturapt)](https://pypi.org/project/faturapt/)
[![CI](https://github.com/JoseFerrao20/faturapt/actions/workflows/ci.yml/badge.svg)](https://github.com/JoseFerrao20/faturapt/actions/workflows/ci.yml)

Biblioteca Python que lê e valida o **código QR das faturas portuguesas** (o da Autoridade Tributária) e NIFs: a partir do texto, de uma fotografia ou do PDF que chega por email.

- **[Experimentar no browser](https://joseferrao20.github.io/faturapt/):** a página corre a própria biblioteca Python com o Pyodide e lê o QR pela câmara do telemóvel. Nada sai do aparelho.
- Publicada no PyPI (`pip install faturapt`), com trusted publishing a partir do GitHub Actions.
- Regras conferidas com a especificação técnica da AT. Os exemplos do próprio documento fazem parte dos testes, e há testes de ida e volta com o Hypothesis.
- Python 3.10 a 3.14, tipos verificados com o mypy, CodeQL e Dependabot.

### 🛡️ Warrantly

Arquivo de garantias: guarda as faturas das compras, calcula até quando cada uma está na garantia (3 anos, Decreto-Lei n.º 84/2021), avisa antes de expirar e, quando algo avaria, escreve a reclamação para a loja.

- Site em React + TypeScript, app móvel em Expo (React Native) e API em FastAPI + PostgreSQL.
- Infraestrutura na AWS descrita em Terraform (Lambda, S3, CloudFront, SES, EventBridge) e CI/CD no GitHub Actions.
- Cerca de 440 testes automáticos: pytest, Vitest, jest-expo e Playwright, com acessibilidade verificada pelo axe.
- Lê as faturas pelo código QR com o faturapt, que nasceu deste projeto.

*O repositório fica público quando a app estiver publicada na AWS.*

## Com o que trabalho

**Python** (FastAPI, SQLAlchemy, pytest) · **TypeScript** (React, React Native com Expo) · **PostgreSQL** · **AWS** e **Terraform** · **GitHub Actions** · **Playwright**

## Como trabalho

- Um PR por alteração, com testes e o CI verde antes do merge.
- As decisões ficam registadas (ADR) e cada projeto tem um diário (DEVLOG).
- Acessibilidade (WCAG 2.2 AA) e segurança desde o início, não no fim.
- Uso o Claude Code como par de programação: eu decido o que construir e revejo o que entra, e o agente acelera a escrita do código e dos testes.
