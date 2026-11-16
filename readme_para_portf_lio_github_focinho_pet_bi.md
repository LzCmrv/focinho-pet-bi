# 🐾 Focinho Pet — Dashboard Executivo de Vendas, Rentabilidade & Logística Reversa

[![Live Demo](https://img.shields.io/badge/Live_Demo-Acessar_Dashboard-2563eb?style=for-the-badge&logo=google-chrome&logoColor=white)](https://SEU-USUARIO.github.io/focinho-pet-bi/dashboard_focinho.html)
![Status](https://img.shields.io/badge/Status-Conclu%C3%ADdo-10b981?style=for-the-badge)
![Stack](https://img.shields.io/badge/Stack-HTML5_%7C_Tailwind_CSS_%7C_JavaScript_%7C_Chart.js_%7C_SheetJS-0f172a?style=for-the-badge)

> **Resumo Executivo:** Projeto completo de **Business Intelligence (BI) e Análise de Dados** desenvolvido sobre uma base real de **2.341 pedidos** (21 SKUs e 6 categorias) do varejo pet entre **janeiro de 2025 e setembro de 2026**. A solução combina auditoria financeira, diagnóstico de anomalias operacionais e um **Dashboard Web Interativo** com filtros dinâmicos e ingestão direta de planilhas `.xlsx`/`.csv`.

---

## 🔗 Link para Acesso ao Dashboard Interativo

👉 **[Clique aqui para explorar o Dashboard ao vivo](https://SEU-USUARIO.github.io/focinho-pet-bi/dashboard_focinho.html)**  
*(Dica: após subir os arquivos no GitHub, ative o **GitHub Pages** em `Settings > Pages > Branch: main` e substitua `SEU-USUARIO` pelo seu nome de usuário no link acima).*

---

## 🎯 Problema de Negócio & Objetivo

O e-commerce **Focinho Pet** apresentou forte expansão de faturamento ao longo de 2025 e 2026, mas enfrentava dúvidas críticas de gestão:
1. O crescimento de receita estava se convertendo proporcionalmente em **lucro bruto**?
2. Qual o impacto real de **devoluções, cancelamentos e cupons promocionais** na margem da operação?
3. Quais **canais de venda, categorias, meios de pagamento e SKUs** concentram os maiores ganhos ou vazamentos financeiros?

---

## 🛠️ Passo a Passo do Projeto (Metodologia)

### Etapa 1 — Ingestão, Saneamento e Auditoria da Base (`ETL`)
Antes de construir qualquer visualização, a base `Base_Pedidos_Focinho.xlsx` passou por uma auditoria rigorosa de qualidade de dados:
* **Volumetria e Unicidade:** Validação de **2.341 registros únicos** (`P-10001` a `P-12341`), sem linhas duplicadas ou valores nulos críticos.
* **Reconciliação Aritmética:** Verificação linha a linha da equação $\text{Valor Total} = (\text{Quantidade} \times \text{Preço Unitário}) - \text{Desconto}$ com **100% de conformidade**.
* **Segregação de Status:** Separação analítica entre **Pedidos Entregues** (receita efetivamente realizada), **Devolvidos** e **Cancelados** (receita não realizada / perda operacional), evitando distorção nos indicadores de caixa.
* **Engenharia de Atributos (Feature Engineering):** Criação de métricas derivadas como *Receita Bruta*, *Lucro Bruto* ($\text{Receita Líquida} - \text{CMV}$), *Margem Bruta (%)*, *Taxa de Devolução (%)*, *Taxa de Cancelamento (%)*, *Ticket Médio*, *Curva ABC/Pareto* e *Comparativo Ano contra Ano (YoY)*.

### Etapa 2 — Análise Exploratória e Diagnóstico Financeiro (`EDA`)
Com os dados saneados, foram conduzidas análises cruzadas por **tempo (mensal e YoY)**, **canal**, **categoria**, **produto (SKU)**, **cupom**, **meio de pagamento**, **região**, **perfil de cliente** e **dia da semana**.

### Etapa 3 — Desenvolvimento do Dashboard Interativo (`Front-End BI`)
Construção de uma aplicação web *single-page* leve, responsiva e sem dependência de servidor:
* **8 Filtros Dinâmicos Simultâneos:** Ano, Mês, Canal de Venda, Categoria, Região, Meio de Pagamento, Tipo de Cliente e Cupom — recalculando instantaneamente todos os cartões, gráficos e tabelas.
* **Botões de Auditoria Rápida:** Atalhos de 1 clique para isolar anomalias críticas (ex.: cupom `VOLTA30` e gargalo de devolução em `Acessórios` no `Marketplace`).
* **Ingestão Self-Service (`.xlsx`/`.csv`):** Integração com a biblioteca **SheetJS**, permitindo importar novas versões da planilha diretamente no navegador.
* **Visualizações Interativas:** 7 gráficos dinâmicos construídos com **Chart.js** e estilizados com **Tailwind CSS**.

---

## 📊 Principais Indicadores Levantados (KPIs Consolidados)

| Indicador | Pedidos Entregues (Realizado) | Pedidos Devolvidos | Pedidos Cancelados | Total Registrado |
| :--- | :---: | :---: | :---: | :---: |
| **Volume de Pedidos** | **2.166** (92,5%) | 101 (4,3%) | 74 (3,2%) | **2.341** (100%) |
| **Unidades Vendidas** | **3.483** | 143 | 112 | **3.738** |
| **Receita Bruta** | R$ 298.213 | R$ 15.652 | R$ 10.243 | R$ 324.108 |
| **Descontos Concedidos** | R$ 8.074 | R$ 388 | R$ 368 | R$ 8.830 |
| **Receita Líquida** | **R$ 290.139** | R$ 15.264 | R$ 9.875 | R$ 315.278 |
| **Custo de Mercadoria (CMV)** | R$ 166.694 | R$ 8.620 | R$ 5.815 | R$ 181.129 |
| **Lucro Bruto** | **R$ 123.445** | R$ 6.644 | R$ 4.060 | R$ 134.149 |
| **Margem Bruta (%)** | **42,5%** | 43,5% | 41,1% | **42,5%** |
| **Ticket Médio Líquido** | **R$ 133,95** | **R$ 151,13** | R$ 133,45 | **R$ 134,68** |

* **Crescimento Ano contra Ano (Jan–Set 2025 vs. Jan–Set 2026):**
  * **Receita Líquida Realizada:** **+33,9%** (de R$ 104.237 para R$ 139.558).
  * **Pedidos Entregues:** **+33,6%** (de 774 para 1.034 entregas).
  * **Lucro Bruto:** **+31,0%** (de R$ 45.202 para R$ 59.215), crescendo abaixo da receita devido à erosão promocional em julho/2026.

---

## 💡 Principais Insights & Anomalias Descobertas

1. **Vazamento e Destruição de Margem no Cupom `VOLTA30` (Julho/2026):**
   * Criado para reativação de clientes antigos, o cupom de 30% foi usado **88 vezes** em julho/2026, mas **61,4% dos usos (54 pedidos) vieram de clientes Novos**.
   * Julho/2026 bateu recorde de receita líquida (**R$ 18.682**), mas gerou **menos lucro bruto (R$ 6.024; margem de 32,2%)** do que meses regulares como março/2026 (R$ 6.843 sobre R$ 15.306).
   * **27 pedidos** operaram com margem crítica ($\le 15\%$) ao combinar `VOLTA30` com **Ração** e **Farmácia** (chegando a **11,3%** de margem).
2. **Gargalo de Logística Reversa em Volumosos no Marketplace:**
   * A categoria **Acessórios** apresenta **8,9% de devolução** (mais que o dobro da média geral de 4,3%).
   * Apenas 2 SKUs explicam **90,9% das devoluções da categoria (20 de 22)**: **Cama Ortopédica G** (**33,3%** de devolução no Marketplace) e **Caixa de Transporte M** (**36,4%** no Marketplace).
3. **Boleto Bancário Cancela 5x Mais que Pix e Cartão:**
   * Enquanto **Pix** (48,8% da receita) e **Cartão** (45,3%) cancelam apenas **2,5%** e **2,3%**, o **Boleto** possui **12,2% de cancelamento** (perda de **R$ 2.002**) e o menor ticket médio (**R$ 111,53**).
4. **Anomalia de Perda Operacional em Fevereiro/2026:**
   * Em fevereiro/2026, a taxa combinada de devoluções e cancelamentos saltou para **14,8%** (16 de 108 pedidos), o dobro da média histórica (7,5%).
5. **Mix de Produtos & Curva Pareto (80/20):**
   * **Ração** representa **44,6% da receita** (R$ 129.469), mas tem a **menor margem (36,7%)**. Já **Petiscos (54,6%)** e **Brinquedos (53,3%)** entregam quase **+18 p.p. de margem**, representando forte alavanca de *cross-sell*.
   * Apenas **2 SKUs** (*Ração Premium Cães Adultos 15kg* e *Ração Premium Gatos Castrados 10kg*) concentram **37,6% da receita líquida** e **32,0% do lucro bruto**.
6. **Canais de Venda, Retenção e Congelamento de Preços:**
   * **App (+55,7%)** e **Marketplace (+53,5%)** lideraram o crescimento YoY; o **WhatsApp** obteve a **maior margem (44,7%)** e taxa de devolução quase nula (**0,5%**).
   * Clientes **Recorrentes** cresceram **+50,9% YoY** e gastam **+15,9% a mais por pedido** (R$ 144,08 vs. R$ 124,35 de Novos).
   * Todos os **21 SKUs** permaneceram com preços congelados por 21 meses consecutivos.

---

## 🎯 Recomendações Estratégicas Geradas

* **Governança Promocional:** Bloquear cupons de reativação por CPF histórico e limitar descontos em Ração/Farmácia a no máximo 15%.
* **Otimização de Cadastro e Embalagem:** Revisar guia de medidas e fotos reais da *Cama Ortopédica G* e *Caixa de Transporte M* no Marketplace para recuperar **~R$ 3.600** em receita estornada.
* **Conversão Boleto → Pix & Order Bump:** Criar régua de conversão de boleto para Pix em 24h e ofertar kits de *Petiscos* no checkout de *Ração*.

---

## 🚀 Como Publicar este Projeto no seu GitHub (Passo a Passo)

1. Crie um novo repositório público no GitHub chamado **`focinho-pet-bi`**.
2. Faça upload dos arquivos **`dashboard_focinho.html`**, **`README.md`** e **`Base_Pedidos_Focinho.xlsx`**.
3. Acesse a aba **Settings** do repositório > menu lateral **Pages**.
4. Em **Source**, selecione `Deploy from a branch`, escolha a branch **`main`** e a pasta **`/ (root)`**, e clique em **Save**.
5. Aguarde cerca de 1 minuto e seu dashboard estará online no endereço:  
   `https://SEU-USUARIO.github.io/focinho-pet-bi/dashboard_focinho.html`

---

## 👨‍💻 Autor

Desenvolvido por **[Seu Nome]** — Estudante de Análise de Dados / Business Intelligence.  
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Conectar-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/SEU-LINKEDIN)
[![GitHub](https://img.shields.io/badge/GitHub-Portf%C3%B3lio-181717?style=flat&logo=github&logoColor=white)](https://github.com/SEU-USUARIO)