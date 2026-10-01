# ClearBank - Análise Financeira com Python

Projeto desenvolvido como desafio prático do módulo de Python aplicado à Análise de Dados. O objetivo é processar, validar e auditar registros de transações financeiras, calcular métricas mensais consolidadas, sinalizar movimentações atípicas e exportar relatórios padronizados.

---

## 📌 Funcionalidades Principais

- **Leitura Resiliente:** Processamento do arquivo `transacoes.csv` utilizando o módulo nativo `csv.DictReader` e tratamento de erros de sistema de arquivos com `try/except FileNotFoundError`.
- **Limpeza e Validação de Dados:** Descarte silencioso de registros inválidos seguindo critérios rígidos:
  - Identificador (`id`) numérico e não nulo.
  - Identificador do cliente (`cliente_id`) preenchido.
  - Formato de data padronizado (`AAAA-MM-DD`) via `datetime.strptime`.
  - Tipo de movimentação restrito a `credito` ou `debito`.
  - Valores monetários numéricos estritamente positivos (`valor > 0`).
- **Métricas Financeiras Mensais:**
  - Quantidade total de operações por mês.
  - Totais acumulados de crédito, débito e saldo líquido.
  - Ticket médio, maior e menor transação do período.
  - Contagem total de dias decorridos entre a primeira e a última transação.
- **Detecção de Fraude / Suspeitas:** Sinalização automática de movimentações acima do teto de `R$ 10.000,00`.
- **Exportação de Dados:** Geração do arquivo estruturado `relatorio.json` com `json.dump(..., indent=2)`.
- **Requisitos Extras (Opcionais):**
  - Análise comparativa e agrupamento utilizando a biblioteca `pandas`.
  - Visualização gráfica comparativa (Crédito x Débito x Saldo) gerada com `matplotlib` e salva em `grafico.png`.

---

## 📁 Estrutura do Repositório

```text
clearbank-analise/
├── desafio-final.ipynb     # Notebook principal com o código e saídas executadas
├── transacoes.csv          # Base de dados utilizada para os testes e validações
├── relatorio.json          # Relatório financeiro consolidado exportado
├── grafico.png             # Gráfico comparativo gerado via matplotlib
└── README.md               # Documentação explicativa do projeto