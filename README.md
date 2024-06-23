# TypeScript - Alura #

## Aplicativo: Controle de Negociações ##

### Módulo I - Evoluindo seu JavaScript ###

- Configuração de ambiente,
- Compilando TypeScript,
- Tipagem estática,
- Modelagem de classes,
- Utilização de tipos, modificadores e outros recursos.

### Módulo II - Avançando na Linguagem ###

- Modificadores de acesso,
- Herança e tipos genéricos,
- Entendendo enumerations,
- Implantando frameworks de atualização de views,
- Visibilidade de métodos,
- TSC e StrictNullChecks.

### Módulo III - Técnicas e Boas Práticas ###

- Vantagens e diferentes tipos de decorators,
- Decorators em métodos e propriedades,
- API externa e interface,
- Proteção e dinamismo utilizando polimorfismo,
- Debugando TypeScript.

### Configuração da Aplicação ###

- Instalar via terminal o node v10.21.0
- Utilizar a versão correta do node `nvm ls` e `nvm use 10.21.0`
- Abrir o VSCode e abrir o terminal integrado na pasta raiz do projeto
- Instalar os modulos da aplicação `npm install`
- Instalar o compilador Typescript `npm install typescript@4.2.2 --save-dev`
- Para subir o servidor `npm run server`
- Para abrir o navegador local `localhost:3000`
- Para iniciar a aplicação `npm run start`
- Para compilar o codigo fonte `npm run compile`

### Configuração da API ###

- Abrir um 2º terminal dentro do VSCode e entrar na API `cd servidor-api`
- Instalar os modulos da API `npm install`
- Para iniciar a aplicação `npm start`
- Para abrir o navegador local API `localhost:8080/dados`

### Configuração do arquivo tsconfig.json ###

```json
{
  "compilerOptions": {
  "outDir": "app/dist/js",
  "target": "ES6",
  "noEmitOnError": true,
  "noImplicitAny": true,
  "removeComments": true,
  "strictNullChecks": true,
  "experimentalDecorators": true,
  "sourceMap": true
  },
  "include": ["app/src/**/*"]
}
```

### Explicação tsconfig ###

- `outDir` => pasta onde os arquivos compilados serão gerados,
- `target` => versão do js que deverá ser compilada,
- `noEmitOnError` => não permite gerar os arquivos js enquanto tiver erros no arquivo ts,
- `noImplicitAny` => desativa o tipo implícito any exigindo especificar a tipagem,
- `removeComments` => remove os comentários do codigo ao compilar,
- `strictNullChecks` => não aceita objetos nulos exigindo especificação,
- `experimentalDecorators` => liga a acao do decorators,
- `include` => local onde está a pasta com os arquivos ts para compilar,
- `sourceMap` => disponibiliza codigo para debugar em dev, **nunca** utilizar em prod.

### Ajuste na configuração do arquivo package.json ###

```json
"scripts": {
  "start": "concurrently \"npm run watch\" \"npm run server\"",
  "compile": "tsc",
  "watch": "tsc -w"
}
```

### Explicação package ###

- `start` => recompila automaticamente e atualiza o servidor,
- `compile` => configura a compilação para o projeto inteiro,
- `watch` => escuta as modificações na pasta dist e atualiza a compilação.

--------------------------------------------------------------------------
Todo código de TypeScript fica dentro da pasta app.
Já o código JavaScript fica dentro da pasta dist.
Então, quando compilar os arquivos ts que estão na pasta app,
eles vão todos de forma automatica para pasta dist com a extensão js.
Assim, quando houver uma modificação no arquivo ts,
automaticamente atualiza o arquivo js.
