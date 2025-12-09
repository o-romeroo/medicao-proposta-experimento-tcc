# Aluno: João Vitor Romero Sales

# Plano de Experimento – Scoping e Planejamento

## 1. Identificação básica

### 1.1 Título do experimento
Análise Comparativa da Qualidade de Código Terraform Gerado por Ferramentas de Inteligência Artificial em Ambientes Multi-Cloud (AWS e Azure)

### 1.2 ID / código
EXP-DEVOPS-AIIAC-2025

### 1.3 Versão do documento e histórico de revisão
| Versão | Data       | Descrição                                                                                                                                  |
| ------ | ---------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| v1.0 | 21/11/2025 | Versão inicial do plano (Identificação dos dados, Contextualização e Definição do Problema)  |
| v1.1 | 24/11/2025 | Versão preliminar (Inserção do Escopo, Objetivos, Stakeholders/Impacto, Riscos principais, Premissas e Critérios de Sucesso) |
| v1.2 | 24/11/2025 | Versão preliminar (Estruturação do Modelo conceitual e hipóteses; Definição de variáveis, fatores e objetos; Desenho experimental) |
| v1.3 | 27/11/2025 | Versão preliminar (Detalhamento da População, sujeitos e amostragem; Instrumentação/Protocolos; Plano de análise de dados na pré-execução |
| v1.4 | 28/11/2025 | Versão preliminar (Análise de ameaças à validade e estratégias de mitigação |
| v1.5 | 29/11/2025 | Versão Final (Planejamento de Experimento finalizado) |
| v1.6 | 09/12/2025 | Versão Final (Mudanças estéticas e melhoria no texto) |

### 1.4 Datas (criação, última atualização)
- Criação: 21/11/2025
- Última atualização: 09/12/2025

### 1.5 Autores (nome, área, contato)
João Vitor Romero Sales, Estudante de Engenharia de Software na Pontifícia Universidade Católica de Minas Gerais, Contato: joao.sales.785111@sga.pucminas.br

### 1.6 Responsável principal (PI / dono do experimento)
João Vitor Romero Sales, como pesquisador principal e executor do trabalho, responsável pelas decisões científicas, execução do experimento e análise de resultados.

### 1.7 Projeto / produto / iniciativa relacionada
Trabalho Final de Medição e Experimentação de Software – Engenharia de Software 
Tema: Análise Comparativa da Qualidade de Código Terraform Gerado por Ferramentas de Inteligência Artificial em Ambientes Multi-Cloud (AWS e Azure)

## 2. Contexto e problema

### 2.1 Descrição do problema / oportunidade
O problema central reside na adoção crescente de ferramentas de Inteligência Artificial (IA) para geração automática de código, inclusive na área de DevOps, particularmente para Infraestrutura como Código (IaC) com Terraform, mas com evidências limitadas sobre a qualidade do código produzido, especialmente em cenários multi-cloud (AWS e Azure). Isso pode introduzir vulnerabilidades de segurança, não conformidade com boas práticas (como modularidade e parametrizabilidade) e valores hard-coded, aumentando riscos de falhas em provisionamento e custos operacionais. O foco deste estudo é avaliar empiricamente a geração de código de infraestrutura feita por três ferramentas de Inteligência Artificial (Chat-GPT, Google Gemini e Claude AI), visando identificar padrões de qualidade e fornecer informações valiosas que acelerem a adoção segura de IA em fluxos de trabalho DevOps acadêmicos e profissionais, reduzindo o tempo de codificação e revisão manual.

### 2.2 Contexto organizacional e técnico
O experimento ocorre em um contexto acadêmico de uma universidade em Belo Horizonte, Minas Gerais, Brasil, no âmbito de um curso de Engenharia de Software, cloud computing (AWS e Azure) e análise de dados. A "organização" é o ambiente de pesquisa individual do estudante, utilizando ferramentas open-source e contas de cloud para simulações. Tecnicamente, envolve Terraform CLI para IaC, APIs de IA para geração de código e ferramentas de análise estática como TFLint e Checkov. O processo de desenvolvimento segue práticas ágeis adaptadas para pesquisa (iterações semanais de preparação, geração e análise), com versionamento via GitHub e análise de dados via Python/Pandas.

### 2.3 Trabalhos e evidências prévias (internos e externos)
Trabalhos prévios na literatura científica incluem o estudo de Dalla Palma et al. (2020), que desenvolveu um catálogo abrangente de 46 métricas de qualidade para código IaC baseado em Ansible, abrangendo atributos como linhas de código, presença de strings hard-coded e code smells associados a defeitos. Os autores validaram o catálogo por meio de modelos preditivos, alcançando precisão de 0,70 a 0,78 e recall de 0,54 a 0,67, demonstrando a viabilidade de adaptar métricas tradicionais de engenharia de software ao contexto de IaC. Adicionalmente, Rahman et al. (2024) investigaram a avaliação de qualidade em código gerado e aprimorado por IA, propondo um framework com métricas funcionais e não funcionais para artefatos de software, incluindo análise estática de vulnerabilidades e conformidade em cenários de automação. A aplicação em datasets reais de código gerado por LLMs revelou taxas de detecção de hard-coded values de 25-35%, enfatizando a necessidade de validação empírica específica para geração assistida por IA em ambientes de desenvolvimento ágil.

### 2.4 Referencial teórico e empírico essencial
O referencial teórico deste experimento fundamenta-se em estudos que investigam especificamente segurança e confiabilidade em Infrastructure as Code (IaC). Em particular, a revisão/mapeamento sistemática de Rahman et al. (2022) “Security and Reliability Issues in Infrastructure as Code: A Systematic Mapping Study”, analisa projetos reais que utilizam IaC para identificar vulnerabilidades recorrentes, falhas de configuração e problemas de manutenibilidade em scripts de infraestrutura. Esse trabalho mapeia categorias típicas de riscos como exposição de credenciais, permissões excessivas, uso inadequado de padrões de segurança e configurações inseguras, e discute como essas classes de problemas impactam a confiabilidade e a operação de sistemas em produção.

Ao sistematizar os principais tipos de defeitos e vulnerabilidades presentes em IaC, Rahman et al. (2022) fornecem uma base conceitual sólida para definir o que significa “qualidade” em código de infraestrutura sob a ótica de segurança e confiabilidade. No contexto deste experimento, esse referencial é diretamente aproveitado para justificar a escolha das métricas de qualidade avaliadas (por exemplo, contagem e gravidade de vulnerabilidades detectadas por Checkov, uso de valores hard-coded e aderência a boas práticas de configuração), bem como o foco em ferramentas de análise estática especializadas para IaC.

No âmbito empírico, o framework proposto por Sellam et al. (2019) para a medição de qualidade em IaC oferece suporte essencial, definindo nove categorias analíticas, incluindo estrutura de código, segurança e automação, mapeadas ao padrão ISO/IEC 25010 e validadas em repositórios de Ansible. Os autores identificaram 104 atributos relevantes, como detecção de valores hard-coded e tratamento de erros, revelando lacunas em práticas tool-specific e a importância de avaliações padronizadas para mitigar riscos em provisionamento. Complementarmente, o estudo comparativo de Frois et al. (2024) entre Terraform e AWS CDK examina dimensões como abstração, escalabilidade e manutenibilidade, constatando que o Terraform apresenta maior conformidade em cenários multi-cloud, embora exiba 15-20% mais vulnerabilidades relacionadas a configurações hard-coded sem ferramentas de linting. Esses achados corroboram hipóteses sobre trade-offs inerentes à qualidade de IaC, orientando o desenho experimental para uma análise multi-cloud focada em segurança e parametrizabilidade.

## 3. Objetivos e questões (Goal / Question / Metric)

### 3.1 Objetivo geral (Goal template)
Analisar a qualidade de código Terraform gerado por ferramentas de Inteligência Artificial (Chat-GPT, Google Gemini e Claude AI), para fins de melhoria na adoção de IA em DevOps, sob a perspectiva de conformidade, segurança e manutenibilidade, em um contexto de infraestruturas multi-cloud (AWS e Azure).

### 3.2 Objetivos específicos
- O1: Gerar e coletar 150 amostras de código Terraform (50 prompts × 3 ferramentas de IA) representativas de cenários DevOps reais em AWS e Azure, garantindo variabilidade controlada na clareza dos prompts.
- O2: Quantificar sistematicamente as métricas de qualidade do código gerado, utilizando ferramentas de análise estática automatizadas, para caracterizar o desempenho individual de cada ferramenta de IA.
- O3: Comparar o desempenho relativo das ferramentas de IA (Chat-GPT, Google Gemini e Claude AI) em termos de conformidade, segurança e manutenibilidade, identificando padrões por provedor de cloud e tipo de prompt.
- O4: Derivar recomendações práticas e evidências empíricas para a integração segura de IA generativa em fluxos de trabalho DevOps multi-cloud, incluindo diretrizes para otimização de prompts e revisão automatizada.

### 3.3 Questões de pesquisa / de negócio
**O1 - Geração e Coleta de Amostras:**
- Q1.1: Qual é a taxa de geração bem-sucedida de código Terraform sintaticamente válido por cada ferramenta de IA?
- Q1.2: Como a clareza dos prompts influencia a completude estrutural do código gerado (presença de recursos essenciais)?
- Q1.3: Há diferenças na estruturação inicial do código gerado entre AWS e Azure para prompts equivalentes?

**O2 - Quantificação de Métricas:**
- Q2.1: Qual o nível de conformidade com boas práticas de IaC exibido pelo código de cada ferramenta?
- Q2.2: Quantas vulnerabilidades de segurança são introduzidas pelo código gerado por cada IA?
- Q2.3: Qual a prevalência de valores hard-coded no código produzido por cada ferramenta?

**O3 - Comparação de Desempenho:**
- Q3.1: Qual ferramenta de IA apresenta melhor desempenho global em conformidade para AWS versus Azure?
- Q3.2: Como as ferramentas diferem na detecção e mitigação automática de vulnerabilidades de segurança?
- Q3.3: Há correlação entre clareza do prompt e redução de valores hard-coded nas diferentes IAs?

**O4 - Recomendações Práticas:**
- Q4.1: Quais padrões de prompts otimizam a qualidade do código gerado pelas melhores ferramentas identificadas?
- Q4.2: De que forma a qualidade do código impacta a Dívida Técnica (Technical Debt) estimada e o esforço potencial de correção?
- Q4.3: Quais ferramentas complementares de linting são mais eficazes para mitigar falhas das IAs?

### 3.4 Métricas associadas (GQM)
#### Tabela GQM: Alinhamento Objetivo-Pergunta-Métrica

| Objetivo Específico | Questões de Pesquisa (Questions) | Métricas Associadas (Metrics) |
| :--- | :--- | :--- |
| **O1. Geração e Coleta de Amostras** | **Q1.1** Qual é a taxa de geração bem-sucedida de código Terraform sintaticamente válido por cada ferramenta de IA? | **M1.** Taxa de Validação Sintática [%]<br>**M2.** Tempo de Geração [s] |
| | **Q1.2** Como a clareza dos prompts influencia a completude estrutural do código gerado (presença de recursos essenciais)? | **M3.** Índice de Completude Estrutural [%]<br>**M4.** Cobertura de Outputs [%] |
| | **Q1.3** Há diferenças na estruturação inicial do código gerado entre AWS e Azure para prompts equivalentes? | **M5.** Densidade de Recursos Específicos por Cloud [recursos/arquivo] |
| **O2. Quantificação de Métricas** | **Q2.1** Qual o nível de conformidade com boas práticas de IaC exibido pelo código de cada ferramenta? | **M6.** Taxa de Conformidade TFLint [%]<br>**M7.** Pontuação de Boas Práticas [0-10] |
| | **Q2.2** Quantas vulnerabilidades de segurança são introduzidas pelo código gerado por cada IA? | **M8.** Contagem de Vulnerabilidades Checkov [#]<br>**M9.** Gravidade Média de Vulnerabilidades [1-10] |
| | **Q2.3** Qual a prevalência de valores *hard-coded* no código produzido por cada ferramenta? | **M10.** Contagem de *Hard-Coded Values* [#]<br>**M11.** Taxa de Parametrização [%] |
| **O3. Comparação de Desempenho** | **Q3.1** Qual ferramenta de IA apresenta melhor desempenho global em conformidade para AWS versus Azure? | **M12.** Ranking de Conformidade por Cloud [posição 1-3]<br>**M13.** Delta Conformidade AWS-Azure [%] |
| | **Q3.2** Como as ferramentas diferem na detecção e mitigação automática de vulnerabilidades de segurança? | **M14.** Taxa de Redução de Vulnerabilidades por IA [%]<br>**M15.** *False Positives* em Segurança [%] |
| | **Q3.3** Há correlação entre clareza do prompt e redução de valores *hard-coded* nas diferentes IAs? | **M16.** Correlação Prompt Qualidade-*Hard-Coded* [r Pearson]<br>**M17.** *Threshold* de Clareza [%] |
| **O4. Recomendações Práticas** | **Q4.1** Quais padrões de prompts otimizam a qualidade do código gerado pelas melhores ferramentas identificadas? | **M18.** Eficiência de Prompts Otimizados [% melhoria]<br>**M19.** Variabilidade Intra-Prompt [DP] |
| | **Q4.2** De que forma a qualidade do código impacta a Dívida Técnica (Technical Debt) estimada e o esforço potencial de correção? | **M20.** Índice Estimado de Dívida Técnica [score/arquivo]<br>*[...] |
| | **Q4.3** Quais ferramentas complementares de *linting* são mais eficazes para mitigar falhas das IAs? | **M22.** Eficácia de *Linting* Complementar [% correção]<br>**M23.** Cobertura de Regras Ativas [%] |

#### Tabela Completa de Métricas

| Métrica | Descrição | Unidade |
| :-- | :-- | :-- |
| Taxa de Validação Sintática | Percentual de códigos que passam em `terraform validate` sem erros | % (0-100) |
| Tempo de Geração | Tempo médio desde envio do prompt até recebimento do código completo | segundos (s) |
| Índice de Completude Estrutural | Percentual de recursos essenciais presentes conforme especificação do prompt | % (0-100) |
| Cobertura de Outputs | Percentual de blocos `resource` com definições `output` correspondentes | % (0-100) |
| Densidade de Recursos Específicos por Cloud | Média de recursos cloud-specific por arquivo (.tf) | recursos/arquivo |
| Taxa de Conformidade TFLint | Percentual de regras TFLint (AWS/Azurerm rulesets) atendidas | % (0-100) |
| Pontuação de Boas Práticas | Pontuação composta (0-10) baseada em checklist manual de 10 itens Terraform | escala 0-10 |
| Contagem de Vulnerabilidades Checkov | Número total de vulnerabilidades detectadas por Checkov | contagem (\#) |
| Gravidade Média de Vulnerabilidades | Média da severidade atribuída por Checkov (CRITICAL=10, HIGH=8, etc.) | escala 1-10 |
| Contagem de Hard-Coded Values | Número de valores fixos detectados (chaves API, IPs, regiões, etc.) | contagem (\#) |
| Taxa de Parametrização | Percentual de configurações que utilizam variáveis ao invés de literais | % (0-100) |
| Ranking de Conformidade por Cloud | Posição relativa (1-3) da IA com melhor conformidade por provedor | posição 1-3 |
| Delta Conformidade AWS-Azure | Diferença percentual de conformidade entre clouds para cada IA | % diferença |
| Taxa de Redução de Vulnerabilidades | Redução percentual de vulnerabilidades após linting vs. código bruto | % (0-100) |
| False Positives em Segurança | Percentual de alertas de segurança que são falsos positivos | % (0-100) |
| Correlação Prompt Qualidade-Hard-Coded | Coeficiente de correlação de Pearson entre clareza do prompt e hard-coded | r (-1 a +1) |
| Eficiência de Prompts Otimizados | Melhoria percentual na qualidade com prompts refinados vs. originais | % melhoria |
| Tempo Estimado de Revisão Manual | Tempo médio estimado para revisão humana baseada em densidade de issues | minutos/arquivo |
| Eficácia de Linting Complementar | Percentual de issues corrigidos automaticamente por TFLint/Checkov | % correção |

## 4. Escopo e contexto do experimento

### 4.1 Escopo funcional / de processo (incluído e excluído)
**Incluído:**
- Geração automatizada de 150 amostras de código Terraform (.tf) divididas entre AWS e Azure.
- Aplicação de 50 prompts distintos com níveis controlados de clareza e especificidade.
- Ferramentas de IA Generativa objeto de estudo: ChatGPT, Google Gemini e Claude AI.
- Análise estática de código utilizando as ferramentas TFLint (rulesets AWS e Azurerm) e Checkov.
- Coleta e análise estatística das métricas definidas no framework GQM.
- Entrega de artefatos: repositório GitHub versionado, dataset de métricas (CSV) e guia de recomendações.

**Excluído:**
- Execução efetiva do provisionamento de infraestrutura (`terraform apply` ou `destroy`).
- Análise dinâmica de desempenho ou comportamento dos recursos em tempo de execução (*runtime*).
- Avaliação de custos financeiros ou computacionais (consumo de tokens/API) das ferramentas.
- Outras linguagens ou frameworks de IaC (ex: Ansible, CloudFormation, Pulumi).
- Análise de Experiência do Usuário (UX) ou usabilidade das interfaces das IAs.
- Validação empírica com usuários reais ou implantação em ambientes de produção.

### 4.2 Contexto do estudo (tipo de organização, projeto, experiência)
O estudo será conduzido no âmbito de um trabalho do curso de Engenharia de Software, em uma universidade brasileira localizada em Belo Horizonte, Minas Gerais, caracterizando um contexto acadêmico de pesquisa individual. O projeto possui criticidade baixa (ambiente de simulação com contas AWS/Azure), executado por estudante com experiência em DevOps (AWS, Azure, Python, Git, Terraform), estatística e experimentação controlada, mas sem exposição a equipes industriais. A infraestrutura técnica compreende execução local (máquina pessoal), ferramentas CLI open-source e acesso via web às APIs de IA.

### 4.3 Premissas
- Estabilidade das APIs das ferramentas de IA (Chat-GPT, Gemini, Claude) durante período experimental.
- Consistência nas versões dos modelos de IA testados (ex: GPT-5, Gemini 2.5 Pro, Claude 4.5 Sonnet).
- Contas AWS/Azure que suportam simulações de `terraform plan` sem interrupções por custo.
- Ferramentas de linting (TFLint, Checkov) mantêm compatibilidade com Terraform v1.7+ e providers AWS/Azurerm atualizados.
- Prompts elaborados são representativos de cenários DevOps reais.

### 4.4 Restrições
- Orçamento limitado a R$300 para créditos de API ou assinaturas mensais das ferramentas de IA.
- Prazo de execução alinhado ao cronograma acadêmico.
- Amostra fixa de 50 prompts (150 códigos) devido a limitações manuais de coleta.
- Ausência de ambiente de staging dedicado; testes limitados a `plan` local.
- Dependência de disponibilidade das APIs de IA (limites de taxa, filas).

### 4.5 Limitações previstas
A generalização externa é limitada pela amostra acadêmica (50 prompts controlados vs uso orgânico em produção), ausência de validação com desenvolvedores reais e foco exclusivo em Terraform (não generaliza para outros IaC). Viés de seleção pode ocorrer por prompts elaborados pelo autor. A análise estática não captura falhas de runtime ou performance. Resultados são específicos às versões de IA de Novembro de 2025 e podem depreciar com atualizações dos modelos.

## 5. Stakeholders e impacto esperado

### 5.1 Stakeholders principais
- **Estudante/Autor (Pesquisador Principal):** Executor e beneficiário direto do trabalho.
- **Professor Orientador:** Validador metodológico e avaliador do trabalho acadêmico.
- **Comunidade Acadêmica DevOps:** Futuros leitores do trabalho.
- **Engenheiros DevOps (indireto):** Desenvolvedores, Engenheiros e Arquitetos interessados na utilização de IA para a geração de IaC.

### 5.2 Interesses e expectativas dos stakeholders
- **Professor Orientador:** Evidências metodologicamente rigorosas (GQM), resultados reproduzíveis, contribuições originais à literatura DevOps.
- **Autor:** Aprovação do trabalho, portfólio técnico com repositório público, publicações potenciais.
- **Comunidade Acadêmica:** Dataset público (150 códigos + métricas), benchmarks comparativos de IAs mas geração de IaC.
- **Engenheiros DevOps:** Recomendações práticas para seleção de IAs e otimização de prompts em workflows multi-cloud.

### 5.3 Impactos potenciais no processo / produto
**Durante execução:** Carga de trabalho concentrada, possível exaustão por coleta manual de prompts. Sem impacto no produto final, pois trata-se de um estudo isolado.
**Após execução:** Repositório GitHub como asset permanente, dataset reutilizável para meta-análises, potencial para guidelines. Nenhum impacto negativo previsto em prazos/produtos existentes. Melhoria indireta na maturidade DevOps acadêmica e nas empresas via disseminação de boas práticas.

## 6. Riscos de alto nível, premissas e critérios de sucesso

### 6.1 Riscos de alto nível (negócio, técnicos, etc.)
- **Técnico:** Instabilidade de APIs de IA interrompendo geração de códigos (probabilidade média, impacto alto).
- **Metodológico:** Viés nos prompts afetando representatividade (probabilidade baixa, impacto médio).
- **Recursos:** Esgotamento de créditos nas contas de Cloud ou limites de API pagos (probabilidade baixa, impacto alto).
- **Acadêmico:** Falha em critérios GQM levando a reprovação na banca (probabilidade baixa, impacto crítico).
- **Dados:** Perda de dataset por falha local de backup (probabilidade muito baixa, impacto médio).

### 6.2 Critérios de sucesso globais (go / no-go)
- **Go (Sucesso):** ≥90% dos 150 códigos gerados válidos sintaticamente; variância explicada ≥70% nas comparações entre IAs; pelo menos 2 recomendações acionáveis validadas estatisticamente (p<0.05); relatório com ≥15 visualizações GQM claras.
- **No-go (Falha):** <70% códigos válidos ou nenhuma diferença estatística significativa entre IAs ou dataset incompleto (<120 códigos analisados).

### 6.3 Critérios de parada antecipada (pré-execução)
- Indisponibilidade de acesso pago às 3 IAs simultaneamente (Chat-GPT Plus, Gemini Pro, Claude Code).
- Reprovação ética formal ou questões de direitos autorais nos códigos gerados.
- Mudança radical no escopo do TCC por decisão da banca/orientador.
- Falha crítica no setup técnico (TFLint/Checkov incompatíveis com providers multi-cloud).
- Esgotamento total de orçamento.

## 7. Modelo conceitual e hipóteses

### 7.1 Modelo conceitual do experimento
O modelo conceitual deste experimento parte da ideia de que três fatores principais influenciam a qualidade do código Terraform gerado por IA: a ferramenta de IA utilizada (Chat-GPT, Google Gemini ou Claude AI), a clareza do prompt (alta ou baixa) e o provedor de cloud alvo (AWS ou Azure). Esses fatores afetam diretamente as respostas observadas, que neste estudo são medidas de qualidade como conformidade com boas práticas de IaC, quantidade de vulnerabilidades de segurança e quantidade de valores hard-coded presentes no código.

Em termos conceituais, supõe-se que prompts mais claros tendem a produzir códigos mais alinhados a boas práticas, que ferramentas de IA podem apresentar desempenhos diferentes entre si e que o contexto da cloud alvo pode impactar a qualidade do código gerado, dado que a documentação, os recursos e a complexidade dos serviços variam entre AWS e Azure. Assim, o experimento busca observar como essas combinações de fatores resultam em diferentes níveis de qualidade de IaC.

De forma simplificada, o modelo conceitual é:

> Ferramenta de IA + Clareza do prompt + Cloud alvo
> → influenciam → Qualidade do IaC (conformidade, segurança, manutenibilidade)

### 7.2 Hipóteses formais (H0, H1)
- **Conformidade e Boas Práticas (Ferramentas)**:
  - **H0_Q1:** Não há diferença significativa nas médias de conformidade com boas práticas de IaC entre as três ferramentas de IA analisadas.
  - **H1_Q1:** Pelo menos uma das ferramentas apresenta desempenho de conformidade distinto, com Claude AI e ChatGPT tendendo a apresentar pontuações superiores às do Google Gemini.

- **Segurança e Vulnerabilidades (Efeito do Prompt)**:
  - **H0_Q2a:** A clareza do prompt (alta ou baixa) não influencia a quantidade média de vulnerabilidades de segurança detectadas no código.
  - **H1_Q2a:** O uso de prompts de alta clareza resulta em uma redução significativa na quantidade de vulnerabilidades introduzidas em comparação aos prompts de baixa clareza.

- **Qualidade e Parametrização (Efeito do Prompt)**:
  - **H0_Q2b:** A incidência média de valores *hard-coded* não difere significativamente entre códigos gerados por prompts de alta versus baixa clareza.
  - **H1_Q2b:** Prompts de alta clareza levam a uma diminuição significativa na ocorrência de valores *hard-coded* (maior parametrização) em relação aos prompts menos claros.

- **Consistência entre Provedores (Interação IA × Cloud)**:
  - **H0_Q3:** Não há interação significativa entre a ferramenta de IA e o provedor de nuvem (AWS/Azure) na taxa de valores *hard-coded*; a diferença entre as ferramentas se mantém constante independente da nuvem.
  - **H1_Q3:** Existe uma interação significativa entre a ferramenta e o provedor, onde ferramentas específicas (como Claude AI) apresentam maior variação de desempenho e tendência a *hard-coding* em um provedor (AWS) comparado ao outro (Azure), enquanto outras mantêm estabilidade.

### 7.3 Nível de significância e considerações de poder
Neste estudo será adotado o nível de significância α = 0,05, valor amplamente utilizado em pesquisas em engenharia de software, por oferecer um equilíbrio adequado entre risco de erro do tipo I (rejeitar a hipótese nula quando ela é verdadeira) e a necessidade de identificar efeitos relevantes. Considerando o tamanho de amostra planejado, com 50 prompts aplicados às três ferramentas de IA, resultando em 150 códigos de Terraform, espera-se obter um poder estatístico razoável para detectar efeitos de magnitude média nas comparações entre ferramentas e entre níveis de clareza de prompt. Embora o experimento não tenha o objetivo de ser um estudo estatístico de larga escala, o tamanho da amostra tende a oferecer evidências empíricas úteis sobre as hipóteses definidas, ainda que sua suficiência não tenha sido avaliada formalmente.

## 8. Variáveis, fatores, tratamentos e objetos de estudo

### 8.1 Objetos de estudo
Os objetos de estudo consistem em 150 arquivos de código Terraform (.tf) gerados automaticamente, totalizando aproximadamente 5.000-10.000 linhas de HCL. Cada arquivo representa uma especificação de infraestrutura em nuvem, direcionada para AWS ou Azure, incluindo recursos como redes virtuais, máquinas virtuais, grupos de segurança e recursos de armazenamento. Esses arquivos são as unidades de análise sobre as quais serão aplicadas as ferramentas de validação e análise estática.

### 8.2 Sujeitos / participantes (visão geral)
O estudo não envolve participantes humanos além do próprio pesquisador. Não há desenvolvedores ou usuários finais diretamente envolvidos na execução do experimento. O pesquisador atua como responsável pela elaboração dos prompts, pela interação com as ferramentas de IA, pela configuração das ferramentas de análise e pela interpretação dos resultados. As ferramentas de IA (Chat-GPT, Google Gemini e Claude AI) são tratadas como ferramentas automatizadas que produzem os artefatos a serem avaliados.

### 8.3 Variáveis independentes (fatores) e seus níveis
Fator 1: Ferramenta de IA – 3 níveis: Chat-GPT, Google Gemini, Claude AI.
Fator 2: Clareza do Prompt – 2 níveis: Alta (detalhada, com especificações de boas práticas), Baixa (genérica, ambígua).
Fator 3: Provedor de Cloud – 2 níveis: AWS, Azure.

### 8.4 Tratamentos (condições experimentais)

#### Tabela de Fatores, Tratamentos e Combinações
| Fator 1: IA | Fator 2: Clareza | Fator 3: Cloud | Tratamento (Combinação) | n por Tratamento |
| :-- | :-- | :-- | :-- | :-- |
| Chat-GPT | Alta | AWS | T1 | 12 |
| Chat-GPT | Alta | Azure | T2 | 13 |
| Chat-GPT | Baixa | AWS | T3 | 12 |
| Chat-GPT | Baixa | Azure | T4 | 13 |
| Gemini | Alta | AWS | T5 | 12 |
| Gemini | Alta | Azure | T6 | 13 |
| Gemini | Baixa | AWS | T7 | 12 |
| Gemini | Baixa | Azure | T8 | 13 |
| Claude | Alta | AWS | T9 | 12 |
| Claude | Alta | Azure | T10 | 13 |
| Claude | Baixa | AWS | T11 | 12 |
| Claude | Baixa | Azure | T12 | 13 |
| **Total** |  |  | **12 tratamentos** | **150** |

*Nota: Cada prompt é replicado nas 3 IAs, gerando 50 × 3 = 150 unidades; balanceamento completo.*

### 8.5 Variáveis dependentes (respostas)
As variáveis dependentes são as medidas de resultado observadas para cada código gerado. As principais variáveis dependentes são: a conformidade com boas práticas de IaC, que será medida por meio da análise com TFLint e de um checklist de boas práticas; a quantidade de vulnerabilidades de segurança, identificadas por ferramentas como Checkov; a quantidade de valores hard-coded presentes no código, detectados por meio de scripts de análise; e a validação sintática do código, verificada com o comando “terraform validate”. Essas medidas representam a resposta do sistema à combinação de fatores aplicada.

### 8.6 Variáveis de controle / bloqueio
Alguns fatores não serão estudados diretamente, mas precisam ser mantidos constantes para evitar influenciar os resultados. Entre eles estão as versões equivalentes das ferramentas de IA utilizadas (por exemplo, versões específicas dos modelos Chat-GPT, Gemini e Claude), a versão do Terraform, do TFLint e do Checkov, o ambiente de execução (mesmo computador e sistema operacional) e a estrutura básica dos prompts (seguindo um formato padrão). Esses aspectos serão tratados como variáveis de controle.

### 8.7 Possíveis variáveis de confusão conhecidas
Algumas variáveis de confusão são reconhecidas e podem influenciar os resultados, mesmo não sendo controladas totalmente. Entre elas estão as variações aleatórias das respostas das IAs, devido à natureza probabilística dos modelos; pequenas diferenças na interpretação de prompts semelhantes; e diferenças na maturidade e na documentação entre serviços de AWS e Azure que podem favorecer uma ou outra ferramenta em determinados cenários. Essas variáveis serão monitoradas na interpretação dos resultados, mas não serão objeto central do estudo.

#### Tabela Completa de Variáveis

| Categoria | Variável | Descrição |
| :-- | :-- | :-- |
| **Independente** | Ferramenta de IA | Modelo generativo utilizado (Chat-GPT, Gemini, Claude) |
| **Independente** | Clareza do Prompt | Nível de detalhamento/especificidade do input (alta ou baixa clareza) |
| **Independente** | Provedor de Cloud | Provedor de nuvem (AWS ou Azure) |
| **Dependente** | Conformidade | Grau de aderência a boas práticas de IaC |
| **Dependente** | Conformidade TFLint | Percentual de regras atendidas em análise estática |
| **Dependente** | Vulnerabilidades Checkov | Quantidade total de issues de segurança detectados |
| **Dependente** | Valores hard-coded | Quantidade de valores fixos não parametrizados |
| **Controle** | Versão das ferramentas | Versão fixa de IA, Terraform, TFLint e Checkov |
| **Confusão** | Variação da IA | Comportamento estocástico do modelo de IA |

## 9. Desenho experimental

### 9.1 Tipo de desenho (completamente randomizado, blocos, fatorial, etc.)
O experimento adotará um desenho fatorial completo 3×2×2 (12 tratamentos), no qual as combinações entre ferramenta de IA, clareza do prompt e cloud alvo serão exploradas de forma sistemática. Esse tipo de desenho é adequado porque permite analisar não apenas o efeito isolado de cada fator (por exemplo, qual IA é melhor em média), mas também possíveis interações entre eles (por exemplo, se uma determinada IA funciona melhor com prompts mais claros ou em um provedor de cloud específico). Além disso, o desenho fatorial é compatível com o número de códigos que será gerado e analisado.

### 9.2 Randomização e alocação
Para reduzir viés de ordem e efeitos não controlados, a ordem de execução dos prompts será randomizada. Isso significa que a sequência em que os prompts serão enviados para as ferramentas de IA será definida de forma aleatória, usando, por exemplo, um script simples em Python. Para cada prompt, a ordem em que as três IAs serão chamadas também poderá ser sorteada, de forma a evitar que sempre a mesma ferramenta seja executada primeiro. Essa estratégia de randomização ajuda a distribuir eventuais instabilidades das APIs ao longo do experimento.

### 9.3 Balanceamento e contrabalanço
O experimento buscará manter o balanceamento entre as condições experimentais, garantindo que todas as três IAs recebam o mesmo conjunto de prompts, com a mesma proporção de prompts de alta e baixa clareza, e distribuídos entre AWS e Azure. Isso significa que cada ferramenta será avaliada nas mesmas situações, o que torna a comparação mais justa. O contrabalanço será feito variando a ordem das IAs por prompt, de forma que, ao longo do experimento, nenhuma IA seja sistematicamente favorecida por ser sempre a primeira ou a última a ser executada.

### 9.4 Número de grupos e sessões
O desenho estabelece exatamente 12 grupos experimentais (tratamentos), formados pelas combinações entre três ferramentas de IA, dois níveis de clareza de prompt e dois provedores de cloud. A execução será realizada em sessões assíncronas de geração (preparação dos prompts e geração dos códigos) e coleta (execução das ferramentas de análise e consolidação dos resultados), não exigindo sessões síncronas com participantes humanos.

## 10. População, sujeitos e amostragem

### 10.1 População-alvo
A população-alvo deste estudo são engenheiros DevOps e de software que utilizam ou pretendem utilizar ferramentas de inteligência artificial para gerar código de infraestrutura como código (IaC) com Terraform em ambientes multi-cloud (AWS e Azure). Em termos práticos, o experimento busca representar o contexto de times que desejam automatizar a criação de infraestrutura, mas se preocupam com qualidade, segurança e manutenção do IaC gerado.

### 10.2 Critérios de inclusão de sujeitos
Como o experimento é automatizado e focado em código gerado por IA, não haverá sujeitos humanos participando diretamente da coleta principal. Ainda assim, considera-se como “sujeitos de referência” perfis de engenheiros de software ou DevOps com conhecimento intermediário em Terraform, AWS ou Azure e familiaridade básica com ferramentas de IA generativa. Esses perfis serão usados como base conceitual para definir os prompts de entrada e os cenários de infraestrutura que serão simulados.

### 10.3 Critérios de exclusão de sujeitos
Não há participantes humanos formais, mas restringe-se a definição dos prompts exclusivamente a engenheiros de software com experiência em infraestrutura em cloud e a engenheiros DevOps. Dessa forma, excluem-se indivíduos que não possuam esse nível de conhecimento especializado, evitando a criação de cenários irreais ou tecnicamente incorretos.

### 10.4 Tamanho da amostra planejado (por grupo)
Defina quantos participantes você pretende ter no total e em cada grupo, relacionando a decisão com poder, recursos e contexto.
A “amostra” do experimento é formada pelos arquivos de código Terraform gerados. Serão utilizados 50 prompts distintos, aplicados às três ferramentas de IA (Chat-GPT, Google Gemini e Claude AI), totalizando 150 códigos. Cada combinação de fatores (por exemplo, IA específica + cloud específica + clareza do prompt) terá várias instâncias de código gerado, o que permite comparar médias de métricas de qualidade entre grupos. Esse tamanho foi escolhido para ser viável em um trabalho deste escopo, mas significativo o suficiente para permitir análises estatísticas básicas com nível de significância de 5%.

### 10.5 Método de seleção / recrutamento
Uma vez que não há recrutamento de pessoas, o “recrutamento” será a seleção dos prompts. Os prompts serão definidos a partir de documentação oficial de AWS, Azure e Terraform, e de exemplos comuns de cenários DevOps (por exemplo, criação de redes, máquinas virtuais, bancos de dados). A seleção será feita por conveniência, pelo próprio pesquisador, buscando cobrir casos típicos (infraestrutura simples, intermediária e um pouco mais complexa).

### 10.6 Treinamento e preparação dos sujeitos
Não há treinamento formal de participantes humanos. A preparação ocorre no nível do pesquisador, que estudará previamente Terraform, TFLint, Checkov, e infraestrutura nas clouds públicas AWS e Azure, além de revisar materiais sobre planejamento de experimentos. Também serão preparados templates de prompts padronizados, para reduzir variação de linguagem e garantir que a comparação entre ferramentas de IA seja justa.

## 11. Instrumentação e protocolo operacional

### 11.1 Instrumentos de coleta (questionários, logs, planilhas, etc.)
Os principais instrumentos de coleta de dados serão:
- Arquivos de código Terraform gerados pelas IAs, que são o objeto central de análise.
- Scripts em Python para automatizar a execução de terraform validate, TFLint e Checkov, e para extrair métricas (por exemplo, contagem de hard-coded values).
- Planilhas Excel para registrar as métricas extraídas (conformidade, vulnerabilidades, hard-coded, etc.) por combinação de prompt, IA e cloud.
- Logs de execução das ferramentas (saídas de TFLint, Checkov e Terraform) para rastreabilidade e conferência de resultados.

### 11.2 Materiais de suporte (instruções, guias)
Serão produzidos alguns materiais de apoio simples:
- Um documento com a lista de prompts e regras de formatação, indicando quais são de alta clareza e quais são de baixa clareza.
- Um pequeno guia de execução do experimento, descrevendo como rodar os scripts, configurar credenciais e executar as ferramentas (Terraform, TFLint, Checkov).
- Um arquivo README no repositório com a descrição dos diretórios (por exemplo, pasta para códigos da AWS, pasta para Azure, pasta de scripts, pasta de resultados).

Esses materiais ajudam a manter o experimento reproduzível, caso algum outro pesquisador queira replicar ou estender o trabalho.

### 11.3 Procedimento experimental (protocolo – visão passo a passo)
O procedimento experimental seguirá uma sequência clara, desde o planejamento até a análise dos dados. Abaixo está um fluxograma textual e, em seguida, a descrição dos passos.

Fluxograma (visão geral):
```text
INÍCIO
                          ↓
================================================================
FASE 1: PREPARAÇÃO
================================================================
                          ↓
1. Definição de Cenários e Prompts [Manual / Revisão Bibliográfica]
   (Elaboração de 50 enunciados cobrindo AWS/Azure com variação de clareza)
   Output: Lista de Prompts Documentada (.md)
                          ↓
2. Configuração do Ambiente [Docker / CLI]
   (Instalação e validação de Terraform, TFLint e Checkov)
   Output: Ambiente de Execução Validado
                          ↓
================================================================
FASE 2: COLETA (GERAÇÃO)
================================================================
                          ↓
3. Submissão aos Modelos [Interface Web / API]
   (Envio dos prompts para ChatGPT, Gemini e Claude AI)
   Output: Snippets de Código Bruto
                          ↓
4. Higienização e Armazenamento [Script Python]
   (Extração dos blocos de código e salvamento padronizado)
   Output: Diretórios de Arquivos .tf organizados
                          ↓
================================================================
FASE 3: EXTRAÇÃO (AUDITORIA)
================================================================
                          ↓
5. Validação Sintática [Terraform CLI]
   (Execução de `terraform validate` em cada arquivo)
   Output: Logs de Validação (Sucesso/Erro)
                          ↓
6. Análise Estática de Qualidade [TFLint]
   (Execução com rulesets AWS e Azurerm)
   Output: Relatórios de Conformidade (JSON)
                          ↓
7. Varredura de Segurança [Checkov]
   (Scan de políticas de segurança e más práticas)
   Output: Relatórios de Vulnerabilidade (JSON/XML)
                          ↓
================================================================
FASE 4: CONSOLIDAÇÃO
================================================================
                          ↓
8. Parsing de Logs e Relatórios [Script Python / Pandas]
   (Leitura estruturada dos outputs das ferramentas)
   Output: DataFrame Bruto
                          ↓
9. Cálculo de Métricas GQM [Script Python]
   (Computação de taxas, densidades e normalização de scores)
   Output: Dataset Final Unificado (.csv)
                          ↓
================================================================
FASE 5: ANÁLISE
================================================================
                          ↓
10. Análise Exploratória - [Jupyter / Matplotlib]
    (Geração de histogramas, boxplots e estatística descritiva)
    Output: Gráficos de Distribuição e Tabelas
                          ↓
11. Testes Estatísticos [Scipy / Statsmodels]
    (Execução de testes de hipótese para comparar IAs e Prompts)
    Output: Resultados de Significância (p-values)
                          ↓
================================================================
FASE 6: DOCUMENTAÇÃO
================================================================
                          ↓
12. Síntese e Discussão [Reunião de Orientação]
    (Interpretação dos dados à luz das hipóteses iniciais)
    Output: Definição das Conclusões e Recomendações
                          ↓
13. Redação do texto final [LaTeX]
    (Elaboração do texto acadêmico e formatação)
    Output: Relatório Final / TCC
                          ↓
FIM
```

### 11.4 Plano de piloto (se haverá piloto, escopo e critérios de ajuste)
Antes de rodar o experimento completo, será feito um piloto com um subconjunto de dados:
- Serão escolhidos 5 prompts (em vez de 50), cobrindo pelo menos um caso de alta e um de baixa clareza, tanto para AWS quanto para Azure.
- Esses prompts serão enviados para as três IAs, gerando 15 arquivos .tf.
- O pipeline completo será executado (validate, TFLint, Checkov, scripts, planilha) para esses 15 arquivos.

O objetivo do piloto é verificar:
- Se os scripts e ferramentas estão funcionando corretamente.
- Se as métricas podem ser coletadas sem grandes problemas.
- Se o tempo de execução é viável para escalar de 15 para 150 arquivos.

Caso o piloto identifique problemas (por exemplo, falha na leitura de arquivos, erro de configuração, métricas pouco úteis), o protocolo será ajustado antes da execução completa. Ajustes podem incluir mudar alguma métrica, refinar prompts ou corrigir scripts.

## 12. Plano de análise de dados (pré-execução)

### 12.1 Estratégia geral de análise (como responderá às questões)
A estratégia geral será usar as métricas coletadas para responder às questões de pesquisa definidas anteriormente (Q1, Q2, Q3). Em resumo:
- Para Q1 (qual IA gera código com maior conformidade), será feita comparação das métricas de conformidade entre Chat-GPT, Gemini e Claude.
- Para Q2 (efeito da clareza do prompt em vulnerabilidades e hard-coded), serão comparadas as médias dessas métricas entre o grupo de prompts de alta clareza e o grupo de baixa clareza.
- Para Q3 (implicações práticas em contexto multi-cloud), serão analisadas as diferenças de resultados entre AWS e Azure, bem como possíveis interações entre IA e cloud.

A partir dessas análises, serão formuladas conclusões de qual IA parece mais adequada para determinado contexto e a relação da melhoria da qualidade do código por conta de prompts mais claros.

### 12.2 Métodos estatísticos planejados
Os principais métodos estatísticos previstos são:
- Estatísticas descritivas (média, mediana, desvio padrão) para todas as métricas, por grupo (IA, clareza, cloud).
- Testes de diferença de médias, como ANOVA de uma ou mais vias, para comparar as ferramentas de IA em termos de conformidade e outras métricas.
- Se necessário, testes t de student para comparar dois grupos específicos (por exemplo, alta vs baixa clareza).
- Caso as suposições de normalidade não sejam atendidas, podem ser usados testes não paramétricos simples (como Mann-Whitney) para comparar dois grupos.
- Análise gráfica (boxplots, gráficos de barras) para visualizar as diferenças entre grupos.

### 12.3 Tratamento de dados faltantes e outliers
O tratamento de dados será definido antes da análise para evitar viés das seguintes formas:
- Se algum arquivo não puder ser analisado (por exemplo, devido a um erro grave no código que impeça a execução do comando terraform validate), ele será marcado como falha e registrado. Esses casos poderão ser excluídos de análises específicas, desde que a proporção de faltantes por métrica não exceda 10% do total (n=150).
  Caso a proporção ultrapasse 10% em algum grupo, esse grupo será analisado com exclusão de casos incompletos, registrando-se a redução no tamanho da amostra. Além disso, será realizado um teste de sensibilidade comparando resultados com e sem imputação, garantindo que as conclusões sejam baseadas em evidências estatisticamente sólidas e não em remoções  arbitrárias.
- Valores extremos (outliers), como um código com número de vulnerabilidades muito acima dos demais, serão inspecionados manualmente. Se forem considerados erros de execução ou de coleta, poderão ser removidos com registro explícito. Se forem casos reais, serão mantidos e incluídos em testes de robustez (por exemplo, ANOVA com e sem o outlier) para avaliação de sensibilidade, e serão discutidos na seção de resultados.

### 12.4 Plano de análise para dados qualitativos (se houver)
O estudo é predominantemente quantitativo. Caso sejam coletados dados qualitativos, como anotações do pesquisador e executor do trabalho sobre problemas recorrentes nos códigos ou padrões percebidos nas respostas das IAs, esses dados serão analisados de forma simples, por meio de leitura e categorização manual. Essas categorias serão então usadas para enriquecer a interpretação dos resultados numéricos, mas não haverá análise qualitativa complexa, como entrevistas ou análise de conteúdo formal.

## 13. Avaliação de validade (ameaças e mitigação)

### 13.1 Validade de conclusão
Neste trabalho, algumas ameaças de conclusão, que estão ligadas à qualidade das inferências estatísticas feitas a partir dos dados são: tamanho de amostra limitado para alguns grupos, escolha inadequada de testes estatísticos, violação de suposições (como normalidade e homogeneidade de variâncias) e erros de medida nas métricas de qualidade do código.

Para mitigar essas ameaças, o planejamento prevê: usar um número razoável de códigos por combinação de fatores (para aumentar o poder do teste), aplicar testes adequados ao desenho experimental (ANOVA quando as suposições forem atendidas e testes não paramétricos quando não forem), verificar previamente as suposições por meio de análise exploratória (histogramas, boxplots, testes simples de normalidade) e padronizar a coleta das métricas via scripts e ferramentas automatizadas, reduzindo a chance de erro manual.

### 13.2 Validade interna
No contexto deste experimento, algumas ameaças de validade interna, que estão relacionadas à existência de explicações alternativas para os efeitos observados são: variações de configuração das ferramentas de IA ao longo do tempo, problemas de ambiente (por exemplo, mudanças na versão do Terraform ou de plugins), diferença de tratamento entre grupos (por exemplo, executar uma IA sempre em um horário e outra em outro) e erros na execução dos scripts.

Para reduzir essas ameaças, serão adotadas algumas estratégias: fixar versões das ferramentas sempre que possível (Terraform, TFLint, Checkov, bibliotecas usadas), registrar as versões dos modelos de IA e a data de execução, automatizar a execução com scripts que tratem todas as combinações de forma padronizada, randomizar a ordem de geração dos códigos e de execução das análises e registrar logs de cada etapa para facilitar a rastreabilidade. Com isso, busca-se garantir que a única diferença sistemática entre grupos seja a combinação de fatores do experimento (ferramenta de IA, clareza do prompt, provedor de cloud).

### 13.3 Validade de constructo
Neste trabalho, as principais ameaças de validade do constructo, que procura compreender se o que está sendo medido de fato representa os conceitos teóricos de interesse são: “qualidade do IaC”, “conformidade com boas práticas” e “segurança do código”. Existe o risco de usar métricas que não capturem bem esses conceitos, ou de interpretá-las de forma ambígua.

Para mitigar isso, as métricas foram escolhidas com base na literatura e em práticas da área: conformidade medida por regras de ferramentas como TFLint, segurança medida por vulnerabilidades apontadas pelo Checkov e manutenibilidade aproximada pela presença de valores hard-coded. Além disso, os instrumentos (configs de TFLint, políticas do Checkov e scripts de contagem) serão descritos claramente, permitindo que o leitor entenda o que cada métrica captura. Na discussão dos resultados, será sempre feita a ponte explícita entre métrica e conceito (por exemplo, explicar por que menos hard-coded sugere melhor manutenibilidade), evitando extrapolações além do que as medidas suportam.

### 13.4 Validade externa
Neste estudo, algumas limitações que ameaçam a sua validade externa, que diz respeito a em que medida os resultados podem ser generalizados para outros contextos são: uso de um conjunto específico de prompts, foco em apenas duas clouds (AWS e Azure), uso de três ferramentas de IA em versões específicas e execução em um contexto acadêmico, sem pressão real de produção.

Os resultados podem ser generalizados com mais segurança para cenários semelhantes: equipes DevOps que usam Terraform para cenários parecidos com os prompts usados (por exemplo, redes, máquinas virtuais e serviços básicos em AWS/Azure) e que recorrem às mesmas ferramentas de IA ou a versões próximas. A generalização para outras nuvens, outros tipos de infraestrutura (por exemplo, arquiteturas muito complexas) ou para versões futuras de modelos de IA deve ser feita com cautela e sempre indicada como hipótese a ser testada em trabalhos futuros.

### 13.5 Resumo das principais ameaças e estratégias de mitigação

| Tipo de validade | Ameaça principal | Estratégia de mitigação |
| :-- | :-- | :-- |
| Conclusão | Baixo poder e violação de suposições | Amostra razoável por grupo, verificação de suposições, uso de testes adequados |
| Conclusão | Erros de medida nas métricas | Coleta automatizada com scripts e ferramentas estáveis |
| Interna | Variação de ambiente e versões | Fixar versões, registrar configurações e datas, automatizar execução |
| Interna | Diferença de tratamento entre combinações | Randomização da ordem de geração e análise, uso de scripts padronizados |
| Constructo | Métricas não representarem bem “qualidade de IaC” | Escolha de métricas baseadas em literatura e práticas, descrição clara dos instrumentos |
| Constructo | Interpretação ambígua das métricas | Discutir explicitamente a relação métrica–conceito na análise |
| Externa | Cenário restrito (prompts, clouds, versões de IA) | Descrever claramente o contexto, limitar a generalização a cenários semelhantes |
| Externa | Diferenças entre ambiente acadêmico e industrial | Reconhecer essa limitação e sugerir replicações em ambientes reais |

Esse conjunto de medidas não elimina todas as ameaças, mas torna algumas delas explícitas e suficientemente controladas para que o trabalho apresente um grau significativo de sucesso em termos conceituais.

## 14. Ética, privacidade e conformidade

### 14.1 Questões éticas (uso de sujeitos, incentivos, etc.)
Este experimento não envolve coleta de dados pessoais nem participação ativa de sujeitos humanos em tarefas experimentais, pois todo o foco está nos códigos gerados por ferramentas de IA e na análise automatizada desses artefatos. Ainda assim, há cuidados éticos básicos a considerar, como transparência com o orientador e com a instituição sobre o uso de ferramentas de IA, respeito à propriedade intelectual das ferramentas e da documentação utilizada como referência e ausência de qualquer tipo de pressão sobre colegas para participação formal. Caso algum colega contribua com sugestões de prompts ou revisão de código, essa colaboração será voluntária, sem incentivos financeiros e devidamente mencionada nos agradecimentos do trabalho.

### 14.2 Consentimento informado
Como não há sujeitos humanos formalmente envolvidos, não será aplicado um processo de consentimento informado tradicional, com um termo assinado. O contato com o professor orientador servirá para informar claramente os objetivos do estudo, o tipo de dados manipulados (apenas artefatos de código e resultados de ferramentas) e a ausência de riscos para pessoas. 

### 14.3 Privacidade e proteção de dados
Neste trabalho não está prevista a coleta de dados pessoais sensíveis, uma vez que os principais dados serão arquivos de código Terraform gerados pelas IAs, saídas de ferramentas (TFLint, Checkov, terraform validate) e planilhas com métricas agregadas. Os arquivos e planilhas serão armazenados em repositórios privados (GitHub privado ou armazenamento local com backup) protegidos por senha. Caso algum dado de conta (como tokens de API das IAs ou credenciais de cloud) precise ser configurado, essas informações ficarão em arquivos separados (variáveis de ambiente ou arquivos .env ignorados pelo controle de versão) e nunca serão incluídas no resultado final do trabalho ou em repositórios públicos.

### 14.4 Aprovações necessárias (comitê de ética, jurídico, DPO, etc.)
Como o estudo não envolve intervenção com seres humanos nem tratamento de dados pessoais, a princípio não se enquadra na obrigatoriedade de submissão a comitê de ética em pesquisa com seres humanos. Ainda assim, o plano será discutido com o professor orientador, que poderá confirmar se é necessário algum tipo de parecer formal da coordenação do curso ou da instituição. Não há envolvimento direto com dados de produção de empresas, portanto, não se espera necessidade de aprovação jurídica ou de um DPO (Data Protection Officer). Caso, em algum momento, sejam utilizadas contas institucionais de cloud ou de IA, o uso seguirá as políticas da universidade e da plataforma de nuvem para este tipo de conta.

## 15. Recursos, infraestrutura e orçamento

### 15.1 Recursos humanos e papéis
A equipe do experimento é formada por:

- Pesquisador principal (aluno de graduação em Engenharia de Software): responsável por planejar o experimento, preparar os prompts, configurar ferramentas, executar as coletas, analisar os dados e escrever o documento final do trabalho.
- Professor orientador: responsável por revisar o plano experimental, orientar decisões metodológicas, acompanhar a análise de resultados e avaliar a versão final do trabalho.
- Eventuais colaboradores informais (colegas pesquisadores com conhecimento em infraestrutura em cloud): podem ajudar na criação e revisão de prompts, e testes de scripts, sem papel formal de decisão.

### 15.2 Infraestrutura técnica necessária
Para executar o experimento, serão necessários:

- Um computador pessoal com boa capacidade computacional (CPU e memória suficientes para rodar Terraform, ferramentas de análise e scripts).
- Acesso à internet estável para utilização das ferramentas de IA (Chat-GPT, Gemini e Claude) e para download de dependências.
- Instalação de Terraform CLI, TFLint, Checkov, Python (com bibliotecas para manipulação de arquivos e análise de dados) e planilhas Excel.
- Um repositório de código GitHub para armazenar scripts, configurações e resultados, em modo privado.
- Eventual uso de uma conta de cloud (AWS e Azure) apenas para referência de documentação e, se necessário, validações simples, sem criação de recursos que gerem custo significativo.

### 15.3 Materiais e insumos
Os principais materiais e insumos são:

- Licenças ou acessos às ferramentas de IA (que podem ser versões gratuitas ou planos estudantis, dependendo da política de cada plataforma ou ferramenta).
- Ferramentas de desenvolvimento VisualStudio Code para a criação e edição de scripts e arquivos Terraform.
- Documentação oficial de Terraform, AWS e Azure, acessível gratuitamente nos sites das plataformas.
- Formulários ou documentos digitais (por exemplo, modelos de planilhas ou templates de TCC) fornecidos pela instituição de ensino.
- Uma conta de e-mail institucional para comunicação com o professor orientador e, caso necessário, com a coordenação.

### 15.4 Orçamento e custos estimados
Os principais custos estimados são:

- Horas de trabalho do pesquisador, que não geram custo financeiro direto, mas representam esforço ao longo do semestre.
- Eventuais custos de uso das ferramentas de IA, caso seja necessário adquirir créditos adicionais além dos limites gratuitos.
- Possíveis custos de uso de cloud (AWS/Azure), que serão mantidos mínimos, evitando a criação de recursos pagos em larga escala (o foco é na geração de código, não na implantação real da infraestrutura).

A fonte de “financiamento” é o próprio aluno pesquisador, eventualmente com apoio de benefícios de acesso gratuito concedido pela universidade por meio de parcerias com provedores de IA ou cloud.

## 16. Cronograma, marcos e riscos operacionais

### 16.1 Macrocronograma (até o início da execução)
Um cronograma realista, considerando um semestre letivo, pode ser:

- **Semana 1–3:** Definição do problema, revisão bibliográfica e escolha das métricas (GQM).
- **Semana 4–6:** Elaboração do plano experimental detalhado e definição dos 50 prompts (Alta/Baixa clareza).
- **Semana 7:** Revisão do plano com orientador e ajustes metodológicos.
- **Semana 8:** Setup técnico (Ambiente Python, Docker, TFLint, Checkov) e desenvolvimento dos scripts de automação.
- **Semana 9:** Execução do **Piloto** (5 prompts) e validação da coleta de dados.
- **Semana 10:** Refinamento dos scripts e tratamento de erros detectados no piloto.
- **Semana 11:** Execução completa (Geração dos 150 códigos e análise estática).
- **Semana 12-14:** Análise estatística dos dados, testes de hipótese e escrita da discussão.
- **Semana 15-16:** Redação final, formatação e entrega.

### 16.2 Dependências entre atividades
Há uma clara relação de dependência entre algumas das etapas. O piloto só pode ser executado após a configuração do ambiente e a finalização dos scripts essenciais. A execução completa do experimento, por sua vez, depende dos ajustes realizados com base no piloto. A análise estatística só pode começar quando o conjunto de dados estiver totalmente consolidado e revisado. Já a redação da seção de resultados e discussão depende da conclusão da análise estatística, embora partes da metodologia e do referencial teórico possam ser desenvolvidas previamente.

### 16.3 Riscos operacionais e plano de contingência
Os principais riscos operacionais incluem:

- Atrasos na revisão do plano pelo professor orientador, o que pode atrasar o cronograma planejado.
- Problemas técnicos com as ferramentas de IA (indisponibilidade temporária, mudanças de API).
- Falhas de configuração em Terraform, TFLint, Checkov ou scripts, que podem demandar retrabalho.
- Sobrecarga do aluno pesquisador com outras disciplinas, reduzindo o tempo disponível.

Como plano de contingência, o trabalho será organizado para que as partes que não dependem diretamente da execução (por exemplo, revisão bibliográfica, escrita de seções teóricas) possam avançar mesmo em caso de atraso na coleta. Além disso, serão mantidas alternativas simples para as ferramentas de IA (por exemplo, uso de interface web caso a API esteja instável) e para a análise de dados (por exemplo, fazer estatísticas descritivas em planilhas, se houver algum problema com scripts). O aluno também reservará margens de segurança no cronograma, evitando deixar toda a coleta e análise para as últimas semanas.

## 17. Governança do experimento

### 17.1 Papéis e responsabilidades formais
Na governança do experimento, o aluno pesquisador é responsável por executar as atividades diárias: implementação dos scripts, geração de códigos, execução de ferramentas e análise de resultados. O professor orientador é responsável por aprovar o plano experimental, acompanhar a execução em marcos definidos, revisar a interpretação dos resultados e garantir que o trabalho mantenha rigor acadêmico. A banca examinadora atua como instância de avaliação ao final, aprovando ou não o produto final do trabalho. Caso haja algum apoio técnico (por exemplo, de um colega experiente em infraestrutura como código Terraform), esse apoio será consultivo e não decisório.

### 17.2 Ritos de acompanhamento pré-execução
Antes da execução completa do experimento, serão realizados alguns ritos de acompanhamento. Está previsto pelo menos um encontro quinzenal (ou semanal, conforme combinado) com o professor orientador para discutir o andamento, revisar decisões e ajustar o plano, se necessário. Haverá um checkpoint importante após a conclusão do piloto, em que os resultados preliminares serão apresentados ao orientador para validação do protocolo definitivo. Qualquer mudança significativa na abordagem será discutida nestes encontros e registrada em anotações ou atas.

### 17.3 Processo de controle de mudanças no plano
Mudanças no desenho ou no escopo do experimento seguirão um processo simples, mas organizado. Primeiro, o pesquisador identificará a necessidade de mudança (por exemplo, ajustar uma métrica, alterar a quantidade de prompts) e registrará a proposta em um documento no repositório. Em seguida, a proposta será discutida com o orientador, que poderá aprovar, rejeitar ou sugerir ajustes. Só após essa aprovação as mudanças serão aplicadas ao plano, e a versão atualizada será armazenada com histórico, usando controle de versão no Git. Isso garante que o plano executado corresponda ao que foi acordado e que o histórico de decisões fique registrado.

## 18. Plano de documentação e reprodutibilidade

### 18.1 Repositórios e convenções de nomeação
Toda a documentação do experimento (plano, scripts, configurações, dados e resultados) será armazenada em um repositório privado, no GitHub. Serão adotadas convenções de nomeação simples e claras, como: `prompts/`, `scripts/`, `terraform_codes/`, `results/` e `docs/`. Arquivos de código serão nomeados com padrão que identifique IA, cloud, clareza e um identificador do prompt, seguindo o padrão: `<nome_da_cloud>_<nome_da_IA>_<nivel_de_clareza>_<numero_do_prompt>.tf`. Isso facilitará o rastreamento de cada artefato até sua origem.

### 18.2 Templates e artefatos padrão
Serão utilizados alguns templates e artefatos padrão, tais como: um modelo de planilha para registro de métricas (com colunas fixas para IA, cloud, clareza, métricas numéricas), um template de README para documentar cada pasta do repositório, scripts padrão para executar as ferramentas de análise e, se necessário, um modelo simples de checklist para o piloto (por exemplo, itens a verificar ao rodar o pipeline pela primeira vez). Esses templates ficarão disponíveis na pasta `docs/` ou `templates/` do repositório.

### 18.3 Plano de empacotamento para replicação futura
Para facilitar a replicação do experimento por outros pesquisadores e pela comunidade científica, será preparado um “pacote” mínimo contendo: o plano experimental detalhado, os scripts de coleta e análise, instruções passo a passo para configurar o ambiente (incluindo versões de ferramentas), exemplos de prompts e um conjunto de dados de exemplo com poucos casos (somente para demonstração). Esse pacote poderá ser disponibilizado em um repositório público, desde que nenhum dado sensível ou credencial esteja incluído.

## 19. Plano de comunicação

### 19.1 Públicos e mensagens-chave pré-execução
O principal público a ser comunicado antes da execução é o professor orientador, que precisa estar alinhado com objetivos, escopo, desenho e cronograma do experimento. As mensagens principais são: o objetivo do estudo (avaliar a qualidade de código Terraform gerado por IAs em contexto multi-cloud), o impacto esperado (contribuições práticas para DevOps e uso de IA em IaC) e o cronograma geral.

### 19.2 Canais e frequência de comunicação
A comunicação com o orientador será feita principalmente por e-mail institucional e por meio de reuniões presenciais ou online (via Microsoft Teams), com frequência combinada semanal ou quinzenal. Se preciso, a coordenação do curso será informada pelos canais oficiais da instituição (sistema acadêmico ou e-mail institucional) nos prazos definidos para entrega de documentos formais. A comunicação com colegas, caso necessária, será feita em sala de aula, grupos de mensagens ou plataformas de colaboração usadas pela turma.

### 19.3 Pontos de comunicação obrigatórios
Alguns pontos exigem comunicação formal e registro, como a aprovação do plano experimental pelo professor orientador, que pode ser feita por e-mail; qualquer mudança relevante no escopo ou cronograma, por exemplo, alterações significativas na quantidade de prompts ou nas ferramentas utilizadas; e situações de adiamento ou cancelamento da execução planejada, caso problemas técnicos graves impeçam sua conclusão dentro do semestre. Também é importante comunicar ao orientador a conclusão de marcos importantes, como a finalização do piloto, o término da coleta de dados e o encerramento da análise.

## 20. Critérios de prontidão para execução (Definition of Ready)

### 20.1 Checklist de prontidão (itens que devem estar completos)
Antes de iniciar a execução completa do experimento, os seguintes itens precisam estar concluídos e revisados:

- Plano experimental finalizado e aprovado pelo professor orientador, incluindo objetivos, hipóteses, desenho, métricas e estratégias de análise.
- Ambiente técnico configurado e testado (Terraform, TFLint, Checkov, Python, repositório, scripts básicos).
- Lista de prompts final (com classificação em alta e baixa clareza, e divisão entre AWS e Azure).
- Scripts de automação validados em um piloto (garantindo que funcionam de ponta a ponta).
- Plano de tratamento de dados faltantes e outliers definido e documentado.
- Cronograma detalhado de execução revisto, com margens de segurança.
- Materiais de apoio (README, guias rápidos) prontos no repositório.

### 20.2 Aprovações finais para iniciar a operação
Para iniciar a execução completa do experimento, será necessário o “ok final” do orientador, confirmando que o plano está maduro e que os riscos foram mapeados e considerados de forma adequada. Esse aceite pode ser registrado por e-mail ou em algum outro documento específico. Se a instituição exigir alguma aprovação adicional, por exemplo, da coordenação do curso ou de uma comissão, essa aprovação também deverá estar registrada antes da execução. Somente após essas confirmações o experimento será oficialmente iniciado.
