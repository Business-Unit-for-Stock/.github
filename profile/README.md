# Business-Unit-for-Stock

Stock research engineering organization.

## Working Principle

Reuse existing open-source capabilities first. Organization forks track and pin upstream
projects; organization-owned GitHub Actions call those capabilities; `stock-research`
normalizes, validates, versions, and analyzes the resulting data.

```text
upstream project -> organization fork -> workflow call -> raw artifact
                                                    -> normalized data -> research
```

## Standard Repositories

- [`requirements`](https://github.com/Business-Unit-for-Stock/requirements): product/business requirements, scope, workflows, acceptance criteria, and open questions.
- [`deploy`](https://github.com/Business-Unit-for-Stock/deploy): deployment orchestration, domains, CI/CD release notes, environment mapping, and operations docs.
- [`.github`](https://github.com/Business-Unit-for-Stock/.github): organization profile and repository map.
- [`stock-research`](https://github.com/Business-Unit-for-Stock/stock-research): organization-owned data contracts, workflow orchestration, analysis, and A-share-aware backtesting.

## Reused Research Capabilities

| Capability | Organization forks |
|---|---|
| Free market data | [`akshare`](https://github.com/Business-Unit-for-Stock/akshare), [`a-stock-data`](https://github.com/Business-Unit-for-Stock/a-stock-data), [`yfinance`](https://github.com/Business-Unit-for-Stock/yfinance) |
| Short-term direction | [`plate-rotation-skill`](https://github.com/Business-Unit-for-Stock/plate-rotation-skill), [`tickflow-stock-panel`](https://github.com/Business-Unit-for-Stock/tickflow-stock-panel) |
| Medium-term direction | [`stock-screener`](https://github.com/Business-Unit-for-Stock/stock-screener), [`TradingAgents-astock`](https://github.com/Business-Unit-for-Stock/TradingAgents-astock) |
| Research and validation | [`quant-momentum-lab`](https://github.com/Business-Unit-for-Stock/quant-momentum-lab), [`qlib`](https://github.com/Business-Unit-for-Stock/qlib), [`alphalens`](https://github.com/Business-Unit-for-Stock/alphalens) |

The detailed license and integration boundaries are maintained in
[`stock-research/docs/reused-repositories.md`](https://github.com/Business-Unit-for-Stock/stock-research/blob/main/docs/reused-repositories.md).

## Repository Map

Current repositories should keep this split:

- Business application repositories own source code, tests, builds, and development docs.
- `stock-research` owns external-module orchestration, canonical data, quality checks, and analysis logic.
- Third-party forks stay close to upstream and do not own organization-specific research logic.
- `requirements` owns durable product/business requirements.
- `deploy` owns deployment and operations workflows.
- `.github` owns organization-level profile and repository map.

## Governance

- Keep development and deployment separate.
- Use GitHub Actions/CI for deployment workflows; store credentials in GitHub Actions secrets.
- Do not commit tokens, passwords, SSH keys, customer private data, or server credentials.
