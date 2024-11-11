# Calculadora PWA

A Calculadora PWA é apenas um exemplo de aplicação que pode ser desenvolvida utilizando o poder do PWA.

## Instalação

Faça um clone do repositório em qualquer pasta do seu computador.
Abra o arquivo `index.html` no seu navegador.

Para instalar o aplicativo direto ao desktop abra as opções da página no seu navegador.
Chrome > Opções > Salvar e Compartilhar > Instalar Calculadora...

## Guia

Os arquivos `sw.js` e `manifest.json` são responsáveis por informar ao navegador as configurações da aplicação que a permitem ser instalada e cachear os dados para ser executado em ambiente offline.

É preciso registrar o `service-worker` da seguinte maneira para que funcione adequadamente:

```javascript
if ("serviceWorker" in navigator) {
  window.addEventListener("load", () => {
    navigator.serviceWorker
      .register("./sw.js")
      .then((reg) => console.log("service Worker: registered"))
      .catch((err) => console.log(`service worker; Error:${err}`));
  });
}
```
