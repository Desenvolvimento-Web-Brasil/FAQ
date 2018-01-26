Esse artigo guia você através dos princípios do AJAX e oferece dois exemplos práticos simples para poder começar.

## O que é AJAX?
AJAX significa Asynchronous JavaScript e XML. Em poucas palavras, é o uso do objeto XMLHttpRequest para se comunicar com os scripts do lado do servidor. Ele pode enviar bem como receber informações em uma variedade de formatos, incluindo JSON, XML, HTML, e até mesmo arquivos de texto. Porém a característica mais atraente do AJAX, é a sua natureza "assíncrona", o que significa que ele pode fazer tudo isso sem a necessidade de atualizar a página. Isso permite a você atualizar partes de uma página com base em eventos do usuário.

Os dois recursos em questão que você pode utilizar são:

- Fazer requisições para o servidor sem recarregar a página
- Receber e trabalhar com dados do servidor

## Passo 1 - Como fazer uma requisição HTTP
Para fazer uma requisição HTTP ao servidor usando JavaScript, você precisa de uma instância de uma classe que fornece essa funcionalidade. Este é o lugar onde o XMLHttpRequest entra. Essa classe foi originalmente introduzida no Internet Explorer como um objeto ActiveX chamado XMLHTTP. Então, Mozilla, Safari e outros navegadores o seguiram, implementando uma classe XMLHttpRequest que suporta os métodos e propriedades do objeto ActiveX original da Microsoft. 

Como resultado, a fim de criar uma instância (objeto) compatível com multiplos navegadores da classe requerida, você pode fazer o seguinte:

```
 var httpRequest;
 if (window.XMLHttpRequest) { // Mozilla, Safari, ...
    httpRequest = new XMLHttpRequest();
 } else if (window.ActiveXObject) { // IE 8 and older
     httpRequest = new ActiveXObject("Microsoft.XMLHTTP");
 }

```
### Nota: Para fins de ilustração, o que precede é uma versão um tanto simplificada do código necessário para criar uma instância XMLHTTP. Para um exemplo mais real, consulte o passo 3 deste artigo.
Em seguida, você precisa decidir o que quer fazer depois de receber a resposta do servidor ao seu pedido. Nesta etapa, você somente precisa dizer ao objeto requisição HTTP qual função JavaScript irá manipular o processamento da resposta. Isto é feito definindo a propriedade onreadystatechange do objeto para o nome da função JavaScript que deve ser chamada quando o estado da requisição muda, desse jeito:

httpRequest.onreadystatechange = nameOfTheFunction;
Observe que não existem parênteses depois do nome da função e nenhum parâmetro é passado, porque você está simplesmente atribuindo uma referência à função, ao invés de realmente chamá-la. Além disso, em vez de dar um nome de função, você pode usar a técnica JavaScript de definir funções dinâmicamente (chamadas "funções anônimas") e definir as ações que irão processar de imediato a resposta, dessa forma:


[Continue Lendo na Fonte](https://developer.mozilla.org/pt-BR/docs/Web/Guide/AJAX/Getting_Started)
