# Índice de Soberania Fática (ISF) - Dados e Modelos Computacionais

Este repositório reúne os conjuntos de dados, scripts de calibração paramétrica e modelos de aprendizado de máquina não supervisionado desenvolvidos no âmbito da dissertação de mestrado apresentada ao Programa de Pós-Graduação em Direito da Universidade Estácio de Sá (PPGD/UNESA).

---

## 1. Estrutura dos Modelos Empíricos

O arcabouço computacional operacionaliza a mensuração da soberania em termos fáticos e materiais, estruturando-se em duas etapas algorítmicas principais:

1. **Calibração Paramétrica da Base de Inovação Civil (WIPO):** Análise de sensibilidade (*Grid Search*) para determinar a fronteira ótima de ponderação entre o núcleo militar dissuasório e a base tecnológica civil.
2. **Clusterização de Estatutos Estratégicos (K-Means):** Agrupamento não supervisionado ancorado por baricentros ontológicos para classificação de 17 Estados da amostra internacional.

---

## 2. Visualizações dos Resultados

### Figura 1: Calibração Paramétrica do Peso WIPO via Análise de Sensibilidade
Determinação do ponto crítico de estabilidade paramétrica ($12\%$) para a base WIPO, prevenindo anomalias de ordenamento no núcleo militar.

![Calibração Paramétrica WIPO](grafico1_sensibilidade_wipo.png)

* **Script correspondente:** `grafico1_sensibilidade_wipo.py`

---

### Figura 2: Matriz de Soberania Fática vs. Autonomia Dissuasória (ISF 88/12)
Partição em quatro clusters (*Soberania Plena*, *Soberania Resiliente*, *Soberania Tutelada* e *Soberania Condicionada*) via algoritmo K-Means ($k=4$).

![Matriz ISF K-Means](grafico2_matriz_isf_kmeans.png)

* **Script correspondente:** `grafico2_matriz_isf_kmeans.py`

---

## 3. Especificação Metodológica das Variáveis

* **Dissuasão Nuclear / Segundo Ataque:** Mensuração do limiar de sobrevivência e veto existencial soberano.
* **Vetores Balísticos Orbitais:** Capacidade autóctone de lançamento espacial e mísseis estratégicos.
* **Domínio Fabril de Turbinas / 5ª Geração:** Autonomia na cadeia produtiva aeroespacial e propulsão.
* **Escore WIPO Normalizado:** Volume e densidade de patentes residentes via normalização Min-Max.

---

## 4. Como Citar

```bibtex
@misc{oliveira2026isf,
  author = {Oliveira, Guilherme Fontenelle Ribeiro de},
  title = {Repositório Institucional de Dados e Códigos: Índice de Soberania Fática (ISF)},
  year = {2026},
  publisher = {GitHub},
  journal = {GitHub repository},
  howpublished = {\url{[https://github.com/guilherme68-linux/dissertacao-mestrado-soberania-isf](https://github.com/guilherme68-linux/dissertacao-mestrado-soberania-isf)}}
}
