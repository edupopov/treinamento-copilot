# Laboratório prático — Microsoft 365 Copilot no Excel

> **Trilha 2 | Análise de dados com linguagem natural**  
> **Cenário:** Contoso Brasil (empresa fictícia)  
> **Material:** [`Laboratorio_M365_Copilot_Excel_Contoso.xlsx`](./Laboratorio_M365_Copilot_Excel_Contoso.xlsx)  
> **Nível:** básico a intermediário, com desafios avançados  
> **Duração:** versão essencial de 60 minutos ou laboratório completo de aproximadamente 2 horas

## 1. Objetivo da capacitação

Ao final, o participante deverá conseguir **entender tabelas desconhecidas, explicar fórmulas, criar indicadores, identificar desvios, investigar indícios de duplicidade, analisar tendências, simular cenários e apresentar conclusões em um painel executivo**, usando o Copilot como apoio e **checando os resultados no Excel**.

Não é necessário decorar fórmulas para começar. É necessário saber formular perguntas, reconhecer limitações dos dados e validar resultados.

> **Aviso:** todos os dados são sintéticos e os alertas foram inseridos para fins didáticos. Uma aparente duplicidade não comprova pagamento indevido; uma anomalia não comprova fraude.

## 2. Preparação do ambiente

### Requisitos

- Conta com licença e permissões adequadas para **Microsoft 365 Copilot no Excel**.
- Excel atualizado (Web ou aplicativo compatível), com acesso ao Copilot habilitado pelo administrador.
- Uma **cópia de trabalho** da planilha, preferencialmente salva no **OneDrive ou SharePoint**, quando exigido pela experiência do Copilot utilizada.
- Permissão de edição; arquivos de exemplo e fórmulas devem ser testados antes da aula.
- Ambiente corporativo com política de tratamento de dados respeitada. **Não cole informações confidenciais em ferramentas não aprovadas.**

### Passo a passo inicial

1. Baixe o arquivo `.xlsx` e salve uma **cópia por participante** (por exemplo, `Contoso_Aluno_01.xlsx`).
2. Abra-o no Excel e confirme que existem cinco abas: `Financeiro`, `Orçamento`, `Ativos`, `Fornecedores` e `Dashboard`.
3. Verifique a presença do botão ou painel **Copilot**. A posição e os comandos mudam conforme a versão e os recursos habilitados.
4. Verifique se as quatro primeiras abas contêm **tabelas estruturadas** com filtros.
5. Faça um teste simples: `Quais são as colunas da tabela da aba Financeiro?`.
6. Se o Copilot não conseguir editar ou gerar objetos no arquivo, use-o para **propor a fórmula ou o procedimento** e execute no Excel. **Não afirme que uma alteração ocorreu sem verificá-la.**
7. Preserve um arquivo original sem modificações para restaurar a atividade caso necessário.

### Estrutura real da planilha

| Aba | Registros | Tabela estruturada | Campos principais |
|---|---:|---|---|
| `Financeiro` | 216 | `TblFinanceiro` | `ID`, `Data`, `Mês`, `Tipo`, `Departamento`, `Categoria`, `Contraparte`, `Documento`, `Valor (R$)`, `Status`, `Descrição` |
| `Orçamento` | 96 | `TblOrcamento` | `ID`, `Competência`, `Mês`, `Departamento`, `Orçado (R$)`, `Realizado (R$)`, `Desvio (R$)`, `Desvio (%)`, `Status` |
| `Ativos` | 100 | `TblAtivos` | `Patrimônio`, `Tipo`, `Fabricante`, `Modelo`, `Departamento`, `Unidade`, `Aquisição`, `Fim garantia`, `Valor (R$)`, `Vida útil (anos)`, `Situação` |
| `Fornecedores` | 48 | `TblFornecedores` | `Contrato`, `Fornecedor`, `Serviço`, `Departamento`, `Início`, `Vencimento`, `Pagamento`, `Valor pago (R$)`, `Nota fiscal`, `Situação`, `Periodicidade` |
| `Dashboard` | Área preparada | — | Indicadores e espaços para análise dos alunos |

**Período de referência:** lançamentos e orçamento de **janeiro a dezembro de 2025**. Datas de aquisição e contratos podem pertencer a outros anos. A aba `Dashboard` tem blocos e títulos, mas **não traz indicadores já calculados**.

**Atenção à modelagem:** cada mês tem 18 registros na aba Financeiro (6 receitas e 12 despesas), para 216 registros anuais. O orçamento contém 8 departamentos por mês, para 96 linhas. Em `Orçamento`, a coluna `Realizado (R$)` contém fórmulas `SUMIFS` referenciando lançamentos **do tipo `Despesa`**, e as colunas `Desvio (R$)` e `Desvio (%)` derivam desse resultado. **Não some receitas e despesas indiscriminadamente para validar o orçamento.**

## 3. Planejamento de tempo

### Versão essencial — 60 minutos

| Tempo | Atividade |
|---:|---|
| 5 min | Preparação e orientação de validação |
| 8 min | Exercício 1 — Explorar e explicar a planilha |
| 10 min | Exercícios 2 e 3 — Fórmulas e orçamento |
| 10 min | Exercício 4 — Tendências e gráficos |
| 10 min | Exercício 7 — Duplicidades e anomalias |
| 12 min | Exercícios 9 e 11 — Projeções e dashboard |
| 5 min | Discussão e conclusão |

### Versão estendida — 120 minutos

| Tempo | Atividade |
|---:|---|
| 10 min | Preparação, contexto, boas práticas de prompts |
| 50 min | Exercícios 1 a 6 — Diagnóstico financeiro e orçamento |
| 25 min | Exercícios 7 e 8 — Fornecedores e contratos |
| 20 min | Exercícios 9 e 10 — Cenários e ativos |
| 10 min | Exercícios 11 e 12 — Dashboard e comunicação executiva |
| 5 min | Avaliação e próximos passos |

Os exercícios 13 e 14 são **bônus** ou atividades posteriores à aula.

## 4. Técnica de prompting usada no laboratório

Estruture solicitações com cinco partes:

1. **Contexto:** qual aba/tabela estamos analisando?
2. **Objetivo:** qual pergunta de negócio será respondida?
3. **Método:** cálculos, filtros e condições desejados.
4. **Formato:** tabela, texto curto, fórmula, gráfico ou nova coluna.
5. **Verificação:** mostrar origem, premissas e incertezas; não inventar dados.

**Exemplo básico:** `Analise as despesas de 2025.`

**Exemplo mais eficaz:**

```text
Na tabela TblFinanceiro, considere apenas os registros com Tipo = "Despesa"
e datas de 2025. Agrupe os valores por Mês, identifique os três meses com
maiores totais e mostre a participação de cada Categoria. Entregue uma
tabela e um gráfico de linhas. Mostre os critérios usados, não invente
causas e destaque limitações da análise.
```

---

# 5. Roteiro dos exercícios

## Exercício 1 — Decifrando uma planilha desconhecida

**Tempo:** 8 minutos  
**Aba:** `Financeiro`  
**Objetivo:** compreender a estrutura antes de analisar os valores.

**Situação:** você recebeu um arquivo sem documentação de um colega da área financeira.

### Execução

1. Abra a aba `Financeiro`.
2. Observe as colunas `Tipo`, `Categoria`, `Departamento`, `Documento` e `Valor (R$)`.
3. Abra o Copilot e envie o prompt abaixo.
4. Compare as definições produzidas com 5 linhas reais da tabela.
5. Peça uma segunda resposta dirigida a um gestor não técnico.

**Prompt:**

```text
Explique a estrutura da tabela TblFinanceiro. Descreva a função de cada
coluna e diferencie receitas de despesas. Informe quantos registros existem,
qual período está representado e quais indicadores é possível calcular.
Resuma tudo em linguagem executiva, sem presumir o significado de campos
além do que os dados permitem confirmar.
```

**Resultado esperado:** reconhecimento de 216 linhas de dados, ano de 2025, distinção entre `Receita` e `Despesa` e uma lista de indicadores viáveis.

**Validação:** filtre `Tipo` e confira os registros; verifique se a IA não confundiu `Documento` com o identificador `ID`.

**Desafio extra:** `Quais perguntas de negócio esta tabela não permite responder com segurança?`

---

## Exercício 2 — Explicando fórmulas existentes

**Tempo:** 5 minutos  
**Aba:** `Orçamento`  
**Objetivo:** compreender referências entre abas e calcular desvios.

### Execução

1. Abra `Orçamento` e selecione a célula `F2`.
2. Examine a fórmula na barra de fórmulas.
3. Faça o Copilot explicar a lógica e os critérios de soma.
4. Repita para `G2` e `H2`.
5. Verifique por que a fórmula percentual trata o caso de orçamento zero.

**Prompt:**

```text
Explique as fórmulas de Orçamento!F2, G2 e H2, uma de cada vez.
Identifique o que é somado, a origem dos dados, os filtros aplicados
e o tratamento de divisão por zero. Dê um exemplo numérico e explique
por que um desvio percentual positivo representa estouro de orçamento.
```

**Conhecimento-chave:** `F = soma de despesas do mês e departamento`; `G = Realizado − Orçado`; `H = G / Orçado`, com tratamento quando o orçamento é zero.

**Validação:** selecione uma linha da aba `Orçamento` e confira, usando filtros na aba `Financeiro`, as despesas correspondentes ao mês e departamento.

**Desafio extra:** pedir uma alternativa com referências estruturadas, verificando se a fórmula sugerida é compatível com a tabela existente.

---

## Exercício 3 — Criando alertas de orçamento

**Tempo:** 5 minutos  
**Aba:** `Orçamento`  
**Objetivo:** destacar desvios e priorizar departamentos.

### Execução

1. Observe as colunas `G` e `H` da aba `Orçamento`.
2. Filtre `Desvio (%)` para localizar valores superiores a 10%.
3. Solicite ao Copilot uma tabela-resumo por departamento.
4. Se o recurso permitir, aplique ou ajuste a formatação condicional.
5. Crie uma lista de até três departamentos que exigem atenção.

**Prompt:**

```text
Na tabela TblOrcamento, identifique as linhas em que Desvio (%) é maior
que 10%. Agrupe por Departamento e apresente a soma dos valores Orçado
e Realizado, o desvio em reais e o desvio percentual agregado, calculado
sobre os totais. Destaque quais departamentos merecem investigação.
Não faça média simples dos percentuais mensais para calcular o desvio anual.
```

**Validação:** o percentual anual correto é `(soma do Realizado − soma do Orçado) / soma do Orçado`.

**Desafio extra:** criar uma classificação com as categorias `Dentro do orçamento`, `Atenção (até 10%)` e `Crítico (acima de 10%)`, esclarecendo o que acontece com percentuais negativos.

---

## Exercício 4 — Tendências financeiras e visualização

**Tempo:** 10 minutos  
**Aba:** `Financeiro`  
**Objetivo:** identificar evolução mensal sem confundir flutuação e causa.

### Execução

1. Solicite o total de receitas e de despesas por mês.
2. Peça uma terceira série com o **saldo mensal** (`Receitas − Despesas`).
3. Solicite um gráfico de linhas com as três séries.
4. Identifique a maior e a menor despesa mensal.
5. Investigue quais categorias contribuíram mais para os aumentos.

**Prompt:**

```text
Com base em TblFinanceiro, agrupe os valores por Mês e Tipo.
Calcule receitas, despesas e saldo mensal (receitas menos despesas)
para janeiro a dezembro de 2025. Apresente uma tabela com 12 linhas
e um gráfico de linhas. Identifique os três meses de maior despesa
e investigue as categorias que contribuíram para a variação mensal.
Não atribua causas sem evidências dos lançamentos.
```

**Validação:** confira um mês manualmente aplicando filtros em `Mês` e `Tipo`. Um gráfico pode ser informativo mesmo sem conclusões causais.

**Desafio extra:** calcular a variação percentual de despesas entre meses consecutivos; definir explicitamente como tratar o primeiro mês.

---

## Exercício 5 — Análise Pareto: onde estão os gastos?

**Tempo:** 8 minutos  
**Aba:** `Financeiro`  
**Objetivo:** concentrar a análise nas categorias que mais pesam no total.

### Execução

1. Filtre somente `Despesa`.
2. Agrupe os valores por `Categoria`.
3. Classifique em ordem decrescente de valor.
4. Peça o percentual acumulado das categorias.
5. Construa um gráfico de barras com as seis maiores categorias.

**Prompt:**

```text
Na tabela TblFinanceiro, considere apenas Tipo = "Despesa".
Some Valor (R$) por Categoria em 2025, ordene do maior para o menor
e calcule participação percentual e percentual acumulado.
Identifique quais categorias respondem por aproximadamente 80%
das despesas. Crie um gráfico de barras das seis maiores categorias.
```

**Validação:** a soma das categorias deve corresponder ao total de despesas do período.

**Desafio extra:** repetir por `Departamento` e comparar se a concentração é semelhante.

---

## Exercício 6 — Orçamento: ranking e recomendações

**Tempo:** 12 minutos  
**Abas:** `Orçamento` e `Financeiro`  
**Objetivo:** passar de números para hipóteses investigáveis.

### Execução

1. Agrupe o orçamento por departamento no ano.
2. Calcule o desvio acumulado em R$ e em %.
3. Selecione os três maiores estouros absolutos.
4. Localize, em `Financeiro`, as categorias de despesas desses departamentos.
5. Produza recomendações, separando **evidência** e **hipótese**.

**Prompt:**

```text
Analise TblOrcamento de 2025 por Departamento, calculando totais
anuais Orçado e Realizado, além de desvio absoluto e percentual.
Escolha os três maiores desvios positivos em reais. Para esses
departamentos, examine em TblFinanceiro quais categorias e meses
concentraram as despesas. Crie uma tabela com: departamento,
evidência numérica, possível explicação a investigar e ação recomendada.
Identifique as recomendações como hipóteses, não como fatos confirmados.
```

**Validação:** reconciliar o valor realizado agregado com os lançamentos `Tipo = Despesa`.

**Desafio extra:** comparar desvios percentuais e absolutos e explicar por que os rankings podem ser diferentes.

---

## Exercício 7 — Caça aos pagamentos possivelmente duplicados

**Tempo:** 10 minutos  
**Abas:** `Financeiro` e `Fornecedores`  
**Objetivo:** identificar padrões suspeitos com critério explícito.

### Execução

1. Na aba `Financeiro`, procure documentos repetidos **somente entre despesas**.
2. Apresente os lançamentos correspondentes, incluindo `ID`, `Documento`, `Valor (R$)`, `Data` e `Contraparte`.
3. Na aba `Fornecedores`, procure `Nota fiscal` repetida.
4. Separe os casos em `Possível duplicidade` e `Requer esclarecimento`.
5. **Não exclua lançamentos** nem conclua que houve pagamento indevido.

**Prompt:**

```text
Investigue possíveis duplicidades em duas tabelas:
1) em TblFinanceiro, apenas registros de Despesa, agrupando por Documento;
2) em TblFornecedores, agrupando por Nota fiscal.
Liste todos os grupos com mais de uma ocorrência e suas linhas originais.
Compare valores, datas, fornecedor/contraparte e contrato, quando houver.
Use o termo "possível duplicidade", indique conflitos e não exclua dados.
```

**Validação:** confirme os documentos duplicados com o filtro de coluna do Excel. **Repetir uma nota com contraparte distinta exige investigação**, não uma deduplicação automática.

**Desafio extra:** criar uma regra de sinalização que combine `documento + valor + contraparte`, discutindo falsos positivos e falsos negativos.

---

## Exercício 8 — Contratos vencidos e concentração de fornecedores

**Tempo:** 15 minutos  
**Aba:** `Fornecedores`  
**Objetivo:** levantar riscos contratuais e de gastos recorrentes.

### Execução

1. Observe as colunas `Início`, `Vencimento`, `Pagamento`, `Situação` e `Periodicidade`.
2. Solicite uma lista de contratos vencidos em uma **data de referência explícita**, por exemplo `28/10/2026`.
3. Solicite um ranking de fornecedores por soma de `Valor pago (R$)`.
4. Procure valores atípicos e notas fiscais repetidas.
5. Discuta se `Mensal`/`Anual` permite concluir o valor total contratado (**não necessariamente**).

**Prompt:**

```text
Analise TblFornecedores tomando 28/10/2026 como data de referência.
Liste os contratos com Vencimento anterior a essa data, mostre os que
vencem nos próximos 90 dias e identifique as maiores somas de Valor pago
(R$) por Fornecedor. Sinalize notas fiscais repetidas e pagamentos
atípicos. Diferencie valor pago de valor contratado: a tabela não possui
um campo explícito para o valor total do contrato.
```

**Validação:** compare `Vencimento` com a data de referência, independentemente do texto de `Situação`; nunca deduza quantidade de pagamentos futuros apenas de `Periodicidade`.

**Desafio extra:** criar uma coluna de `Dias até o vencimento` com uma data de referência fixa em uma célula separada.

---

## Exercício 9 — Projeção de fluxo de caixa e cenários

**Tempo:** 12 minutos  
**Aba:** `Financeiro` (resultado em `Dashboard` ou em uma nova tabela)  
**Objetivo:** projetar cenários usando premissas transparentes.

**Importante:** a planilha fornece **receitas e despesas registradas**, mas **não possui saldo bancário inicial comprovado**. Portanto, a diferença acumulada entre receitas e despesas **não é automaticamente o saldo de caixa real**. Neste exercício, defina um saldo inicial hipotético de `R$ 100.000`.

### Execução

1. Calcule a média mensal de receitas e despesas em 2025.
2. Crie uma célula de entrada `Saldo inicial hipotético = 100000`.
3. Defina três cenários para os três meses seguintes ao período histórico: **jan–mar/2026**, como simulação didática retrospectiva.
4. Cenário **base**: médias mensais sem ajuste; **otimista**: receitas +10% e despesas −5%; **conservador**: receitas −10% e despesas +5%.
5. Para cada mês, calcule `Saldo final = Saldo inicial + Receitas projetadas − Despesas projetadas`, carregando o saldo final para o mês seguinte.
6. Construa gráfico comparando saldos finais dos três cenários.

**Prompt:**

```text
A partir de TblFinanceiro, calcule a média mensal de receitas e despesas
em 2025. Simule janeiro, fevereiro e março de 2026, usando saldo inicial
HIPOTÉTICO de R$ 100.000. Crie cenários: base = médias sem alteração;
otimista = receitas 10% maiores e despesas 5% menores;
conservador = receitas 10% menores e despesas 5% maiores.
Calcule saldo inicial e final a cada mês e faça um gráfico comparativo.
Mostre fórmulas, premissas e destaque que esta não é uma previsão validada
nem corresponde necessariamente ao saldo bancário real.
```

**Validação:** conferir se o saldo final de um mês é exatamente o inicial do próximo. Aplique os percentuais aos componentes **receitas e despesas**, não ao saldo final.

**Desafio extra:** alterar a hipótese de saldo inicial para `R$ 50.000` e comparar o risco de saldo negativo.

---

## Exercício 10 — Inventário, vida útil e garantias

**Tempo:** 8 minutos  
**Aba:** `Ativos`  
**Objetivo:** priorizar renovação de notebooks e servidores.

### Execução

1. Conte os equipamentos por `Tipo`, `Fabricante` e `Departamento`.
2. Use como referência **28/10/2026**, evitando que os resultados mudem conforme o dia da aula.
3. Identifique garantias encerradas (`Fim garantia` anterior à referência).
4. Calcule idade aproximada desde `Aquisição` e compare com `Vida útil (anos)`.
5. Classifique os equipamentos por urgência e explique os critérios.

**Prompt:**

```text
Analise TblAtivos com data de referência 28/10/2026.
Conte ativos por Tipo, Fabricante e Departamento. Identifique:
(a) equipamentos com Fim garantia antes da referência;
(b) equipamentos cuja idade supera a Vida útil (anos);
(c) equipamentos que atendem aos dois critérios.
Mostre Patrimônio, Tipo, Departamento, Aquisição, Fim garantia e Valor (R$).
Crie um ranking de prioridades e explicite os critérios; não use o valor
de aquisição como se fosse o custo atual de reposição.
```

**Validação:** compare datas de aquisição e vencimento. `Valor (R$)` representa um valor registrado, não um preço de compra atual de item equivalente.

**Desafio extra:** solicitar o percentual de ativos fora da garantia **por tipo** e construir um gráfico de barras.

---

## Exercício 11 — Construindo um dashboard executivo

**Tempo:** 10 minutos  
**Aba:** `Dashboard`  
**Objetivo:** transformar análises em uma página de acompanhamento.

### Execução

1. Acesse a aba `Dashboard`, que já tem títulos e áreas reservadas.
2. Peça fórmulas para os quatro indicadores no topo: `RECEITAS 2025`, `DESPESAS 2025`, `SALDO DO PERÍODO` e `DESVIO ORÇAMENTÁRIO`.
3. Defina **saldo do período** como `Receitas − Despesas` de 2025, **não** saldo bancário final.
4. Defina **desvio orçamentário** como `Total Realizado − Total Orçado`, com total referente apenas às despesas.
5. Insira um gráfico mensal de receitas e despesas, um gráfico de desvios por departamento e um gráfico de garantias vencidas por tipo.
6. Verifique se os gráficos são editáveis e se os números batem com as tabelas de origem.

**Prompt:**

```text
Ajude a preencher a aba Dashboard usando dados das tabelas existentes.
Indicadores: receitas de 2025 (TblFinanceiro, Tipo=Receita), despesas
de 2025 (Tipo=Despesa), saldo do período = receitas - despesas,
e desvio orçamentário agregado = soma(Realizado) - soma(Orçado)
da TblOrcamento. Crie fórmulas editáveis e gráficos para a evolução
mensal, desvio por departamento e garantias vencidas por Tipo.
Preserve as abas originais e mostre a origem de cada indicador.
Se não for possível editar diretamente, proponha os passos exatos.
```

**Validação:** os totais do Dashboard devem ser iguais aos totais filtrados das tabelas. Para evitar dupla contagem, **não some o valor realizado do orçamento às despesas do Financeiro** — são duas visões da mesma despesa.

**Desafio extra:** adicionar filtros por departamento e período, se a modalidade do Excel utilizada permitir segmentações.

---

## Exercício 12 — Comunicação executiva baseada em evidências

**Tempo:** 5 minutos  
**Abas:** todas  
**Objetivo:** criar uma síntese para a diretoria sem extrapolar os dados.

### Execução

1. Reúna os três maiores achados verificados nos exercícios anteriores.
2. Separe cada item entre **fato observado**, **hipótese** e **próxima ação**.
3. Solicite um resumo em até 150 palavras.
4. Confirme números e referências antes de enviar o texto.

**Prompt:**

```text
Prepare um resumo executivo de até 150 palavras sobre a Contoso Brasil.
Use somente informações verificáveis nas abas Financeiro, Orçamento,
Ativos e Fornecedores. Inclua três achados, duas recomendações e uma
limitação dos dados. Para cada conclusão numérica, informe a aba e o
critério de cálculo. Separe fatos de hipóteses e não afirme existência
de fraude ou de saldo bancário sem comprovação.
```

**Resultado esperado:** uma mensagem curta que um gestor conseguiria revisar e utilizar como ponto de partida.

---

## Exercício 13 (bônus) — Engenharia de prompts: ambiguidade e precisão

**Tempo:** 10 minutos  
**Objetivo:** comparar uma solicitação vaga com uma instrução verificável.

1. Faça o pedido: `Quais são os principais problemas da empresa?`.
2. Anote afirmações vagas, inferências e eventuais números não explicados.
3. Faça o pedido aprimorado abaixo.
4. Compare utilidade e confiabilidade das respostas.

```text
Identifique até cinco pontos de atenção no conjunto de dados da Contoso.
Para cada ponto, apresente: aba, campos consultados, filtro utilizado,
cálculo realizado, evidência observada, incerteza e sugestão de validação.
Não classifique exceções como erro ou fraude sem comprovação.
```

**Discussão:** o que mudou quando foram exigidos evidência, filtros, cálculos e incerteza?

---

## Exercício 14 (bônus) — Auditoria dos resultados da própria IA

**Tempo:** 10 minutos  
**Objetivo:** estabelecer um processo de verificação independente.

1. Escolha três números fornecidos pelo Copilot (por exemplo, despesas de um mês, desvio de um departamento e quantidade de garantias vencidas).
2. Recalcule cada um usando filtros, funções `SOMASES`/`SUMIFS`, `CONT.SES`/`COUNTIFS` ou tabela dinâmica.
3. Registre se a IA usou filtros e períodos corretos.
4. Caso encontre divergência, reformule o prompt e documente a correção.

```text
Audite suas três afirmações numéricas mais importantes. Para cada uma,
mostre a tabela de origem, os filtros, a fórmula ou procedimento de
reprodução e os riscos de dupla contagem. Se não puder verificar um
resultado, marque-o como não confirmado.
```

---

# 6. Fórmulas úteis para validar sem o Copilot

> As fórmulas abaixo usam **nomes de funções em inglês**, como as expressões armazenadas na planilha. No Excel configurado em pt-BR, nomes e separadores podem ser localizados (`SOMASES`, `SE`, `;`). Use a sintaxe aceita pela sua instalação.

### Receitas e despesas de 2025

```excel
=SUMIFS(Financeiro!$I$2:$I$217,Financeiro!$D$2:$D$217,"Receita")
=SUMIFS(Financeiro!$I$2:$I$217,Financeiro!$D$2:$D$217,"Despesa")
```

### Conferência do realizado por mês/departamento

A fórmula de `Orçamento!F2` deve seguir o mesmo padrão:

```excel
=SUMIFS(Financeiro!$I$2:$I$217,Financeiro!$C$2:$C$217,C2,Financeiro!$E$2:$E$217,D2,Financeiro!$D$2:$D$217,"Despesa")
```

### Desvios

```excel
=F2-E2
=IF(E2=0,0,G2/E2)
```

### Verificação de chaves repetidas

Em uma **coluna auxiliar** da aba Financeiro, se permitido:

```excel
=COUNTIF($H$2:$H$217,H2)
```

Esse cálculo sinaliza documentos repetidos, **mas não prova duplicidade de pagamento**.

### Conferência de contrato vencido em data fixa

```excel
=IF(F2<DATE(2026,10,28),"Vencido na referência","Não vencido na referência")
```

> **Cuidado:** não substitua sem necessidade fórmulas que já existem na aba `Orçamento`. Utilize cópias ou colunas auxiliares.

---

# 7. Critérios de avaliação dos participantes

| Critério | Pontuação |
|---|---:|
| Aplicação correta dos filtros, períodos e condições | 25 |
| Cálculos corretos e evidências reproduzíveis | 30 |
| Capacidade de identificar desvios e fazer perguntas relevantes | 20 |
| Clareza dos gráficos e do resumo executivo | 15 |
| Reconhecimento dos limites dos dados e da IA | 10 |
| **Total** | **100** |

**Entrega sugerida:** uma cópia da pasta de trabalho contendo análises, gráficos, indicadores e, em uma nota ou célula, os prompts utilizados. O professor avalia **a verificação do resultado**, não apenas a qualidade da redação do prompt.

# 8. Perguntas para debate

- Por que um aumento de despesa não representa necessariamente desperdício?
- Qual a diferença entre valor pago, custo contratado e orçamento autorizado?
- Quando duas linhas com a mesma nota fiscal são realmente duplicadas?
- Por que a média simples de percentuais de desvio pode estar errada?
- Um gráfico visualmente correto garante que a métrica está correta?
- O que muda na análise quando utilizamos uma data de referência diferente?
- Como distinguir o resultado histórico de uma simulação financeira?
- Quais informações não devem ser enviadas a ferramentas de IA sem autorização?

---

# 9. Guia reservado ao instrutor — pistas e verificações

> **Spoilers didáticos:** não apresente esta seção aos participantes antes do encerramento. Ela identifica situações intencionais e verificações úteis; não substitui a conferência diretamente no Excel.

### Eventos inseridos deliberadamente na base

1. **Financeiro — duplicidade de documento:** há dois registros de despesa em **julho/2025** com `Documento = NF-2025-77881` e `Valor (R$) = 12.980,00`. Verifique as respectivas contrapartes antes de falar em duplicidade de pagamento.
2. **Financeiro — valor atípico:** um lançamento de despesa em **outubro/2025** foi ajustado para **R$ 84.500,00**. A análise deve evidenciar o registro e comparar seu contexto.
3. **Financeiro — tendência:** a geração dos dados incluiu crescimento gradual das receitas e **crescimento proporcionalmente maior nas despesas** ao longo de 2025, mais elevações pontuais em meses e departamentos específicos. A conclusão deve ser sustentada por somas mensais reais, não apenas pela intenção da modelagem.
4. **Orçamento — pressão sobre gastos:** os departamentos **TI** e **Marketing** receberam premissas de orçamento com maior propensão a desvio positivo de maio a dezembro de 2025; a atividade deve localizar os casos efetivos pela coluna `Desvio (%)`.
5. **Fornecedores — nota fiscal repetida:** existe repetição de `NF-FOR-0008` em dois contratos, incluindo o contrato **CTR-0026**. Verifique se o mesmo fornecedor está presente e discuta os limites do critério.
6. **Fornecedores — valor atípico:** um registro apresenta `Valor pago (R$) = 98.750,00`, associado ao **CTR-0040**.
7. **Fornecedores — contratos:** existem vencimentos anteriores a 28/10/2026; a avaliação deve considerar a coluna de data, não somente o texto `Situação`.
8. **Ativos — renovação:** há aquisições de **2017 a 2026**, garantias de diferentes prazos e campos de vida útil de 5 ou 7 anos, conforme o tipo de equipamento.

### Limitações relevantes que os alunos devem perceber

- Os lançamentos de `Financeiro` são **fictícios e sintéticos**, com 18 registros mensais predefinidos; não representam o plano de contas completo de uma empresa real.
- A aba `Fornecedores` possui registros de pagamento, mas não apresenta valor contratual total, saldo de contrato ou comprovantes financeiros.
- Não há **saldo bancário inicial real** nem data de liquidação de caixa suficiente para uma conciliação financeira verdadeira.
- A coluna `Status` de `Financeiro` apresenta lançamentos confirmados, mas isso não prova conciliação bancária.
- A coluna `Situação` dos contratos foi preparada a partir de uma data de referência e pode divergir de análises feitas com outra data.
- O valor dos ativos não deve ser tratado automaticamente como custo de reposição ou valor contábil depreciado.
- O campo `Mês` é numérico (1–12). **O ano de referência financeiro é 2025**; não misture com anos de aquisição ou início de contratos.
- A coluna `Realizado (R$)` de `Orçamento` soma despesas de `Financeiro`; agregar ambas como se fossem conjuntos independentes gera **dupla contagem**.

### Checklist de validação antes da apresentação

- [ ] O Excel abre o `.xlsx` sem aviso de reparo.
- [ ] As cinco abas aparecem e os filtros funcionam.
- [ ] As fórmulas de `Orçamento!F2:H97` produzem valores coerentes.
- [ ] A experiência do Copilot escolhida consegue ler a(s) tabela(s) necessária(s).
- [ ] A demonstração de edição e gráficos foi testada no tenant do instrutor.
- [ ] Há um arquivo original para recuperação em caso de alteração acidental.
- [ ] A atividade usa somente dados sintéticos.
- [ ] O instrutor está preparado para executar ações manualmente no Excel se o Copilot apenas sugerir etapas.

---

# 10. Publicação no GitHub

Estrutura sugerida do repositório:

```text
m365-copilot-excel-lab/
├── README.md
├── dados/
│   └── Laboratorio_M365_Copilot_Excel_Contoso.xlsx
└── entregas/
    └── .gitkeep
```

Se optar por essa organização, atualize o link do arquivo no início do README para `./dados/Laboratorio_M365_Copilot_Excel_Contoso.xlsx`.

**Recomendação:** deixe o arquivo de exercício e o README públicos somente porque os dados são fictícios. Entregas dos alunos e arquivos com dados corporativos reais devem permanecer em repositórios e plataformas autorizados.

## Referências oficiais

- [Ajuda do Microsoft 365 Copilot](https://support.microsoft.com/copilot)
- [Ajuda do Excel](https://support.microsoft.com/excel)
- [Visão geral do Microsoft 365 Copilot — Microsoft Learn](https://learn.microsoft.com/copilot/microsoft-365/microsoft-365-copilot-overview)

> **Nota de compatibilidade:** os recursos do Copilot mudam com o tempo e dependem da licença, da versão do Excel, do armazenamento e das políticas de TI. Os prompts desta apostila são **instruções propostas para demonstração**; a criação automática de gráficos, fórmulas ou dashboards deve ser comprovada no ambiente utilizado.

---

**Material didático — TREINAMENTO MICROSOFT 365 COPILOT | Trilha 2: Excel.**
