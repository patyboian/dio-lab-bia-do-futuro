# Avaliação e Métricas

## Como Avaliar seu Agente

A avaliação pode ser feita de duas formas complementares:

1. **Testes estruturados:** Você define perguntas e respostas esperadas;
2. **Feedback real:** Pessoas testam o agente e dão notas.

---

## Métricas de Qualidade

| Métrica | O que avalia | Exemplo de teste |
|---------|--------------|------------------|
| **Assertividade** | O agente respondeu o que foi perguntado? | Perguntar o saldo guardado e receber o valor correto |
| **Segurança** | O agente evitou inventar informações? | Perguntar algo fora do contexto e ele admitir que não sabe |
| **Coerência** | A resposta faz sentido para o perfil do cliente? | Sugerir metas que o cliente não solicitou |

> [!TIP]
> Peça para 3-5 pessoas (amigos, família, colegas) testarem seu agente e avaliarem cada métrica com notas de 1 a 5. Isso torna suas métricas mais confiáveis! Caso use os arquivos da pasta `data`, lembre-se de contextualizar os participantes sobre o **cliente fictício** representado nesses dados.

---

## Exemplos de Cenários de Teste

Crie testes simples para validar seu agente:

### Teste 1: Usuária quer juntar dinheiro para viajar e ainda não sabe quanto precisa guardar por mês.
- **Pergunta:** "Quero juntar 6 mil reais em 12 meses para viajar. Como faço?"
- **Resposta esperada:** Que meta incrível! ✨ Vamos organizar isso juntas.
Para juntar R$ 6.000 em 12 meses, você precisa guardar R$ 500 por mês.
Se começar agora e manter esse valor mensalmente, sua viagem fica totalmente possível.
Quer que eu acompanhe seu progresso mês a mês?
- **Resultado:** [ ] Correto  [ ] Incorreto

### Teste 2: Usuária já tem uma meta ativa e quer registrar um depósito.
- **Pergunta:** "Guardei 600 reais esse mês."
- **Resposta esperada:** Perfeito! Já registrei seu depósito de R$ 600 👏
Você está acima do valor planejado para este mês. Isso acelera sua conquista!
Se continuar nesse ritmo, pode atingir sua meta antes do prazo.
- **Resultado:** [ ] Correto  [ ] Incorreto

### Teste 3: Usuária deveria guardar R$ 500 por mês, mas guardou apenas R$ 300.
- **Pergunta:** "Esse mês só consegui guardar 300."
- **Resposta esperada:** Sem problema! O importante é não parar 😊
Você guardou R$ 300, e isso já é um passo importante.
Se quiser, posso recalcular o valor mensal para manter o prazo ou ajustar a meta para ficar mais confortável para você.
- **Resultado:** [ ] Correto  [ ] Incorreto

### Teste 4: Pergunta fora do escopo
- **Pergunta:** "Qual a previsão do tempo para amanhã?"
- **Resposta esperada:** Sou especializada em metas financeiras e não tenho informações sobre previsão do tempo. Posso ajudar com algo relacionado às suas metas?
- **Resultado:** [ ] Correto  [ ] Incorreto

---

## Resultados

Após os testes, registre suas conclusões:

**O que funcionou bem:**
- Todos os testes funcionaram corretamente

**O que pode melhorar:**
- Pode ser melhorado questões fora do escopo

---

## Métricas Avançadas (Opcional)

Para quem quer explorar mais, algumas métricas técnicas de observabilidade também podem fazer parte da sua solução, como:

- Latência e tempo de resposta;
- Consumo de tokens e custos;
- Logs e taxa de erros.

Ferramentas especializadas em LLMs, como [LangWatch](https://langwatch.ai/) e [LangFuse](https://langfuse.com/), são exemplos que podem ajudar nesse monitoramento. Entretanto, fique à vontade para usar qualquer outra que você já conheça!
