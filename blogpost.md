# Equivalência de termos da Interface do Firefox
## entre Inglês e Português do Brasil ##

### 1. Baixe os dois language packs(en-US e pt-BR) do ftp da Mozilla ###

#### 1.1 Firefox Nighly ou Aurora ####

Se você planeja utilizar o Firefox Nightly ou Aurora como fonte das strings que
quer comparar, os endereços para download dos "language packs"
no ftp da Mozilla são:

* https://ftp.mozilla.org/pub/mozilla.org/firefox/nightly/latest-mozilla-central/
ou https://ftp.mozilla.org/pub/mozilla.org/firefox/nightly/latest-mozilla-aurora/
  * baixe o arquivo que termine em .en-US.langpack.xpi clicando com o botão da
  direita do mouse e selecionando "Salvar link como…"
* https://ftp.mozilla.org/pub/mozilla.org/firefox/nightly/latest-mozilla-central-l10n/
ou https://ftp.mozilla.org/pub/mozilla.org/firefox/nightly/latest-mozilla-aurora-l10n/
  * faça um scroll até o fim da lista onde tem as pastas relativas aos diferentes
  sistemas (linux, mac, windows)
  * clique na pasta do sistema que vc quer baixar o language pack e depois a pasta xpi.
  * baixe o arquivo terminado em pt-BR.langpack.xpi clicando com o botão da
  direita do mouse e selecionando "Salvar link como…"

#### 1.2 Firefox Atual ####

Se você planeja utilizar o último release do Firefox como fonte das strings que
quer comparar, os endereços para download dos "language packs"
no ftp da Mozilla são:

* https://ftp.mozilla.org/pub/mozilla.org/firefox/releases/latest/
  * clique na pasta do sistema operacional desejado (exemplo: mac)
  * faça scroll até o fim da página e procure uma pasta de nome "xpi"
    * baixe os arquivos en-US.xpi e pt-BR.xpi clicando com o botão da
direita do mouse e selecionando "Salvar link como…"

#### 1.3 Outras versões do Firefox ####

A mesma idéia dos exemplos acima, o endereço será alguma coisa como:

    https://ftp.mozilla.org/pub/mozilla.org/firefox/releases/[VERSAO]/[SO]/xpi/[pt-BR.xpi ou en-US.xpi]

#### 2. Renomeie os dois arquivos .xpi e extraia o conteúdo ####

A extensão .xpi é um arquivo Zip, portanto, para extrair o conteúdo dos language
packs vc precisa renomear os dois arquivos de extensão .xpi para .zip antes de
extrair.

### 3. Abra o conteúdo dos pacotes em um editor de texto/código ###

Aqui eu usarei o [Sublime Text 2](http://www.sublimetext.com/) que é um editor
de texto disponível para Mac, Linux e Windows e que possui uma busca textual boa.

Eu criei uma nova pasta e coloquei as duas pastas extraídas anteriormente (2)
dentro dela, se eu arrastar/abrir esta pasta com o Sublime Text, ele vai
considerar todos os arquivos dos dois language packs na hora que você efetuar
uma busca "Find in files…" (Cmd+Shift+F).

### 3. Procure o termo em Inglês ###

Por exemplo, digamos que eu esteja traduzindo
[este artigo](https://support.mozilla.org/en-US/kb/send-performance-data-improve-firefox)
e precise saber como aparece na interface do Firefox em Português o texto:
"Submit performance data".

Esta é uma string presente na versão 19 do Firefox, então considerando que eu
segui as etapas de 1 a 3 para esta versão do Firefox e ja estou dentro do
editor de texto que está considerando os arquivos dos dois language packs,
basta eu fazer uma busca textual por "Submit performance data". O resultado
será algo tipo:

    Searching 510 files for "performance data"

    /Users/fabricio/trampos/2013/sumo/languages/19.0.2/en-US/chrome/en-US/locale/browser/preferences/advanced.dtd:
       35  <!ENTITY submitCrashes.label             "Submit crash reports">
       36  <!ENTITY submitCrashes.accesskey         "S">
       37: <!ENTITY submitTelemetry.label           "Submit performance data">
       38  <!ENTITY submitTelemetry.accesskey       "P">
       39

    1 match in 1 file

#### 3.1 Copie o nome da variável ####

No exemplo acima, a variável que contem o texto que eu preciso saber o
equivalente em Português é o que vai depois de ENTITY e antes de das aspas, ou
seja: submitTelemetry.label

### 4. Encontre o termo em Português ###

Com o nome da variável em mãos, basta realizar uma nova busca, desta vez pelo
nome da variável:

    Searching 510 files for "submitTelemetry.label"

    /Users/fabricio/trampos/2013/sumo/languages/19.0.2/en-US/chrome/en-US/locale/browser/preferences/advanced.dtd:
       35  <!ENTITY submitCrashes.label             "Submit crash reports">
       36  <!ENTITY submitCrashes.accesskey         "S">
       37: <!ENTITY submitTelemetry.label           "Submit performance data">
       38  <!ENTITY submitTelemetry.accesskey       "P">
       39

    /Users/fabricio/trampos/2013/sumo/languages/19.0.2/pt-BR/chrome/pt-BR/locale/browser/preferences/advanced.dtd:
       35  <!ENTITY submitCrashes.label             "Enviar relatórios de travamento">
       36  <!ENTITY submitCrashes.accesskey         "n">
       37: <!ENTITY submitTelemetry.label           "Enviar dados sobre desempenho">
       38  <!ENTITY submitTelemetry.accesskey       "d">
       39

    2 matches across 2 files

Para o exemplo que estamos usando, o termo equivalente deste label do Firefox
em Português seria: "Enviar dados sobre desempenho" e eu posso continuar minha
tradução do artigo sabendo que o texto no artigo será o mesmo que o usuário vê
na interface.






