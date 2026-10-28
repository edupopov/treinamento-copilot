# Laboratório avançado — Microsoft 365 Copilot no Excel

> **Trilha 2 — Módulo avançado** | Contoso Brasil (dados fictícios)  
> **Material:** [`Laboratorio_M365_Copilot_Excel_Contoso.xlsx`](./Laboratorio_M365_Copilot_Excel_Contoso.xlsx)  
> **Apoio:** [`20_Prompts_Avancados_M365_Copilot_Excel.txt`](./20_Prompts_Avancados_M365_Copilot_Excel.txt)  
> **Nível:** intermediário a avançado | **20 exercícios** | **Duração sugerida:** 3h em módulos ou sessões independentes

## Objetivo

Evoluir da consulta a dados para **modelagem analítica, tabelas dinâmicas, gráficos, segmentações, dashboards, cenários e auditoria dos resultados do Copilot**. A planilha contém 460 registros: Financeiro (216), Orçamento (96), Ativos (100) e Fornecedores (48); a aba Dashboard é o espaço de montagem. Os dados de movimentação são de 2025.

## Orientações antes de começar

1. Trabalhe **sempre em uma cópia** da planilha, idealmente em OneDrive/SharePoint autorizado para a experiência do Copilot.
2. Confirme licenciamento, habilitação do Copilot, permissões e compatibilidade da versão do Excel.
3. As tabelas estruturadas disponíveis são: `TblFinanceiro`, `TblOrcamento`, `TblAtivos` e `TblFornecedores`. A aba `Dashboard` não é uma tabela estruturada.
4. Se o Copilot não criar uma Tabela Dinâmica, gráfico ou edição automaticamente, use a resposta como roteiro e faça **Inserir > Tabela Dinâmica**, **Inserir > Gráficos** e **Inserir > Segmentação de Dados** no Excel. Inspecione o resultado; não presuma que foi inserido.
5. **Atenção:** `Orçamento!Realizado (R$)` utiliza fórmulas vinculadas às despesas da aba Financeiro. Deixe o Excel recalcular e confirme os valores antes de avaliar desvios.
6. O campo `Mês` é numérico de 1 a 12. O campo `Data` possui datas. As tabelas `Financeiro` e `Fornecedores` usam documento e nota fiscal, respectivamente.
7. A data-base usada nas atividades de vencimento e garantia é **28/10/2026** para manter os resultados reprodutíveis. As simulações de 2026 são exercícios hipotéticos construídos sobre 2025.
8. Nunca confunda **indício de duplicidade** com pagamento irregular comprovado, **valor de aquisição** com custo de reposição ou **saldo operacional** com saldo bancário disponível.

### Estrutura de colunas

| Aba / tabela | Colunas principais |
|---|---|
| `Financeiro` / `TblFinanceiro` | `ID`, `Data`, `Mês`, `Tipo`, `Departamento`, `Categoria`, `Contraparte`, `Documento`, `Valor (R$)`, `Status`, `Descrição` |
| `Orçamento` / `TblOrcamento` | `ID`, `Competência`, `Mês`, `Departamento`, `Orçado (R$)`, `Realizado (R$)`, `Desvio (R$)`, `Desvio (%)`, `Status` |
| `Ativos` / `TblAtivos` | `Patrimônio`, `Tipo`, `Fabricante`, `Modelo`, `Departamento`, `Unidade`, `Aquisição`, `Fim garantia`, `Valor (R$)`, `Vida útil (anos)`, `Situação` |
| `Fornecedores` / `TblFornecedores` | `Contrato`, `Fornecedor`, `Serviço`, `Departamento`, `Início`, `Vencimento`, `Pagamento`, `Valor pago (R$)`, `Nota fiscal`, `Situação`, `Periodicidade` |

## Roteiro de aplicação

**Workshop de 2 horas:** exercícios 1, 3, 4, 5, 6, 7, 9, 11, 14, 16, 19 e 20 como demonstrações + práticas orientadas, ajustando o ritmo. Os demais ficam como atividades de aprofundamento. **Percurso completo:** duas sessões de 90 a 120 minutos, mais revisão em casa.

| Bloco | Exercícios | Ênfase |
|---|---|---|
| Integridade e modelagem | 01–02 | Chaves, granularidade, filtros |
| Tabelas dinâmicas e visuais | 03–07 | Agregações, Pareto, heatmap |
| Investigações | 08–10 | Outliers, duplicidades, contratos |
| Gestão de ativos e cenários | 11–14 | Garantia, renovação, caixa, projeção |
| Painéis interativos | 15–17 | Segmentadores e dashboards |
| Decisão e qualidade | 18–20 | Sensibilidade, resumo, auditoria |

## Como avaliar cada exercício

- **40% exatidão:** totais e regras verificáveis na base.
- **25% artefato:** gráfico/tabela dinâmica/painel realmente criados e editáveis.
- **20% interpretação:** não confunde hipótese com evidência.
- **15% rastreabilidade:** identifica fonte, filtros, datas e premissas.

---


## Exercício 01 — Auditoria inicial de qualidade dos dados

**Tempo estimado:** 6 min  
**Abas:** `Financeiro, Orçamento, Ativos, Fornecedores`  
**Conceito:** Antes de visualizar dados, verifique a confiabilidade do conjunto.

### Passo a passo

1. Abra as quatro tabelas e confirme cabeçalhos e filtros.
2. Peça ao Copilot um inventário por aba e uma lista de riscos de qualidade.
3. Confronte contagens e datas com os filtros do Excel.

### Prompt para o Copilot

```text
Atue como analista de qualidade de dados. Inspecione TblFinanceiro, TblOrcamento, TblAtivos e TblFornecedores. Informe quantidade de linhas, campos, granularidade de cada tabela, períodos cobertos e campos potencialmente vazios ou repetidos. Diferencie erro confirmado de possível inconsistência. Não modifique os dados. Entregue um checklist de validação com coluna "Como conferir no Excel".
```

### Conferência / aceite

Contagens esperadas: 216, 96, 100 e 48. Status "Vencido" não basta para concluir que um pagamento é irregular.

### Desafio extra

Verifique se há datas fora da referência de 2025 e explique por que isso pode ser esperado.

**Entrega do aluno:** Checklist de integridade


## Exercício 02 — Modelo de dados: granularidade e chaves

**Tempo estimado:** 6 min  
**Abas:** `Financeiro e Orçamento`  
**Conceito:** Evitar somas duplicadas antes de criar uma tabela dinâmica.

### Passo a passo

1. Identifique o grão de cada tabela.
2. Compare ID financeiro com ID de orçamento.
3. Explique o risco de cruzar linhas sem agregar.

### Prompt para o Copilot

```text
Analise a granularidade de TblFinanceiro e TblOrcamento. Qual é a chave única de cada linha? Em Orçamento, a combinação Mês + Departamento deveria ser única? Explique por que um cruzamento linha a linha pode multiplicar valores. Proponha uma agregação segura por Mês e Departamento para confrontar despesas realizadas contra orçamento; utilize apenas Tipo="Despesa" no Financeiro. Mostre como conferir o cruzamento em uma tabela dinâmica.
```

### Conferência / aceite

Orçamento tem uma linha por mês e departamento; comparar despesas, nunca receitas como gasto.

### Desafio extra

Teste se chaves agrupadas se repetem.

**Entrega do aluno:** Plano de cruzamento sem dupla contagem


## Exercício 03 — Tabela dinâmica de receita e despesa por mês

**Tempo estimado:** 8 min  
**Abas:** `Financeiro`  
**Conceito:** Agrupar movimentos e comparar montantes mensais.

### Passo a passo

1. Clique em uma célula de TblFinanceiro.
2. Solicite uma tabela dinâmica em uma nova área/aba.
3. Configure Mês nas linhas, Tipo nas colunas e Soma de Valor nos valores.
4. Confira totais anuais aplicando filtros manuais.

### Prompt para o Copilot

```text
Crie, se o recurso estiver disponível, uma Tabela Dinâmica editável com origem em TblFinanceiro: linhas = Mês (ordem 1 a 12); colunas = Tipo; valores = Soma de Valor (R$). Mostre total anual de Receita e Despesa. Sugira um gráfico de colunas agrupadas vinculado à tabela dinâmica. Não transforme as 216 linhas em médias. Caso não consiga inserir, forneça passos exatos no Excel para criar a tabela dinâmica manualmente.
```

### Conferência / aceite

Soma de receitas e despesas da tabela dinâmica deve bater com SOMASES por Tipo.

### Desafio extra

Adicione um segmentador de Tipo caso faça sentido.

**Entrega do aluno:** Tabela dinâmica mensal


## Exercício 04 — Gráfico combinado: receitas, despesas e saldo

**Tempo estimado:** 8 min  
**Abas:** `Financeiro`  
**Conceito:** Visualizar trajetória e saldo sem misturar escalas.

### Passo a passo

1. Parta dos totais por mês do exercício 3.
2. Calcule Saldo = Receita - Despesa em uma tabela auxiliar.
3. Crie gráfico de colunas com receitas/despesas e uma linha de saldo ou gráficos separados.
4. Revise os eixos e rótulos.

### Prompt para o Copilot

```text
A partir de TblFinanceiro, agregue por Mês: Soma das Receitas, Soma das Despesas e Saldo=Receitas-Despesas. Monte uma tabela-resumo editável de janeiro a dezembro de 2025 e um gráfico gerencial que mostre os três indicadores. Indique claramente R$ e a unidade usada. Se for gráfico combinado, explique o uso de eixo secundário para não distorcer a leitura. Valide cada mês nos lançamentos.
```

### Conferência / aceite

Saldo é fluxo líquido do mês; não é necessariamente saldo bancário acumulado.

### Desafio extra

Construa também a versão acumulada a partir de saldo inicial hipotético identificado como premissa.

**Entrega do aluno:** Tabela auxiliar e gráfico combinado


## Exercício 05 — Tabela dinâmica: orçamento por departamento

**Tempo estimado:** 8 min  
**Abas:** `Orçamento`  
**Conceito:** Comparar previsto versus realizado por departamento no ano.

### Passo a passo

1. Selecione TblOrcamento.
2. Peça tabela dinâmica por Departamento.
3. Some Orçado e Realizado; crie desvio de totais.
4. Gere barras horizontais com comparação de departamentos.

### Prompt para o Copilot

```text
Crie uma Tabela Dinâmica de TblOrcamento com Departamento nas linhas e Soma de Orçado (R$) e Soma de Realizado (R$) nos valores. Gere uma coluna calculada fora da tabela dinâmica para Desvio=Realizado-Orçado e Desvio %=Desvio/Orçado, com tratamento para zero. Ordene pelo maior estouro em reais. Crie um gráfico de barras agrupadas. Não utilize média dos Desvios (%) mensais para representar o anual.
```

### Conferência / aceite

Células de Realizado usam fórmulas referenciando TblFinanceiro; recalcule o Excel antes de concluir.

### Desafio extra

Fatie o resultado por mês com segmentação ou filtro de relatório.

**Entrega do aluno:** Tabela dinâmica de orçamento e gráfico


## Exercício 06 — Heatmap de desvios mês x departamento

**Tempo estimado:** 7 min  
**Abas:** `Orçamento`  
**Conceito:** Detectar concentração de diferenças por período.

### Passo a passo

1. Monte tabela dinâmica com linhas Departamento e colunas Mês.
2. Valor: soma de Desvio (R$), não a média percentual.
3. Aplique escala de cores e legenda.

### Prompt para o Copilot

```text
Usando TblOrcamento, crie uma matriz com Departamento nas linhas, Mês nas colunas e Soma de Desvio (R$) como valor. Aplique uma formatação condicional em três cores para distinguir estouro, proximidade do planejado e economia; deixe explícita a legenda. Identifique os cinco cruzamentos mês/departamento com maior desvio positivo. Se não puder aplicar a formatação, ensine o passo a passo para fazer no Excel.
```

### Conferência / aceite

Quanto maior o valor positivo, maior o realizado acima do orçado.

### Desafio extra

Crie outra matriz com desvio percentual calculado corretamente para cada grupo.

**Entrega do aluno:** Heatmap por departamento


## Exercício 07 — Pareto de categorias de despesas

**Tempo estimado:** 8 min  
**Abas:** `Financeiro`  
**Conceito:** Priorizar os principais grupos de gasto por participação acumulada.

### Passo a passo

1. Filtre Tipo="Despesa".
2. Agrupe Categoria por soma do valor.
3. Ordene decrescente e calcule percentual acumulado.
4. Construa barras e curva acumulada.

### Prompt para o Copilot

```text
Na TblFinanceiro, considere apenas Tipo="Despesa". Faça uma tabela de Pareto por Categoria com total em R$, participação percentual sobre o total de despesas e participação acumulada. Ordene do maior para o menor e crie gráfico de Pareto com barras + linha percentual acumulada. Marque o ponto próximo de 80%. Não inclua receitas.
```

### Conferência / aceite

A última linha acumulada deve somar 100% com tolerância a arredondamentos.

### Desafio extra

Faça Pareto também por Departamento.

**Entrega do aluno:** Tabela e gráfico de Pareto


## Exercício 08 — Anomalias estatísticas em despesas

**Tempo estimado:** 8 min  
**Abas:** `Financeiro`  
**Conceito:** Uma discrepância numérica não é prova de fraude.

### Passo a passo

1. Filtre despesas.
2. Compare valores à distribuição por Categoria.
3. Solicite critérios numéricos claros para outliers.
4. Examine os registros sinalizados.

### Prompt para o Copilot

```text
Procure outliers entre os registros Tipo="Despesa" de TblFinanceiro. Avalie valores por Categoria (não compare gastos heterogêneos sem normalização). Defina e explique um critério reproduzível, como IQR ou valor acima de 2 vezes a mediana da categoria. Liste ID, Data, Categoria, Valor e motivo do alerta. Inclua explicitamente FIN correspondente ao maior valor de despesa, caso identificado. Não rotule alertas como fraude.
```

### Conferência / aceite

Há despesa injetada de R$ 84.500 em outubro; avalie contexto e agrupamento.

### Desafio extra

Compare resultados de IQR versus múltiplo da mediana.

**Entrega do aluno:** Tabela de anomalias auditável


## Exercício 09 — Duplicidade de documentos e notas fiscais

**Tempo estimado:** 8 min  
**Abas:** `Financeiro e Fornecedores`  
**Conceito:** Evidências distintas para duplicidades potenciais.

### Passo a passo

1. Procure valores repetidos em Documento e Nota fiscal.
2. Mostre todas as linhas associadas.
3. Compare data, contraparte, valor e tipo.
4. Sugira revisão humana.

### Prompt para o Copilot

```text
Verifique documentos potencialmente duplicados, separadamente: em TblFinanceiro use registros com Tipo="Despesa" agrupados por Documento; em TblFornecedores agrupe por Nota fiscal. Exiba todas as ocorrências repetidas com ID/Contrato, documento, fornecedor, datas e valores. Destaque grupos com mesmo documento e valor, mas não afirme duplicidade de pagamento sem conciliação com o sistema de origem. Não exclua nada.
```

### Conferência / aceite

Há DOC/NF intencionalmente repetidos; repetir identificador é um alerta, não confirmação.

### Desafio extra

Proponha identificador composto para futura prevenção.

**Entrega do aluno:** Lista de grupos suspeitos


## Exercício 10 — Contratos: risco de vencimento e concentração

**Tempo estimado:** 7 min  
**Abas:** `Fornecedores`  
**Conceito:** Separar data de vencimento, situação e exposição financeira.

### Passo a passo

1. Escolha data de referência explicitamente: 28/10/2026.
2. Agrupe por Fornecedor e Serviço.
3. Calcule vencidos e aqueles com prazo de 90 dias.
4. Exiba gráfico de barras por fornecedor.

### Prompt para o Copilot

```text
Na TblFornecedores, avalie contratos relativamente à data fixa de 28/10/2026. Conte vencidos e os que vencerão em até 90 dias após essa data. Compare campo Situação com a regra baseada em Vencimento, destacando discordâncias. Agrupe Valor pago (R$) por Fornecedor e crie barras dos dez maiores. Atenção: pagamentos registrados em 2025 não são necessariamente o valor total do contrato.
```

### Conferência / aceite

A situação da amostra foi calculada com base em 28/10/2026, mas deve ser validada.

### Desafio extra

Crie segmentação por Serviço.

**Entrega do aluno:** Matriz de vencimentos e concentração


## Exercício 11 — Ativos: envelhecimento e garantia

**Tempo estimado:** 8 min  
**Abas:** `Ativos`  
**Conceito:** Auditar idade e cobertura com data de referência.

### Passo a passo

1. Use 28/10/2026 para referência.
2. Calcule idade na data com diferença de anos cuidadosa.
3. Separe garantia vencida de vida útil ultrapassada.
4. Crie tabela dinâmica por Tipo e Unidade.

### Prompt para o Copilot

```text
Na TblAtivos, use a data fixa 28/10/2026. Adicione colunas auxiliares editáveis: Idade em anos completos, Garantia vencida? (Fim garantia < data de referência) e Vida útil ultrapassada? (idade > Vida útil (anos)). Crie uma Tabela Dinâmica por Tipo e Unidade contando Patrimônio; outra visão para garantias vencidas. Explique como tratar os equipamentos cuja vida útil vence exatamente na data e não presuma que precisem de substituição imediata.
```

### Conferência / aceite

Verifique datas e quantidade de 100 ativos; diferença de dias/365 não define idade civil perfeitamente.

### Desafio extra

Monte um gráfico de colunas empilhadas por cobertura de garantia.

**Entrega do aluno:** Indicadores de lifecycle e tabela dinâmica


## Exercício 12 — Ativos: matriz de renovação com orçamento

**Tempo estimado:** 8 min  
**Abas:** `Ativos`  
**Conceito:** Transformar diagnóstico técnico em priorização financeira.

### Passo a passo

1. Estabeleça critérios de prioridade.
2. Crie matriz por departamento, tipo e criticidade.
3. Some valor histórico de aquisição, sem rotular como preço novo.
4. Simule orçamento com preço unitário explicitamente hipotético.

### Prompt para o Copilot

```text
Use TblAtivos para gerar uma matriz de renovação por Departamento e Tipo. Prioridade alta: garantia vencida E vida útil ultrapassada em 28/10/2026; média: apenas uma condição; baixa: nenhuma. Conte Patrimônio por prioridade e calcule o valor histórico de compra, deixando claro que ele não é custo de reposição. Para simular novo investimento, use preço hipotético de R$ 6.000 por notebook e R$ 38.000 por servidor, em tabela separada e marcada como simulação. Mostre resultados em tabela dinâmica e barras.
```

### Conferência / aceite

Não confundir valor histórico com preço de mercado ou valor residual.

### Desafio extra

Simule renovação de apenas 30% dos itens de prioridade alta.

**Entrega do aluno:** Matriz de priorização e custos hipotéticos


## Exercício 13 — Fluxo de caixa acumulado com parâmetro de abertura

**Tempo estimado:** 8 min  
**Abas:** `Financeiro`  
**Conceito:** Distinguir saldo do período de saldo disponível.

### Passo a passo

1. Resuma receita e despesa mensal.
2. Defina saldo inicial simulado de R$ 100.000.
3. Calcule evolução acumulada com fórmulas.
4. Faça gráfico de linha e encontre mínimos.

### Prompt para o Copilot

```text
Com TblFinanceiro de 2025, agregue receitas e despesas por mês e calcule saldo líquido mensal. Em tabela auxiliar, adote Saldo Inicial SIMULADO de R$ 100.000 em 01/01/2025 e calcule Saldo Final mensal = Saldo Inicial do mês + Receitas - Despesas, carregando o saldo ao mês seguinte. Faça gráfico de evolução e identifique menor saldo. Mantenha o parâmetro em célula editável e jamais apresente esse saldo como saldo bancário real.
```

### Conferência / aceite

Reconcilie a diferença saldo final - saldo inicial com receitas menos despesas anuais.

### Desafio extra

Teste saldo inicial zero e compare as conclusões.

**Entrega do aluno:** Fluxo projetado retrospectivo


## Exercício 14 — Cenários prospectivos com premissas editáveis

**Tempo estimado:** 10 min  
**Abas:** `Financeiro`  
**Conceito:** Simulações dependem de hipóteses declaradas.

### Passo a passo

1. Use média de outubro a dezembro de 2025.
2. Projete janeiro a março de 2026 como simulação retrospectiva.
3. Construa 3 cenários de receita/despesa.
4. Crie gráfico comparativo por cenário.

### Prompt para o Copilot

```text
A partir de TblFinanceiro, calcule a média mensal de receitas e despesas de outubro a dezembro de 2025. Projete janeiro, fevereiro e março de 2026 como exercício hipotético, com cenários: Base = médias constantes; Otimista = receitas 10% maiores e despesas 5% menores; Conservador = receitas 10% menores e despesas 5% maiores. Use saldo inicial simulado de R$ 100.000 no primeiro mês, fórmulas ligadas a uma tabela de premissas e gráfico de linhas dos saldos finais. Diferencie explicitamente hipótese de previsão comprovada.
```

### Conferência / aceite

As datas projetadas são futuras em relação ao ano-base 2025, não eventos atuais de 2026.

### Desafio extra

Teste sensibilidade a 20% de queda de receita.

**Entrega do aluno:** Tabela de premissas, 3 cenários e gráfico


## Exercício 15 — Segmentações interativas e gráficos dinâmicos

**Tempo estimado:** 8 min  
**Abas:** `Financeiro, Orçamento`  
**Conceito:** Filtros devem refletir as mesmas bases e períodos.

### Passo a passo

1. Crie tabela dinâmica mensal de despesas por departamento.
2. Insira segmentador para Departamento e filtro de Mês.
3. Crie gráfico dinâmico vinculado.
4. Teste alternância entre TI e RH.

### Prompt para o Copilot

```text
Oriente a criação de Tabela Dinâmica com TblFinanceiro, filtro Tipo="Despesa", linhas=Mês, colunas=Departamento, valores=Soma Valor (R$). Crie um Gráfico Dinâmico e segmentador de Departamento; se possível, conecte os controles à tabela dinâmica correta. Demonstre o efeito de selecionar apenas TI e depois apenas RH. Não afirme que o segmentador filtra TblOrcamento se não houver modelo de dados/relacionamento configurado.
```

### Conferência / aceite

Verifique que totais mudam conforme filtro e voltam ao selecionar Tudo.

### Desafio extra

Crie uma segunda visualização para selecionar Categoria.

**Entrega do aluno:** Gráfico dinâmico e segmentador


## Exercício 16 — Dashboard executivo em cinco indicadores

**Tempo estimado:** 10 min  
**Abas:** `Financeiro, Orçamento, Ativos, Dashboard`  
**Conceito:** Dashboard rastreável, não uma imagem estática.

### Passo a passo

1. Crie tabela auxiliar na área abaixo do painel ou nova aba de apoio.
2. Preencha quatro cartões já previstos sem apagar cabeçalhos.
3. Acrescente um quinto KPI de quantidade de ativos.
4. Construa dois gráficos e valide bases.

### Prompt para o Copilot

```text
Construa na aba Dashboard, mantendo o cabeçalho existente, um painel com KPIs: Receitas de 2025 (somente Tipo="Receita"), Despesas de 2025 (somente Tipo="Despesa"), Saldo operacional do período (Receitas menos Despesas), Desvio total do orçamento (Soma Realizado menos Soma Orçado em TblOrcamento) e Qtde de ativos (contagem de Patrimônio em TblAtivos). Use fórmulas editáveis e rastreáveis, crie gráfico mensal de receitas/despesas e barras de desvio por departamento. Não invente dado de caixa bancário e evite gráficos que sobreponham áreas existentes.
```

### Conferência / aceite

Ativos=100; orçamento não inclui receitas; faça validação com tabelas de origem.

### Desafio extra

Adicione legenda de data-base e alertas condicionais.

**Entrega do aluno:** Dashboard v1 editável


## Exercício 17 — Dashboard com matriz de risco e drill-down

**Tempo estimado:** 10 min  
**Abas:** `Fornecedores, Ativos, Dashboard`  
**Conceito:** Da visão geral ao registro que originou o alerta.

### Passo a passo

1. Construa visão por garantias e contratos.
2. Crie tabelas de suporte com identificadores.
3. Adicione gráficos de barras para prioridade e vencimento.
4. Teste filtro e rastreabilidade.

### Prompt para o Copilot

```text
Amplie Dashboard com uma seção "Riscos operacionais". Usando TblAtivos e TblFornecedores, crie indicadores de garantia vencida e contratos vencidos na data-base 28/10/2026. Exiba dois gráficos de barras e tabelas auxiliares com Patrimônio ou Contrato que permitam conferir a origem de cada contagem. Prefira tabela dinâmica editável com filtros a figuras estáticas. Não misture a situação cadastral com uma avaliação jurídica do contrato.
```

### Conferência / aceite

Cada indicador precisa ter lista de registros subjacentes verificável.

### Desafio extra

Classifique riscos pelo número de itens e não por uma pontuação inventada.

**Entrega do aluno:** Dashboard v2 de riscos


## Exercício 18 — Análise de sensibilidade: metas e limites

**Tempo estimado:** 8 min  
**Abas:** `Orçamento, Financeiro`  
**Conceito:** Quantificar impacto de hipóteses e achar ponto de equilíbrio.

### Passo a passo

1. Crie parâmetros de economia percentuais.
2. Calcule resultado sobre despesas totais.
3. Faça tabela de sensibilidade 0%, 5%, 10%, 15%.
4. Compare com saldo operacional.

### Prompt para o Copilot

```text
Com base nas despesas totais de 2025 em TblFinanceiro, crie uma tabela de sensibilidade para reduções SIMULADAS de custos de 0%, 5%, 10% e 15%, mantendo receitas constantes. Calcule despesas ajustadas e saldo operacional em cada cenário. Mostre em gráfico de colunas e calcule qual redução seria necessária para atingir saldo operacional-alvo de R$ 500.000, se for matematicamente possível. Não altere a origem e registre as hipóteses.
```

### Conferência / aceite

Nunca aplicar percentual duas vezes e manter unidade/escopo do ano.

### Desafio extra

Faça o inverso: receita -10%, despesas constantes.

**Entrega do aluno:** Tabela de sensibilidade


## Exercício 19 — Resumo executivo baseado em indicadores

**Tempo estimado:** 7 min  
**Abas:** `Dashboard`  
**Conceito:** Comunicar decisões sem inventar explicações.

### Passo a passo

1. Revise KPIs do Dashboard.
2. Peça resumo com evidências numéricas.
3. Marque hipóteses e pendências.
4. Compare texto com números e gráficos.

### Prompt para o Copilot

```text
Utilize apenas os indicadores calculados e conferidos da aba Dashboard. Escreva um resumo executivo de até 180 palavras para diretoria com: três fatos numéricos, dois riscos/alertas, duas recomendações, respectivas fontes de dados e uma nota sobre limites da amostra. Separe claramente "Dado observado", "Hipótese" e "Recomendação". Não atribua causalidade nem responsáveis inexistentes.
```

### Conferência / aceite

Todos os números devem ser rastreáveis a células ou tabelas de apoio.

### Desafio extra

Refaça o texto para público técnico, sem mudar números.

**Entrega do aluno:** Nota executiva validada


## Exercício 20 — Auditoria final: reconciliação de painel e pivôs

**Tempo estimado:** 10 min  
**Abas:** `Todas`  
**Conceito:** A qualidade da resposta importa mais que a estética.

### Passo a passo

1. Compare KPI com somatório de origem.
2. Recalcule amostra independente com SOMASES.
3. Revise filtros e parâmetros das tabelas dinâmicas.
4. Registre inconsistências e correções.

### Prompt para o Copilot

```text
Atue como auditor do laboratório. Verifique Dashboard e tabelas dinâmicas contra TblFinanceiro, TblOrcamento, TblAtivos e TblFornecedores. Teste: total receitas, total despesas, receitas-despesas, desvio orçamentário total, 100 patrimônios, ausência de dupla contagem, recorte temporal, filtros Tipo e premissas simuladas. Produza quadro "Indicador | Fonte | Regra | Valor reportado | Valor recalculado | Conforme? | Ação". Não corrija silenciosamente; solicite confirmação antes de alterações.
```

### Conferência / aceite

Um painel bonito pode estar incorreto se usar médias ou filtros errados.

### Desafio extra

Troque deliberadamente um filtro e peça ao colega localizar o erro.

**Entrega do aluno:** Checklist de auditoria


---

## Encerramento e entrega final

A entrega de cada participante deve incluir uma cópia da pasta de trabalho com pelo menos **duas tabelas dinâmicas, três gráficos, dois painéis de dashboard e um resumo executivo**, acompanhada de uma breve nota sobre critérios, data-base, filtros, fórmulas e limitações. Para reproduzir o laboratório, mantenha o arquivo original preservado.

### Cuidados com o Microsoft 365 Copilot

A funcionalidade de editar a pasta de trabalho, criar gráficos ou construir tabelas dinâmicas pode variar por licença, aplicativo, atualização e configuração. Um prompt é uma **instrução solicitada**, não evidência de que o Excel criou corretamente o objeto. Verifique cada objeto inserido, as fórmulas, os filtros e a fonte dos dados. Se necessário, solicite ao Copilot **o procedimento detalhado** e conclua a operação manualmente.

### Publicação no GitHub

```text
m365-copilot-excel-lab/
├── README.md                           # guia introdutório (14 exercícios)
├── GUIA_AVANCADO_20_EXERCICIOS.md     # este arquivo
├── 20_Prompts_Avancados_M365_Copilot_Excel.txt
├── Laboratorio_M365_Copilot_Excel_Contoso.xlsx
└── instrutor/
    └── GABARITO_Avancado_20_Exercicios.txt
```

> **Dica:** mantenha o gabarito fora da pasta distribuída aos alunos se desejar preservar a dinâmica de descoberta.
