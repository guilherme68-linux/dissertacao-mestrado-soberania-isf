# Índice de Soberania Fática (ISF) - Dados, Modelos Computacionais e Documentos Suplementares

Este repositório reúne os conjuntos de dados empíricos, scripts de calibração paramétrica, rotinas matriciais multicritério e algoritmos de aprendizado de máquina não supervisionado desenvolvidos no âmbito da dissertação de mestrado apresentada ao Programa de Pós-Graduação em Direito da Universidade Estácio de Sá (PPGD/UNESA).

A arquitetura do projeto integra jurimetria, teoria do Estado e inteligência computacional aplicada à segurança e defesa nacional, contemplando a formalização metodológica dos três apêndices técnicos da dissertação:

* **APÊNDICE A – Memória de Cálculo dos Subvetores do Índice de Soberania Fática (ISF):** Fundamentação psicofísica (Weber-Fechner), modelagem analítica AHP de Thomas Saaty com consistência estrita ($CR = 0,0000$) via Perron-Frobenius e validação paramétrica dos 18 países da amostra.
* **APÊNDICE B – Modelagem Computacional e Agrupamento Não Supervisionado (K-Means):** Pipeline em Python, padronização estatística por *Z-Score* (*StandardScaler*) e particionamento euclidiano em quatro clusters ontológicos ($k = 4$).
* **APÊNDICE C – Matriz Contábil do Descompasso Financeiro e Teoria dos Grafos:** Auditoria orçamentária do SIOP (Ação 14T5 - SISFRON vs. GLO / Intervenção Federal) sob a ótica da Teoria das Escolhas Trágicas e modelagem de redes da cadeia de suprimentos da defesa.

---

## 1. Estrutura dos Modelos Empíricos e Pipeline Jurimétrico

O arcabouço computacional operacionaliza a mensuração da soberania em termos fáticos e materiais a partir de um pipeline reproduzível em três etapas algorítmicas:

1. **Partição da Reserva Militar via Processo de Hierarquia Analítica (AHP de Saaty):** Modelagem pareada recíproca ancorada nos limiares psicofísicos de Weber-Fechner (degrau tático marginal de 10% e degrau estruturante de 20%) para dedução axiomática e unívoca dos escores máximos dos subvetores:
   * **$X_1$ (Propulsão Nobre e Soberania Lógica):** Teto de $0,33$ ($\alpha_1 = 0,18$ e $\alpha_2 = 0,15$);
   * **$X_2$ (Dissuasão Nuclear, Segundo Ataque e Latência):** Teto de $0,30$ ($\beta_1 = 0,16$, $\beta_2 = 0,14$ e $\beta_3 = 0,18$);
   * **$X_3$ (Espaço, Vetores Balísticos e Navegação PNT):** Teto de $0,25$ ($\gamma_1 = 0,10$, $\gamma_2 = 0,08$ e $\gamma_3 = 0,07$);
   * **Macrovetor Militar Consolidado:** $M = X_1 + X_2 + X_3 = 0,88$ (88% do índice global).
2. **Calibração da Base de Inovação Tecnológica Civil (WIPO):** Delimitação da reserva científico-industrial de uso dual ($W \le 0,12$, representando 12% do esforço global), extraída dos depósitos internacionais de patentes de alta tecnologia (PCT) da Organização Mundial da Propriedade Intelectual.
3. **Clusterização de Estatutos Estratégicos (K-Means, $k = 4$):** Agrupamento não supervisionado sobre o plano cartesiano bidimensional $[ISF \times \text{Autonomia Dissuasória Direta } Y]$, categorizando com isenção matemática as **18 nações da amostra internacional** em quatro estratos:
   * **Cluster Verde (Soberania Plena — 6 países):** Estados Unidos, China, Rússia, França, Reino Unido e Índia;
   * **Cluster Azul (Soberania Resiliente — 4 países):** Israel, Coreia do Norte, Paquistão e Irã;
   * **Cluster Vermelho (Soberania Tutelada — 4 países):** Suécia, Coreia do Sul, Turquia e Polônia;
   * **Cluster Laranja (Soberania Condicionada — 4 países):** Brasil, Argentina, Arábia Saudita e Suíça.

---

## 2. Estrutura do Repositório e Scripts de Auditoria

```text
├── data/
│   ├── amostra_18_paises_isf.csv                # Matriz com indicadores SIPRI, IISS, AIEA e WIPO
│   └── siop_orcamento_sisfron_glo_2012_2025.csv # Série histórica orçamentária do SIOP
├── apendices/
│   ├── Apendice_A_Memoria_de_Calculo_ISF.pdf    # Dedução matemática detalhada e justificativa pericial
│   ├── Apendice_B_Pipeline_KMeans_Python.pdf    # Documentação do particionamento não supervisionado
│   └── Apendice_C_Matriz_Contabil_SISFRON.pdf   # Demonstração contábil do hiato financeiro
├── scripts/
│   ├── script_01_ahp_perron_frobenius.py        # Resolução dos autovetores dominantes e teste CR = 0,0000
│   ├── script_02_kmeans_clusterizacao.py        # Normalização StandardScaler, K-Means (k=4) e plotagem
│   ├── grafico_sisfron_planejado_vs_pago.py     # Auditoria do hiato orçamentário (Ação 14T5 do SIOP)
│   └── grafico_escolhas_tragicas_glo_sisfron.py # Custo de oportunidade pericial (GLO vs. SISFRON)
└── README.md
---

## 3. Especificação Metodológica das Variáveis

* **Propulsão Nobre e Soberania Lógica ($X_1$ – Teto: 0,33):** Domínio metalúrgico de turbofans militares supersônicos de alto empuxo (superligas monocristalinas) e imunidade a embargos externos (regime ITAR) pela posse irrestrita do código-fonte do computador de bordo e radares AESA.
* **Dissuasão Nuclear e Segundo Ataque ($X_2$ – Teto: 0,30):** Modelagem disjunta via operador máximo $\max(\text{Arsenal Operacional}, \text{Latência Crítica})$. Mensura a capacidade de segundo ataque garantido (SSBN) e a capacidade de enriquecimento isotópico autóctone de $^{235}\text{U}$ em instalações protegidas.
* **Espaço, Mísseis e Alcance Cinético ($X_3$ – Teto: 0,25):** Vetores balísticos intercontinentais pesados (ICBM), veículos lançadores de satélites com infraestrutura de tiro (SLV) e autonomia de sinais militares criptografados via constelação própria de Posicionamento, Navegação e Tempo (PNT).
* **Base Civil WIPO ($W$ – Teto: 0,12):** Volume e densidade de patentes residentes internacionais via Tratado PCT/OMPI, mensurando a sustentabilidade científico-industrial dual no tempo.
* **Eixo Vertical ($Y$):** Autonomia Militar Dissuasória Direta: $Y = \left(\frac{M}{0,88}\right) \times 100\%$.
* **Eixo Horizontal ($X$):** Índice de Soberania Fática global: $X = ISF = M + W$.

---

## 4. Descrição Detalhada da Metodologia e Fundamentação Científica

### 4.1. Fundamentação Dogmática e Jurimétrica: Da Soberania Nominal à Soberania Fática
O Direito Constitucional contemporâneo e a Teoria Geral do Estado enfrentam uma crise de efetividade quando confrontados com a anarquia das relações internacionais do século XXI. A soberania proclamada formalmente em tratados e textos constitucionais (Art. 1º, I, da CF/88) frequentemente degenera em mera *soberania nominal* (na acepção de Karl Loewenstein e Stephen Krasner) se desprovida do lastro material que Ferdinand Lassalle denominou de *fatores reais de poder* (*Machtfaktoren*).

O **Índice de Soberania Fática (ISF)** estabelece uma ponte jurimétrica entre o comando normativo supremo e a eficácia material do poder estatal. Sob o prisma do postulado da **Proibição da Proteção Deficiente (*Untermassverbot*)**, o modelo quantifica o **Mínimo Existencial Estratégico** — isto é, o conjunto de capacidades materiais, tecnológicas e operacionais irredutíveis sem as quais o Estado brasileiro não detém capacidade autônoma de veto existencial, convertendo sua soberania em ficção jurídica perante o decisionismo das superpotências.

### 4.2. Dedução Analítica dos Subvetores Militares ($M = 0,88$) via AHP e Psicofísica de Weber-Fechner
A calibração dos tetos máximos dos subvetores militares críticos ($X_1 = 0,33$; $X_2 = 0,30$; $X_3 = 0,25$) não resultou de ajustes empíricos discricionários (*overfitting*), mas da resolução analítica de Matrizes Pareadas de Decisão Recíproca segundo o Método de Análise Hierárquica (*Analytic Hierarchy Process* - AHP) de Thomas Saaty.

Para contornar as distorções da escala discreta tradicional de Saaty (1 a 9) — que geraria saltos abruptos de 300% a 500% entre ativos de sobrevivência estatal —, a modelagem ancorou-se nos postulados psicofísicos de **Weber-Fechner** sobre limiares de percepção proporcional (*Just Noticeable Difference* - JND), estruturando-se em uma malha de granularidade fina:
1. **Degrau Tático Operacional (10% ou fator 1,10):** Reflete a assimetria funcional mínima de emprego contínuo (ex.: a aviação de caça convencional voando 24 horas por dia em $X_1$ precedendo a dissuasão nuclear estática em $X_2$, segundo o Paradoxo Estabilidade-Instabilidade de Snyder);
2. **Degrau Existencial Estruturante (20% ou fator 1,20):** Reflete o dobro da assimetria tática, demarcando uma barreira física, metalúrgica ou ontológica intransponível (ex.: a aniquilação nuclear terminal em $X_2$ sobrepondo-se ao alcance cinético convencional em $X_3$; e a inércia secular da física de materiais de alta temperatura em turbofans $\alpha_1$ sobre a maleabilidade cíclica da reprogramação de software $\alpha_2$).

A transitividade axiomática perfeita ($a_{ik} = a_{ij} \cdot a_{jk}$) garante, pelo **Teorema de Perron-Frobenius**, que o maior autovalor dominante ($\lambda_{\max}$) seja exatamente igual à dimensão matricial ($n$), certificando analiticamente um **Índice de Consistência Nulo ($CR = 0,0000$)** em todos os níveis hierárquicos do modelo.

### 4.3. Pipeline Computacional, Normalização Multivariada e Machine Learning
A esteira de processamento de dados (*data pipeline*) implementada em Python divide-se em três etapas computacionais auditáveis:
1. **Padronização Estatística por Z-Score (`StandardScaler`):** Grandezas físicas heterogêneas (escores fracionários militares de $0,00$ a $0,88$ e registros absolutos de patentes civis WIPO) são redimensionadas para média zero ($\mu = 0$) e variância unitária ($\sigma = 1$), eliminando distorções de magnitude no cálculo das distâncias geométricas;
2. **Agrupamento Não Supervisionado (`K-Means`, $k = 4$):** Processamento do algoritmo de aprendizado de máquina sobre o plano cartesiano euclidiano $[\text{ISF} \times \text{Autonomia Dissuasória Direta } Y]$, com inicialização ancorada em centróides teóricos nodais para garantir estabilidade topológica e neutralidade ideológica;
3. **Métrica de Validação de Clusterização:** Acomodação dos 18 países em 4 estratos ontológicos (*Soberania Plena, Resiliente, Tutelada e Condicionada*), atestada por testes de compacidade e separabilidade (*Silhouette Score* e Método do Cotovelo).

### 4.4. Fontes Primárias Oficiais e Governança de Dados
A pesquisa apoia-se exclusivamente em inventários periciais e relatórios de inteligência estratégica homologados internacionalmente:
* **Capacidade Bélica e Aviação:** International Institute for Strategic Studies (IISS — *The Military Balance*, edições 2022 a 2026);
* **Forças Nucleares e Transferências de Armas:** Stockholm International Peace Research Institute (SIPRI — *World Nuclear Forces* e *Arms Transfers Database*, 2024);
* **Ciclo de Combustível e Enriquecimento ($^{235}\text{U}$):** Agência Internacional de Energia Atômica (AIEA — *Safeguards Implementation Reports*, 2024);
* **Inovação Tecnológica Civil de Uso Dual:** World Intellectual Property Organization (WIPO/OMPI — *IP Statistics Data Center*, depósitos via Tratado PCT, 2024);
* **Execução Orçamentária Federal:** Sistema Integrado de Planejamento e Orçamento (SIOP/MPO — Série Histórica 2012–2025 das Ações 14T5/SISFRON e 20ZF/GLO).

---

## 5. Como Citar

### Referência Bibliográfica (ABNT NBR 6023:2018)
OLIVEIRA, Guilherme Fontenelle Ribeiro de. **ISF – Índice de Soberania Fática**: pipeline computacional jurimétrico, matrizes AHP de Saaty e agrupamento não supervisionado K-Means. Rio de Janeiro: GitHub, 2026. Disponível em: https://github.com/guilherme68-linux/ISF-Soberania-Fatica. Acesso em: 28 set. 2026.

### Entrada BibTeX
```bibtex
@misc{oliveira2026isf,
  author       = {Oliveira, Guilherme Fontenelle Ribeiro de},
  title        = {ISF -- {\'I}ndice de Soberania F{\'a}tica: pipeline computacional jurim{\'e}trico, matrizes AHP de Saaty e agrupamento n{\~a}o supervisionado K-Means},
  year         = {2026},
  publisher    = {GitHub},
  journal      = {GitHub repository},
  howpublished = {\url{[https://github.com/guilherme68-linux/ISF-Soberania-Fatica](https://github.com/guilherme68-linux/ISF-Soberania-Fatica)}},
  institution  = {Programa de P{\'o}s-Gradua{\c{c}}{\~a}o em Direito, Universidade Est{\'a}cio de S{\'a} (PPGD/UNESA)},
  address      = {Rio de Janeiro, Brasil},
  note         = {Acesso em: 28 set. 2026}
}
