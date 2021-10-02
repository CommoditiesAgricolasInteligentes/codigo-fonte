
Data Science Academy - Grupo de Mentoria 2021


Previsão do Preço da Commodity Agrícola Trigo com base em dados Climáticos e Econômicos
30 de Setembro de 2021


Participantes:
João Vitor de Oliveira (mentor)
		jvitordeoliveiras@gmail.com

Guilherme Antonio Oliver
		guilhermeaoliver@gmail.com

Rafael Schena
		rafaelschena@gmail.com

Renata de Cássia Thomazelli
		recalesi@yahoo.com.br

Objetivo: Desenvolver um modelo de machine learning capaz de prever o comportamento do preço da commodity agrícola trigo, utilizando dados climáticos e econômicos históricos. O modelo serve como auxílio para investidores que já investem ou gostariam de começar a investir nessa commodity. A interação com o modelo é feita a partir de uma aplicação web interativa.

Proposta de solução: Para criarmos um modelo satisfatório, coletamos diversos dados para o seguinte grupo de países que se destacam na produção, importação ou exportação do trigo: Austrália, Brasil, Canadá, China, Alemanha, Egito, França, Grã-Bretanha, Indonésia, Índia, Filipinas, Rússia, Turquia e Estados Unidos. Dentre os dados coletados, estão:

Indicadores econômicos, de pobreza e desigualdade social e populacionais para analisar a tendência de aumento ou diminuição do consumo de itens básicos como o trigo:
PIB.
Inflação.
Poverty gap at USD 5.50 a day (2011 PPP) (%) - (código: SI.POV.UMIC.GP) porcentagem da população vivendo abaixo da linha da pobreza.
Poverty headcount ratio at USD 5.50 a day (2011 PPP) (% of population) - (código: SI.POV.UMIC) - proporção da população vivendo na pobreza.
Crescimento populacional.

Indicadores que influenciam na produtividade agrícola: 
Temperaturas.
Precipitação.
% de território destinado à agricultura.
Produtividade agrícola.

Indicadores históricos da commodity em análise:
Produção de trigo
Importação do trigo.
Exportação do trigo.
Preços históricos do Trigo

Além destes, também foi incluído no modelo uma variável com o preço de outra commodity que interfere diretamente no valor de todas as outras: o petróleo.

Fontes de Dados:
Produção mundial do trigo 
https://knoema.com/atlas/topics/Agriculture/Crops-Production-Quantity-tonnes/Wheat-production 
Importação do trigo
https://knoema.com/atlas/topics/Agriculture/Trade-Import-Value/Wheat-imports
Exportação do Trigo 
https://knoema.com/atlas/topics/Agriculture/Trade-Export-Quantity/Wheat-exports-quantity
Infração 
https://data.worldbank.org/indicator/FP.CPI.TOTL.ZG
Poverty gap e poverty headcount ratio. 
https://data.worldbank.org/topic/11
Para PIP
 https://data.worldbank.org/indicator/NY.GDP.MKTP.CD
temperaturas e precipitação : 
https://datahelpdesk.worldbank.org/knowledgebase/articles/902061-climate-data-api
https://www.ncdc.noaa.gov/cdo-web/webservices/v2
https://climateknowledgeportal.worldbank.org/download-data
GCMs: IPCC SPECIAL REPORT EMISSIONS SCENARIOS https://escholarship.org/content/qt9sz5p22f/qt9sz5p22f.pdf
Preços históricos do trigo no mercado internacional  em US$/bushel:
https://www.macrotrends.net/2534/wheat-prices-historical-chart-data
Investimento em pesquisa agrícola:
https://datacatalog.worldbank.org/search/datasets?sort_by=changed&f%5B0%5D=type%3Adataset
https://www.ers.usda.gov/data-products/international-agricultural-productivity/
https://www.ers.usda.gov/topics/farm-economy/agricultural-research-and-productivity/
https://www.asti.cgiar.org/
https://www.asti.cgiar.org/data
https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/LLVX1G
https://dataverse.harvard.edu/dataset.xhtml?persistentId=hdl:1902.1/20514
https://onlinelibrary.wiley.com/doi/full/10.1111/agec.12620
Terras agrícolas 
https://data.worldbank.org/indicator/AG.LND.AGRI.ZS

Documento do departamento de agricultura americano que traz a produção por país de algumas commodities
https://downloads.usda.library.cornell.edu/usda-esmis/files/5q47rn72z/7m01ch41v/jw828882z/production.pdf
Crescimento populacional:
https://data.worldbank.org/indicator/SP.POP.GROW
Preço de energia:
Não foram encontrados datasets gratuitos. Porém, optou-se por descartar esta variável pela altíssima correlação com o preço do petróleo, dado que em 2019 aproximadamente 84% de toda a energia gerada no mundo vinha de combustíveis fósseis. Fonte: https://ourworldindata.org/fossil-fuels)
ities Data Hub


Ferramentas utilizadas: O processo de limpeza de dados, treinamento e validação do modelo foi inteiramente feito em linguagem Python, utilizando o Jupyter Notebook e Colab para que as etapas ficassem bem documentadas. Para a organização dos datasets e demais arquivos coletados e criados pelos participantes, foi utilizado o armazenamento em nuvem do Google Drive.  A aplicação web foi produzida utilizando a ferramenta Streamlit e Heroku.

Lições Aprendidas:
Existe uma vasta quantidade de datasets e dados disponíveis de forma gratuita pela internet. Porém, a coleta e limpeza de dados ocupou a maior parte do tempo do projeto, o que mostra sua importância.
Existem diversos modelos de machine learning que podem ser utilizados para uma mesma aplicação. Automatizar os testes iniciais para cobrir todos os modelos disponíveis foi uma excelente iniciativa que nos permitiu chegar mais facilmente ao melhor modelo.
A princípio consideramos utilizar os dados climáticos já com as projeções disponíveis no world bank para as próximas décadas. Contudo, analisando os dados, descobrimos que existem diferentes tipos de GCMs - Global Climate Models, estes por sua vez tem diferentes tipos de cenários, como por exemplo A2 e B1, que consideram diversos comportamentos da sociedade capazes de impactar diretamente nas mudanças climáticas.  
Os GCMs são cálculos feitos por clusters de computadores que consideram inúmeros fatores químicos e físicos da atmosfera e dos oceanos, e fatores comportamentais da sociedade. Com estes cálculos pode-se prever possíveis futuros. 
No site do World Bank são disponibilizados quinze tipos de GCMs ,cada um elaborado por um determinado país como Japão, Canadá, Alemanha e outros. Não encontramos um GCM padrão que respondesse por todos os países, pois sua elaboração depende das especificações técnicas dos responsáveis pelos parâmetros nos cálculos a serem executados pelos clusters.
Entre as variáveis para se elaborar um GCM podemos citar: química atmosférica, biogeoquímica interativa, água líquida, espécies químicas, etc.
Quanto aos cenários: O A2,  considera que a população mundial vai continuar usando o combustível fóssil, que a tecnologia vai crescer ainda mais e que as empresas não irão mudar a postura delas com relação a emissão de poluentes, já o B1 seria outra visão, considerando uma mudança de posicionamento dos emissores, o efeito estufa, e o aumento da população mundial como exemplos.
exemplo A2 Environment Canada - Climate Change - CCCma: Animations from CGCM3 - Projected change in surface temperature, SRES A2
exemplo B1 Environment Canada - Climate Change - CCCma: Animations from CGCM3 - Projected change in precipitation, SRES B1
A diferença das mensurações entre os vários tipos de GCMs é muito grande, ao ponto de enquanto um GCM tinha uma temperatura média mínima de 15ºC o outro previa 30ºC para o mesmo período.
Portanto, por não haver um padrão único para os GCMS optamos por usar apenas os dados históricos.
Aprendemos sobre as técnicas de interpolação para preencher valores desconhecidos. Utilizamos a  função interpolate() com o pandas na análise dos dados de crescimento da população, pobreza e desigualdade.
Conhecemos o framework Streamlit utilizado para a criação de apps. https://streamlit.io/ e o utilizamos para fazer o deploy de nosso projeto.

GitHub: xxxx


