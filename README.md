Painel Unificado de Gestão de Vendas e Inventário Automotivo

Ferramenta analítica desenvolvida em Microsoft Excel para consolidação de indicadores de performance (KPIs), monitoramento de fluxo de caixa e controle automatizado de pátio/estoque para concessionárias multimarcas, com foco nas montadoras GM, VW e CAOA.
O projeto adota uma arquitetura de tela única unificada, otimizando o processamento das fórmulas e oferecendo uma interface limpa com usabilidade no padrão "Modo Aplicativo".


Perguntas de Negócio Respondidas (KPIs Macros)

O bloco central de Fechamento do Mês isola a complexidade dos registros diários e responde em tempo real a 3 perguntas estratégicas de governança comercial:
Volume de Saídas Globais (Vendas):
	• Mapeamento: Calculado na célula A13. Soma a quantidade total de veículos faturados e entregues aos clientes no mês corrente.

Receita Bruta Acumulada (Faturamento Total):
	• Mapeamento: Calculado na célula A16. Consolida o valor financeiro total em Reais (R$) gerado estritamente pelas operações de venda (Saídas).

Posição de Giro de Pátio (Estoque Geral):
	• Mapeamento: Calculado na célula A19. Monitora o saldo físico de veículos remanescentes em pátio, cruzando as entradas e saídas históricas.


Engenharia de Dados e Algoritmos de Cálculo

Toda a inteligência e transição de dados do painel operam de forma automatizada por meio das seguintes funções do Excel:

Consolidação com Filtro de Blocos (SOMASE)

Utilizado para filtrar fluxos macro com base no tipo de movimentação operacional:
• Faturamento Total (A16): =SOMASE(C$3:C$10; "Saída"; F$3:F$10)


Filtro Multicritério Avançado (SOMASES)

Aplicado na tabela comparativa por marca (Linhas 26 a 35) para cruzar simultaneamente a montadora correspondente e o tipo de operação, isolando faturamentos e volumes de frota:
• Faturamento por Marca (Ex: GM na célula A35):excel
=SOMASES(F$3:F$10; B$3:B$10; A22; C$3:C$10; "Saída")
Use o código com cuidado.


Equação de Fluxo de Inventário Dinâmico

Elimina contagens manuais na planilha ao atualizar o pátio de forma indexada por marca:
• Saldo Atual em Estoque (Linha 32): =Total_Entradas_Marca - Total_Saídas_Marca


Matriz Relacional de Desempenho do Repositório

Os dados consolidados no fechamento do arquivo executável seguem os parâmetros reais abaixo:

Métrica Gerencial	Coluna A (GM)	Coluna B (VW)	Coluna C (CAOA)
Total de Entradas
	10	20	8
Total de Saídas / Vendas
	6	6	3
Saldo Atual em Estoque
	4	14	5
Faturamento em Reais (R$)
	R$ 570.000,00	R$ 492.000,00	R$ 390.000,00
