📊 Análise de Dados do ENEM 2023 – Capitais do Nordeste
Pipeline completo de tratamento, pré-processamento e análise exploratória e de clusterização dos microdados do ENEM 2023, com foco nas nove capitais da região Nordeste do Brasil. O objetivo é transformar dados brutos em insights acionáveis.

🌟 Resumo do Projeto
O projeto é estruturado em duas fases principais:

Tratamento e Pré-processamento: Limpeza, filtragem (foco em capitais do Nordeste), encoding de variáveis e redução dimensional.

Análise e Clusterização (K-Means): Aplicação de algoritmos de agrupamento para identificar perfis de estudantes e validação estatística dos resultados.

📁 Estrutura do Repositório
Caminho	Descrição
tratamento_dados_enem2.ipynb	Notebook Principal: Carregamento, limpeza, transformação e visualização inicial.
clustering_enem/clusterizacao_enem.ipynb	Notebook de Clusterização: Análise K-Means, seleção de k ideal e validação.
data/	Contém dados tratados (microdados_enem_tratados2.csv) e intermediários.
outputs/	Resultados: Mapas, gráficos, estatísticas e o relatório final.
MICRODADOS_ENEM_2023.csv	Entrada: Microdados brutos do ENEM (não incluso, deve ser obtido no INEP).
🔧 Fase 1: Processamento e Limpeza de Dados
O primeiro notebook (tratamento_dados_enem2.ipynb) lida com a preparação dos dados:

⚙️ Etapas de Tratamento
Carregamento: Leitura de CSV com separador ; e encoding latin1.

Filtragem: Foco nas 9 capitais do Nordeste e participantes que concluíram ou estão concluindo o Ensino Médio.

Correção de Coluna: NO_MUNICIPIO_ESCOLA foi substituída por NO_MUNICIPIO_PROVA.

Encoding: Uso de One-Hot Encoding (variáveis nominais) e Label Encoding (variáveis socioeconômicas ordinais Q001–Q025).

Visualização Geográfica: Utilização da biblioteca geobr para gerar um Mapa de Calor das notas médias por estado do Nordeste.

🧠 Fase 2: Análise de Clusterização (K-Means)
O segundo notebook (clustering_enem/clusterizacao_enem.ipynb) realiza a identificação de perfis:

🎯 Variáveis-Chave Utilizadas
Desempenho: NU_NOTA_MEDIA (Nota Média nas áreas do conhecimento).

Socioeconômicas: Q001 (Escolaridade do Pai), Q002 (Escolaridade da Mãe), Q006 (Renda Familiar), Q024 (Computador), Q025 (Internet).

Escola: TP_ESCOLA (Tipo de escola) e TP_COR_RACA (Raça/Cor).

📈 Métodos e Resultados
Método	Uso
K-Means	Agrupamento dos estudantes.
Cotovelo e Silhueta	Determinação do número ideal de clusters (k=3).
ANOVA	Validação estatística (diferenças significativas entre grupos).
🚀 Perfis de Cluster Identificados (3 Grupos)
Cluster	Descrição do Perfil	Estatística de Exemplo
🔴 Vulnerável	Baixa escolaridade parental, menor renda e acesso limitado a recursos.	Nota Média: 500.03
🟡 Intermediário	Características socioeconômicas medianas e mistas.	Nota Média: 575.62
🟢 Privilegiado	Maior escolaridade parental, alta renda, acesso a recursos tecnológicos e escola privada.	Nota Média: 660.00
🛠️ Como Executar
1. Dependências
Instale as bibliotecas necessárias:

bash
pip install pandas numpy matplotlib seaborn scikit-learn plotly geobr python-docx
2. Execução
Obtenha o arquivo MICRODADOS_ENEM_2023.csv e coloque-o no diretório raiz do projeto.

Execute em sequência os notebooks:

tratamento_dados_enem2.ipynb

clustering_enem/clusterizacao_enem.ipynb

Os arquivos intermediários e as visualizações finais (mapas, gráficos) serão salvos automaticamente nas pastas data/ e outputs/.

📊 Análise de Clusterização – Dados do ENEM no Nordeste
Este projeto realiza uma análise de clusterização utilizando dados do ENEM de estudantes do Nordeste brasileiro, com o objetivo de identificar perfis socioeconômicos e de desempenho acadêmico.

📌 Objetivo
Identificar grupos de estudantes com características socioeconômicas e desempenhos semelhantes, permitindo uma análise regionalizada e a proposição de políticas públicas direcionadas.

🧮 Métodos de Clusterização
Foram utilizados os seguintes métodos para determinar o número ideal de clusters:

Método do Cotovelo (Elbow Method)

Método da Silhueta (Silhouette Score)

Método Davies-Bouldin

📊 Resultados Principais
Clusters Identificados (3 grupos):
Vulnerável – Baixa escolaridade dos pais, menor renda, menor acesso a recursos.

Intermediário – Características medianas entre vulnerável e privilegiado.

Privilegiado – Maior escolaridade dos pais, maior renda, acesso a recursos tecnológicos e escola privada.

Estatísticas por Cluster:
Variável	Vulnerável	Intermediário	Privilegiado
Renda Familiar (Q006)	1.55	3.56	10.82
Computador em Casa	0.19	0.71	2.21
Escola Privada	0.03	0.47	0.94
Nota Média	500.03	575.62	660.00
🗺️ Visualizações Geradas
Mapa coroplético do Nordeste com cluster predominante por estado

Gráficos de dispersão (PCA 2D e 3D)

Gráficos de barras com distribuição proporcional por estado

Documento Word com tabela comparativa entre os grupos sociais

📄 Relatório de Validação Estatística
Foi aplicada ANOVA para validar a significância estatística das diferenças entre clusters. Todas as variáveis socioeconômicas apresentaram p-valor < 0.05, indicando que os clusters são estatisticamente distintos.

📌 Observações
Os dados utilizados são do ENEM, tratados e filtrados para o Nordeste.

O tratamento inclui normalização de texto, codificação de variáveis categóricas e remoção de outliers.

O relatório final em Word é gerado automaticamente ao final da execução.

🔭 Análises Futuras
Correlações: Detalhamento da relação entre Fatores Socioeconômicos e Desempenho.

Séries Temporais: Análise da evolução das notas por estado/ano para identificar tendências históricas.

melhore a escrita desse readme. nao está com destaque nem nada.


