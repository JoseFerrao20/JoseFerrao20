# Olá, sou o José Ferrão 👋

Construo projetos completos, do código aos testes, ao CI e à infraestrutura: aplicações full stack, pipelines de dados e bibliotecas, sempre com dados e problemas reais de Portugal.

## Projetos

### ⛽ [combustiveis-pt](https://github.com/JoseFerrao20/combustiveis-pt)

[![CI](https://github.com/JoseFerrao20/combustiveis-pt/actions/workflows/ci.yml/badge.svg)](https://github.com/JoseFerrao20/combustiveis-pt/actions/workflows/ci.yml)

**Onde abastecer mais barato, e quanto do preço é imposto.** Um pipeline de dados que junta o preço de cada posto de combustível em Portugal (DGEG), o boletim semanal da Comissão Europeia desde 2005, as cotações internacionais e os preços máximos dos Açores e da Madeira, e publica tudo num [site](https://joseferrao20.github.io/combustiveis-pt/) que se atualiza sozinho.

[![O site no telemóvel: o resumo dos preços, um posto acompanhado face aos concorrentes a 5 km e os preços máximos dos Açores e da Madeira](https://raw.githubusercontent.com/JoseFerrao20/combustiveis-pt/main/docs/images/painel-telemovel-paginas.png)](https://joseferrao20.github.io/combustiveis-pt/)

- **Dados:** ingestão em Python, transformação com o dbt e o DuckDB (com testes de dados), e o histórico dos preços de cada posto guardado semana a semana no próprio repositório, porque a DGEG só mostra o preço em vigor.
- **Fontes sem contrato, lidas com desconfiança:** o ficheiro do boletim, a API da DGEG e os despachos em PDF dos jornais oficiais são validados à entrada, e uma mudança de formato falha com um erro claro e um email.
- **Uma previsão para segunda-feira,** a partir dos mercados, testada nas semanas que o ajuste não viu (erro médio de 1,1 cêntimos).
- **Um site leve:** páginas estáticas em Svelte com JSON pequenos, que funcionam sem rede e se instalam no telemóvel. Começou no Evidence e saiu dele página a página (12 MB → 200 KB).
- Cerca de 275 testes (pytest, dbt e Playwright, com acessibilidade verificada pelo axe), dados abertos em CSV e decisões registadas em ADR.

### 🛡️ [Warrantly](https://github.com/JoseFerrao20/warrantly)

[![Backend](https://github.com/JoseFerrao20/warrantly/actions/workflows/backend.yml/badge.svg)](https://github.com/JoseFerrao20/warrantly/actions/workflows/backend.yml)
[![E2E](https://github.com/JoseFerrao20/warrantly/actions/workflows/e2e.yml/badge.svg)](https://github.com/JoseFerrao20/warrantly/actions/workflows/e2e.yml)

**Arquivo de garantias:** guarda as faturas das compras, calcula até quando cada uma está na garantia (3 anos, Decreto-Lei n.º 84/2021), avisa antes de expirar e, quando algo avaria, escreve a reclamação para a loja.

[![Painel do Warrantly com as garantias, das que expiram primeiro às já expiradas](https://raw.githubusercontent.com/JoseFerrao20/warrantly/main/docs/images/painel.png)](https://github.com/JoseFerrao20/warrantly)

- Site em React + TypeScript, app móvel em Expo (React Native) e API em FastAPI + PostgreSQL.
- Infraestrutura na AWS descrita em Terraform (Lambda, S3, CloudFront, SES, EventBridge) e CI/CD no GitHub Actions, com um script que verifica o primeiro deploy antes de correr.
- Cerca de 540 testes automáticos: pytest, Vitest, jest-expo e Playwright, com acessibilidade verificada pelo axe.
- Lê as faturas pelo código QR com o faturapt, que nasceu deste projeto: na app, basta apontar a câmara ao QR.

### 🧾 [faturapt](https://github.com/JoseFerrao20/faturapt)

[![PyPI](https://img.shields.io/pypi/v/faturapt)](https://pypi.org/project/faturapt/)
[![CI](https://github.com/JoseFerrao20/faturapt/actions/workflows/ci.yml/badge.svg)](https://github.com/JoseFerrao20/faturapt/actions/workflows/ci.yml)

Biblioteca Python que lê e valida o **código QR das faturas portuguesas** (o da Autoridade Tributária) e NIFs: a partir do texto, de uma fotografia ou do PDF que chega por email.

- **[Experimentar no browser](https://joseferrao20.github.io/faturapt/):** a página corre a própria biblioteca Python com o Pyodide e lê o QR pela câmara do telemóvel. Nada sai do aparelho.
- Publicada no PyPI (`pip install faturapt`), com trusted publishing a partir do GitHub Actions.
- Regras conferidas com a especificação técnica da AT. Os exemplos do próprio documento fazem parte dos testes, e há testes de ida e volta com o Hypothesis.

## Com o que trabalho

**Python** (FastAPI, SQLAlchemy, pytest) · **Dados** (dbt, DuckDB, Parquet) · **TypeScript** (React, Svelte, React Native com Expo) · **PostgreSQL** · **AWS** e **Terraform** · **GitHub Actions** · **Playwright**

## Como trabalho

- Um PR por alteração, com testes e o CI verde antes do merge.
- As decisões ficam registadas (ADR) e cada projeto tem um diário (DEVLOG).
- Acessibilidade (WCAG 2.2 AA) e segurança desde o início, não no fim.
- Os projetos mantêm-se sozinhos: cada fonte de dados é vigiada e avisa por email quando para ou muda.
- Uso o Claude Code como par de programação: eu decido o que construir e revejo o que entra, e o agente acelera a escrita do código e dos testes.
