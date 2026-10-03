# 🏎️ Porsche Guards — Dashboard Comercial
 
Dashboard interativo de vendas para uma concessionária Porsche, entregue em **um único arquivo HTML**, sem build, sem backend e sem instalação. Basta abrir no navegador ou publicar em qualquer hospedagem estática.
 
> ⚠️ Os dados incluídos são **fictícios**, gerados por código para demonstração.
 
---
 
## ✨ Visão geral
 
O projeto responde a três perguntas de negócio com visualizações conectadas aos mesmos filtros:
 
1. **Quais modelos dão mais retorno financeiro em relação ao volume vendido?**
   Gráfico de bolhas: unidades (X) × receita (Y) × preço médio (tamanho da bolha).
2. **Qual a preferência de pagamento por faixa de preço?**
   Barras empilhadas 100%, com os modelos do mais barato ao mais caro, divididos em À Vista, Financiamento e Consórcio Premium.
3. **Quem são os melhores vendedores e como estão frente à meta?**
   Barras horizontais com linha vertical de meta. Quem bate a meta fica em branco; quem não bate fica em titânio.
## 📈 KPIs
 
| Indicador | O que mostra |
|---|---|
| Receita Bruta Total | Soma das vendas filtradas |
| Volume de Vendas | Unidades entregues |
| Ticket Médio por Veículo | Receita ÷ unidades |
| Modelo Mais Vendido | Campeão em unidades, com silhueta em miniatura |
 
## 🎛️ Filtros
 
- **Modelo:** 911, Cayenne, Taycan, Panamera, Macan, 718
- **Cidade / Região:** São Paulo, Rio de Janeiro, Curitiba, Belo Horizonte, Brasília
- **Ano do Modelo:** 2022 a 2025 (novos × seminovos)
- **Método de Pagamento:** À Vista, Financiamento, Consórcio Premium
Cada filtro é um grupo de botões (uma opção por vez; "Todos" limpa). KPIs e gráficos se atualizam juntos.
