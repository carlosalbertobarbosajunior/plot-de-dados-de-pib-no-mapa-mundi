# analise-de-dados-pib-world-bank
## Objetivo:
Capturar dados CSV disponibilizados pelo banco mundial (https://www.worldbank.org/en/home) e tratá-los devidamente para exibir um gráfico de mapa com o valor do PIB dos países em diferentes anos.

### 1. Visualizando os dados:
Utiliza a biblioteca pandas para ler o arquivo CSV e visualizá-lo.

### 2. Funções:
Um conjunto de quatro funções que tratam os dados do arquivo CSV e exibe um mapa mundi com informações de PIB no ano desejado.

#### read_csv_as_nested_dict(filename, keyfield, separator, quote):
    """
    Inputs:
      filename  - Nome do arquivo CSV
      keyfield  - Coluna a ser usada como chave do dicionário
      separator - Caractere utilizado na separação de informações do arquivo CSV
      quote     - Caractere utilizado em citação no arquivo CSV

    Output:
      Retorna um dicionário de dicionários, onde o dicionário externo
      mapeia a coluna keyfield para a linha correspondente no arquivo
      CSV. Os dicionários internos mapeiam os nomes dos campos para os
      valores da respectiva linha.
    """
    
#### reconcile_countries_by_name(plot_countries, gdp_countries):
    """
    Inputs:
      plot_countries - Dicionário onde as chaves são códigos dos países de uma
                       biblioteca de exibição de gráficos, e os valores são os
                       nomes dos países correspondentes.
      gdp_countries  - Dicionário onde as chaves são os nomes dos países presentes
                       nos dados de PIB a serem analisados.

    Output:
      Uma tupla contendo um dicionário e um set.
      O dicionário possui os códigos (chaves) e nomes (valores) dos países 
      presentes em plot_countries e em gdp_countries.
      O set contém os códigos de plot_countries que não foram encontrados
      em gdp_countries.
    """

#### build_map_dict_by_name(gdpinfo, plot_countries, year):
    """
    Inputs:
      gdpinfo        - Um dicionário de informações de PIB
      plot_countries - Dicionário onde as chaves são códigos dos países de uma
                       biblioteca de exibição de gráficos, e os valores são os
                       nomes dos países correspondentes.
      year           - Ano para criação do gráfico de mapa

    Output:
      Uma tupla contendo um dicionário e dois sets.
      O dicionário vincula os códigos dos países com o log (base 10)
      do valor do PIB do país e ano correspondentes.
      O primeiro set contém os códigos dos países do plot_countries que
      não foram encontrados no arquivo de dados de PIB.
      O segundo set contém os códigos dos países do plot_countries que
      foram encontrados no arquivo de dados de PIB, mas que não possui 
      informações de PIB no ano requisitado.
    """

#### render_world_map(gdpinfo, plot_countries, year, map_file):
    """
    Inputs:
      gdpinfo        - Um dicionário de informações de PIB
      plot_countries - Dicionário onde as chaves são códigos dos países de uma
                       biblioteca de exibição de gráficos, e os valores são os
                       nomes dos países correspondentes.
      year           - Ano para criação do gráfico de mapa (string ou int)
      map_file       - Nome do arquivo svg a ser criado

    Output:
      Retorna None.

    Ação:
      Cria um gráfico de mapa múndi das informações de PIB para o ano
      fornecido, escreve o arquivo em formato SVG nomeado por map_file
      e também o exibe no navegador do usuário.
    """
