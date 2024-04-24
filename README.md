# Processando-e-Transformando-Dados-com-Power-BI

# Extração de dados na Azure  com MySQL

Selecione MySQL em [Azure](https://portal.azure.com/#home) - Conectar -> Utilizar SHEEL da Azure -> Bash -> Conectar por meio do navegador ou localmente (copiar script no bahs)

## Enviando script para azure
- criando database: create database if not exists azure_company;
- use azure-company;
- criar tables (usar scripts testes para o desafio). Comando: CREATE TABLES <nome> ( ..);
- depois de criar fazer o L;
- pode fazer a conecção da azure em MySQL  Workbench e realizar o processo por lá para criar databases
	- Os passos para realizar em MySQL Workbench: Azure> Conectar> MySQL Workbench

# Evitando erro de importação Azure
Para importar banco de dado sql para power BI do Azure MySQl você precisa instalar conector SQL server atualizado:

Baixar e instalar MySQL conector. (https://dev.mysql.com/downloads/connector/net/)
**Baixar Certificado público SSL. Instale o certificado SSL no armazenamento de autoridades de certificação raiz confiável usando certmgr.msc
Use a autenticação de banco de dados para conectar-se ao servidor de banco de dados.**

É extremamente importante instalar o certificado SSL:
## [Pré-requisitos](https://learn.microsoft.com/pt-br/azure/mysql/flexible-server/connect-with-powerbi-desktop).
1. Instalar o Power BI Desktop.
2. Se você se conectar ao banco de dados MySQL pela primeira vez no Power BI, precisará instalar o pacote MySQL Connector/NET do Oracle.
3. Ignore as etapas abaixo, se o SSL estiver desabilitado no servidor MySQL. Se o SSL estiver habilitado, siga as etapas abaixo para instalar o certificado.
	a. Baixe o certificado público SSL.
	b. Instale o certificado SSL no armazenamento de autoridades de certificação raiz confiáveis seguindo estas etapas:
		- Inicie o Console de Gerenciamento certmgr.msc no sistema Windows.
    - Clique com o botão direito do mouse em Autoridades de Certificação de Raiz Confiável e selecione Importar.
		- Siga os prompts no assistente para importar o certificado raiz (por exemplo, DigiCertGlobalRootCA.crt.pem) e clique em OK.

## Diferença de Mesclar e Atribuir (por IA)
No Power BI Query Editor, "mesclar" e "atribuir" são termos que se referem a operações diferentes, mas ambos estão relacionados à transformação e manipulação de dados. Vamos esclarecer a diferença entre esses dois termos:

### Mesclar (Merge):
A operação de mesclagem no Power BI Query Editor é usada para combinar duas ou mais consultas (queries) ou tabelas com base em colunas comuns. Isso permite que você una dados de diferentes fontes em uma única tabela.
A mesclagem é útil quando você precisa trazer informações de tabelas separadas para uma única tabela, criando relações entre elas. Por exemplo, você pode mesclar uma tabela de clientes com uma tabela de pedidos usando um campo comum, como o ID do cliente.
Para mesclar tabelas no Query Editor, você pode usar a opção "Mesclar Consultas" na guia "Página Inicial" e definir as colunas de junção e o tipo de junção (INNER JOIN, LEFT JOIN, etc.).

### Atribuir (Add Column / Custom Column):
A operação de atribuição no Power BI Query Editor permite criar novas colunas em uma tabela existente ou adicionar colunas calculadas com base em lógica personalizada.
Você pode usar a opção "Adicionar Coluna" para criar colunas derivadas de outras colunas na mesma tabela. Por exemplo, você pode criar uma coluna que calcula o total de vendas multiplicando a quantidade pelo preço unitário.
Além disso, você pode usar a opção "Coluna Personalizada" (Custom Column) para criar colunas com base em expressões M, que é a linguagem de fórmulas do Power Query.

Em resumo, enquanto a mesclagem é usada para combinar dados de diferentes fontes ou tabelas, a atribuição (Adicionar Coluna / Coluna Personalizada) é usada para criar novas colunas ou colunas calculadas em uma tabela existente. Ambas as operações são essenciais para transformar e preparar dados para análise no Power BI.

## Diferença de Mesclar e Atribuir (por Curso)
Atriburi - análogo inner join
Mesclar - análogo ao diferentes JOINs

### Tarefas
12. Mescle as colunas de Nome e Sobrenome para ter apenas uma coluna definindo os nomes dos colaboradores
  - Isso não é mesclar, seria juntar colunas e identar os valores por delimitadores.
13. Mescle os nomes de departamentos e localização. Isso fará que cada combinação departamento-local seja único. Isso irá auxiliar na criação do modelo estrela em um módulo futuro.
  - Deve fazer um join, umas mescla de tabelas (preferencialmente nova). A partir desse JOIN (mescle) você pode fazer um relatório específico desse contexto (local-departament)
15. Explique por que, neste caso supracitado, podemos apenas utilizar o mesclar e não o atribuir.

# Arquivos do projeto

- banco de dados sql
- modelo powerBI
- arquivo de tarefa

