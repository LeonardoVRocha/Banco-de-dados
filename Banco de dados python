# Banco de dados

import pandas as pd

 # após a instalação no terminal eu importei o pandas e dei o apelido de pd através do as
 
import numpy
import plotly.express as px # FERRAMENTA QUE CRIA UM GRAFICO

#importação de um arquivo usando pandas, deve-se definir qual o formato do arquivo, por isso o csv
tabela = pd.read_csv(r"C:\Users\Leona\Desktop\telecom.csv")

#excluir coluna da tabela, primeiro o nome da coluna, depois diz que é coluna através do axis=1
tabela = tabela.drop("Unnamed: 0", axis = 1)

#transformar uma coluna de str(texto) em int ou float e o coerce para deixar a coluna vazia
tabela["TotalGasto"] = pd.to_numeric(tabela["TotalGasto"],errors="coerce")

#para excluir todas as colunas que estiverem vazias, all igual a todas e axis= 1 é coluna e axis=0 linha
tabela = tabela.dropna(how="all", axis=1)

# para excluir as linhas que tem alguma informação vazia, any= pelo menos um valor vazio, íden anterior o axis
tabela = tabela.dropna(how="any", axis=0)

#Realizam da contagem usando a coluna mais a ferramenta ( Value_counts() )

print(tabela["Churn"].value_counts())
print(tabela["Churn"].value_counts(normalize=True).map("{:.1%}".format))
print(tabela.info())

#Criar grafico
grafico = px.histogram(tabela, x="MesesComoCliente", color="Churn")

#Exibir grafico e será exibido em um janela em um navegador !
grafico.show()

