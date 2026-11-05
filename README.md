# norte-predicao

Preparação de atributos, treino, avaliação e inferência dos modelos de previsão. Primeiro alvo: ROTI em até 72 h (XGBoost recursivo, vindo do TCC).

| | |
| --- | --- |
| Responsável | time `ml` |
| Executa em | a definir com o time da AWS |
| Situação | repositório novo; primeira tarefa é reproduzir o modelo atual |

## Prioridades

1. Especificar o ROTI previsto (estação, agregação, janela) e reproduzir o modelo atual num período conhecido.
2. Guardar cada previsão emitida, sem apagar, e comparar com o observado depois.
3. Avaliar por horizonte (1, 6, 24, 48, 72 h) contra referências simples (persistência e mesmo horário do dia anterior).

## Rodar localmente

```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
cp .env.example .env   # preencher
```

## O que não entra no git

Dados e modelos treinados. Modelos vão para o S3 com versão; cada versão registra o commit, o período de dados e as métricas.

## Pastas

- `docs/`: especificação do alvo, protocolo de avaliação, decisões
- `tests/`: testes (`pytest`)
