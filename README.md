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
