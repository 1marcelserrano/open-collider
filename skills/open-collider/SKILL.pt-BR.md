---
name: open-collider
description: Engine de ideação por colisão controlada entre domínios estruturalmente distantes (protocolo Open Collider / bisociação de Koestler). Foge do Hivemind Artificial — a tendência do LLM de convergir pro centro denso da distribuição de treino. Gera um banco de 5–7 domínios distantes com referências nomeadas, roda colisões isoladas mais uma colisão cross-domain, aplica curadoria de 3 filtros, devolve um pool rankeado. GATILHOS — open collider, bisociação, prompting cross-domain, banco de domínios, fugir do hivemind, ideias não-triviais, brainstorm com IA, gerar ideias originais, bater o óbvio, colisão de domínios distantes, bisociação de Koestler, pensamento lateral com IA, gerar ângulos, gerar teses, gerar hooks, briefing de ideação, pool de ideias. Use quando o brief é aberto, quando o output anterior pareceu genérico, ou quando originalidade é requisito explícito. NÃO use quando o brief já tem uma tese forte e precisa convergir, pra fact-checking, ou pra tarefas de edição.
---

# OPEN COLLIDER — Engine de Ideação por Colisão Controlada

> Versão: 1.0 (genérica)
> Base: CL-ML, "Escape the Artificial Hivemind" (2026) + Koestler, *The Act of Creation* (1964)
> Status: protocolo validado empiricamente pelo paper original (12 projetos, ~23k ideias, 4320 julgamentos pareados).

---

## 1. Quando usar

**USE quando:**
- Brief de ideação aberto, sem tese pré-definida
- O output anterior pareceu genérico, óbvio, ou "som de qualquer LLM"
- O usuário pede explicitamente "ideias diferentes" / "não-óbvio" / "fora do clichê"
- Gerar teses pra ensaios, artigos ou pesquisa
- Gerar ângulos pra conteúdo, marketing ou produto
- Brainstorm de hooks que precisam furar o ruído saturado
- Qualquer tarefa criativa ou estratégica onde a resposta default do LLM é previsível

**NÃO use quando:**
- O brief já tem tese forte e precisa de convergência
- Copy de conversão de alta intenção (use ferramentas focadas de copy)
- Fact-checking, edição, QA
- Tarefas com orçamento duro de tokens — esta skill é cara por design

---

## 2. Mecanismo (resumo do paper)

**Hivemind Artificial:** LLMs convergem pro centro denso da distribuição de treino. Adicionar mais contexto do domínio ou pedir pro modelo "ser original" quase não move o output (efeito medido: 4–13× menor que o prompting por colisão).

**Bisociação (Koestler):** uma ideia genuinamente nova nasce da colisão entre dois quadros de referência distantes — especificamente, quando se descobre uma *dimensão oculta de proximidade* entre eles (ex.: parasitologia × economia de plataforma → mecanismo compartilhado de redirecionamento comportamental pra benefício assimétrico).

**Movimento contraintuitivo:** injetar material *menos* relacionado, não mais relacionado. Volume + curadoria compensam o ruído inevitável.

---

## 3. Protocolo (5 estágios)

### Estágio 1 — Briefing

Elicitar do usuário (ou aceitar se já fornecido):

- **Problema de ideação:** qual é a questão aberta?
- **Critério de "ideia boa":** o que valida uma ideia? (originalidade pura, viabilidade operacional, fit de voz, etc.)
- **Restrições inegociáveis:** o que precisa estar presente ou ausente?
- **Destino do output:** isso alimenta o quê? (ensaio, campanha, produto, pesquisa)
- **Volume desejado:** quantas ideias curadas no fim? (default: 10)

### Estágio 2 — Gerar o banco de domínios

Produzir 5–7 domínios **estruturalmente distantes** a partir do brief. Cada domínio descrito como:

```
DOMÍNIO N: [nome do domínio + REFERÊNCIA ESPECÍFICA NOMEADA]
  Persona: [especialista hipotético daquele campo]
  Mecanismo contraintuitivo: [a regra/dinâmica não-óbvia do campo]
  Pergunta-ponte: [pergunta que força uma ponte pro brief]
```

**REGRA CRÍTICA:** cada domínio precisa de uma **referência específica nomeada** — um caso histórico, espécie nomeada, evento datado, pessoa real, obra específica. Domínio genérico produz analogia decorativa; referência específica produz mecanismo operacional.

- ❌ Fraco: "Aviação"
- ✅ Forte: "Aviação — acidente do voo Air France 447 (2009)"
- ❌ Fraco: "Falsificação de arte"
- ✅ Forte: "Falsificação de arte — Han van Meegeren, Wolfgang Beltracchi"
- ❌ Fraco: "Liturgia católica"
- ✅ Forte: "Liturgia católica após o Vaticano II (1962–65)"

**Critérios de distância:**
- Vocabulário diferente
- Contexto histórico/cultural diferente
- Escala temporal diferente (microbiologia × geologia × ciclo de moda)
- Disciplina diferente (engenharia × ritual × botânica × jurisprudência)

**Antipadrão:** evitar domínios que são "primos próximos" disfarçados (ex.: marketing × publicidade × branding = mesma zona). Buscar *outsiders* de verdade.

### Estágio 3 — Colisões em contextos isolados

Pra cada (brief × domínio), gerar 15–20 ideias num **bloco dedicado**, com instrução explícita de:

1. Identificar o mecanismo do domínio distante
2. Construir a ponte (que dimensão oculta os conecta?)
3. Produzir ideias que só fazem sentido *através dessa ponte*

**Formato de output por colisão:**

```
=== COLISÃO N: [brief] × [domínio] ===

DIMENSÃO OCULTA IDENTIFICADA:
[1–2 frases sobre o que torna esses dois campos secretamente próximos]

IDEIAS (15–20):
1. [...]
2. [...]
...
```

### Estágio 3.5 — Segunda colisão cross-domain

Depois do Estágio 3, identificar os **dois domínios que produziram as colisões mais fortes** (maior densidade de ideias com pontes reais, não decorativas).

Rodar **uma colisão adicional cruzando esses dois domínios entre si** (não com o brief):

```
=== COLISÃO CROSS: [domínio forte 1] × [domínio forte 2] → [brief] ===

DIMENSÃO TRIPLA:
[o que conecta os dois domínios entre si, e ambos ao brief]

IDEIAS (5–10):
```

**Por quê:** colisões cross-domain produzem empiricamente as ideias mais distintivas — articulam ângulos que nenhuma colisão de domínio único alcança.

Limitar a UMA segunda colisão por run. Mais que isso vira combinatória sem retorno.

### Estágio 4 — Curadoria (3 filtros)

Aplicar nesta ordem:

**Filtro 1 — Sinal vs. ruído**
- Descartar ideias que: (a) são absurdas sem payoff, (b) só repetem o domínio distante sem ponte real, (c) reconstroem o óbvio com vocabulário exótico.

**Filtro 2 — Fit de voz/estilo (com reescrita inline)**
- Checar candidatos contra os critérios de voz ou estilo do destino do output.
- Se uma ideia tem mecanismo forte mas formulação fraca, REESCREVER inline aqui — não adiar pra entrega. Reescrita tardia desperdiça tempo e contamina o output final.
- Critério de descarte: ideia cujo mecanismo só funciona com vocabulário ou tom inadequados pro destino.
- Critério de flag: ideia estruturalmente original mas operacionalmente complexa — sinalizar, deixar o usuário decidir.

**Filtro 3 — Critério do brief**
- Aplicar a definição de "o que valida" do Estágio 1.

### Estágio 5 — Output rankeado

Entregar:

```
## TOP {N} IDEIAS CURADAS

1. [ideia]
   ↳ Veio da colisão: [domínio]
   ↳ Dimensão oculta: [a ponte]
   ↳ Próximo passo: [ação concreta]

2. [...]
```

Mais um bloco de **descartes interessantes** (3–5 ideias que não passaram mas valem o registro pra iteração futura).

---

## 4. Falsificadores embutidos

Antes de entregar, rodar checagens internas:

- **Teste A vs B:** se eu removesse o banco de domínios e usasse só o brief, chegaria nas mesmas ideias? Se sim → falhou, refazer o Estágio 2 com domínios mais distantes.
- **Teste C:** as ideias dependem da ponte, ou seriam as mesmas se eu só dissesse "seja original"? Se são independentes → falhou.
- **Teste D:** se o brief fosse 3× mais longo e detalhado (sem domínios), eu chegaria aqui? Se sim → falhou.

Se qualquer um dos três falhar, declarar e oferecer um rerun.

---

## 5. Gate de custo

Esta skill é **cara por design** (5–7 colisões × 15–20 ideias = ~100 ideias geradas, depois curadas pra ~10, mais a colisão cross-domain).

**Gate inicial — perguntar ao usuário antes de rodar:**

> "O Open Collider vai gerar ~100 ideias em colisões separadas e curar pra {N}. O custo em tokens é alto. Vale rodar, ou um passe mais leve resolve?"

Alternativas mais leves a sugerir conforme o contexto:
- Brainstorm direto com o modelo
- Geração focada de ângulos
- Outline estruturado sem colisões de domínio

---

## 6. Antipadrões

- ❌ Gerar domínios genéricos sem referência específica nomeada (aviação ≠ "Air France 447, 2009")
- ❌ Gerar domínios "criativos" mas próximos (design × arquitetura × moda — mesma zona)
- ❌ Pular o Estágio 4 (curadoria) e entregar o pool cru
- ❌ Pular o Estágio 3.5 (cross-domain) quando há duas colisões claramente fortes
- ❌ Aplicar o passe de voz/estilo *na entrega* em vez de *na curadoria* (desperdiça tempo + contamina o output)
- ❌ Rodar sem o gate de custo
- ❌ Usar como substituto de skills convergentes (copy, ensaio com tese definida, edição)
- ❌ Rodar mais de UMA colisão cross-domain por execução (combinatória sem retorno)

---

## 7. Limitações declaradas

- O paper original testou só no Claude Sonnet 4; replicação cross-vendor é trabalho futuro
- LLM-as-judge é uma métrica imperfeita — o output ainda exige julgamento humano
- Bisociação produz **novidade**, não **valor** — a curadoria humana segue sendo o filtro real
- Risco de "ideia exótica sem viabilidade operacional" — o Estágio 4 mitiga, não elimina

---

## 8. Log de iteração (pra quem adapta esta skill)

Depois de rodar em 3 briefs reais, revisar:
- Quais domínios genéricos seguiram recorrendo (montar uma blacklist)
- Quais pontes funcionaram (montar uma biblioteca de "dimensões ocultas confirmadas")
- Razão sinal-ruído por brief (calibrar volume de domínios)
- Quais colisões cross-domain (Estágio 3.5) produziram as top-3 ideias finais

É assim que a skill compõe valor com o uso.

---

## Referências

- CL-ML (2026). "Escape the Artificial Hivemind." Open Collider research. github.com/CL-ML/open-collider
- Koestler, A. (1964). *The Act of Creation*. Hutchinson.
- Hofstadter, D. & Sander, E. (2013). *Surfaces and Essences*. Basic Books.
- Jiang, L. et al. (2025). "Artificial Hivemind: The Open-Ended Homogeneity of Language Models." arXiv:2510.22954.
- Polanyi, M. (1958). *Personal Knowledge*. (Pela dimensão tácita que a curadoria não codifica por inteiro.)
