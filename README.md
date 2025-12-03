📊 Análise de Dados do ENEM 2023 – Capitais do Nordeste

Este repositório contém o pipeline completo de tratamento, pré-processamento e análise exploratória dos microdados do ENEM 2023, com foco nas nove capitais da região Nordeste.
O projeto inclui limpeza dos microdados, encoding das variáveis, geração de datasets intermediários e criação de visualizações geográficas.

📁 Estrutura do Projeto
🧠 Notebook Principal

tratamento_dados_enem2.ipynb
Contém todo o pipeline de carregamento, limpeza, transformação e visualização dos dados.

📚 Arquivos de Dados
Entrada

MICRODADOS_ENEM_2023.csv — Microdados brutos do ENEM 2023 (formato original do INEP)

Intermediários

microdados_enem_tratados.csv — Dataset filtrado e limpo

microdados_enem_tratados2.csv — Dataset após pré-processamento completo (encoding + ajustes)

Saída

nota_enem_nordeste.png — Mapa de calor das notas médias por estado

🔧 Processamento de Dados
1️⃣ Carregamento Inicial

Leitura de arquivo CSV com:

Separador ;

Encoding latin1

Mais de 60 variáveis relacionadas a:

Dados socioeconômicos

Notas das provas

Informações demográficas e escolares

2️⃣ Filtragem Inicial

Foco em estudantes das capitais do Nordeste:

Aracaju, Fortaleza, João Pessoa, Maceió, Natal, Recife, Salvador, São Luís e Teresina

Filtros aplicados:

Apenas participantes que concluíram ou estão concluindo o Ensino Médio

Correção de coluna inexistente (NO_MUNICIPIO_ESCOLA → NO_MUNICIPIO_PROVA)

3️⃣ Tratamento de Variáveis

Raça/Cor recodificada (Branca = 1, demais = 0)

Remoção de valores inválidos (ex.: "Não sei")

Transformação de variáveis binárias (1 = Sim / 0 = Não)

Redução para 22 variáveis principais

4️⃣ Encoding

One-Hot Encoding:

TP_SEXO, TP_LOCALIZACAO_ESC, entre outras

Label Encoding:

Questões socioeconômicas (Q001–Q025)

Faixa etária, escolaridade etc.

5️⃣ Geoprocessamento

Uso da biblioteca geobr

Recorte para estados do Nordeste:
AL, BA, CE, MA, PB, PE, PI, RN, SE

Cálculo da nota média geral por estado

União com shapefile para visualização no mapa

📈 Visualização
🗺️ Mapa de Calor – Notas Médias por Estado

Coloração: YlOrRd (amarelo → vermelho)

Estados identificados por sigla

Bordas dos estados em preto

Figura gerada e salva automaticamente em:

C:\Users\CWS\Documents\TCC\Meu tcc\imagem2\

🛠️ Dependências
Biblioteca	Uso
pandas	Manipulação e limpeza dos dados
geobr	Carregamento de dados geográficos
matplotlib	Visualizações
scikit-learn	Pré-processamento e encoding
IPython.display	Exibição no Jupyter
Instalação
pip install pandas geobr matplotlib scikit-learn

🚀 Como Executar

Coloque o arquivo MICRODADOS_ENEM_2023.csv no diretório do notebook

Instale as dependências

Abra tratamento_dados_enem2.ipynb

Execute célula por célula

Os arquivos intermediários e o mapa final serão gerados automaticamente

📋 Considerações Técnicas
⚠️ Problemas Encontrados

Coluna inexistente:
NO_MUNICIPIO_ESCOLA → substituído por NO_MUNICIPIO_PROVA

Warning de downcasting:
Pandas gerou alerta ao substituir valores em TP_COR_RACA

CRS geográfico:
Advertência ao usar projeção default dos shapefiles do geobr

✨ Otimizações

Redução significativa do dataset com filtros iniciais

Encoding otimizado

Agrupamento eficiente para gerar mapas

🔮 Possíveis Análises Futuras
📌 Correlações

Fatores socioeconômicos × desempenho

Tipo de escola × notas

📌 Clusterização

Perfis socioeconômicos usando K-Means, PCA ou UMAP

📌 Séries Temporais

Evolução das notas por estado/ano
