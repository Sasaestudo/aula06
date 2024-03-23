# aula06


19/03/2024


## terninal em aulas 

Dentro da pasta aplicar auals npx express-generator --no-view aula06

se der erro instalar: npm install express-generator

e repete npx express-generator --no-view aula06

entrar na pasta aula06 e instalar: npm install

ir em public e deletar a pasta.

ir em routes e deletar index.js e users.js

entar no app.js e apagar a linho 2 var path = require('path');

linha 6 e var indexRouter = require('./routes/index');
var usersRouter = require('./routes/users');


linha 15 app.use(express.static(path.join(__dirname, 'public')));

linha 17 e 18 app.use('/', indexRouter);
app.use('/users', usersRouter); 

agora aplicar o npm start


tem que ficar assim o codigo 
"var express = require('express');
var cookieParser = require('cookie-parser');
var logger = require('morgan');



var app = express();

app.use(logger('dev'));
app.use(express.json());
app.use(express.urlencoded({ extended: false }));
app.use(cookieParser());




module.exports = app;"


dentro da aula 06 criar a pasta "controllers"


dentros da pasta "routes" criar arquivo "produtos.js" conforme a API/recurso


dentro do arquivo produtos.js inserir:

-----1
const express = require('express');

const router = express.Router();

module.exports = router;


-----2 no arquivo app.js inserir
const produtosRouter = require('./routes/produtos')


----3 inserir no app.js: app.use('/produtos', produtosRouter);



----4  sair e instar no npm start de novo



---5 crtl + c sair de novo


----6 ir em produtos.js e inserir 

router.get("/");

router.get("/:produtoId");

router.post("/");

router.put("/:produtoId");

router.delete("/:produtoId");


-----7 pasta controllers cirar arquivo controller_produto.js


-----8 controller_produto.js


function listarTodos(req,res) {

}

function buscarPeloId(req, res) {

}

function criar(req, res) {
    
}

function atualizar(req, res) {
      
}

function remover(req, res) {
    
}

module.exports = { listarTodos, buscarPeloId, criar, atualizar, remover }


-----9 produto.js

const produtosController = require("../controllers/controller_produto");



-----10 produto.js

router.get("/", produtosController.listarTodos);

router.get("/:produtoId", produtosController.buscarPeloId);

router.post("/", produtosController.criar);

router.put("/:produtoId", produtosController.atualizar);

router.delete("/:produtoId", produtosController.remover);


----- 11 terminal 
npm start


----12 controller_produtos.js


varias alteraçoes 


-----13 se deu certo sem erro 
ir no thunder client testar


-----14


----15



----16




---17


22/03/24

instalar npm install --save-dev nodemon 

ir no package.json e acrescentar: [ "scripts": {
    "start": "node ./bin/www", 
    --"dev": "nodemon ./bin/www"--
  },]

instalar npm run dev

instalar npm install --save-dev jest supertest

dentro da pasta aula06 criar pasta "test" para guardar os testes.

ir no package.son e acrescentar:
"scripts": {
    "start": "node ./bin/www",
    "dev": "nodemon ./bin/www", 
    -----"test": "jest --watchAll"---
  },


  instalar npm run test



  ir na pasta tests e criar arquivo "produtos.test.js"











#### GET:

O método GET é usado para solicitar dados de um recurso específico no servidor.
Quando você faz uma solicitação GET, você está pedindo ao servidor para enviar os dados associados a um determinado URI (Uniform Resource Identifier).
Os parâmetros GET são incluídos na URL como uma string de consulta, após o caractere "?", e são usados principalmente para recuperar dados do servidor.
As solicitações GET devem ser seguras e idempotentes, o que significa que elas não devem alterar o estado do servidor e fazer a mesma solicitação repetidamente deve retornar o mesmo resultado.

#### POST:

O método POST é usado para enviar dados para serem processados por um recurso específico no servidor.
É comumente usado para enviar dados de um formulário HTML para o servidor, mas também pode ser usado para enviar dados JSON ou XML.
As solicitações POST geralmente resultam em uma mudança no estado do servidor, como a criação de um novo recurso ou a atualização de dados existentes.
Ao contrário das solicitações GET, as solicitações POST não são idempotentes, o que significa que fazer a mesma solicitação repetidamente pode ter efeitos diferentes no servidor.

#### PUT:

O método PUT é usado para atualizar um recurso específico no servidor com os dados fornecidos na solicitação.
Ele substitui completamente o recurso existente com os dados fornecidos na solicitação.
As solicitações PUT são idempotentes, o que significa que fazer a mesma solicitação repetidamente terá o mesmo efeito no servidor.

#### DELETE:

O método DELETE é usado para remover um recurso específico do servidor.
Quando uma solicitação DELETE é feita para um recurso, esse recurso é removido do servidor.
As solicitações DELETE também são idempotentes, o que significa que fazer a mesma solicitação repetidamente terá o mesmo efeito no servidor.
Esses métodos HTTP são usados para permitir que aplicativos cliente interajam com servidores da web de maneira significativa, realizando operações como recuperar dados, enviar dados, atualizar recursos e excluir recursos.



GET: Imagine que você está navegando na internet e quer ver uma página. Você usa um navegador (cliente) para enviar um pedido GET para o servidor que hospeda essa página. O servidor então envia de volta a página solicitada para você ver. É como pedir um livro emprestado da biblioteca e apenas lê-lo, sem alterar nada.

POST: Agora, imagine que você quer enviar uma mensagem para um amigo. Você escreve a mensagem em um pedaço de papel (dados) e envia para o seu amigo (servidor) usando um mensageiro (cliente). Seu amigo recebe a mensagem e pode decidir o que fazer com ela, como lê-la, respondê-la ou descartá-la. É usado para enviar dados para o servidor, como enviar um formulário online.

PUT: Suponha que você tem um quadro branco (recurso) e deseja atualizar o que está escrito nele. Você pega um marcador e escreve uma nova informação no quadro (dados), substituindo o que estava lá antes. PUT é como atualizar o conteúdo de um recurso existente no servidor. Você envia os dados atualizados para o servidor e ele os substitui no recurso correspondente.

DELETE: Agora, imagine que você tem um brinquedo que não quer mais. Você joga fora esse brinquedo na lixeira. DELETE é como jogar fora um recurso no servidor. Você solicita ao servidor para remover um recurso específico e ele o exclui.

Então, resumindo:

GET: Obter dados do servidor.
POST: Enviar dados para o servidor.
PUT: Atualizar dados no servidor.
DELETE: Excluir dados do servidor