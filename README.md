# Projeto DBT
O real objetivo deste trabalho é demonstrar, passo a passo, como instalar o DBT (Data Build Tool) e configurar um novo projeto, através da interface gráfica conhecida como Visual Studio Code. Esta ferramenta permite que analistas e engenheiros de dados criem, transformem e validem os dados em um data warehouse de maneira mais eficiente.


## 🔨 Ferramentas Necessárias
Este projeto foi desenvolvido utilizando as seguintes ferramentas:
- [Visual Studio Code](https://code.visualstudio.com/download)
- [Git](https://git-scm.com/downloads)


## 🧪 Tecnologias
O projeto foi desenvolvido com a seguinte tecnologia:
- [Python](https://www.python.org/downloads/)


## 💻 Configurações Iniciais de Sistema
Antes de proceguirmos com o projeto é necessário algumas configurações. A princípio vamos adicionar as variavés de ambiente necessárias:
1.0  Na barra de pesquisa do windons digite: EDITAR AS VARIAVEIS DE AMBIENTE.

2.0  Editar a variável "Path" e adicionar os caminhos:
```bash
C:\Users\B045523\AppData\Roaming\Python\Python311
C:\Users\B045523\AppData\Roaming\Python\Python311\Scripts
```

3.0 Em Variáveis de usuário para xxxxxxx acrescentar as variáveis:
```bash
http_proxy: http://proxy.mercantil.com.br:3128
https_proxy: http://proxy.mercantil.com.br:3128
```
	
## 💻 Instalação de Extensões
Antes de proceguirmos com o projeto é necessário a instalação de algumas extensões na IDE VS Code. Após abrir o sistema, no menu lateral, baixar as seguintes extensões:
- [Python]
- [Power User for DBT Core]


## 🚀 Inicializando o projeto DBT
Com a ferramenta do VS Code aberta, acesse o terminal pelo atalho *Ctrl'*. 
Acesse o caminho no qual deseja configurar seu primeiro projeto:
```bash
PS: ...> cd K:\
  PS: K:\>
PS: K:\> cd GEC\2024\'04. Dados'\'0_Snowflake' 
  PS K:\GEC\2024\04. Dados\0_Snowflake>
```

Dentro da pasta na qual o projeto irá ser salvo, executar o comando:	
```bash
PS K:\GEC\2024\04. Dados\0_Snowflake> dbt init
  Running with dbt=1.5.0
  Enter a name for yout project (letters, dgits, underscore): NOME_DO_NOVO_PROJETO
    Precione "Enter"
```

Informe os parâmetros da conexão com o banco de dados seguindo as instruções exibidas no terminal:
```bash
Which database would you like to use?
[1]snowflake
Enter a number: 1
account (https://<this_value>.snowflakecomputing.com): ffa72186.us-east-1		
user (dev username): xxxxxxx@MERCANTIL.COM.BR
[1] password	
[2] keypair
[3] sso
Desired authentication type option (enter a number): 3
authenticator ('externalbrowser' or a valid Okta URL) [externalbrowser]: externalbrowser
role (dev role): SNFLK_AD_GERENCIA_EXCELENCIA_COMERCIAL
warehouse (warehouse name): WH_DEV
database (default database that dbt will build objects in): SDX_EXCELENCIA_COMERCIAL
schema (default schema that dbt will build objects in):  EFET_CAMPANHAS__INCENVITO_REDE
threads (1 or more) [1]: 16
  PS K:\GEC\2024\04. Dados\0_Snowflake\NOME_DO_NOVO_PROJETO>
```

Nesta fase, o projeto foi criado junto com seus respectivos arquivos como: .vscode, analyses, dbt_project.yml. Para abri-ló basta digitar o comando seguinte:
```bash
PS K:\GEC\2024\04. Dados\0_Snowflake\NOME_DO_NOVO_PROJETO> code .
```
 
Acesse o terminal do novo VS Code aberto através do comando anterior *Ctrl '*:
```bash
PS K:\GEC\2024\04. Dados\0_Snowflake\NOME_DO_NOVO_PROJETO>
```

Teste a conexão criada entre o projeto e o banco de dados executando a linha de comando abaixo:
```bash
PS K:\GEC\2024\04. Dados\0_Snowflake\NOME_DO_NOVO_PROJETO> dbt debug
  Registered adapter: snowflake=1.7.3
  Connection test: [OK connection ok]
  All checks passed!
  PS K:\GEC\2024\04. Dados\0_Snowflake\NOME_DO_NOVO_PROJETO>
```

## 🚀 Inicializando o projeto DBT em ambiente virtual
Com a ferramenta do VS Code aberta, acesse o terminal pelo atalho *Ctrl'*. 
Acesse o caminho no qual deseja configurar seu primeiro projeto:
```bash
PS: ...> cd K:\
  PS: K:\>
PS: K:\> cd GEC\2024\'04. Dados'\'0_Snowflake' 
  PS K:\GEC\2024\04. Dados\0_Snowflake>
```

Crie um ambiente virtual:
```bash
PS K:\GEC\2024\04. Dados\0_Snowflake> python -m venv dbt_venv
```

Ative o ambiente virtual criado:
*Obs*: Comando para sistema Windows, este muda no sistema Linux.
```bash
PS K:\GEC\2024\04. Dados\0_Snowflake> .\dbt_venv\Scripts\Activate.ps1
  (dbt_venv) PS K:\GEC\2024\04. Dados\0_Snowflake>
```

Instale o adapter que estiver utilizando:
```bash
(dbt_venv) PS K:\GEC\2024\04. Dados\0_Snowflake> pip install dbt_snowflake
  [notice] To update, run: python.exe -m pip install --upgrade pip
  (dbt_venv) PS K:\GEC\2024\04. Dados\0_Snowflake>
```

Antes de iniciar um novo projeto dbt com o ambiente virtual, é necessário criar uma pasta *.dbt* no diretório do seu usuário. Este arquivo manterá o profile.yaml e as credenciais do usuário são armazenadas:
```bash
(dbt_venv) PS K:\GEC\2024\04. Dados\0_Snowflake> mkdir $home\.dbt
```

Para iniciar o novo projeto, execute:	
```bash
(dbt_venv) PS K:\GEC\2024\04. Dados\0_Snowflake> dbt init		
  Running with dbt=1.5.0
  Enter a name for yout project (letters, dgits, underscore): NOME_DO_NOVO_PROJETO
    Precione "Enter"
```

Informe os parâmetros da conexão com o banco de dados seguindo as instruções exibidas no terminal:
```bash
Which database would you like to use?
[1]snowflake
Enter a number: 1
account (https://<this_value>.snowflakecomputing.com): ffa72186.us-east-1		
user (dev username): xxxxxxx@MERCANTIL.COM.BR
[1] password	
[2] keypair
[3] sso
Desired authentication type option (enter a number): 3
authenticator ('externalbrowser' or a valid Okta URL) [externalbrowser]: externalbrowser
role (dev role): SNFLK_AD_GERENCIA_EXCELENCIA_COMERCIAL
warehouse (warehouse name): WH_DEV
database (default database that dbt will build objects in): SDX_EXCELENCIA_COMERCIAL
schema (default schema that dbt will build objects in):  EFET_CAMPANHAS__INCENVITO_REDE
threads (1 or more) [1]: 16
  (dbt_venv) PS K:\GEC\2024\04. Dados\0_Snowflake\NOME_DO_NOVO_PROJETO>
```

Nesta fase, o projeto foi criado junto com seus respectivos arquivos como: .vscode, analyses, dbt_project.yml. Para abri-ló basta digitar o comando seguinte:
```bash
(dbt_venv) PS K:\GEC\2024\04. Dados\0_Snowflake\NOME_DO_NOVO_PROJETO> code .
```

Acesse o terminal do novo VS Code aberto através do comando anterior *Ctrl '* e ative o ambiente virtual:
```bash
PS K:\GEC\2024\04. Dados\0_Snowflake\NOME_DO_NOVO_PROJETO> K:\GEC\2024\04. Dados\0_Snowflake\dbt_venv\Scripts\Activate.ps1
  (dbt_venv) PS K:\GEC\2024\04. Dados\0_Snowflake\NOME_DO_NOVO_PROJETO> 
```

Teste a conexão criada entre o projeto e o banco de dados executando a linha de comando abaixo:
```bash
(dbt_venv) PS K:\GEC\2024\04. Dados\0_Snowflake\NOME_DO_NOVO_PROJETO> dbt debug
  Registered adapter: snowflake=1.7.3
  Connection test: [OK connection ok]
  All checks passed!
  (dbt_venv) PS K:\GEC\2024\04. Dados\0_Snowflake\NOME_DO_NOVO_PROJETO>
```

Note que na pasta *.dbt*, criada no diretório do usuário, agora possui um arquivo profiles.yaml. Este arquivo armazena os detalhes da conexão informada anteriormente na inicialização do dbt.

## 🧪 Vídeo Demonstrativo
O projeto foi desenvolvido com base nas instruções do vídeo seguinte:
- [Vídeo Base](https://www.youtube.com/watch?v=1fY1A8SRflI&t=62s)



