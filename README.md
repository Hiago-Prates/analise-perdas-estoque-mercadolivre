# 🔍 Análise de Perdas Operacionais — Investigação de Estoque | Mercado Livre

> Metodologia de investigação e recuperação de itens perdidos no estoque, rastreando a jornada completa do produto desde o recebimento até a localização da inconsistência.

---

## 🎯 O Problema

Itens classificados como **Lost (perdidos)** no sistema representam prejuízo financeiro direto para a operação. Uma peça marcada como Lost significa que o sistema não sabe onde ela está — ela pode ter sumido em qualquer etapa do processo logístico:

```
Recebimento → Check-in → Put Away → Armazenagem → Coleta → Expedição
```

O desafio: **encontrar onde a peça se perdeu** analisando centenas (às vezes milhares) de movimentações no sistema.

---

## 💡 A Solução

Desenvolvi uma **metodologia própria de investigação** que permite localizar e conciliar itens perdidos de forma sistemática, rastreando toda a cadeia de movimentos do produto no sistema interno do Mercado Livre.

---

## 🔧 Ferramentas e Sistemas Utilizados

| Ferramenta | Uso |
|---|---|
| **Sistema interno ML** | Relatório de inconsistências de estoque |
| **Módulo de movimentos** | Rastreamento da jornada completa do produto |
| **Relatório de recebimento (IS)** | Verificação da entrada correta do item |
| **Análise de posição física** | Checagem do endereço físico no galpão |

---

## 📋 Metodologia — Passo a Passo

### 1️⃣ Identificação da inconsistência
Acesso ao **Relatório de Inconsistências de Estoque** e filtro por itens em status **Lost + Pendente**.

> Exemplo real: **569 unidades** do mesmo SKU classificadas como Lost.

### 2️⃣ Análise dos movimentos
Para cada item, investigo:
- Como as peças caíram para Lost
- Quantas coletas foram realizadas e quantas unidades foram coletadas
- Se houve ação de setores terceiros (coletas de qualidade, time de suporte)
- Se houve movimentações sistêmicas ou conciliações anteriores
- Como as peças chegaram ao endereço de origem

### 3️⃣ Reconstrução da jornada
Refaço **toda a movimentação da peça** desde o recebimento (IS) até o momento da inconsistência — página por página no histórico de movimentos.

### 4️⃣ Verificações complementares
- ✅ Verificação de inversão com outras peças
- ✅ Verificação de sobras da mesma peça em outros endereços
- ✅ Verificação da posição física no galpão

### 5️⃣ Resolução
- **Se encontrada fisicamente** → Conciliação da posição
- **Se houver sobras no sistema** → Conciliação das sobras
- Finalização da análise com registro do resultado

---

## 📊 Exemplo Real Analisado

| Dado | Valor |
|---|---|
| SKU analisado | YDKO46599 |
| Produto | Arroz Polido Tipo 1 Tio João 1kg |
| EAN | 7893500020110 |
| Unidades recebidas (IS) | 2.250 |
| Unidades em Lost | 569 |
| Páginas de movimentos analisadas | 12 páginas (574 movimentos) |
| Valor unitário | R$ 7,51 |
| **Valor em risco** | **R$ 4.273,19** |

---

## 🧠 Diferenciais da Metodologia

- **Rastreamento cronológico completo** — do recebimento ao Lost, sem pular etapas
- **Análise multi-variável** — considera movimentos sistêmicos, terceiros e posição física
- **Foco financeiro** — cada análise tem impacto direto em R$ recuperados para a operação
- **Metodologia replicável** — pode ser aplicada a qualquer SKU com inconsistência

> 📎 *Prints do processo de investigação em anexo.*

---

## 👨‍💻 Autor

**Hiago Prates** — Analista Operacional | Estudante de Ciência de Dados
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/hiago-prates-a3a295400)
