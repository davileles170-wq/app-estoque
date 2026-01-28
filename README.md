<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Controle de Estoque</title>
  <link rel="stylesheet" href="css/style.css">
  <link rel="manifest" href="manifest.json">
</head>
<body class="center">
  <form class="card" onsubmit="login(event)">
    <h2>Controle de Estoque</h2>
    <input type="email" id="email" placeholder="Email" required>
    <input type="password" id="senha" placeholder="Senha" required>
    <button type="submit">Entrar</button>
  </form>

  <script src="js/app.js"></script>
</body>
</html>
<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Dashboard | Estoque</title>
  <link rel="stylesheet" href="css/style.css">
</head>
<body>
  <h2>Painel</h2>
  <div class="menu">
    <a href="produtos.html">📦 Produtos</a>
    <a href="movimentacoes.html">🔄 Movimentações</a>
    <a href="relatorios.html">📊 Relatórios</a>
  </div>
</body>
</html>
<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Produtos</title>
  <link rel="stylesheet" href="css/style.css">
</head>
<body>
  <h2>Produtos</h2>
  <form id="form-produto" onsubmit="cadastrarProduto(event)">
    <input id="nome" placeholder="Nome do produto" required>
    <input id="quantidade" type="number" placeholder="Quantidade" required>
    <input id="preco" type="number" step="0.01" placeholder="Preço" required>
    <button type="submit">Cadastrar</button>
  </form>

  <ul id="lista-produtos"></ul>

  <script src="js/app.js"></script>
</body>
</html>
<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Movimentações</title>
  <link rel="stylesheet" href="css/style.css">
</head>
<body>
  <h2>Movimentações</h2>
  <form onsubmit="registrarMovimentacao(event)">
    <input id="produto" placeholder="Produto" required>
    <input id="quantidade" type="number" placeholder="Quantidade" required>
    <select id="tipo">
      <option value="entrada">Entrada</option>
      <option value="saida">Saída</option>
    </select>
    <button type="submit">Registrar</button>
  </form>

  <ul id="lista-movimentacoes"></ul>

  <script src="js/app.js"></script>
</body>
</html>
<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Relatórios</title>
  <link rel="stylesheet" href="css/style.css">
</head>
<body>
  <h2>Relatórios</h2>
  <ul id="relatorios">
    <li>Total de Produtos</li>
    <li>Produtos em Estoque Baixo</li>
    <li>Últimas Movimentações</li>
  </ul>
</body>
</html>
body {
  font-family: Arial, sans-serif;
  background: #f4f6f8;
  margin: 0;
  padding: 20px;
}

.card, form {
  background: #fff;
  padding: 20px;
  border-radius: 10px;
  max-width: 400px;
  margin: auto;
}

input, button, select {
  width: 100%;
  padding: 12px;
  margin-top: 10px;
  border-radius: 5px;
}

button {
  background: #0a7cff;
  color: white;
  border: none;
  font-size: 16px;
}

.menu a {
  display: block;
  background: #fff;
  margin: 10px 0;
  padding: 15px;
  border-radius: 8px;
  text-decoration: none;
  color: #000;
  font-weight: bold;
}

@media(max-width:600px){
  body { padding: 10px; }
  .card, form { width: 90%; }
}
// Armazenamento local
let produtos = JSON.parse(localStorage.getItem("produtos")) || [];
let movimentacoes = JSON.parse(localStorage.getItem("movimentacoes")) || [];

// Login fake
function login(e){
  e.preventDefault();
  const email = document.getElementById("email").value;
  const senha = document.getElementById("senha").value;
  if(email && senha){
    alert("Login realizado!");
    window.location.href = "dashboard.html";
  }
}

// Produtos
function cadastrarProduto(e){
  e.preventDefault();
  const nome = document.getElementById("nome").value;
  const quantidade = document.getElementById("quantidade").value;
  const preco = document.getElementById("preco").value;
  produtos.push({nome, quantidade, preco});
  localStorage.setItem("produtos", JSON.stringify(produtos));
  alert("Produto cadastrado!");
}

// Movimentações
function registrarMovimentacao(e){
  e.preventDefault();
  const produto = document.getElementById("produto").value;
  const quantidade = document.getElementById("quantidade").value;
  const tipo = document.getElementById("tipo").value;
  movimentacoes.push({produto, quantidade, tipo, data: new Date()});
  localStorage.setItem("movimentacoes", JSON.stringify(movimentacoes));
  alert("Movimentação registrada!");
}
{
  "name": "Controle de Estoque",
  "short_name": "Estoque",
  "start_url": "index.html",
  "display": "standalone",
  "background_color": "#ffffff",
  "theme_color": "#0a7cff",
  "icons": [
    {
      "src": "icon-192.png",
      "sizes": "192x192",
      "type": "image/png"
    },
    {
      "src": "icon-512.png",
      "sizes": "512x512",
      "type": "image/png"
    }
  ]
}
