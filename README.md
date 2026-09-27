# Painel Estoque & OS

Painel para acompanhar, produto por produto, **estoque**, **venda empenhada**, **estoque disponível** e **dias em estoque**, com aviso de **PERIGO** quando um produto tem 30 dias de estoque ou menos no ritmo de consumo atual.

Funciona direto no navegador, sem servidor. Os dados ficam só no navegador de quem abre.

## Como usar

1. Abra o `index.html` no navegador (ou pelo GitHub Pages, se estiver ativado).
2. Clique em **Importar planilha** e escolha um ou mais arquivos `.xlsx`, `.xls` ou `.csv`.
3. As colunas são reconhecidas automaticamente. Dá para conferir e ajustar na tela de importação.

Ao abrir sem dados, o painel mostra um exemplo identificado como **Dados de exemplo**. O botão **Baixar modelo** gera uma planilha com as colunas esperadas.

## Colunas reconhecidas

Não é preciso ter todas. Nomes parecidos também são aceitos.

| Informação | Exemplos de nome de coluna |
|---|---|
| Código | Código do Material, Código do Produto, SKU |
| Produto | Descrição do Material, Produto, Material |
| Estoque | Estoque, Quantidade em Estoque, Saldo |
| Venda empenhada | Empenhado, Quantidade Empenhada, Venda, Reservado |
| Consumo (com data) | Data + Consumo / Saída / Baixa |
| OS | Número da OS, OS, Ordem de Serviço |
| Movimentação | Data da Movimentação, Etapa, Tipo de Movimentação |

## Cálculos

- **Estoque disponível** = Estoque − Venda empenhada. Valor negativo aparece como estoque insuficiente.
- **Consumo médio diário** = consumo no período ÷ dias do período (padrão: últimos 30 dias, trocando para 15 quando o ritmo muda muito).
- **Dias em estoque** = Estoque disponível ÷ Consumo médio diário.
- **Perigo**: 30 dias ou menos (limite ajustável na engrenagem ⚙).

Sem histórico de consumo, os dias em estoque aparecem como "sem dados". Nenhum valor é estimado.

## Exportação

Excel, CSV e PDF pela tabela ou pelo menu **Exportar**.
