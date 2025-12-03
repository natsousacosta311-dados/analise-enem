<div style="font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; line-height: 1.6; color: #333; max-width: 900px; margin: 0 auto; padding: 20px; border: 1px solid #eee; border-radius: 8px;">

    <header style="border-bottom: 3px solid #007bff; padding-bottom: 10px; margin-bottom: 20px;">
        <h1 style="color: #007bff; font-size: 2.2em; display: flex; align-items: center;">
            <span style="font-size: 1.5em; margin-right: 15px;">📊</span> Análise de Dados do ENEM 2023 – Capitais do Nordeste
        </h1>
        <p style="font-size: 1.1em; color: #555;">
            Pipeline completo de tratamento, pré-processamento e análise exploratória e de clusterização dos microdados do ENEM 2023, com foco nas nove capitais da região Nordeste.
        </p>
    </header>

    <section style="margin-bottom: 30px; padding: 15px; background-color: #f8f9fa; border-left: 5px solid #28a745; border-radius: 4px;">
        <h2 style="color: #28a745; font-size: 1.5em; margin-top: 0; display: flex; align-items: center;">
            <span style="margin-right: 10px;">🌟</span> Resumo do Projeto
        </h2>
        <p>O projeto está dividido em duas fases:</p>
        <ul style="list-style-type: none; padding: 0;">
            <li style="margin-bottom: 8px; padding-left: 20px; position: relative;"><span style="color: #007bff; font-weight: bold; position: absolute; left: 0;">➤</span> <strong>Tratamento e Pré-processamento:</strong> Limpeza, filtragem (capitais do Nordeste), <em>encoding</em> de variáveis e redução dimensional.</li>
            <li style="margin-bottom: 8px; padding-left: 20px; position: relative;"><span style="color: #007bff; font-weight: bold; position: absolute; left: 0;">➤</span> <strong>Análise e Clusterização (K-Means):</strong> Identificação de perfis socioeconômicos e de desempenho acadêmico.</li>
        </ul>
    </section>

    <section style="margin-bottom: 30px;">
        <h2 style="color: #333; font-size: 1.5em; margin-bottom: 15px; border-bottom: 1px dashed #ccc; padding-bottom: 5px; display: flex; align-items: center;">
            <span style="margin-right: 10px;">📁</span> Estrutura do Repositório
        </h2>
        <table style="width: 100%; border-collapse: collapse; text-align: left;">
            <thead style="background-color: #e9ecef;">
                <tr>
                    <th style="padding: 10px; border: 1px solid #dee2e6;">Caminho</th>
                    <th style="padding: 10px; border: 1px solid #dee2e6;">Descrição</th>
                </tr>
            </thead>
            <tbody>
                <tr style="background-color: #f1f1f1;">
                    <td style="padding: 10px; border: 1px solid #dee2e6;"><code>tratamento_dados_enem2.ipynb</code></td>
                    <td style="padding: 10px; border: 1px solid #dee2e6;">Notebook Principal: Limpeza, transformação e visualização inicial.</td>
                </tr>
                <tr>
                    <td style="padding: 10px; border: 1px solid #dee2e6;"><code>clustering_enem/clusterizacao_enem.ipynb</code></td>
                    <td style="padding: 10px; border: 1px solid #dee2e6;">Notebook de Clusterização: K-Means, seleção de <em>k</em> ideal e validação.</td>
                </tr>
                <tr style="background-color: #f1f1f1;">
                    <td style="padding: 10px; border: 1px solid #dee2e6;"><code>data/</code></td>
                    <td style="padding: 10px; border: 1px solid #dee2e6;">Dados tratados e intermediários.</td>
                </tr>
                <tr>
                    <td style="padding: 10px; border: 1px solid #dee2e6;"><code>outputs/</code></td>
                    <td style="padding: 10px; border: 1px solid #dee2e6;">Resultados finais (mapas, gráficos, estatísticas e relatório).</td>
                </tr>
                <tr style="background-color: #f1f1f1;">
                    <td style="padding: 10px; border: 1px solid #dee2e6;"><code>MICRODADOS_ENEM_2023.csv</code></td>
                    <td style="padding: 10px; border: 1px solid #dee2e6;"><strong>Entrada:</strong> Microdados brutos do ENEM (obtido via INEP).</td>
                </tr>
            </tbody>
        </table>
    </section>

    <section style="margin-bottom: 30px;">
        <h2 style="color: #333; font-size: 1.5em; margin-bottom: 15px; border-bottom: 1px dashed #ccc; padding-bottom: 5px; display: flex; align-items: center;">
            <span style="margin-right: 10px;">🔧</span> Detalhes do Processamento
        </h2>
        
        <h3 style="color: #495057; font-size: 1.3em; margin-top: 20px;">Fase 1: Tratamento de Dados</h3>
        <ul style="padding-left: 25px;">
            <li><strong>Filtragem:</strong> Foco nas 9 capitais do Nordeste e participantes concluintes/cursando o Ensino Médio.</li>
            <li><strong>Ajustes:</strong> Correção de coluna inexistente (<code>NO_MUNICIPIO_ESCOLA</code> → <code>NO_MUNICIPIO_PROVA</code>).</li>
            <li><strong>Encoding:</strong> Uso de One-Hot (Ex.: TP_SEXO) e Label Encoding (Ex.: Questões socioeconômicas Q001-Q025).</li>
            <li><strong>Geoprocessamento:</strong> Geração de Mapa de Calor de Notas Médias por estado Nordestino (<code>geobr</code> + <code>matplotlib</code>).</li>
        </ul>

        <h3 style="color: #495057; font-size: 1.3em; margin-top: 20px;">Fase 2: Análise de Clusterização (K-Means)</h3>
        <ul style="padding-left: 25px;">
            <li><strong>Variáveis-Chave:</strong> Q001, Q002 (Escolaridade dos Pais), Q006 (Renda Familiar), Q024, Q025 (Recursos Tecnológicos) e <code>NU_NOTA_MEDIA</code>.</li>
            <li><strong>Metodologia:</strong> Determinação do <em>k</em> ideal via **Métodos do Cotovelo e Silhueta**.</li>
            <li><strong>Validação:</strong> Aplicação de **ANOVA** para comprovar a significância estatística dos clusters ($\small p \text{-valor} < 0.05$).</li>
        </ul>

        <h4 style="color: #495057; font-size: 1.2em; margin-top: 20px; border-left: 3px solid #ffc107; padding-left: 10px;">Resultados: 3 Perfis Identificados</h4>
        <div style="display: flex; justify-content: space-between; gap: 15px; margin-top: 15px;">
            <div style="flex: 1; border: 1px solid #dc3545; padding: 10px; border-radius: 4px; background-color: #fceae9;">
                <p style="font-weight: bold; color: #dc3545; margin-top: 0;">🔴 Vulnerável</p>
                <p style="font-size: 0.9em; margin: 0;">Baixa renda e escolaridade dos pais. **Nota Média: 500.03**.</p>
            </div>
            <div style="flex: 1; border: 1px solid #ffc107; padding: 10px; border-radius: 4px; background-color: #fff8e6;">
                <p style="font-weight: bold; color: #ffc107; margin-top: 0;">🟡 Intermediário</p>
                <p style="font-size: 0.9em; margin: 0;">Características medianas de desempenho e socioeconomia.</p>
            </div>
            <div style="flex: 1; border: 1px solid #28a745; padding: 10px; border-radius: 4px; background-color: #e9f5e9;">
                <p style="font-weight: bold; color: #28a745; margin-top: 0;">🟢 Privilegiado</p>
                <p style="font-size: 0.9em; margin: 0;">Maior renda, recursos tecnológicos e escola privada. **Nota Média: 660.00**.</p>
            </div>
        </div>
    </section>

    <section style="margin-bottom: 30px; background-color: #e9f4ff; padding: 20px; border-radius: 8px;">
        <h2 style="color: #007bff; font-size: 1.5em; margin-bottom: 15px; display: flex; align-items: center;">
            <span style="margin-right: 10px;">🚀</span> Como Executar
        </h2>
        
        <h3 style="color: #495057; font-size: 1.2em; margin-top: 0;">1. Dependências</h3>
        <p>Instale as bibliotecas necessárias:</p>
        <pre style="background-color: #343a40; color: #fff; padding: 10px; border-radius: 4px; overflow-x: auto;"><code>pip install pandas numpy matplotlib seaborn scikit-learn plotly geobr python-docx</code></pre>
        
        <h3 style="color: #495057; font-size: 1.2em;">2. Execução</h3>
        <ol style="padding-left: 25px;">
            <li style="margin-bottom: 5px;">Coloque o arquivo <code>MICRODADOS_ENEM_2023.csv</code> na raiz do diretório.</li>
            <li style="margin-bottom: 5px;">Execute as células do notebook <code>tratamento_dados_enem2.ipynb</code>.</li>
            <li>Execute as células do notebook <code>clustering_enem/clusterizacao_enem.ipynb</code>.</li>
        </ol>
        <p style="margin-top: 15px; color: #dc3545; font-weight: bold; border-top: 1px solid #ff8888; padding-top: 10px;">⚠️ Os arquivos intermediários e o mapa final serão gerados automaticamente nas pastas <code>data/</code> e <code>outputs/</code>.</p>
    </section>

    <footer style="border-top: 1px solid #ccc; padding-top: 15px; margin-top: 20px; font-size: 0.9em; color: #6c757d;">
        <h4 style="color: #6c757d; margin-top: 0; display: flex; align-items: center;"><span style="margin-right: 10px;">📋</span> Considerações Técnicas</h4>
        <ul style="padding-left: 25px;">
            <li>**Otimizações:** Redução significativa do dataset e uso de <em>encoding</em> otimizado para a clusterização.</li>
            <li>**Problemas:** Necessária correção da coluna <code>NO_MUNICIPIO_ESCOLA</code> para <code>NO_MUNICIPIO_PROVA</code>.</li>
        </ul>
        <p style="text-align: center; margin-top: 15px;">Desenvolvido para análise de TCC/Acadêmica.</p>
    </footer>
</div>


