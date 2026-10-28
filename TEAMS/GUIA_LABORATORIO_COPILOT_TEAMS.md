# Laboratório prático — Microsoft 365 Copilot no Teams

**Trilha 1 | Reuniões e colaboração | Professor Eduardo Popovici**  
**16 exercícios progressivos • Nível iniciante ao intermediário/avançado • Português (Brasil)**

> **Aprenda a transformar conversas em decisões, reuniões em ações e informação dispersa em acompanhamento confiável.** O Copilot é um assistente para análise e redação; a responsabilidade pelo conteúdo e pelas decisões continua sendo das pessoas.

## 1. Objetivos de aprendizagem

Ao concluir, o participante deverá: (a) preparar reuniões usando o contexto disponível; (b) resumir chats, canais e reuniões; (c) distinguir propostas de decisões; (d) montar atas, relatórios e follow-ups; (e) identificar pendências, responsáveis e riscos; (f) verificar informações antes de compartilhá-las.

## 2. Pré-requisitos e limites importantes

1. Conta de treinamento com licença Microsoft 365 Copilot e Teams compatível. Recursos podem variar conforme plano, política, idioma, tipo de reunião e implantação.
2. Usar **somente dados fictícios** e participantes que saibam sobre a simulação e as opções de transcrição/IA.
3. No Teams, verificar **Opções da reunião → Copilot e outras IAs** (a nomenclatura pode variar). A opção **Durante e após a reunião** exige transcrição para o Copilot usar conteúdo falado depois. **Somente durante** pode funcionar sem salvar uma transcrição, porém perguntas posteriores sobre falas exigem conteúdo disponível. Recursos de recapitulação sem transcrição podem existir em cenários licenciados específicos; não presumir que estão habilitados.
4. O Copilot em chats/canais acessa conteúdo conforme permissões e contexto. Nem todos os recursos de busca ou ações estão habilitados em todas as contas.
5. **Nenhum prompt autoriza publicar mensagens, atribuir tarefas, enviar e-mails, gravar/transcrever sem consentimento ou alterar convites automaticamente.** Peça *rascunhos* e revise-os.
6. Ao usar recapitulação após uma reunião, confira se há transcrição acessível; caso contrário, utilize **o chat da reunião** ou um roteiro fictício como texto de teste, declarando que não é transcrição automática.
7. Evite dados reais sensíveis; respeite regras internas de retenção, gravação e compartilhamento.

**Referências Microsoft (consultadas em outubro de 2026):**  
- [Copilot durante e após reuniões](https://support.microsoft.com/pt-br/teams/copilot/catch-up-on-meetings-with-microsoft-365-copilot-in-teams)  
- [Recapitulação inteligente sem transcrição — disponibilidade condicionada](https://support.microsoft.com/pt-br/teams/meetings/use-intelligent-recap-microsoft-teams-meetings-without-transcription)

## 3. Planejamento sugerido

| Formato | Duração | Dinâmica |
|---|---:|---|
| Sessão essencial | 50–60 min | Configuração e exercícios 01, 02, 06, 07, 08, 09, 10 e 16 em demonstração/duplas |
| Laboratório completo | 120–150 min | Todos os 16 exercícios, rodadas de revisão e desafios extras |

**Método didático:** observar → perguntar → verificar fontes → corrigir → registrar a entrega. Reserve 2 minutos para avaliação de cada bloco.

## 4. Preparando o cenário fictício Contoso Brasil

Crie uma equipe ou chat de treinamento chamada **Contoso | Portal Corporativo** com as pessoas fictícias abaixo interpretadas pelos participantes. Recomenda-se que o instrutor coloque as mensagens no Teams **com antecedência** usando contas e permissões adequadas. Não é necessário cadastrar essas pessoas como usuários reais se o roteiro for lido e encenado pelos alunos.

### 4.1 Participantes e funções

| Personagem | Papel na simulação |
|---|---|
| Camila | Coordenação do projeto |
| Rafael | TI / implantação |
| Bruna | Financeiro |
| Luciana | Operações |
| Diego | Segurança da Informação |

### 4.2 Mensagens de treinamento para o chat

1. **Camila — 09:00:** “O piloto do Portal Contoso está nas unidades Centro e Norte. Precisamos consolidar pendências antes de discutir expansão.”
2. **Rafael — 09:12:** “A versão 1.4.2 está no ambiente de homologação. A correção de login foi testada, mas os testes de carga não terminaram.”
3. **Luciana — 09:25:** “Treinamos 42 pessoas no Centro e 31 no Norte. Seis usuários do Norte solicitaram reforço.”
4. **Diego — 09:40:** “A validação de logs e auditoria ainda está em andamento. Não libero a expansão até verificarmos os controles mínimos.”
5. **Bruna — 10:02:** “A estimativa de comunicação é R$ 18.000, mas o orçamento ainda não foi aprovado.”
6. **Camila — 10:15:** “Sugiro avaliar a expansão em 18/11, desde que os testes críticos e o plano de capacitação sejam concluídos. **Não é data aprovada de entrada em produção.**”
7. **Rafael — 10:22:** “Posso enviar o resultado de carga até 12/11.”
8. **Camila — 10:30:** “Rafael, por favor envie o relatório de carga até 12/11. Diego, precisamos do parecer de segurança até 13/11.”
9. **Diego — 10:41:** “Confirmo que preparo o parecer até 13/11, condicionado ao recebimento dos logs.”
10. **Luciana — 10:55:** “Minha equipe pode organizar reciclagem para os seis usuários. Ainda preciso confirmar a data.”
11. **Bruna — 11:06:** “Reforço que os R$ 18.000 são somente estimativa, sem aprovação.”
12. **Camila — 11:18:** “Vou preparar a próxima reunião para revisar evidências. A expansão continua pendente.”

**Armadilhas intencionais:** confundir **proposta de 18/11** com go-live; transformar **estimativa financeira** em verba aprovada; ignorar dependência dos logs; atribuir data à reciclagem sem confirmação; considerar teste de carga concluído.

### 4.3 Roteiro de reunião simulada (8 minutos)

> Pode ser lido pelos participantes como uma reunião real no Teams, com ciência sobre Copilot/transcrição. Não apresente o texto como se fosse uma gravação automática.

- **00:00 Camila:** objetivo: decidir se existem condições de expandir o piloto e registrar riscos.
- **01:00 Rafael:** correção do login concluída em homologação; testes de carga ainda pendentes; compromete-se a enviar relatório até **12/11**.
- **02:00 Diego:** logs de auditoria ainda não validados; prepara parecer até **13/11**, desde que receba os logs. **Não aprova a expansão**.
- **03:00 Luciana:** 73 treinados no total; seis do Norte precisam de reforço. Sugere sessão adicional, **sem data definida**.
- **04:00 Bruna:** custo de comunicação estimado em **R$ 18 mil**, **sem aprovação orçamentária**.
- **05:00 Camila:** propõe discutir expansão em **18/11**, mas deixa claro que **não é a data de entrada em produção**.
- **06:00 Grupo:** confirma como encaminhamentos o relatório de carga, o parecer de segurança e o planejamento de reforço. Não aprova a expansão.
- **07:00 Camila:** encerra pedindo minuta de ata e follow-up para validação antes de compartilhar.

### 4.4 Gabarito conceitual do instrutor (não publicar como resposta do aluno)

- **Confirmado:** testes de carga ainda não concluídos; Rafael envia relatório até 12/11; Diego prepara parecer até 13/11, dependendo dos logs; 73 treinados, dos quais 6 solicitam reforço; expansão **não aprovada**.
- **Não confirmado:** data da reciclagem, aprovação de R$ 18 mil, liberação de segurança, data de produção.
- **Ação preventiva:** se o aluno declarar “expansão em 18/11 aprovada”, pedir que encontre a fala que comprova isso.

---

## 5. Exercícios guiados

Cada exercício traz cenário, objetivo, passos, prompt e verificação. Os prompts estão reunidos também no arquivo `16_PROMPTS_M365_COPILOT_TEAMS.txt`.

### Exercício 01 — Preparar uma reunião a partir do contexto

**Onde executar:** Chat do projeto ou chat da reunião  
**Objetivo:** Criar pauta objetiva a partir de mensagens prévias.

**Passo a passo**

1. Abra o chat fictício do projeto Contoso; revise as mensagens; acione o Copilot no chat; solicite a pauta; compare com as pendências reais.
2. Copie o prompt abaixo para o Copilot no contexto indicado.
3. Leia toda a resposta, confira as mensagens ou falas originais e marque eventuais inconsistências.
4. Ajuste o prompt, se necessário, e salve o resultado como rascunho ou anotação do laboratório.

**Prompt**

```text
Com base somente nas mensagens deste chat, prepare uma pauta de 25 minutos para uma reunião sobre a implantação do Portal Contoso. Inclua objetivo, 4 tópicos priorizados, tempo por tópico, perguntas em aberto e materiais necessários. Separe fatos de suposições; não invente responsáveis nem compromissos.
```

**Resultado esperado:** Pauta contextualizada, com perguntas sobre a homologação de segurança e a expansão piloto.

**Pergunta de conferência:** A pauta apresenta como aprovada alguma data que era apenas proposta?

**Desafio extra:** reescreva o pedido solicitando referências explícitas às fontes e uma coluna “confirmado / pendente / não disponível”.

---

### Exercício 02 — Recuperar contexto de um chat longo

**Onde executar:** Chat de grupo  
**Objetivo:** Encontrar rapidamente progresso, bloqueios e prazos.

**Passo a passo**

1. Abra o chat de teste com ao menos 12 mensagens; peça resumo; abra as mensagens citadas para comprovar números.
2. Copie o prompt abaixo para o Copilot no contexto indicado.
3. Leia toda a resposta, confira as mensagens ou falas originais e marque eventuais inconsistências.
4. Ajuste o prompt, se necessário, e salve o resultado como rascunho ou anotação do laboratório.

**Prompt**

```text
Resuma este chat em até 180 palavras. Organize em: progresso confirmado, problemas em aberto, decisões efetivas, responsáveis explicitamente mencionados e próximos prazos. Aponte mensagens contraditórias e cite os trechos de origem quando disponíveis.
```

**Resultado esperado:** Resumo útil sem transformar hipótese em fato.

**Pergunta de conferência:** Quais afirmações não possuem suporte nas mensagens?

**Desafio extra:** reescreva o pedido solicitando referências explícitas às fontes e uma coluna “confirmado / pendente / não disponível”.

---

### Exercício 03 — Extrair tarefas de mensagens

**Onde executar:** Chat de grupo  
**Objetivo:** Converter conversa informal em quadro de pendências.

**Passo a passo**

1. Use o mesmo chat; gere tabela de ações; confira o status e a fonte.
2. Copie o prompt abaixo para o Copilot no contexto indicado.
3. Leia toda a resposta, confira as mensagens ou falas originais e marque eventuais inconsistências.
4. Ajuste o prompt, se necessário, e salve o resultado como rascunho ou anotação do laboratório.

**Prompt**

```text
Extraia somente tarefas explicitamente solicitadas neste chat. Crie uma tabela com ação, responsável, prazo, status e evidência. Se responsável ou prazo não estiver definido, escreva NÃO DEFINIDO. Não inclua sugestões como tarefas aprovadas.
```

**Resultado esperado:** Lista rastreável de ações reais.

**Pergunta de conferência:** O Copilot atribuiu alguém que apenas participou da conversa?

**Desafio extra:** reescreva o pedido solicitando referências explícitas às fontes e uma coluna “confirmado / pendente / não disponível”.

---

### Exercício 04 — Criar comunicação para um canal

**Onde executar:** Canal de treinamento  
**Objetivo:** Produzir comunicado profissional sem publicar automaticamente.

**Passo a passo**

1. Selecione o canal laboratório; gere texto; revise com o grupo; publique somente após autorização.
2. Copie o prompt abaixo para o Copilot no contexto indicado.
3. Leia toda a resposta, confira as mensagens ou falas originais e marque eventuais inconsistências.
4. Ajuste o prompt, se necessário, e salve o resultado como rascunho ou anotação do laboratório.

**Prompt**

```text
Redija um anúncio para o canal da equipe sobre a reunião de alinhamento do Portal Contoso. Explique objetivo, preparação solicitada e como registrar bloqueios. Tom corporativo e acolhedor, máximo 120 palavras. Não declare datas, horários ou links inexistentes. Entregue como RASCUNHO para revisão.
```

**Resultado esperado:** Mensagem clara e pronta para revisão.

**Pergunta de conferência:** Há promessas ou datas não verificadas?

**Desafio extra:** reescreva o pedido solicitando referências explícitas às fontes e uma coluna “confirmado / pendente / não disponível”.

---

### Exercício 05 — Comparar opiniões e divergências

**Onde executar:** Chat de projeto  
**Objetivo:** Identificar desacordos e consensos sem distorção.

**Passo a passo**

1. Releia as mensagens divergentes sobre expandir o piloto; peça comparação estruturada; valide.
2. Copie o prompt abaixo para o Copilot no contexto indicado.
3. Leia toda a resposta, confira as mensagens ou falas originais e marque eventuais inconsistências.
4. Ajuste o prompt, se necessário, e salve o resultado como rascunho ou anotação do laboratório.

**Prompt**

```text
Identifique onde os participantes concordam e discordam sobre a expansão do Portal Contoso. Construa uma tabela: tema, posição A, posição B, evidências e informação adicional necessária. Não apresente divergência como decisão.
```

**Resultado esperado:** Diferenças reconhecidas com neutralidade.

**Pergunta de conferência:** O resumo reduziu nuances importantes?

**Desafio extra:** reescreva o pedido solicitando referências explícitas às fontes e uma coluna “confirmado / pendente / não disponível”.

---

### Exercício 06 — Configurar uma reunião para usar Copilot

**Onde executar:** Opções da reunião Teams  
**Objetivo:** Verificar condições técnicas e governança.

**Passo a passo**

1. Crie reunião fictícia entre contas autorizadas; abra Opções da reunião > Copilot e outras IAs; confirme permissões e consentimento; escolha configuração adequada; inicie somente após informar participantes.
2. Copie o prompt abaixo para o Copilot no contexto indicado.
3. Leia toda a resposta, confira as mensagens ou falas originais e marque eventuais inconsistências.
4. Ajuste o prompt, se necessário, e salve o resultado como rascunho ou anotação do laboratório.

**Prompt**

```text
Elabore um checklist de preparação para esta reunião: agenda, objetivo, participantes, habilitação de Copilot e transcrição, consentimento, classificação da informação, riscos de privacidade e plano alternativo se o recurso não estiver disponível. Não afirme ter alterado configurações.
```

**Resultado esperado:** Checklist com requisitos confirmados pelo aluno.

**Pergunta de conferência:** A opção Durante e após requer transcrição?

**Desafio extra:** reescreva o pedido solicitando referências explícitas às fontes e uma coluna “confirmado / pendente / não disponível”.

---

### Exercício 07 — Recapitular reunião em andamento

**Onde executar:** Reunião ao vivo  
**Objetivo:** Fazer catch-up sem interromper a discussão.

**Passo a passo**

1. Inicie a reunião simulada; permita Copilot conforme políticas; entre depois da introdução ou simule perda de contexto; solicite atualização.
2. Copie o prompt abaixo para o Copilot no contexto indicado.
3. Leia toda a resposta, confira as mensagens ou falas originais e marque eventuais inconsistências.
4. Ajuste o prompt, se necessário, e salve o resultado como rascunho ou anotação do laboratório.

**Prompt**

```text
Até este momento da reunião, resuma o objetivo, os três pontos principais discutidos, o que já foi decidido e quais perguntas ainda precisam ser respondidas. Cite falas ou momentos quando disponíveis. Não trate discussão como aprovação.
```

**Resultado esperado:** Retomada objetiva e fiel ao ocorrido.

**Pergunta de conferência:** Algum ponto foi confundido com decisão?

**Desafio extra:** reescreva o pedido solicitando referências explícitas às fontes e uma coluna “confirmado / pendente / não disponível”.

---

### Exercício 08 — Identificar decisões tomadas

**Onde executar:** Reunião e transcrição  
**Objetivo:** Separar decisões finais de propostas condicionais.

**Passo a passo**

1. Após debate do roteiro, peça lista; compare com falas da reunião e transcrição.
2. Copie o prompt abaixo para o Copilot no contexto indicado.
3. Leia toda a resposta, confira as mensagens ou falas originais e marque eventuais inconsistências.
4. Ajuste o prompt, se necessário, e salve o resultado como rascunho ou anotação do laboratório.

**Prompt**

```text
Liste apenas decisões efetivamente confirmadas nesta reunião. Para cada uma, mostre decisão, justificativa apresentada, quem confirmou e evidência. Separe propostas, hipóteses e aprovações condicionais em uma segunda seção. Se não houver decisão, informe explicitamente.
```

**Resultado esperado:** Decisões rastreáveis; condições preservadas.

**Pergunta de conferência:** A expansão total foi aprovada?

**Desafio extra:** reescreva o pedido solicitando referências explícitas às fontes e uma coluna “confirmado / pendente / não disponível”.

---

### Exercício 09 — Produzir ata executiva

**Onde executar:** Recapitulação de reunião  
**Objetivo:** Montar ata curta, confiável e auditável.

**Passo a passo**

1. Finalize a reunião com transcrição; vá ao chat da reunião ou Recapitulação; solicite minuta; revise antes de publicar.
2. Copie o prompt abaixo para o Copilot no contexto indicado.
3. Leia toda a resposta, confira as mensagens ou falas originais e marque eventuais inconsistências.
4. Ajuste o prompt, se necessário, e salve o resultado como rascunho ou anotação do laboratório.

**Prompt**

```text
Gere uma MINUTA de ata da reunião Contoso com: objetivo, participantes apenas se confirmados, temas, decisões confirmadas, propostas não aprovadas, riscos e ações. Termine com uma tabela: ação, responsável, prazo, dependência e evidência. Use NÃO DEFINIDO quando necessário.
```

**Resultado esperado:** Ata editável, sem inventar aprovações.

**Pergunta de conferência:** O texto diferencia status de proposta e aprovação?

**Desafio extra:** reescreva o pedido solicitando referências explícitas às fontes e uma coluna “confirmado / pendente / não disponível”.

---

### Exercício 10 — Gerar follow-up pós-reunião

**Onde executar:** Chat da reunião  
**Objetivo:** Criar mensagem de acompanhamento com responsáveis.

**Passo a passo**

1. Pegue ata revisada; peça rascunho de follow-up; confira destinatários e dependências; não envie sem consentimento.
2. Copie o prompt abaixo para o Copilot no contexto indicado.
3. Leia toda a resposta, confira as mensagens ou falas originais e marque eventuais inconsistências.
4. Ajuste o prompt, se necessário, e salve o resultado como rascunho ou anotação do laboratório.

**Prompt**

```text
A partir das decisões e ações confirmadas nesta reunião, produza um RASCUNHO de follow-up para os participantes em tom profissional. Liste decisões, pendências, responsáveis, prazos e itens que precisam de validação. Não atribua prazos novos nem anuncie publicação ou envio.
```

**Resultado esperado:** Mensagem pronta para revisão humana.

**Pergunta de conferência:** Os prazos são confirmados ou sugeridos?

**Desafio extra:** reescreva o pedido solicitando referências explícitas às fontes e uma coluna “confirmado / pendente / não disponível”.

---

### Exercício 11 — Detectar riscos e bloqueios

**Onde executar:** Reunião e chat  
**Objetivo:** Construir quadro de riscos baseado em evidências.

**Passo a passo**

1. Use transcrição e chat; peça matriz; confronte com fonte e grau de incerteza.
2. Copie o prompt abaixo para o Copilot no contexto indicado.
3. Leia toda a resposta, confira as mensagens ou falas originais e marque eventuais inconsistências.
4. Ajuste o prompt, se necessário, e salve o resultado como rascunho ou anotação do laboratório.

**Prompt**

```text
Identifique riscos e bloqueios discutidos nesta reunião. Retorne tabela: risco, impacto possível, evidência, mitigação mencionada, responsável confirmado e próximo passo. Classifique prioridade como sugestão, não como decisão formal. Não crie fatos não discutidos.
```

**Resultado esperado:** Riscos claros e priorizados com ressalvas.

**Pergunta de conferência:** Qual é o bloqueio de segurança?

**Desafio extra:** reescreva o pedido solicitando referências explícitas às fontes e uma coluna “confirmado / pendente / não disponível”.

---

### Exercício 12 — Avaliar encaminhamentos sem responsável

**Onde executar:** Ata ou transcrição  
**Objetivo:** Detectar tarefas órfãs e dúvidas de execução.

**Passo a passo**

1. Peça somente itens sem dono ou data; simule reunião de fechamento para definir pendências.
2. Copie o prompt abaixo para o Copilot no contexto indicado.
3. Leia toda a resposta, confira as mensagens ou falas originais e marque eventuais inconsistências.
4. Ajuste o prompt, se necessário, e salve o resultado como rascunho ou anotação do laboratório.

**Prompt**

```text
Revise os itens de ação e liste quais não possuem responsável, prazo ou critério de aceite confirmado. Proponha perguntas objetivas para encerrar essas lacunas, sem preencher os campos por conta própria.
```

**Resultado esperado:** Lista de lacunas e perguntas de fechamento.

**Pergunta de conferência:** Copilot completou lacunas indevidamente?

**Desafio extra:** reescreva o pedido solicitando referências explícitas às fontes e uma coluna “confirmado / pendente / não disponível”.

---

### Exercício 13 — Comparar reuniões recorrentes

**Onde executar:** Duas reuniões transcritas acessíveis  
**Objetivo:** Medir evolução entre encontros.

**Passo a passo**

1. Realize duas reuniões simuladas ou use duas transcrições acessíveis; peça comparação e indique quando faltar acesso a uma delas.
2. Copie o prompt abaixo para o Copilot no contexto indicado.
3. Leia toda a resposta, confira as mensagens ou falas originais e marque eventuais inconsistências.
4. Ajuste o prompt, se necessário, e salve o resultado como rascunho ou anotação do laboratório.

**Prompt**

```text
Compare as reuniões de acompanhamento do Portal Contoso às quais tenho acesso. Apresente avanços, pendências encerradas, itens ainda abertos, decisões alteradas e próximos marcos. Cite de qual reunião veio cada informação. Se faltar acesso a alguma reunião, informe a limitação em vez de supor.
```

**Resultado esperado:** Quadro antes/depois com fontes.

**Pergunta de conferência:** Um item foi declarado concluído sem evidência?

**Desafio extra:** reescreva o pedido solicitando referências explícitas às fontes e uma coluna “confirmado / pendente / não disponível”.

---

### Exercício 14 — Preparar apresentação de status

**Onde executar:** Chat e reunião  
**Objetivo:** Criar síntese para liderança.

**Passo a passo**

1. Use conclusões validadas; gere briefing de 1 minuto; faça revisão do vocabulário.
2. Copie o prompt abaixo para o Copilot no contexto indicado.
3. Leia toda a resposta, confira as mensagens ou falas originais e marque eventuais inconsistências.
4. Ajuste o prompt, se necessário, e salve o resultado como rascunho ou anotação do laboratório.

**Prompt**

```text
Elabore um briefing executivo de até 150 palavras para a diretoria sobre o Portal Contoso: situação atual, duas entregas, dois riscos, decisões efetivas e próximos passos. Inclua observações sobre informações não confirmadas. Linguagem objetiva, sem jargões desnecessários.
```

**Resultado esperado:** Resumo gerencial seguro e conciso.

**Pergunta de conferência:** O texto chama piloto de produção?

**Desafio extra:** reescreva o pedido solicitando referências explícitas às fontes e uma coluna “confirmado / pendente / não disponível”.

---

### Exercício 15 — Auditar a resposta do Copilot

**Onde executar:** Chat, ata e transcrição  
**Objetivo:** Exercitar pensamento crítico e conferência.

**Passo a passo**

1. Escolha a ata gerada; localize 5 afirmações e verifique evidências; solicite revisão crítica.
2. Copie o prompt abaixo para o Copilot no contexto indicado.
3. Leia toda a resposta, confira as mensagens ou falas originais e marque eventuais inconsistências.
4. Ajuste o prompt, se necessário, e salve o resultado como rascunho ou anotação do laboratório.

**Prompt**

```text
Audite o resumo produzido anteriormente. Construa tabela com afirmação, evidência na conversa ou transcrição, nível de confiança, risco de interpretação incorreta e correção recomendada. Priorize datas, números, aprovações, responsáveis e prazos. Não declare como verificado o que não pode comprovar.
```

**Resultado esperado:** Registro de verificações e correções.

**Pergunta de conferência:** Quais elementos permanecem incertos?

**Desafio extra:** reescreva o pedido solicitando referências explícitas às fontes e uma coluna “confirmado / pendente / não disponível”.

---

### Exercício 16 — Desafio integrado — reunião orientada a resultados

**Onde executar:** Chat + reunião + recapitulação  
**Objetivo:** Consolidar preparação, discussão, atas e follow-up.

**Passo a passo**

1. Em duplas, execute uma reunião de 8 minutos: crie pauta, discuta o roteiro, peça decisões, ata e follow-up; faça auditoria cruzada.
2. Copie o prompt abaixo para o Copilot no contexto indicado.
3. Leia toda a resposta, confira as mensagens ou falas originais e marque eventuais inconsistências.
4. Ajuste o prompt, se necessário, e salve o resultado como rascunho ou anotação do laboratório.

**Prompt**

```text
Atue como assistente de reunião para o projeto Contoso usando apenas chat e transcrição disponíveis. Entregue: (1) resumo executivo de até 120 palavras; (2) decisões efetivas; (3) propostas pendentes; (4) tabela de ações com responsável, prazo e evidência; (5) três perguntas para o próximo encontro; (6) rascunho de follow-up. Sinalize qualquer dado não encontrado. Não publique nem atribua ações automaticamente.
```

**Resultado esperado:** Pacote completo de acompanhamento, revisado.

**Pergunta de conferência:** Compare com o roteiro de referência e identifique divergências.

**Desafio extra:** reescreva o pedido solicitando referências explícitas às fontes e uma coluna “confirmado / pendente / não disponível”.

---

## 6. Desafio de encerramento e avaliação

Em grupos de 2–3, conduza a reunião fictícia e entregue um **pacote de acompanhamento**: pauta, resumo, matriz de decisões, tabela de ações, minuta de ata, follow-up e cinco afirmações checadas contra a fonte.

| Critério | Pontos |
|---|---:|
| Fidelidade aos fatos e preservação das condições | 40 |
| Decisões versus propostas claramente separadas | 20 |
| Ações com dono/prazo apenas quando conhecidos | 20 |
| Clareza de comunicação e revisão humana | 10 |
| Verificabilidade e cuidado com privacidade | 10 |

## 7. Diagnóstico de falhas e alternativas

| Problema | Como proceder |
|---|---|
| Copilot não aparece | Verificar licença, políticas, versão e conta correta; usar roteiro manual em chat permitido |
| Não há conteúdo de fala após a reunião | Confirmar transcrição acessível e configuração de Copilot; não afirmar que houve resumo automático |
| Copilot cita pessoa incorreta | Conferir transcrição/chat e corrigir; não atribuir tarefas por inferência |
| O assistente inventa prazo | Pedir “NÃO DEFINIDO” quando o prazo não constar na fonte |
| Atas diferem das falas | Fazer validação item a item e registrar evidência antes de compartilhar |
| Não é possível criar um canal/equipe | Usar chat de grupo de treinamento, observando as permissões de acesso |

## 8. Checklist para o instrutor

- [ ] Licenças, políticas e versões testadas.
- [ ] Contas e equipe/chat de laboratório separados do ambiente produtivo.
- [ ] Participantes informados sobre uso de IA, transcrição e gravação.
- [ ] Cenário de mensagens fictícias preparado antes da aula.
- [ ] Reunião simulada agendada e roteiro distribuído.
- [ ] Teste de acesso à recapitulação/transcrição após reunião.
- [ ] Critérios de gabarito e validação disponíveis ao professor.
- [ ] Plano de contingência disponível caso o Copilot não esteja habilitado.

## 9. Publicação no GitHub

```text
trilha-teams/
├── GUIA_LABORATORIO_COPILOT_TEAMS.md
└── 16_PROMPTS_M365_COPILOT_TEAMS.txt
```

**Autor:** Professor Eduardo Popovici  
**Propósito:** treinamento corporativo e educação em produtividade com Microsoft 365 Copilot.  
**Princípio:** IA para acelerar a preparação e a análise; pessoas para validar fatos, decidir e agir.
