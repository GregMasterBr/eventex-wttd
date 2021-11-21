# eventex-wttd
Sistema de gerenciamento de Eventos - Projeto de aprendizagem WTTD - Henrique Bastos

##PASSO A PASSO
* Criar uma pasta de trabalho mkdir nome-da-pasta-de-trabalho
* Com o prompt, navegar até o diretório criado de trabalho para criar a váriavel de ambiente
* python -m venv .wttd (o . antes do nome da variável de ambiente, indica que é um diretório oculto)
  ** Ativar o ambiente .wttd\Scripts\activate (Prompt)
  ** .wttd\Scripts\Activate.ps1 (PowerShell)
* Instalar o Django
  ** pip  install django
* Criar o projeto
  ** COMANDO: django-admin startproject eventex . (esse ponto no final indica que para instalar o projeto django eventex no diretório atual.  (o startproject receberá o diretório de trabalho))
* Para facilitar as chamadas do manage.py, sugere-se, usar a variável do virtual_env e criar um alias
  ** alias manage='python $VIRTUAL_ENV/../manage.py' -> Só funciona  em sistemas UNIX (Mac e linux)
  ** Para funcionar no WINDOWS: Dentro do diretório scripts criar um arquivo manage.bat -> wttd\.wttd\Scripts\manage.bat
  *** E insira esse código: @python "%VIRTUAL_ENV%\..\manage.py" %*
  ***Teste se o projeto está rodando: manage runserver
* Criar uma app core dentro do projeto eventex com o comando manage startapp core.
*Estrutura de Pasta do Projeto:
 ** WTTD - Diretório de trabalho
  *** eventex - Diretório de projeto
  *** core - APP (subdiretório)
  *** manage.py
* Adicionar a app 'eventex.core', no INSTALLED_APPS no arquivo settings.py.
* ROTAS: Criar uma rota, acessando urls.py do eventex. Esse arquivo é a raiz de todas as rotas de nossa aplicação.
* Dentro do arquivo URLS.py do eventex, vai importar o URLs (arquivo que você vai criar do CORE)
  ** URLS do CORE -> [...] path('', views.home, name='home'),
  ** URLS do EVENTEX ->[..] path('', include('eventex.core.urls')),  path('admin/', admin.site.urls),
]
* No APS do core -> wttd\.wttd\eventex\core\apps.py
**     name = 'eventex.core'
* Criar view home dentro de eventex.core.views. A View ela retorna um template.
* Dentro de CORE, cria uma nova pasta chamada TEMPLATES e cria o o arquivo .html (Criar template index.html em eventex.core.templates.)
* Executar o projeto com o comando manage runserver.


