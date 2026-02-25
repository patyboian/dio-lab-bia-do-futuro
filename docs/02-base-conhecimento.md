# Base de Conhecimento

>[!TIP]
> **Prompt sugerido para essa etapa:
> ```
> Preciso organizar a base de conhecimento do meu agente de metas. Tenhos estes arquivos de dados:
> historico_atendimento.csv;
> perfil_investidor.json;
> transacoes.csv;
> Me ajude a:
> (1) Entender o que cada arquivo contém.
> (2) Decidir como usar cada um.
> (3) Criar um exemplo de contexto formatado para incluir no prompt
```


## Dados Utilizados

Descreva se usou os arquivos da pasta `data`, por exemplo:

| Arquivo | Formato | Utilização no Agente |
|---------|---------|---------------------|
| `historico_atendimento.csv` | CSV | Contextualizar interações anteriores |
| `perfil_investidor.json` | JSON | Personalizar metas |
| `transacoes.csv` | CSV | Analisar padrão de gastos do cliente |

## Adaptações nos Dados

> Você modificou ou expandiu os dados mockados? Descreva aqui.

A base de conhecimento foi adaptada para refletir um agente focado em planejamento de metas financeiras, removendo complexidade relacionada a produtos de investimento e priorizando dados de renda, gastos e metas pessoais.

---

## Estratégia de Integração

### Como os dados são carregados?
> Descreva como seu agente acessa a base de conhecimento.

Existem duas possibilidades, injetar os dados diretamente no prompt (Ctrl + C, Ctrl + V) ou carregar os arquivos via código, como no exemplo abaixo:

``` python
import pandas as pd
import json

#CSV
historico = pd.read_csv('data/historico_atendimento.csv')
transacoes = pd.read_csv('data/transacoes.csv')

#Json
whith open ('data/perfil_investidor.json', 'r', encoding-'utf-8') as f:
    perfil = json.load(f)
```

### Como os dados são usados no prompt?
> Os dados vão no system prompt? São consultados dinamicamente?

Para simplificar, podemos simplesmente "injetar" os dados em nosso prompt, garantindo que o Agente tenha o melhor contexto possível. Lembrando que, em soluções mais robustas, o ideal é que estas informações sejam carregadas dinamicamente para que possamos ganhar flexibilidade.

```
Dados do Cliente:
{
  "nome": "João Silva",
  "idade": 32,
  "renda_mensal": 5000.00,
  "objetivo_principal": "Reserva de emergência",
  "metas": [
    {
      "nome_meta": "Reserva de emergência",
      "valor_total": 15000.00,
      "valor_atual": 10000.00,
      "prazo_meses": 6
    }
  ]
}

Transações:
data	descricao	categoria	valor	tipo
2025-10-01	Salário	receita	5000.00	entrada
2025-10-02	Aluguel	moradia	1200.00	saida
2025-10-03	Supermercado	alimentacao	450.00	saida
2025-10-05	Netflix	lazer	55.90	saida
2025-10-07	Farmácia	saude	89.00	saida
2025-10-10	Restaurante	alimentacao	120.00	saida

Histórico de atendimento:
data	canal	tema	resumo	resolvido
2026-02-01	chat	Criacao de meta	Cliente criou meta de viagem	sim
2026-02-10	chat	Atualizacao de deposito	Cliente registrou novo aporte	sim
2026-02-20	chat	Atraso na meta	Cliente pediu recalculo de prazo	sim
```

---

## Exemplo de Contexto Montado

> Mostre um exemplo de como os dados são formatados para o agente.

```
Dados do Cliente:
- Nome: João Silva
- Saldo disponível: R$ 5.000

Últimas transações:
- 01/11: Supermercado - R$ 450
- 03/11: Streaming - R$ 55

```
