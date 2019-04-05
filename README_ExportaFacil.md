[checkmark]: https://raw.githubusercontent.com/mozgbrasil/mozgbrasil.github.io/master/assets/images/logos/logo_32_32.png "MOZG"
![valid XHTML][checkmark]

[url-method]: http://www2.correios.com.br/exportafacil/
[requerimentos]: http://mozgbrasil.github.io/requerimentos/
[contact-correios]: http://www2.correios.com.br/sistemas/falecomoscorreios/
[consulta-precos]: http://www2.correios.com.br/sistemas/efi/consulta/precos/default.cfm
[tickets]: https://cerebrum.freshdesk.com/support/tickets/new
[preco]: http://www.cerebrum.com.br/preco/
[github-boxpacker]: https://github.com/mozgbrasil/magento-boxpacker-php_71#mozgboxpacker
[getcomposer]: https://getcomposer.org/
[uninstall-mods]: https://getcomposer.org/doc/03-cli.md#remove
[artigo-composer]: http://mozg.com.br/ubuntu/composer
[ioncube-loader]: http://www.ioncube.com/loaders.php
[acordo]: http://mozg.com.br/acordo-licenca-usuario-final/

# Mozg\Correios

## Sinopse

Integração ao [Correios Exporta Fácil][url-method]

## Motivação

Atender o mercado de módulos para Magento oferecendo melhorias e um excelente suporte

## Suporte / Dúvidas

Para obter o devido suporte [Clique aqui][tickets], relatando o motivo da ocorrência o mais detalhado possível e anexe o print da tela para nosso entendimento

## Preço

[Clique aqui][preco]

## Recursos do módulo

- [✓] Cálculo do frete

## Característica técnica

Atualmente diversos módulos de terceiros relativo a métodos de entrega sempre soma o peso e dimensões dos produtos gerando falha na requisição a transportadora devido não terem um sistema que separa os produtos em sua devida embalagem distribuindo seu peso.

O nosso módulo foi desenvolvido visando total transparência dos processos executados, para efeito de análise visualize os processos armazenado em log.

A extensão permite você definir as dimensões de seus produtos, as dimensões, peso e valor de sua Embalagem/Caixa e regras de como empacotar diferentes combinações de produtos em conjunto como por exemplo embalar os produtos separadamente ou combinar os produtos na mesma Embalagem/Caixa.

A extensão escolhe qual embalagem será utilizado para embalar os produtos para o pedido.

A extensão pode distribuir os produtos em diversas embalagens até o peso máximo suportado para a embalagem.

Como será cadastrado a embalagem com as dimensões e peso suportado pelas transportadoras não deve ocorrer falha relativa as dimensões ou peso.

A primeira coisa a se levar em consideração no uso do módulo é o [Gerenciamento de Embalagem/Caixa][github-boxpacker], como já vem alguns registros pré inseridos certifique se de atualizar os registros conforme sua necessidade.

Certifique se ter cadastrado as devidas dimensões para os produtos.

Para cada embalagem é feito uma requisição a transportadora onde é passado os devidos parâmetros

O módulo possui armazenamento de cache

Na finalização do pedido é armazenado no histórico do pedido um comentário contendo um identificador único que poderá ser usado para consulta no arquivo de log a discriminação dos pacotes seus itens e a visualização de cada pacote com seus itens em 3D

Sempre confira as informações de frete antes de processar cada pedido, caso algo esteja inconsistente será necessário cancelar o pedido até a correção da ocorrência

## Testando na Heroku

Gostaria de apresentar o aplicativo que disponibilizei para a plataforma Heroku

Com apenas 1 clique, o aplicativo cria sua loja virtual usando a plataforma de comércio eletrônico Magento e instala os módulos da MOZG

[https://github.com/mozgbrasil/heroku-magento#descrição](https://github.com/mozgbrasil/heroku-magento#descrição)

## Instalação - Atualização - Desinstalação - Desativação

--

Sugiro "printar" as telas com todos os procedimentos executados

Envie para nós as imagens das telas na eventualidade de quaisquer dificuldades

--

Este módulo destina-se a ser instalado usando o [Composer][getcomposer]

Execute o seguinte comando no terminal, para visualizar a existencia do Composer e sua versão

	composer --version

Caso não tenha o Composer em seu ambiente, sugiro ler o seguinte artigo [Clique aqui][artigo-composer]

--

É necessário que o servidor tenha o suporte a extensão [ionCube PHP Loader][ioncube-loader]

Para visualizar a existência da extensão nesse ambiente denominado PHP CLI, execute o seguinte comando no terminal

	php -v

Para visualizar se essa extensão está ativa em seu servidor no ambiente denominado PHP WEB

Certique se da presença do arquivo phpinfo.php na raiz do seu projeto

	<?php phpinfo(); ?>

Caso não exista o arquivo phpinfo.php na raiz do projeto Magento, crie o mesmo adicionado o conteúdo acima

Acesse o arquivo pelo browser

Em seguida pesquise pelo termo "ionCube PHP Loader"

Caso o seu servidor não tenha o suporte a extensão, entre em contato com sua empresa de hospedagem e peça para que eles ativem a extensão

Caso tenha a permissão e queira ativar a extensão, [Clique aqui][ioncube-loader]

Em "Loader Downloads API", efetue download do pacote compatível com o seu servidor

Descompacte o pacote e faça upload do arquivo "loader-wizard.php" para seu servidor, onde será demonstrado o passo a passo para a ativação da extensão

[Clique aqui](https://youtu.be/GZ2J6MLkko4) para ver os processos executados

--

Na presença do "ionCube PHP Loader" efetue o download do seguinte arquivo e coloque na raiz do seu servidor e acesse, se funcionar quer dizer que o "ionCube" está lendo esse tipo de encriptação

https://raw.githubusercontent.com/mozgbrasil/heroku-magento/master/phpinfo-ioncube-encoder10-x86-64-php_71.php

--

Para utilizar o(s) módulo(s) da MOZG é necessário aceitar o [Acordo de licença do usuário final][acordo]

--

Sugiro manter um ambiente de testes para efeito de testes e somente após os devidos testes aplicar os devidos procedimento no ambiente de produção

--

Sugiro efetuar backup da plataforma Magento e do banco de dados

--

Antes de efetuar qualquer atualização no Magento sempre mantenha o Compiler e o Cache desativado

--

Certique se da presença do arquivo composer.json na raiz do seu projeto Magento e que o mesmo tenha os parâmetros semelhantes ao modelo JSON abaixo

	{
	  "minimum-stability": "dev",
	  "prefer-stable": true,
	  "license": [
	    "proprietary"
	  ],
	  "repositories": [
	    {
	      "type": "composer",
	      "url": "https://packages.firegento.com"
	    }
	  ],
	  "extra": {
	    "magento-root-dir": "./",
	    "magento-deploystrategy": "copy",
	    "magento-force": true
	  }
	}

Caso não exista o arquivo composer.json na raiz do projeto Magento, crie o mesmo adicionado o conteúdo acima

### Para instalar o módulo execute o comando a seguir no terminal do seu servidor no diretório do seu projeto

	composer require mozgbrasil/magento-correios-php_71:dev-master

Você pode verificar se o módulo está instalado, indo ao backend em:

	STORES -> Configuration -> ADVANCED/Advanced -> Disable Modules Output

--

### Para atualizar o módulo execute o comando a seguir no terminal do seu servidor no diretório do seu projeto

Antes de efetuar qualquer processo que envolva atualização no Magento é recomendado manter o Compiler e Cache desativado

	composer update

Na ocorrência de erro, renomeie a pasta /vendor/mozgbrasil e execute novamente

Para checar a data do módulo execute o seguinte comando

	grep -ri --include=*.json 'time": "' ./vendor/mozgbrasil

--

### Para [desinstalar][uninstall-mods] o módulo execute o comando a seguir no terminal do seu servidor no diretório do seu projeto

	composer remove mozgbrasil/magento-correios-php_71

--

### Para desativar o módulo

1. Antes de efetuar qualquer processo que envolva atualização sobre o Magento é necessário manter o Compiler e Cache desativado

2. Caso queira desativar os módulos da MOZG renomeie a seguinte pasta app/code/local/Mozg

A desativação do módulo pode ser usado para detectar se determinada ocorrência tem relação com o módulo

## Como configurar o método de entrega

Antes de configurar o módulo você deve cadastrar o CEP de origem, indo ao backend em:

	STORES -> Configuration -> Sales/Shipping Settings -> Origin

Para configurar o método de entrega, acesse no backend em:

	STORES -> Configuration -> Sales/Shipping Methods -> Correios Exporta Fácil (powered by MOZG)

Você terá os campos a seguir

### • **Ativar**

Para "ativar" ou "desativar" o uso do método

### • **Ordem de exibição**

É a ordem apresentada em métodos de entrega no passo de fechamento de pedido

### • **Título**

Nome do método que deve ser exibido

### • **Serviços**

Selecione os serviços desejado, para selecionar mais de um, segure a tecla "Ctrl" e clique nos serviços

### • **Serviço Para Entrega Gratuita**

Quando houver um desconto de frete grátis, esse serviço terá o valor zero

### • **Calcular taxa de manuseio**

Podendo ser fixo ou percentual

### • **Taxa de Manuseio**

Será adicionado o valor ao frete

### • **Mostrar método se não aplicável**

Quando configurado como "Não", caso seja retornado algum serviço com erro, não será exibido o método de entrega

### • **Debug**

Deve ser armazenado os processos do módulo em var/log/

O arquivo

DATE_mozg.log

se trata de log do módulo sendo um log mais detalhado contendo todos os processos inclusive das execuções realizadas pelas bibliotecas externas do módulo

O arquivo

shipping_METHOD.log

se trata de log nativo do magento relativo ao método de entrega

### • **Enviar para países aplicáveis**

Você pode definir se o método deve funcionar para "Todos os Países aceito" ou "Especificar Países "

### • **Enviar para países específicos**

Você deve selecionar os países que o método deve ser funcional

Foi mapeado os seguintes países

http://www2.correios.com.br/sistemas/efi/bb/consulta_pais.cfm?reset=true

### • **Identificador do atributo largura dos produtos**

Permite definir o nome do atributo de largura dos produtos usado no projeto

### • **Identificador do atributo comprimento dos produtos**

Permite definir o nome do atributo de comprimento dos produtos usado no projeto

### • **Identificador do atributo altura dos produtos**

Permite definir o nome do atributo de altura dos produtos usado no projeto

### • **Unidade de medida**

Sendo o padrão do peso do produto como kilo

Caso esteja usando a unidade de massa em gramas, tanto os produtos como as embalagens devem respeitar o mesmo padrão

Ao informar na configuração do método o uso da unidade de massa em gramas é feito a conversão do peso de grama para kilo

1 Kg no formato "Kilo" será "1.000", já em "Gramas" será "1000.000"

### • **Exibir Prazo de Entrega**

Se será ou não mostrado o prazo de entrega para seu cliente

### • **Mensagem que Exibe o Prazo de Entrega**

Se será ou não mostrado o prazo de entrega para seu cliente

### • **Adicionar (dias) ao prazo de entrega**

Quantidade de dias que será adicionado ao prazo

### • **Mostrar serviço com retorno de erro**

Quando configurado como "Não", caso seja retornado algum serviço com erro, o mesmo não deve ser exibido no método de entrega

### • **Sigla do Estado de origem**

Informe a sigla do estado de origem

### • **Identificar se foi postado na Capital (C) ou no Interior ( I ) do Estado**

Identificar se foi postado na Capital ou no Interior do Estado

## Perguntas mais frequentes "FAQ"

### Como conferir os valores dos fretes junto a transportada

Você pode visualizar no log os parâmetros enviado a transportada

Quando finalizado o pedido é armazenado no historico as dimensões da caixa que foi usada para o obter o frete

#### Simulação da requisição do preço

Ao efetuar o calculo do frete do produto

Temos o devido retorno ao processar a seguinte requisição

http://www2.correios.com.br/sistemas/efi/bb/Consulta.cfm?tipoConsulta=Geral&PAIS=FR&ESPECIF=110&PESO=6050&UFORIGEM=SP&LARGURA=14&PROFUNDIDADE=18&ALTURA=9&LOCALIDADE=C&RESET=false

### Como é feito o cálculo de preços

[Clique aqui][consulta-precos] para calcular o preço da encomenda o sistema utiliza a distância origem/destino(CEP), o peso e as dimensões do objeto

### Como aplicar o Frete Grátis

Na configuração do módulo para o método de entrega é possível definir o "Serviço Para Entrega Gratuita" recurso que deve ser aplicado quando definido a ação de "Frete Grátis" nas "Regras da Promoção"

No Backend do Magento, acesse o menu: Promoções -> Regras de Promoção -> Criar regra -> Crie uma regra e defina na aba "Ações" o uso do Frete Grátis

Dessa forma na exibição do cálculo do frete será exibido para o serviço escolhido o valor zerado

Esse recurso se trata de regra nativa do Magento caso tenha algum problema sugiro desativar todas as regras de promoção e ativar uma de cada vez até encontrar o motivo da ocorrência

### Dados de contato - Correios

Para entrar em contato com os [Correios][contact-correios]

## Manual

https://apps.correios.com.br/componentes/home/index.html#/

https://apps.correios.com.br/componentes/home/index.html#/documentacao/rest/192/292

:cat2:
