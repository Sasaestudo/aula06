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




