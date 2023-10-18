# repositorio-analise-filmes
Analise em Python de filmes do IMDb

import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Carregar os dados
def carregar_dados(caminho):
    """
    Carrega os dados de um arquivo CSV.
    """
    dados = pd.read_csv(caminho)
    return dados

# Análise exploratória de dados
def analise_exploratoria(dados):
    """
    Realiza uma análise exploratória dos dados.
    """
    # Visualizar as primeiras linhas para verificar a estrutura dos dados
    print(dados.head())
    
    # Descrição estatística básica
    print(dados.describe())
    
    # Informações sobre tipos de dados e missing values
    print(dados.info())

# Visualizações básicas
def visualizacoes(dados):
    """
    Cria visualizações básicas com os dados.
    """
    # Histograma das avaliações dos filmes
    sns.histplot(dados['Rating'], kde=True, bins=10)
    plt.title('Distribuição das Avaliações dos Filmes')
    plt.show()

    # Contagem de filmes por ano
    sns.countplot(data=dados, x='Year')
    plt.title('Número de Filmes por Ano')
    plt.xticks(rotation=90)  # Rotaciona os rótulos do eixo x, se estiverem sobrepostos
    plt.show()

    # Qualquer outra visualização que seja interessante para seu conjunto de dados

# Função principal para execução do script
def main():
    caminho_dados = 'caminho/para/seu/arquivo.csv'  # atualize com o caminho do seu arquivo de dados
    dados = carregar_dados(caminho_dados)

    analise_exploratoria(dados)

    visualizacoes(dados)

# Ponto de entrada do script
if __name__ == "__main__":
    main()
