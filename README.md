# 🏎️ Porsche Guards — Dashboard Comercial
 
Dashboard interativo de vendas de uma concessionária Porsche, em **um único arquivo HTML** (sem build, sem backend).
 
🔗 **Dashboard publicada:** https://nickolasrodolphi.github.io/porsche_dashboard/ 

📦 **Código:** https://github.com/nickolasrodolphi/porsche_dashboard/blob/main/index.html 
 
> ⚠️ Os dados são **fictícios**, gerados por código para fins de demonstração.
 
---
 
## 1. Perguntas de negócio escolhidas (e por quê)
 
| # | Pergunta | Gráfico | Por que esta pergunta |
|---|---|---|---|
| 1 | Quais modelos trazem o maior retorno financeiro em relação ao volume vendido? | Bolhas (unidades × receita × preço médio) | Decide **estoque**: um nicho de ticket alto (911) pode render tanto quanto um SUV de volume (Macan) com muito menos unidades. |
| 2 | Qual a preferência de método de pagamento por faixa de preço? | Barras empilhadas 100% | Decide **parcerias e taxas** com financeiras: se os modelos de entrada dependem mais de financiamento, é ali que a negociação importa. |
| 3 | Quem são os melhores vendedores e qual a consistência no trimestre? | Barras horizontais + linha de meta | Decide **premiação e suporte**: mostra de imediato quem bate a meta e quem precisa de apoio. |
 
Juntas, as três cobrem os três eixos de decisão de uma concessionária: **o que vender** (produto), **como financiar** (condição comercial) e **quem vende** (equipe). Cada uma tem um tipo de gráfico diferente, adequado ao tipo de comparação.
 
Também há 4 KPIs fixos no topo (Receita Bruta, Volume, Ticket Médio e Modelo Mais Vendido) e 4 filtros (Modelo, Cidade, Ano do Modelo e Método de Pagamento) que atualizam tudo ao mesmo tempo.
 
## 2. Prompt que gerou a dashboard
 
Foi usado **um único prompt de especificação**, que já definia identidade visual, KPIs, filtros e as 3 perguntas com o gráfico recomendado para cada uma. Resumo da estrutura:
 
- **Identidade visual:** Premium Minimalist, Dark Mode. Cores `#0B0C10`, `#D11A2A`, `#F5F5F7`, `#8A9A86`. Fonte Porsche Next ou Helvetica Neue.
- **KPIs fixos no topo:** Receita Bruta Total, Volume de Vendas, Ticket Médio por Veículo, Modelo Mais Vendido (com miniatura).
- **Filtros:** Modelo (911, Cayenne, Taycan, Panamera, Macan, 718), Cidade/Região, Ano do Modelo (novos × seminovos Porsche Approved), Método de Pagamento (À Vista, Financiamento, Consórcio Premium).
- **3 perguntas de negócio**, cada uma com gráfico recomendado, "como funciona" e "insight" (bolhas; barras empilhadas 100%; barras horizontais com linha de meta em vermelho).
- **Entrega:** "faça isso e me entregue o HTML único como um dashboard para compartilhamento".
### O que mudou até a versão final
 
A dashboard foi gerada **em uma única passagem**, sem reescrever o prompt. As mensagens seguintes serviram para explicar o resultado, simplificar a explicação e gerar este README, não para alterar o visual.
 
Decisões que a IA tomou por conta própria, por falta de informação no prompt:
 
- **Dados fictícios:** o prompt não trazia base, então foram gerados 130 vendas de forma determinística (mesmo resultado a cada abertura).
- **Meta fixa** de R$ 12 mi por vendedor.
- **Foto do modelo campeão:** substituída por uma silhueta em SVG, porque a página não carrega imagens externas.
- **Chart.js** via CDN para os gráficos.

 
## 3. Tratamento da base antes de ir para a IA
 
**Nenhuma base real foi enviada para a IA**, então não houve tratamento prévio. Os dados foram **sintetizados pela própria IA** a partir de regras simples:
 
- 6 modelos com preço-base e peso de popularidade;
- desconto de 7% por ano de idade do modelo (simulando seminovos);
- mais financiamento nos modelos de entrada e menos nos topo de linha;
- 8 vendedores com pesos de desempenho diferentes.
Para usar **dados reais**, a base precisaria de uma linha por venda com as colunas `model`, `city`, `year`, `pay`, `seller` e `price`, e de:
 
1. padronizar nomes (modelos, cidades, vendedores) e métodos de pagamento;
2. converter preços para número, em reais, sem símbolo nem separadores;
3. remover duplicatas e vendas canceladas;
4. tratar valores ausentes;
5. anonimizar dados pessoais de clientes (LGPD) e, se for compartilhar, dos vendedores.

## 4. Ferramenta de IA utilizada
 
**Claude (Anthropic), no chat do claude.ai**, com criação de arquivos e publicação de página (artifact). **Não** foi usado ChatGPT com Canvas, e **não** foi usado um agente com skill específica: o HTML foi escrito diretamente pelo modelo a partir do prompt.
