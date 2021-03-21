# serverless-rocketseat
Criar os arquivos:
 - .editorconfig
 - .eslintrc


 - Copiar em .editorconfig
```
root = true

[*]
end_of_line = lf
insert_final_newline = true
trim_trailing_whitespace = true
charset = utf-8
indent_style = space

[*.{js,jsx,html,json,yml}]
indent_size = 2

[*.md]
trim_trailing_whitespace = false 
```

 - Copiar em .eslintrc 
```
{
  "extends": ["standard"],
  "plugins": ["json"],
  "rules": {
    "no-unused-expressions": "off",
    "complexity": ["error", 7],
    "eqeqeq": "error",
    "max-statements": ["error", { "max": 15 }],
    "comma-dangle": [
      "error",
      {
        "arrays": "always-multiline",
        "objects": "always-multiline",
        "imports": "always-multiline",
        "exports": "always",
        "functions": "never"
      }
    ],
    "semi": ["error", "always"]
  },
  "globals": {
    "it": true,
    "describe": true,
    "expect": true,
    "sinon": true,
    "before": true,
    "beforeEach": true,
    "after": true,
    "afterEach": true,
    "context": true
  }
}
```

### Iniciar o projeto Nodejs
yarn init -y

No arquivo package.json, colar "dependencies" e "devDependencies"
```
  },
  "dependencies": {
    "aws-sdk": "^2.796.0",
    "uuid": "^8.3.1"
  },
  "devDependencies": {
    "eslint": "^4.19.1",
    "eslint-config-standard": "^11.0.0",
    "eslint-plugin-import": "^2.11.0",
    "eslint-plugin-json": "^1.2.0",
    "eslint-plugin-node": "^6.0.1",
    "eslint-plugin-promise": "^3.7.0",
    "eslint-plugin-standard": "^3.0.1",
    "eslint-watch": "^3.1.4",
    "husky": "^1.3.1",
    "serverless": "^2.11.1"
  }
```
colar "scripts"
```
  "scripts": {
    "start": "",
    "dev": "",
    "deploy": "serverless deploy",
    "lint": "eslint ./src --ext .json --ext .js --fix"
  },
```

colar "husky"
```
"husky": {
    "hooks": {
      "pre-push": "npm run lint"
    }
  },
```

yarn install

#### Salvar no Git

--

### SERVERLESS
serverless
```
Serverless: No project detected. Do you want to create a new one? (Y/n) Y

Serverless: What do you want to make? (Use arrow keys)
❯ AWS Node.js 
  AWS Python 
  Other 

Serverless: What do you want to call this project? serverless-rocketseat
Project successfully created in 'serverless-rocketseat' folder.
You can monitor, troubleshoot, and test your new service with a free Serverless account.

Serverless: Would you like to enable this? (Y/n) N
You can run the “serverless” command again if you change your mind later.
No AWS credentials were found on your computer, you need these to host your application.


Serverless: Do you want to set them up now? No
You can setup your AWS account later. More details available here:
  http://slss.io/aws-creds-setup

Serverless: Would you like to setup a command line <tab> completion? (Y/n) n
```

### Estrutura do projeto
```
Criar uma pasta src/repository
Copiar o arquivo handler.js da pasta serverless-rocketseat para src/repository
Copiar o arquivo serverless.yml para a raiz do projeto.
Apagar a pasta serverless-rocketseat
```

### Arquivo serverless.yml
```
Apagar os comentários
Alteração do handler: src/handler.hello
```

### Configurar serverless credentials
```
serverless config credentials -o --provider aws --key <key> --secret <secret>

-o = override, apagar configurações anteriores.

➜  serverless config credentials -o --provider aws --key $$$$$$ --secret $$$$$
Serverless: Running "serverless" installed locally (in service node_modules)
Serverless: Setting up AWS...

serverless deploy
```


