# Mission Control AI - Missão Aleph-01 

Repositório destinado ao sistema de monitoramento e análise de dados da missão espacial **Aleph-01**, desenvolvido para avaliar a integridade dos sistemas durante múltiplos ciclos operacionais.

##  Integrantes da Equipe 01
* **Julia Johanson Peniche Dias Da Silva** - RM: 572220
* **Lucas Bomfim Leite** - RM: 570420
* **Eduardo Barcelos De Carvalho Braziliano** - RM: 573274

---

##  Descrição da Solução

O **Mission Control AI** é um script em Python projetado para atuar como um sistema de suporte à decisão e monitoramento contínuo de missões críticas. O sistema recebe uma matriz de dados onde cada linha representa um "ciclo" da missão e as colunas representam os níveis aferidos de cinco áreas vitais:

1. Temperatura interna (°C)
2. Comunicação com a base (%)
3. Sistema de energia / Bateria (%)
4. Suporte de oxigênio (%)
5. Estabilidade operacional (%)

Com base nesses dados, a solução analisa cada métrica individualmente, atribuindo um nível de gravidade (Normal, Atenção ou Crítico) e uma pontuação de risco. Ao final do processamento, o sistema emite relatórios detalhados ciclo a ciclo e um **Relatório Final** consolidado, fornecendo conclusões sobre a tendência da missão e identificando as áreas mais afetadas que requerem manutenção.

---

##  Arquitetura e Fluxo do Sistema

A arquitetura do código foi construída de forma modular utilizando funções puras para avaliação de regras de negócio. O fluxo de execução segue as seguintes etapas:

1. **Entrada de Dados (Mock):** Os dados da missão são carregados através da matriz `dados_missao`.
2. **Iteração de Ciclos:** O sistema percorre cada linha da matriz utilizando um laço de repetição (`for`), extraindo os valores de cada sensor.
3. **Módulos de Análise (Regras de Negócio):** Os valores são passados por funções validadoras independentes (ex: `analisar_temperatura`, `analisar_oxigenio`), que retornam o *status*, a *pontuação de risco* e uma *mensagem de diagnóstico*.
4. **Cálculo de Risco e Classificação:** As pontuações de todas as áreas são somadas para classificar o ciclo atual ("MISSÃO ESTÁVEL", "MISSÃO EM ATENÇÃO", "MISSÃO CRÍTICA") e gerar uma recomendação imediata.
5. **Consolidação de Dados:** Variáveis acumuladoras registram o histórico de pontuações, médias de operação e a tendência geral da missão (melhora, piora ou estável).
6. **Emissão de Relatório:** O sistema imprime no console o diagnóstico de cada ciclo e encerra com um relatório analítico contendo o ciclo mais crítico, o risco médio e a área de maior vulnerabilidade.

---

##  Instruções Básicas de Uso

Para executar este sistema em sua máquina local, siga os passos abaixo:

**Pré-requisitos:**
* Ter o [Python 3.x](https://www.python.org/downloads/) instalado na sua máquina.

**Passo a passo:**
1. Faça o clone deste repositório ou baixe o arquivo `.py` com o código-fonte.
2. Abra o terminal (ou prompt de comando) e navegue até o diretório onde o arquivo está salvo.
3. Execute o script utilizando o comando:
   ```bash
   python nome_do_arquivo.py
