# Laboratório Prático — Microsoft 365 Copilot no PowerPoint

> **Professor Eduardo Popovici**  
> Trilha de produtividade corporativa • 16 exercícios práticos • Contoso Brasil

## Apresentação

Este laboratório ensina a transformar informações empresariais em apresentações claras, visuais e verificáveis. A IA apoia a criação; a responsabilidade por fatos, decisões, cálculos e compartilhamento continua com o profissional. Todo o conteúdo da Contoso Brasil é fictício e didático.

## Arquivos do laboratório

- `CONTOSO_Apresentacao_Inicial_Copilot_PowerPoint.pptx` — apresentação inicial, propositalmente sujeita a melhorias.
- `CONTOSO_Relatorio_Acoes_Desempenho_Didatico.docx` — documento fonte criado na trilha Word.
- `16_PROMPTS_M365_COPILOT_POWERPOINT.txt` — biblioteca de prompts.
- Este guia Markdown com etapas, entregas e critérios de avaliação.

## Pré-requisitos e preparação

1. Abrir os arquivos no Microsoft 365 com uma conta corporativa habilitada para os recursos necessários do Copilot.
2. Salvar uma **cópia de trabalho** dos arquivos em OneDrive ou SharePoint permitido pela organização e conferir permissões.
3. Abrir o PowerPoint e localizar o Copilot. A interface e os comandos podem variar entre Windows, Mac e Web.
4. Confirmar se criação a partir de arquivo, edição de slides, recursos de design e notas estão habilitados na licença e pelas políticas.
5. Sempre selecionar explicitamente o documento Word de referência ao pedir criação baseada em arquivo. O Copilot não deve ser tratado como tendo acesso automático a qualquer arquivo.
6. Manter o documento de origem ao lado da apresentação para verificação cruzada.
7. Usar dados de laboratório; não inserir dados confidenciais, pessoais ou jurídicos reais em demonstrações.

> **Disponibilidade:** criação de apresentação a partir de arquivo, criação de slides e recursos de design podem exigir recursos/licenças adicionais ou políticas específicas. Quando uma ação não aparecer no Copilot, solicite primeiro o conteúdo como texto e execute manualmente no PowerPoint, preservando o objetivo pedagógico.

## Roteiro de aula

| Formato | Tempo | Seleção |
|---|---:|---|
| Demonstração compacta | 45 min | 01, 02, 05, 06, 09, 15 |
| Workshop | 60 min | 01, 02, 04, 05, 06, 10, 15, 16 |
| Laboratório completo | 120 min | Todos os 16 exercícios em duplas, com debates |

## Orientação geral para todos os exercícios

Para cada prompt: **preparar fonte → solicitar ao Copilot → inspecionar saída → comparar com dados originais → corrigir → salvar cópia da entrega**. A resposta textual do Copilot não equivale à alteração do arquivo: confirme se o slide foi efetivamente criado ou editado.

## Exercícios

### Exercício 01 — Conhecer e resumir uma apresentação

**Arquivo-base:** Apresentação inicial.  
**Missão:** Solicite uma síntese dos slides e a identificação dos temas centrais.  
**Entrega esperada:** Resumo com referências aos slides e distinção entre fatos e propostas.

**Passo a passo**

1. Abra a apresentação inicial e crie uma cópia de trabalho.
2. Acesse o Copilot no PowerPoint; quando necessário, selecione o arquivo de referência.
3. Copie e execute o prompt abaixo. Confirme se o resultado foi inserido no slide ou apenas sugerido no chat.
4. Ajuste layout, legibilidade, ordem narrativa e fontes dos dados, sem alterar valores indiscriminadamente.
5. Valide o resultado com o arquivo original e salve sua versão.

**Prompt para copiar**

```text
Resuma a apresentação aberta em até 8 tópicos. Identifique objetivo, resultados, principais riscos e decisões efetivamente confirmadas. Para cada conclusão, informe o slide de origem. Não trate propostas como decisões aprovadas.
```

**Validação:** Compare a síntese com os slides 2, 4 e 7.

**Desafio extra:** crie uma segunda versão destinada a outro público e explique o que mudou, sem alterar os fatos.

**Critério de conclusão:** um colega deve conseguir entender o slide e localizar a evidência que sustenta as afirmações.

---

### Exercício 02 — Criar apresentação a partir do Word

**Arquivo-base:** Relatório Word.  
**Missão:** Gere rascunho a partir do documento de ações e desempenho.  
**Entrega esperada:** Rascunho editável de 7 slides com trilha de origem.

**Passo a passo**

1. Abra o relatório Word e o PowerPoint e crie uma cópia de trabalho.
2. Acesse o Copilot no PowerPoint; quando necessário, selecione o arquivo de referência.
3. Copie e execute o prompt abaixo. Confirme se o resultado foi inserido no slide ou apenas sugerido no chat.
4. Ajuste layout, legibilidade, ordem narrativa e fontes dos dados, sem alterar valores indiscriminadamente.
5. Valide o resultado com o arquivo original e salve sua versão.

**Prompt para copiar**

```text
Crie uma apresentação executiva de 7 slides com base no arquivo CONTOSO_Relatorio_Acoes_Desempenho_Didatico.docx, que vou referenciar. Público: diretoria. Estruture: contexto, metas, resultados, orçamento, riscos, plano de ação e conclusão. Preserve números e sinalize divergências de fonte em vez de escolher um valor arbitrário.
```

**Validação:** Confronte cobertura 92% versus nota de 96% e status do orçamento.

**Desafio extra:** crie uma segunda versão destinada a outro público e explique o que mudou, sem alterar os fatos.

**Critério de conclusão:** um colega deve conseguir entender o slide e localizar a evidência que sustenta as afirmações.

---

### Exercício 03 — Definir narrativa e público

**Arquivo-base:** Relatório Word + apresentação.  
**Missão:** Reorganize o argumento para reunião de 5 minutos.  
**Entrega esperada:** Roteiro sintético orientado a decisão.

**Passo a passo**

1. Abra o relatório Word e o PowerPoint e crie uma cópia de trabalho.
2. Acesse o Copilot no PowerPoint; quando necessário, selecione o arquivo de referência.
3. Copie e execute o prompt abaixo. Confirme se o resultado foi inserido no slide ou apenas sugerido no chat.
4. Ajuste layout, legibilidade, ordem narrativa e fontes dos dados, sem alterar valores indiscriminadamente.
5. Valide o resultado com o arquivo original e salve sua versão.

**Prompt para copiar**

```text
Proponha uma narrativa de 5 minutos para a diretoria a partir deste material, com mensagem-chave por slide, 3 decisões solicitadas e transições. Evite jargões e não acrescente decisões que não constem no relatório.
```

**Validação:** A contratação de consultoria foi somente proposta.

**Desafio extra:** crie uma segunda versão destinada a outro público e explique o que mudou, sem alterar os fatos.

**Critério de conclusão:** um colega deve conseguir entender o slide e localizar a evidência que sustenta as afirmações.

---

### Exercício 04 — Criar slide de resumo executivo

**Arquivo-base:** Apresentação inicial.  
**Missão:** Inserir um resumo executivo no começo.  
**Entrega esperada:** Um slide com até 4 blocos e afirmações conferíveis.

**Passo a passo**

1. Abra a apresentação inicial e crie uma cópia de trabalho.
2. Acesse o Copilot no PowerPoint; quando necessário, selecione o arquivo de referência.
3. Copie e execute o prompt abaixo. Confirme se o resultado foi inserido no slide ou apenas sugerido no chat.
4. Ajuste layout, legibilidade, ordem narrativa e fontes dos dados, sem alterar valores indiscriminadamente.
5. Valide o resultado com o arquivo original e salve sua versão.

**Prompt para copiar**

```text
Adicione um slide de resumo executivo após a capa com quatro blocos: avanço operacional, situação orçamentária, principal risco e decisão necessária. Baseie-se apenas nos dados existentes e assinale o que exige validação.
```

**Validação:** Os quatro blocos precisam ter origem identificável.

**Desafio extra:** crie uma segunda versão destinada a outro público e explique o que mudou, sem alterar os fatos.

**Critério de conclusão:** um colega deve conseguir entender o slide e localizar a evidência que sustenta as afirmações.

---

### Exercício 05 — Converter números em mensagens visuais

**Arquivo-base:** Apresentação inicial.  
**Missão:** Refaça o slide de métricas com KPIs.  
**Entrega esperada:** KPIs legíveis e comparáveis.

**Passo a passo**

1. Abra a apresentação inicial e crie uma cópia de trabalho.
2. Acesse o Copilot no PowerPoint; quando necessário, selecione o arquivo de referência.
3. Copie e execute o prompt abaixo. Confirme se o resultado foi inserido no slide ou apenas sugerido no chat.
4. Ajuste layout, legibilidade, ordem narrativa e fontes dos dados, sem alterar valores indiscriminadamente.
5. Valide o resultado com o arquivo original e salve sua versão.

**Prompt para copiar**

```text
Transforme o slide de indicadores em um painel executivo com 5 KPIs: cobertura de inventário, prazo médio, capacitados, orçamento realizado e taxa de reabertura. Mostre meta e realizado, com indicação correta de atingimento.
```

**Validação:** 92% é inferior a 95%; 11% é maior que o limite de 8%.

**Desafio extra:** crie uma segunda versão destinada a outro público e explique o que mudou, sem alterar os fatos.

**Critério de conclusão:** um colega deve conseguir entender o slide e localizar a evidência que sustenta as afirmações.

---

### Exercício 06 — Criar gráfico de orçamento

**Arquivo-base:** Relatório Word.  
**Missão:** Visualize despesas por frente.  
**Entrega esperada:** Gráfico editável acompanhado de legenda e fonte.

**Passo a passo**

1. Abra o relatório Word e o PowerPoint e crie uma cópia de trabalho.
2. Acesse o Copilot no PowerPoint; quando necessário, selecione o arquivo de referência.
3. Copie e execute o prompt abaixo. Confirme se o resultado foi inserido no slide ou apenas sugerido no chat.
4. Ajuste layout, legibilidade, ordem narrativa e fontes dos dados, sem alterar valores indiscriminadamente.
5. Valide o resultado com o arquivo original e salve sua versão.

**Prompt para copiar**

```text
Crie um slide com gráfico de colunas agrupadas comparando orçado e realizado em Infraestrutura, Treinamento, Licenças e Consultoria. Use os valores da tabela do documento de referência. Mostre o desvio total e não conte a linha TOTAL como uma quinta categoria.
```

**Validação:** Totais: R$ 480.000 versus R$ 512.500; diferença R$ 32.500.

**Desafio extra:** crie uma segunda versão destinada a outro público e explique o que mudou, sem alterar os fatos.

**Critério de conclusão:** um colega deve conseguir entender o slide e localizar a evidência que sustenta as afirmações.

---

### Exercício 07 — Criar gráfico de evolução mensal

**Arquivo-base:** Relatório Word.  
**Missão:** Evidencie evolução no atendimento.  
**Entrega esperada:** Gráfico temporal com unidade, período e meta.

**Passo a passo**

1. Abra o relatório Word e o PowerPoint e crie uma cópia de trabalho.
2. Acesse o Copilot no PowerPoint; quando necessário, selecione o arquivo de referência.
3. Copie e execute o prompt abaixo. Confirme se o resultado foi inserido no slide ou apenas sugerido no chat.
4. Ajuste layout, legibilidade, ordem narrativa e fontes dos dados, sem alterar valores indiscriminadamente.
5. Valide o resultado com o arquivo original e salve sua versão.

**Prompt para copiar**

```text
Crie um gráfico de linhas com o prazo médio de atendimento de julho a dezembro, usando apenas os valores da tabela de evolução mensal do documento. Adicione uma referência visual à meta de menos de 5 dias e não presuma causalidade.
```

**Validação:** De 7,2 para 4,8 dias; a meta é estritamente abaixo de 5.

**Desafio extra:** crie uma segunda versão destinada a outro público e explique o que mudou, sem alterar os fatos.

**Critério de conclusão:** um colega deve conseguir entender o slide e localizar a evidência que sustenta as afirmações.

---

### Exercício 08 — Melhorar slide sobrecarregado

**Arquivo-base:** Apresentação inicial.  
**Missão:** Reduza excesso de texto sem perder fatos.  
**Entrega esperada:** Slide mais claro sem alterar o conteúdo.

**Passo a passo**

1. Abra a apresentação inicial e crie uma cópia de trabalho.
2. Acesse o Copilot no PowerPoint; quando necessário, selecione o arquivo de referência.
3. Copie e execute o prompt abaixo. Confirme se o resultado foi inserido no slide ou apenas sugerido no chat.
4. Ajuste layout, legibilidade, ordem narrativa e fontes dos dados, sem alterar valores indiscriminadamente.
5. Valide o resultado com o arquivo original e salve sua versão.

**Prompt para copiar**

```text
Revise o slide de riscos e dependências. Substitua parágrafos longos por um título informativo e três riscos com impacto, evidência e ação de mitigação. Preserve as ressalvas e não invente responsáveis.
```

**Validação:** Compare cada afirmação com o relatório.

**Desafio extra:** crie uma segunda versão destinada a outro público e explique o que mudou, sem alterar os fatos.

**Critério de conclusão:** um colega deve conseguir entender o slide e localizar a evidência que sustenta as afirmações.

---

### Exercício 09 — Reescrever para comunicação executiva

**Arquivo-base:** Apresentação inicial.  
**Missão:** Ajuste o texto e o tom.  
**Entrega esperada:** Textos concisos que não escondam riscos.

**Passo a passo**

1. Abra a apresentação inicial e crie uma cópia de trabalho.
2. Acesse o Copilot no PowerPoint; quando necessário, selecione o arquivo de referência.
3. Copie e execute o prompt abaixo. Confirme se o resultado foi inserido no slide ou apenas sugerido no chat.
4. Ajuste layout, legibilidade, ordem narrativa e fontes dos dados, sem alterar valores indiscriminadamente.
5. Valide o resultado com o arquivo original e salve sua versão.

**Prompt para copiar**

```text
Reescreva os textos dos slides para um público executivo, usando frases curtas, verbos objetivos e números verificáveis. Limite a 35 palavras por slide, exceto tabelas e fontes. Não mude os valores nem o status das decisões.
```

**Validação:** A precisão deve prevalecer sobre a estética.

**Desafio extra:** crie uma segunda versão destinada a outro público e explique o que mudou, sem alterar os fatos.

**Critério de conclusão:** um colega deve conseguir entender o slide e localizar a evidência que sustenta as afirmações.

---

### Exercício 10 — Gerar notas do apresentador

**Arquivo-base:** Apresentação inicial.  
**Missão:** Desenvolva explicações de 45 segundos.  
**Entrega esperada:** Notas úteis para a apresentação oral.

**Passo a passo**

1. Abra a apresentação inicial e crie uma cópia de trabalho.
2. Acesse o Copilot no PowerPoint; quando necessário, selecione o arquivo de referência.
3. Copie e execute o prompt abaixo. Confirme se o resultado foi inserido no slide ou apenas sugerido no chat.
4. Ajuste layout, legibilidade, ordem narrativa e fontes dos dados, sem alterar valores indiscriminadamente.
5. Valide o resultado com o arquivo original e salve sua versão.

**Prompt para copiar**

```text
Crie notas do apresentador para cada slide, com mensagem principal, explicação de números, ressalvas e uma transição para o próximo. Mire aproximadamente 45 segundos por slide; não invente evidências.
```

**Validação:** Notas devem explicar divergências quando aparecerem.

**Desafio extra:** crie uma segunda versão destinada a outro público e explique o que mudou, sem alterar os fatos.

**Critério de conclusão:** um colega deve conseguir entender o slide e localizar a evidência que sustenta as afirmações.

---

### Exercício 11 — Criar linha do tempo das ações

**Arquivo-base:** Relatório Word.  
**Missão:** Organize entregas confirmadas e lacunas.  
**Entrega esperada:** Linha do tempo sem datas inventadas.

**Passo a passo**

1. Abra o relatório Word e o PowerPoint e crie uma cópia de trabalho.
2. Acesse o Copilot no PowerPoint; quando necessário, selecione o arquivo de referência.
3. Copie e execute o prompt abaixo. Confirme se o resultado foi inserido no slide ou apenas sugerido no chat.
4. Ajuste layout, legibilidade, ordem narrativa e fontes dos dados, sem alterar valores indiscriminadamente.
5. Valide o resultado com o arquivo original e salve sua versão.

**Prompt para copiar**

```text
Crie um slide de linha do tempo para as ações do relatório. Use apenas prazos explicitamente registrados; em atividades sem data, exiba “Prazo não definido”. Destaque a ação indicada como concluída sem evidência.
```

**Validação:** Dois prazos ausentes e uma conclusão sem evidência.

**Desafio extra:** crie uma segunda versão destinada a outro público e explique o que mudou, sem alterar os fatos.

**Critério de conclusão:** um colega deve conseguir entender o slide e localizar a evidência que sustenta as afirmações.

---

### Exercício 12 — Construir matriz de riscos

**Arquivo-base:** Relatório Word.  
**Missão:** Sintetize os riscos corporativos.  
**Entrega esperada:** Matriz clara com classificação argumentada.

**Passo a passo**

1. Abra o relatório Word e o PowerPoint e crie uma cópia de trabalho.
2. Acesse o Copilot no PowerPoint; quando necessário, selecione o arquivo de referência.
3. Copie e execute o prompt abaixo. Confirme se o resultado foi inserido no slide ou apenas sugerido no chat.
4. Ajuste layout, legibilidade, ordem narrativa e fontes dos dados, sem alterar valores indiscriminadamente.
5. Valide o resultado com o arquivo original e salve sua versão.

**Prompt para copiar**

```text
Crie um slide com matriz de riscos baseada na seção Riscos, bloqueios e dependências. Inclua risco, evidência, impacto e mitigação sugerida. Não atribua probabilidade numérica sem base factual.
```

**Validação:** Considere divergência de inventário, licenças e aceite.

**Desafio extra:** crie uma segunda versão destinada a outro público e explique o que mudou, sem alterar os fatos.

**Critério de conclusão:** um colega deve conseguir entender o slide e localizar a evidência que sustenta as afirmações.

---

### Exercício 13 — Comparar versões do discurso

**Arquivo-base:** Apresentação inicial.  
**Missão:** Produza versões para dois públicos.  
**Entrega esperada:** Dois roteiros, mesmos fatos.

**Passo a passo**

1. Abra a apresentação inicial e crie uma cópia de trabalho.
2. Acesse o Copilot no PowerPoint; quando necessário, selecione o arquivo de referência.
3. Copie e execute o prompt abaixo. Confirme se o resultado foi inserido no slide ou apenas sugerido no chat.
4. Ajuste layout, legibilidade, ordem narrativa e fontes dos dados, sem alterar valores indiscriminadamente.
5. Valide o resultado com o arquivo original e salve sua versão.

**Prompt para copiar**

```text
A partir desta apresentação, sugira duas versões de roteiro: uma para diretoria financeira, priorizando orçamento e retorno, e outra para equipe operacional, priorizando atendimento e execução. Liste o que permanece idêntico e o que muda na ênfase.
```

**Validação:** As métricas devem permanecer iguais.

**Desafio extra:** crie uma segunda versão destinada a outro público e explique o que mudou, sem alterar os fatos.

**Critério de conclusão:** um colega deve conseguir entender o slide e localizar a evidência que sustenta as afirmações.

---

### Exercício 14 — Preparar perguntas difíceis da diretoria

**Arquivo-base:** Relatório Word + apresentação.  
**Missão:** Antecipe dúvidas críticas.  
**Entrega esperada:** FAQ executivo sem alucinações.

**Passo a passo**

1. Abra o relatório Word e o PowerPoint e crie uma cópia de trabalho.
2. Acesse o Copilot no PowerPoint; quando necessário, selecione o arquivo de referência.
3. Copie e execute o prompt abaixo. Confirme se o resultado foi inserido no slide ou apenas sugerido no chat.
4. Ajuste layout, legibilidade, ordem narrativa e fontes dos dados, sem alterar valores indiscriminadamente.
5. Valide o resultado com o arquivo original e salve sua versão.

**Prompt para copiar**

```text
Liste 10 perguntas difíceis que uma diretoria poderia fazer sobre orçamento, metas, qualidade dos dados e planos de ação. Escreva respostas apenas quando houver evidência; caso contrário, indique que dados adicionais seriam necessários.
```

**Validação:** Questões sobre 92% versus 96% devem explicitar divergência.

**Desafio extra:** crie uma segunda versão destinada a outro público e explique o que mudou, sem alterar os fatos.

**Critério de conclusão:** um colega deve conseguir entender o slide e localizar a evidência que sustenta as afirmações.

---

### Exercício 15 — Auditar a apresentação

**Arquivo-base:** Apresentação inicial.  
**Missão:** Localize afirmações, números e conclusões frágeis.  
**Entrega esperada:** Checklist de correções baseado nas fontes.

**Passo a passo**

1. Abra a apresentação inicial e crie uma cópia de trabalho.
2. Acesse o Copilot no PowerPoint; quando necessário, selecione o arquivo de referência.
3. Copie e execute o prompt abaixo. Confirme se o resultado foi inserido no slide ou apenas sugerido no chat.
4. Ajuste layout, legibilidade, ordem narrativa e fontes dos dados, sem alterar valores indiscriminadamente.
5. Valide o resultado com o arquivo original e salve sua versão.

**Prompt para copiar**

```text
Audite esta apresentação usando o relatório de referência. Liste afirmações potencialmente incorretas, números incompatíveis, decisões apresentadas como aprovadas sem comprovação e gráficos sem fonte. Apresente slide, problema, evidência e correção proposta. Não edite antes da revisão.
```

**Validação:** Encontre a afirmação incorreta sobre 96% e a consultoria.

**Desafio extra:** crie uma segunda versão destinada a outro público e explique o que mudou, sem alterar os fatos.

**Critério de conclusão:** um colega deve conseguir entender o slide e localizar a evidência que sustenta as afirmações.

---

### Exercício 16 — Desafio final: apresentação para a diretoria

**Arquivo-base:** Relatório Word + apresentação.  
**Missão:** Crie uma versão final de 6 a 8 slides e ensaie.  
**Entrega esperada:** Apresentação revisada com roteiro e decisões claras.

**Passo a passo**

1. Abra o relatório Word e o PowerPoint e crie uma cópia de trabalho.
2. Acesse o Copilot no PowerPoint; quando necessário, selecione o arquivo de referência.
3. Copie e execute o prompt abaixo. Confirme se o resultado foi inserido no slide ou apenas sugerido no chat.
4. Ajuste layout, legibilidade, ordem narrativa e fontes dos dados, sem alterar valores indiscriminadamente.
5. Valide o resultado com o arquivo original e salve sua versão.

**Prompt para copiar**

```text
Com base no relatório Word e nos slides de trabalho, prepare uma apresentação final de 6 a 8 slides para uma reunião de 5 minutos. Inclua objetivo, indicadores, orçamento, riscos, ações e decisões solicitadas. Use gráficos editáveis onde viável, notas de fala e uma seção de pontos a validar. Não apresente hipóteses como resultados confirmados.
```

**Validação:** Aprovação de consultoria não pode constar como decisão tomada.

**Desafio extra:** crie uma segunda versão destinada a outro público e explique o que mudou, sem alterar os fatos.

**Critério de conclusão:** um colega deve conseguir entender o slide e localizar a evidência que sustenta as afirmações.

---

## Desafio de qualidade e gabarito do instrutor

Este bloco pode ser mantido separado em uma versão do aluno. Não aceite automaticamente como verdade o conteúdo da apresentação inicial: ela contém **duas afirmações propositalmente incorretas** para estimular auditoria.

- Cobertura de inventário: a tabela consolidada apresenta **92%**, meta **95%**; uma nota isolada cita **96%** e requer reconciliação.
- Orçamento aprovado **R$ 480.000**; realizado **R$ 512.500**; desvio de **R$ 32.500**, cerca de **6,77%** acima do orçamento.
- Prazo médio de atendimento: **7,2 dias** em julho e **4,8 dias** em dezembro; a meta é **menos de 5 dias**.
- Capacitação: **104 colaboradores** ante meta de **80**.
- Reabertura: **11%**, com meta **inferior a 8%**.
- Contratação de consultoria adicional: **proposta, não aprovada**.
- Duas ações sem prazo confirmado e uma marcada concluída sem evidência.

## Avaliação sugerida

| Critério | Peso |
|---|---:|
| Fidelidade ao relatório e fontes | 40% |
| Qualidade da narrativa executiva | 20% |
| Clareza visual e acessibilidade | 20% |
| Validação, transparência e revisão humana | 20% |

## Soluções para dificuldades frequentes

- **Arquivo não encontrado no Copilot:** salve o Word no local corporativo permitido, confira permissão e escolha o arquivo explicitamente.
- **Copilot apenas respondeu em texto:** use o texto como roteiro, insira os elementos manualmente e registre essa limitação.
- **Gráfico criado como imagem:** recrie com gráfico nativo e tabela de origem, verificando editabilidade.
- **Dados inconsistentes:** não force uma reconciliação fictícia; documente a divergência.
- **Layout ultrapassou o limite do slide:** reduza densidade e divida conteúdo em dois slides.

## Leituras oficiais

- [Criar uma nova apresentação com Copilot](https://support.microsoft.com/pt-br/powerpoint/copilot/create-a-new-presentation-with-copilot-in-powerpoint)
- [Adicionar slide de um arquivo](https://support.microsoft.com/pt-br/powerpoint/copilot/add-a-slide-from-a-file-with-copilot-in-powerpoint)
- [Editar com o Copilot](https://support.microsoft.com/pt-br/powerpoint/edit-with-copilot-in-powerpoint)
- [Adicionar notas do apresentador](https://support.microsoft.com/pt-br/powerpoint/copilot/add-speaker-notes-to-your-presentations-using-copilot)

---

**Professor Eduardo Popovici**  
Treinamento Microsoft 365 Copilot — Produtividade com responsabilidade.