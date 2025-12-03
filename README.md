📊 Análise de Dados do ENEM 2023 – Capitais do Nordeste

Pipeline completo de tratamento, pré-processamento, análise exploratória e clusterização dos microdados do ENEM 2023, com foco nas nove capitais do Nordeste do Brasil.
O objetivo é transformar dados brutos em insights acionáveis sobre desempenho e fatores socioeconômicos.

🌟 Resumo do Projeto

O projeto é dividido em duas grandes fases:

1️⃣ Tratamento e Pré-processamento

Limpeza de dados e padronização de colunas

Filtragem para estudantes das capitais do Nordeste

Encoding (One-Hot e Label Encoding)

Redução dimensional e primeiras visualizações

2️⃣ Análise e Clusterização (K-Means)

Identificação de perfis socioeconômicos

Avaliação com Elbow, Silhouette e Davies-Bouldin

Validação estatística com ANOVA

Visualizações geográficas e relatórios automatizados

📁 Estrutura do Repositório
Caminho	Descrição
tratamento_dados_enem2.ipynb	Notebook principal de limpeza, transformação e visualização inicial
clustering_enem/clusterizacao_enem.ipynb	Notebook de clusterização com K-Means e validação
data/	Dados tratados e intermediários (ex.: microdados_enem_tratados2.csv)
outputs/	Gráficos, mapas, tabelas e relatório final
MICRODADOS_ENEM_2023.csv	Microdados brutos do ENEM (não incluído no repositório)
🔧 Fase 1 — Processamento e Limpeza
⚙️ Principais Etapas

Carregamento:

Leitura do CSV com ; e encoding latin1.

Filtragem:

Foco nas 9 capitais do Nordeste.

Apenas estudantes que concluíram ou estão concluindo o Ensino Médio.

Correções:

Coluna NO_MUNICIPIO_ESCOLA substituída por NO_MUNICIPIO_PROVA.

Codificação:

One-Hot Encoding para variáveis nominais

Label Encoding para variáveis socioeconômicas Q001–Q025.

Visualização Geográfica:

Uso de geobr para criar mapa de calor das notas.

🧠 Fase 2 — Clusterização (K-Means)
🎯 Variáveis Utilizadas

Desempenho:

NU_NOTA_MEDIA (média das 5 áreas)

Socioeconômicas:

Q001 – Escolaridade do pai

Q002 – Escolaridade da mãe

Q006 – Renda familiar

Q024 – Computador

Q025 – Internet

Escola / Demografia:

TP_ESCOLA

TP_COR_RACA

📈 Métodos de Análise
Método	Uso
K-Means	Algoritmo de agrupamento
Elbow Method	Determinação do k ideal
Silhouette Score	Avaliação da separação entre clusters
Davies-Bouldin	Validação de coesão x dispersão
ANOVA	Teste estatístico entre clusters

Resultado: 3 clusters (k = 3)

🚀 Perfis de Cluster Identificados
📌 Resumo dos 3 Grupos
Cluster	Descrição do Perfil	Nota Média
🔴 Vulnerável	Baixa renda, pouca escolaridade parental, acesso tecnológico limitado	500.03
🟡 Intermediário	Condições medianas e heterogêneas	575.62
🟢 Privilegiado	Alta renda, pais com maior escolaridade, acesso a recursos e escola privada	660.00
📊 Estatísticas Socioeconômicas por Cluster
Variável	Vulnerável	Intermediário	Privilegiado
Renda Familiar (Q006)	1.55	3.56	10.82
Computador em Casa (Q024)	0.19	0.71	2.21
Escola Privada (%)	0.03	0.47	0.94
🗺️ Visualizações Geradas

Mapa coroplético do Nordeste mostrando o cluster predominante

PCA 2D e PCA 3D

Gráficos de distribuição por estado

Gráficos de barras comparando variáveis socioeconômicas

Documento Word automático com comparações entre clusters

📄 Validação Estatística

Foi aplicada ANOVA para todas as variáveis socioeconômicas e de desempenho.
Resultado: p-valor < 0.05 em todas as variáveis, indicando que:

✔️ Os clusters são estatisticamente distintos.

🛠️ Como Executar
1️⃣ Instalar dependências
pip install pandas numpy matplotlib seaborn scikit-learn plotly geobr python-docx

2️⃣ Organizar dados

Coloque o arquivo MICRODADOS_ENEM_2023.csv no diretório raiz.

3️⃣ Executar notebooks

Na ordem:

tratamento_dados_enem2.ipynb

clustering_enem/clusterizacao_enem.ipynb

Os arquivos tratados e os gráficos serão salvos automaticamente nas pastas data/ e outputs/.

🔭 Possíveis Análises Futuras

Análise de correlação entre fatores socioeconômicos e notas

Séries temporais para comparação inter-anos por estado

Modelos preditivos de desempenho (Regressão / Gradient Boosting)

Análise espacial mais detalhada por bairro / escola (caso disponível)

