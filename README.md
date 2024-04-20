# CONFIGURAÇÃO PYENV E POETRY PARA UTILIZAR COM PYTHON 

![projeto](https://github.com/thiagoamorim11/Config_pyenv_poetry/blob/main/img_readme.PNG)

## INSTALAÇÃO PYENV | INSTALAÇÃO WINDOWS

- Abrir o prompt (Tecla Windowns + R --> Digite CMD).
- Entrar no link: https://github.com/pyenv-win/pyenv-win
- Copiar o código que está abaixo do Quick start, deixarei abaixo, mas copia da fonte é mais confiavél!
- Executar no prompt:
~~~~python:
Invoke-WebRequest -UseBasicParsing -Uri "https://raw.githubusercontent.com/pyenv-win/pyenv-win/master/pyenv-win/install-pyenv-win.ps1" -OutFile "./install-pyenv-win.ps1"; &"./install-pyenv-win.ps1"
~~~~
- Normalmente vai ocorrer um erro devido o código não tem permissão de execução, para corrigir execute outro código:
- Site onde tem a solução. Link: https://pt.stackoverflow.com/questions/220078/o-que-significa-o-erro-execu%C3%A7%C3%A3o-de-scripts-foi-desabilitada-neste-sistema
- Vou deixar o código aqui para copiar e executar no prompt:
~~~python:
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
~~~

- Copiar o primeiro código e executar novamente.

- Executar o comando no **bash** para verificar se **pyenv** está instalado:
~~~python:
pyenv --version
~~~

- Após a instalação, vamos adicionar as variaveis de ambiente (se não estiver sido adicionada).

### INSTALAÇÃO DAS VARIAVEIS | INSTALAÇÃO WINDOWS

1. Digitar **variáveis** na barra de pesquisa do windows e abrir as **Propriedades de sistema**.
2. Ir para aba **avançado**, na parte inferior da aba avançado clicar em **Variáveis de Ambiente**.
3. Dentro das **Variáveis de Ambiente** clicar **novo** e criar 3 variáveis:
- 3.1. 1ª Variável --> nome: **PYENV** 		valor: C:\Users\seu_usuario\ .pyenv\pyenv-win
- 3.2. 2ª Variável --> nome: **PYENV_ROOT** 	valor: C:\Users\seu_usuario\ .pyenv\pyenv-win
- 3.3. 3ª Variável --> nome: **PYENV_HOME** 	valor: C:\Users\seu_usuario\ .pyenv\pyenv-win

4. Clicar na variável **Patch** duas vezes e criar mais dois **Patchs**:
- 4.1. Clicar em novo e adicionar : C:\Users\seu_usuario\ .pyenv\pyenv-win\bin
- 4.2. Clicar em novo e adicionar : C:\Users\seu_usuario\ .pyenv\pyenv-win\shims
- 4.3. Clicar em cada um dos **Patchs adicionados** e clicar em **Mover para Cima** até um ser o primeiro e o outro o segundo da lista.


## CONFIGURAR O PYENV PARA AS DIFERENTES VERSÕES DO PYTHON

- Instalar versõesdo python (executar no **bash**):
~~~~python:
pyenv install 3.11.5
~~~~

- Verificação das versões instaladas (executar no **bash**):
~~~~python:
pyenv versions
~~~~

- Configurar qual a **versão padrão** para os projetos (executar no **bash**):
~~~~python:
pyenv global 3.12.1
~~~~

- Configurar uma **versão local** para o projeto especifico (executar no **bash**):
~~~~python:
pyenv local 3.12.1
~~~~

### PIP

- Verificação das bibliotecas (executar no **bash**):
~~~~python:
pip list
~~~~

- Lista todas bibliotecas (executar no **bash**):
~~~~python:
pip freeze
~~~~

- Instalação das bibliotecas (executar no **bash**):
~~~~python:
pip install pandas
~~~~

- Desistalação das bibliotecas (executar no **bash**):
~~~~python:
pip uninstall pandas
~~~~

- Limpeza do pip list (executar no **bash**):
~~~~python:
pip freeze | grep -v "^-e" | xargs pip uninstall -y
~~~~

## CRIAÇÃO DO AMBIENTE VIRTUAL

- Acessar a pasta do projeto para criar o ambiente virtual.

- Criar o ambiente virtual dentro da pasta do projeto (executar no **bash**):
~~~~python:
python -m venv .venv
~~~~

- Verificação da pasta **venv** dentro da pasta do projeto (executar no **bash**):
~~~~python:
ls -al
~~~~

- Ativação do ambiente virtual (executar no **bash**):
~~~~python:
source .venv/Scripts/activate
~~~~

- Agora todas as bibliotecas instaladas estarão somente dentro do projeto (executar no **bash**):
~~~~python:
pip install pandas
~~~~

- Desativação do ambiente virtual (executar no **bash**):
~~~~python:
deactivate
~~~~

## INSTALAÇÃO DO POETRY | INSTALAÇÃO WINDOWS

- Utilizar o **pipx** para configural de forma global.

- Instalação do **POETRY** (executar no **bash**):
~~~~python:
pipx install poetry
~~~~

- Configurar o **POETRY** para cuidar do ambiente virtual (executar no **bash**):
~~~~python:
poetry config virtualenvs.in-project true
~~~~

- Criação de projeto com **POETRY** (executar no **bash**):
~~~~python:
poetry new projeto_novo
~~~~

- Configurar uma **versão local** para o projeto (executar no **bash**):
~~~~python:
pyenv local 3.12.1
~~~~

- Configuração da versão local do python com **POETRY** (executar no **bash**):
~~~~python:
poetry env use 3.12.1
~~~~

- Instalação de **bibliotecas** com **POETRY** (executar no **bash**):
~~~~python:
poetry add pandas
~~~~

- Desistalação de **bibliotecas** com **POETRY** (executar no **bash**):
~~~~python:
poetry remove pandas
~~~~

- Shell **POETRY** (executar no **bash**):
~~~~python:
poetry shell
~~~~




#### Instalação foi baseada no video do **Luciano Galvão Filho**

- Git hub: https://github.com/lvgalvao
- Video Youtube: https://www.youtube.com/watch?v=9LYqtLuD7z4








