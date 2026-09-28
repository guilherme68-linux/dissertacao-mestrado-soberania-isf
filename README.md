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
