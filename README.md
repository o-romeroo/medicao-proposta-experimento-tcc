# Aluno: João Vitor Romero Sales

# Plano de Experimento – Scoping e Planejamento

## 1. Identificação básica

### 1.1 Título do experimento
Análise Comparativa da Qualidade de Código Terraform Gerado por Ferramentas de Inteligência Artificial em Ambientes Multi-Cloud (AWS e Azure)

### 1.2 ID / código
EXP-DEVOPS-IAIAC-2025

### 1.3 Versão do documento e histórico de revisão
Versão: v1.0
Histórico de revisão:
 - v1.0 (21/11/2025): Versão inicial, baseada no escopo de pesquisa definido para o trabalho e contendo todos os conteúdos necessários da primeira entrega.
 - v1.1 (24/11/2025): Segunda versão, baseada no escopo de pesquisa definido para o trabalho e contendo todos os conteúdos necessários da segunda entrega.
 - v1.2 (27/11/2025): Terceira versão, baseada no escopo de pesquisa definido para o trabalho e contendo todos os conteúdos necessários da terceira entrega.

### 1.4 Datas (criação, última atualização)
Criação: 21/11/2025
Última atualização: 27/11/2025

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
O experimento ocorre em um contexto acadêmico de uma universidade em Belo Horizonte, Minas Gerais, Brasil, no âmbito de um curso de Engenharia de Software, cloud computing (AWS e Azure) e análise de dados. A "organização" é o ambiente de pesquisa individual do estudante, utilizando ferramentas open-source e free tiers de cloud para simulações. Tecnicamente, envolve Terraform CLI para IaC, APIs de IA para geração de código e ferramentas de análise estática como TFLint e Checkov. O processo de desenvolvimento segue práticas ágeis adaptadas para pesquisa (iterações semanais de preparação, geração e análise), com versionamento via GitHub e análise de dados via Python/Pandas.

### 2.3 Trabalhos e evidências prévias (internos e externos)
Trabalhos prévios na literatura científica incluem o estudo de Dalla Palma et al. (2020), que desenvolveu um catálogo abrangente de 46 métricas de qualidade para código IaC baseado em Ansible, abrangendo atributos como linhas de código, presença de strings hard-coded e code smells associados a defeitos. Os autores validaram o catálogo por meio de modelos preditivos, alcançando precisão de 0,70 a 0,78 e recall de 0,54 a 0,67, demonstrando a viabilidade de adaptar métricas tradicionais de engenharia de software ao contexto de IaC. Adicionalmente, Rahman et al. (2024) investigaram a avaliação de qualidade em código gerado e aprimorado por IA, propondo um framework com métricas funcionais e não funcionais para artefatos de software, incluindo análise estática de vulnerabilidades e conformidade em cenários de automação. A aplicação em datasets reais de código gerado por LLMs revelou taxas de detecção de hard-coded values de 25-35%, enfatizando a necessidade de validação empírica específica para geração assistida por IA em ambientes de desenvolvimento ágil.

### 2.4 Referencial teórico e empírico essencial
O referencial teórico deste experimento fundamenta-se no paradigma Goal-Question-Metric (GQM) proposto por Basili et al. (1994), o qual estabelece uma estrutura hierárquica para o planejamento de experimentos em engenharia de software, alinhando objetivos gerais a questões específicas e métricas quantificáveis. Essa abordagem promove a rastreabilidade conceitual e a validação empírica de hipóteses, conforme preconizado pelas diretrizes de escrita científica que enfatizam a decomposição lógica e a fundamentação em evidências mensuráveis.

No âmbito empírico, o framework proposto por Sellam et al. (2019) para a medição de qualidade em IaC oferece suporte essencial, definindo nove categorias analíticas, incluindo estrutura de código, segurança e automação, mapeadas ao padrão ISO/IEC 25010 e validadas em repositórios de Ansible. Os autores identificaram 104 atributos relevantes, como detecção de valores hard-coded e tratamento de erros, revelando lacunas em práticas tool-specific e a importância de avaliações padronizadas para mitigar riscos em provisionamento. Complementarmente, o estudo comparativo de Frois et al. (2024) entre Terraform e AWS CDK examina dimensões como abstração, escalabilidade e manutenibilidade, constatando que o Terraform apresenta maior conformidade em cenários multi-cloud, embora exiba 15-20% mais vulnerabilidades relacionadas a configurações hard-coded sem ferramentas de linting. Esses achados corroboram hipóteses sobre trade-offs inerentes à qualidade de IaC, orientando o desenho experimental para uma análise multi-cloud focada em segurança e parametrizabilidade.

## 3. Objetivos e questões (Goal / Question / Metric)

### 3.1 Objetivo geral (Goal template)
Analisar para fins de melhoria na adoção de IA em DevOps, a qualidade de código Terraform gerado por ferramentas de Inteligência Artificial (Chat-GPT, Google Gemini e Claude AI), sob a perspectiva de conformidade, segurança e manutenibilidade, em um contexto de infraestruturas multi-cloud (AWS e Azure) com 50 prompts variados em clareza.

### 3.2 Objetivos específicos
O1: Gerar e coletar 150 amostras de código Terraform (50 prompts × 3 ferramentas de IA) representativas de cenários DevOps reais em AWS e Azure, garantindo variabilidade controlada na clareza dos prompts.
O2: Quantificar sistematicamente as métricas de qualidade do código gerado, utilizando ferramentas de análise estática automatizadas, para caracterizar o desempenho individual de cada ferramenta de IA.
O3: Comparar o desempenho relativo das ferramentas de IA (Chat-GPT, Google Gemini e Claude AI) em termos de conformidade, segurança e manutenibilidade, identificando padrões por provedor de cloud e tipo de prompt.
O4: Derivar recomendações práticas e evidências empíricas para a integração segura de IA generativa em fluxos de trabalho DevOps multi-cloud, incluindo diretrizes para otimização de prompts e revisão automatizada.

### 3.3 Questões de pesquisa / de negócio
**O1 - Geração e Coleta de Amostras:**
Q1.1: Qual é a taxa de geração bem-sucedida de código Terraform sintaticamente válido por cada ferramenta de IA?
Q1.2: Como a clareza dos prompts influencia a completude estrutural do código gerado (presença de recursos essenciais)?
Q1.3: Há diferenças na estruturação inicial do código gerado entre AWS e Azure para prompts equivalentes?

**O2 - Quantificação de Métricas:**
Q2.1: Qual o nível de conformidade com boas práticas de IaC exibido pelo código de cada ferramenta?
Q2.2: Quantas vulnerabilidades de segurança são introduzidas pelo código gerado por cada IA?
Q2.3: Qual a prevalência de valores hard-coded no código produzido por cada ferramenta?

**O3 - Comparação de Desempenho:**
Q3.1: Qual ferramenta de IA apresenta melhor desempenho global em conformidade para AWS versus Azure?
Q3.2: Como as ferramentas diferem na detecção e mitigação automática de vulnerabilidades de segurança?
Q3.3: Há correlação entre clareza do prompt e redução de valores hard-coded nas diferentes IAs?

**O4 - Recomendações Práticas:**
Q4.1: Quais padrões de prompts otimizam a qualidade do código gerado pelas melhores ferramentas identificadas?
Q4.2: De que forma a qualidade do código afeta o tempo que os revisores humanos levam para realizar uma revisão do código IaC?
Q4.3: Quais ferramentas complementares de linting são mais eficazes para mitigar falhas das IAs?

### 3.4 Métricas associadas (GQM)
#### Tabela GQM: Alinhamento Objetivo-Pergunta-Métrica

| Objetivo | Pergunta | Métricas Associadas |
| :-- | :-- | :-- |
| **O1** | Q1.1 | Taxa de Validação Sintática [%], Tempo de Geração [s] |
| **O1** | Q1.2 | Índice de Completude Estrutural [%], Cobertura de Outputs [%] |
| **O1** | Q1.3 | Densidade de Recursos Específicos por Cloud [recursos/arquivo] |
| **O2** | Q2.1 | Taxa de Conformidade TFLint [%], Pontuação de Boas Práticas [0-10] |
| **O2** | Q2.2 | Contagem de Vulnerabilidades Checkov [\#], Gravidade Média de Vulnerabilidades [1-10] |
| **O2** | Q2.3 | Contagem de Hard-Coded Values [\#], Taxa de Parametrização [%] |
| **O3** | Q3.1 | Ranking de Conformidade por Cloud [posição 1-3], Delta Conformidade AWS-Azure [%] |
| **O3** | Q3.2 | Taxa de Redução de Vulnerabilidades por IA [%], False Positives em Segurança [%] |
| **O3** | Q3.3 | Correlação Prompt Qualidade-Hard-Coded [r Pearson], Threshold de Clareza [%] |
| **O4** | Q4.1 | Eficiência de Prompts Otimizados [% melhoria], Variabilidade Intra-Prompt [DP] |
| **O4** | Q4.2 | Tempo Estimado de Revisão Manual [min/arquivo], Redução Estimada de Revisão [%] |
| **O4** | Q4.3 | Eficácia de Linting Complementar [% correção], Cobertura de Regras Ativas [%] |

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
**Incluído:** Geração automatizada de 150 códigos Terraform (.tf) a partir de 50 prompts variados, análise estática com TFLint (rulesets AWS/Azurerm) e Checkov, quantificação de 15 métricas GQM, comparação estatística entre Chat-GPT, Google Gemini e Claude AI, elaboração de recomendações. Artefatos: repositório GitHub com códigos versionados, dataset CSV com métricas, relatório analítico com visualizações.

**Excluído:** Execução real de provisionamento (`terraform apply`), análise dinâmica de performance em runtime, avaliação de custo computacional das IAs, testes com outras linguagens IaC (Ansible, CloudFormation), análise de experiência do usuário nas interfaces das IAs, validação em produção ou com usuários reais.

### 4.2 Contexto do estudo (tipo de organização, projeto, experiência)
O estudo será conduzido no âmbito de um trabalho do curso de Engenharia de Software, em uma universidade brasileira localizada em Belo Horizonte, Minas Gerais, caracterizando um contexto acadêmico de pesquisa individual. O projeto possui criticidade baixa (ambiente de simulação com contas AWS/Azure), executado por estudante com experiência em DevOps (AWS, Azure, Python, Git, Terraform), estatística e experimentação controlada, mas sem exposição a equipes industriais. A infraestrutura técnica compreende execução local (máquina pessoal), ferramentas CLI open-source e acesso via web às APIs de IA.

### 4.3 Premissas
- Estabilidade das APIs das ferramentas de IA (Chat-GPT, Gemini, Claude) durante período experimental.
- Consistência nas versões dos modelos de IA testados (ex: GPT-5, Gemini 2.5 Pro, Claude 4.5 Sonnet).
- Contas AWS/Azure que suportam simulações de `terraform plan` sem interrupções por custo.
- Ferramentas de linting (TFLint, Checkov) mantêm compatibilidade com Terraform v1.7+ e providers AWS/Azurerm atualizados.
- Prompts elaborados são representativos de cenários DevOps reais.

### 4.4 Restrições
- Orçamento limitado a R$200 (acesso pago às IAs e contas AWS/Azure).
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
**Go (Sucesso):** ≥90% dos 150 códigos gerados válidos sintaticamente; variância explicada ≥70% nas comparações entre IAs; pelo menos 2 recomendações acionáveis validadas estatisticamente (p<0.05); relatório com ≥15 visualizações GQM claras.
**No-go (Falha):** <70% códigos válidos ou nenhuma diferença estatística significativa entre IAs ou dataset incompleto (<120 códigos analisados).

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
**Para Q1 (Conformidade por ferramenta de IA)**

**H0_Q1:** As médias de conformidade com boas práticas de IaC são iguais entre as três ferramentas de IA, ou seja:  
Média_Conf_ChatGPT = Média_Conf_Gemini = Média_Conf_Claude.

**H1_Q1:** Pelo menos uma das ferramentas de IA apresenta média de conformidade diferente, sendo esperado que Claude AI e ChatGPT apresentem, em média, uma conformidade entre **75% e 85%**, enquanto o Google Gemini apresente entre **65% e 75%**.

---

**Para Q2 (Efeito da clareza do prompt)**

**H0_Q2a:** A média de vulnerabilidades detectadas não difere entre prompts de alta e baixa clareza, isto é:  
Média_Vuln_Alta = Média_Vuln_Baixa.

**H1_Q2a:** Prompts de alta clareza resultam em menos vulnerabilidades do que prompts de baixa clareza, com redução esperada de aproximadamente **1 a 2 vulnerabilidades por arquivo** (por exemplo, Média_Vuln_Alta ≈ 1–2 contra Média_Vuln_Baixa ≈ 3–4).

---

**H0_Q2b:** A média de valores hard-coded não difere entre prompts de alta e baixa clareza, isto é:  
Média_HC_Alta = Média_HC_Baixa.

**H1_Q2b:** Prompts de alta clareza resultam em menos valores hard-coded do que prompts de baixa clareza, com redução esperada de **30% a 40%** (por exemplo, Média_HC_Alta ≈ 2–3 valores por arquivo e Média_HC_Baixa ≈ 4–5).

---

**Para Q3 (Interação IA × Cloud)**

**H0_Q3:** Não há interação significativa entre ferramenta de IA e provedor de cloud na taxa de valores hard-coded, ou seja, a diferença entre as ferramentas é semelhante em AWS e Azure.

**H1_Q3:** Existe interação entre ferramenta de IA e provedor de cloud na taxa de valores hard-coded. Em particular:  
- **Claude AI** tende a gerar cerca de **2 valores hard-coded em Azure** e **3–4 em AWS**.  
- **ChatGPT** tende a gerar aproximadamente **3 valores hard-coded** em ambos os provedores.  
- **Google Gemini** tende a manter uma taxa mais alta e estável, cerca de **4–5 valores** em ambas as clouds.

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
| Chat-GPT | Alta | AWS | T1 | 25 |
| Chat-GPT | Alta | Azure | T2 | 25 |
| Chat-GPT | Baixa | AWS | T3 | 25 |
| Chat-GPT | Baixa | Azure | T4 | 25 |
| Gemini | Alta | AWS | T5 | 25 |
| Gemini | Alta | Azure | T6 | 25 |
| Gemini | Baixa | AWS | T7 | 25 |
| Gemini | Baixa | Azure | T8 | 25 |
| Claude | Alta | AWS | T9 | 25 |
| Claude | Alta | Azure | T10 | 25 |
| Claude | Baixa | AWS | T11 | 25 |
| Claude | Baixa | Azure | T12 | 25 |
| **Total** |  |  | **12 tratamentos** | **300** |

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
O desenho considera, conceitualmente, até doze grupos experimentais, formados pelas combinações entre três ferramentas de IA, dois níveis de clareza de prompt e dois provedores de cloud. Na prática, o experimento será conduzido em uma única “sessão” principal de execução, dividida em etapas: preparação dos prompts, geração dos códigos, execução das ferramentas de análise e consolidação dos resultados. A repetição de prompts ao longo das diferentes ferramentas de IA garante um número adequado de observações por combinação de fatores, sem necessidade de múltiplas sessões com participantes humanos.

## 10. População, sujeitos e amostragem

### 10.1 População-alvo
Descreva qual é a população real que você deseja representar com o experimento (por exemplo, "desenvolvedores Java de times de produto web").

### 10.2 Critérios de inclusão de sujeitos
Especifique os requisitos mínimos para um participante ser elegível (experiência, conhecimento, papel, disponibilidade, etc.).

### 10.3 Critérios de exclusão de sujeitos
Liste condições que impedem participação (conflitos de interesse, falta de skills essenciais, restrições legais ou éticas).

### 10.4 Tamanho da amostra planejado (por grupo)
Defina quantos participantes você pretende ter no total e em cada grupo, relacionando a decisão com poder, recursos e contexto.

### 10.5 Método de seleção / recrutamento
Explique como os participantes serão escolhidos (amostra de conveniência, sorteio, convite aberto, turma de disciplina, time específico).

### 10.6 Treinamento e preparação dos sujeitos
Descreva qual treinamento ou material preparatório será fornecido para nivelar entendimento e reduzir vieses por falta de conhecimento.

## 11. Instrumentação e protocolo operacional

### 11.1 Instrumentos de coleta (questionários, logs, planilhas, etc.)
Liste todos os instrumentos que serão usados para coletar dados (arquivos, formulários, scripts, ferramentas), com uma breve descrição do papel de cada um.

### 11.2 Materiais de suporte (instruções, guias)
Descreva as instruções escritas, guias rápidos, slides ou outros materiais que serão fornecidos a participantes e administradores do experimento.

### 11.3 Procedimento experimental (protocolo – visão passo a passo)
Escreva, em ordem, o que acontecerá na operação (do convite ao encerramento), de modo que alguém consiga executar o experimento seguindo esse roteiro.

### 11.4 Plano de piloto (se haverá piloto, escopo e critérios de ajuste)
Indique se um piloto será realizado, com que participantes e objetivos, e defina que tipo de ajuste do protocolo poderá ser feito com base nesse piloto.

## 12. Plano de análise de dados (pré-execução)

### 12.1 Estratégia geral de análise (como responderá às questões)
Explique, em alto nível, como os dados coletados serão usados para responder cada questão de pesquisa ou de negócio.

### 12.2 Métodos estatísticos planejados
Liste os principais testes ou técnicas estatísticas que pretende usar (por exemplo, t-teste, ANOVA, testes não paramétricos, regressão).

### 12.3 Tratamento de dados faltantes e outliers
Defina previamente as regras para lidar com dados ausentes e valores extremos, evitando decisões oportunistas após ver os resultados.

### 12.4 Plano de análise para dados qualitativos (se houver)
Descreva como você tratará dados qualitativos (entrevistas, comentários, observações), especificando a técnica de análise (codificação, categorias, etc.).

## 13. Avaliação de validade (ameaças e mitigação)

### 13.1 Validade de conclusão
Liste ameaças que podem comprometer a robustez das conclusões estatísticas (baixo poder, violação de suposições, erros de medida) e como pretende mitigá-las.

### 13.2 Validade interna
Identifique ameaças relacionadas a causas alternativas para os efeitos observados (history, maturation, selection, etc.) e explique suas estratégias de controle.

### 13.3 Validade de constructo
Reflita se as medidas escolhidas realmente representam os conceitos de interesse e descreva como você reduzirá ambiguidades de interpretação.

### 13.4 Validade externa
Discuta em que contextos os resultados podem ser generalizados e quais diferenças de cenário podem limitar essa generalização.

### 13.5 Resumo das principais ameaças e estratégias de mitigação
Faça uma síntese das ameaças mais críticas e das ações planejadas, de preferência em forma de lista ou tabela simples.

## 14. Ética, privacidade e conformidade

### 14.1 Questões éticas (uso de sujeitos, incentivos, etc.)
Descreva potenciais questões éticas (pressão para participar, uso de estudantes, incentivos, riscos de exposição) e como serão tratadas.

### 14.2 Consentimento informado
Explique como os participantes serão informados sobre objetivos, riscos, benefícios e como registrarão seu consentimento.

### 14.3 Privacidade e proteção de dados
Indique que dados pessoais serão coletados, como serão protegidos (anonimização, pseudoanonimização, controle de acesso) e por quanto tempo serão mantidos.

### 14.4 Aprovações necessárias (comitê de ética, jurídico, DPO, etc.)
Liste órgãos ou pessoas que precisam aprovar o experimento (comitê de ética, jurídico, DPO, gestores) e o status atual dessas aprovações.

## 15. Recursos, infraestrutura e orçamento

### 15.1 Recursos humanos e papéis
Identifique os membros da equipe do experimento e descreva brevemente o papel e responsabilidade de cada um.

### 15.2 Infraestrutura técnica necessária
Liste ambientes, servidores, ferramentas, repositórios e integrações que devem estar disponíveis para executar o experimento.

### 15.3 Materiais e insumos
Relacione materiais físicos ou digitais necessários (máquinas, licenças, formulários, dispositivos) que precisam estar prontos antes da operação.

### 15.4 Orçamento e custos estimados
Faça uma estimativa dos principais custos envolvidos (horas de pessoas, serviços, licenças, infraestrutura) e a fonte de financiamento.

## 16. Cronograma, marcos e riscos operacionais

### 16.1 Macrocronograma (até o início da execução)
Defina as principais datas e marcos (conclusão do plano, piloto, revisão, início da operação) com uma visão de tempo realista.

### 16.2 Dependências entre atividades
Indique quais atividades dependem de outras para começar (por exemplo, treinamento após aprovação ética), deixando essas dependências claras.

### 16.3 Riscos operacionais e plano de contingência
Liste riscos ligados a cronograma, disponibilidade de pessoas ou recursos, e descreva ações de contingência caso esses riscos se materializem.

## 17. Governança do experimento

### 17.1 Papéis e responsabilidades formais
Defina quem decide, quem executa, quem revisa e quem apenas deve ser informado, deixando claro o fluxo de responsabilidade.

### 17.2 Ritos de acompanhamento pré-execução
Descreva as reuniões, checkpoints e revisões previstos antes da execução, incluindo frequência e participantes.

### 17.3 Processo de controle de mudanças no plano
Explique como mudanças no desenho ou no escopo do experimento serão propostas, analisadas, aprovadas e registradas.

## 18. Plano de documentação e reprodutibilidade

### 18.1 Repositórios e convenções de nomeação
Indique onde o plano, instrumentos, scripts e dados (futuros) serão armazenados e quais convenções de nomes serão usadas.

### 18.2 Templates e artefatos padrão
Liste os modelos (questionários, formulários, checklists, scripts) que serão usados e onde podem ser encontrados.

### 18.3 Plano de empacotamento para replicação futura
Descreva o que será organizado desde já (documentos, scripts, instruções) para facilitar a replicação do experimento por outras equipes ou no futuro.

## 19. Plano de comunicação

### 19.1 Públicos e mensagens-chave pré-execução
Liste os grupos que precisam ser comunicados e quais mensagens principais devem receber (objetivos, escopo, datas, impactos esperados).

### 19.2 Canais e frequência de comunicação
Defina por quais canais (e-mail, reuniões, Slack/Teams, etc.) e com que frequência as comunicações serão feitas.

### 19.3 Pontos de comunicação obrigatórios
Especifique os eventos que exigem comunicação formal (aprovação do plano, mudanças relevantes, adiamentos, cancelamentos).

## 20. Critérios de prontidão para execução (Definition of Ready)

### 20.1 Checklist de prontidão (itens que devem estar completos)
Liste os itens que precisam estar finalizados e aprovados (plano, instrumentos, aprovação ética, recursos, comunicação) para autorizar o início da operação.

### 20.2 Aprovações finais para iniciar a operação
Indique quem precisa dar o "ok final" (nomes ou cargos) e como esse aceite será registrado antes da execução começar.
