# minidan-framework
Um framework simples para estilização de páginas web, com o objetivo de ser minimalista, elegante e, principalmente, muito simples de usar.

<hr>

<p>Atualmente, o framework possúi apenas  as configurações necessárias para  fazer:</p>
<ul>
<li>Cabeçalho;</li>
<li>Caixas;</li>
<li>Botões;</li>
<li>Modais;</li>
<li>Tabelas;</li>
<li>Cartões;</li>
<li>Listas;</li>
<li>Formulários;</li>
</ul> 

<hr>

<h3>Iniciando:</h3>
<p>Copie a pasta assets para a estrutura de seu projeto.</p>
<p>Crie sua estrutura html e adicione ao cabeçalho as tags:</p>

```
<meta charset="UTF-8">
<meta http-equiv="X-UA-Compatible" content="IE=edge">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<link rel="stylesheet"
    href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@48,400,0,0" />
<link rel="stylesheet" type="text/css" href="assets/css/minidan-framework.css">
```
<p>Antes de fechar sua tag body adicione a tag script da seguinte forma:</p>

```
<script src="assets/js/minidan-framework.js"></script>
```
<hr>

<h4>Como fazer Cabeçalho:</h4>

<p>Existe, por enquanto, apenas uma configuração para o cabeçalho, que se dá pela seguinte estrutura, devendo ser colocada logo em seguida da tag body, antes da div com classe 'container':</p>

```
<header class="header">
    <div class="all-menu">
        <input type="checkbox" id="menu" class="input-menu">
        <label for="menu" class="label-menu">
            <span class="icon-menu"></span>

        </label>
        <div class="content-menu">
            <ul>
                <li><a href="#">
                        <p>Início</p>
                        <span class="material-symbols-outlined">
                            home
                        </span>
                    </a></li>
                <li><a href="#">
                        <p>Configurações</p>
                        <span class="material-symbols-outlined">
                            settings
                        </span>
                    </a></li>
                <li><a href="#">
                        <p>Conta</p>
                        <span class="material-symbols-outlined">
                            account_circle
                        </span>
                    </a></li>
            </ul>
        </div>
    </div>
</header>
```

<h4>Como fazer Caixas:</h4>

<p>Atualmente há duas caixas que ajudam na separação, organização e responsividade:</p>
<ul>
    <li>container;</li>
    <li>box.</li>
</ul>

<p>Container: para um contexto geral, geralmente para englobar todo conteúdo da página.</p>
<p>Box: para contexto menores, servindo como separador de conteúdos de dentro da página.</p>

```
<div class="container">
    <div class="box">
        conteúdo
    <div>
</div>
```

<h4>Como fazer botões:</h4>
<p>Basta  definir a classe como btn-{cor}, podendo ser {cor}:</p>
<ul>
    <li>branco (padrão)</li>
    <li>verde</li>
    <li>vermelho</li>
    <li>azul</li>
</ul>

```
<button class="btn">btn</button>
<button class="btn-green">btn-green</button>
<button class="btn-red">btn-red</button>
<button class="btn-blue">btn-blue</button>

```
<h4>Como fazer tabelas:</h4>

<p>Defina a classe da tag 'table' como 'table' e defina os  ítens do cabeçalho.</p>
<p>No corpo da tabela, defina em cada ítem um 'data-title="{nome do item}"', é necessário para responsividade.</p>

```
<table class="table">
    <thead>
        <th>Id</th>
        <th>Nome</th>
        <th>Idade</th>
        <th>Profissão</th>
        <th>Descrição</th>
        <th>Opção</th>
    </thead>
    <tbody>
        <tr>
            <th data-title="Id">1</th>
            <td data-title="Nome">Daniel</td>
            <td data-title="Idade">22</td>
            <td data-title="Profissão">Programador</td>
            <td data-title="Descrição" class="td-desc">
                <p>Estudante, gosta de estudar, mas só o que gosta.</p>
            </td>
            <td class="td-btn">
                <div>
                    <button class="btn-green">Ok</button>
                    <button class="btn-red">Delete</button>
                    <button class="btn-blue">edit</button>
                </div>
            </td>
        </tr>
        <tr>
            <th data-title="Id">2</th>
            <td data-title="Nome">Sara</td>
            <td data-title="Idade">20</td>
            <td data-title="Profissão">Médica</td>
            <td data-title="Descrição" class="td-desc">
                <p>Estudante, gosta de estudar,
                    mas só o que gosta.Estudante,
                    gosta de estudar, mas só o que gosta.
                    Estudante, gosta de estudar, mas só o
                    que gosta.Estudante, gosta de estudar,
                    mas só o que gosta.Estudante, gosta de estudar, mas só o que gosta.
                    Estudante, gosta de estudar, mas só o que gosta.
                <p>

            </td>
            <td class="td-btn">
                <div>
                    <button class="btn-green">Ok</button>
                    <button class="btn-red">Delete</button>
                    <button class="btn-blue">edit</button>
                </div>
            </td>
        </tr>
    </tbody>
</table>
```
<h4>Como fazer modais:</h4>

<p>Crie um botão e passe no atributo 'onclick' o valor passando uma função chamada 'openModal("{id-do-modla}")'.</p>

```
<button class="btn-blue" onclick="openModal('#modal1')">Mostrar Modal</button>
```

<p>Crie o modal em qualquer lugar do código que esteja fora do container principal, com um id unico e e a classe como 'modal'.</p>
<p>Dentro do modal, temos seu conteúdo colocado dentro de uma div com classe 'content-modal'.<br>
Não é necessário colocar o 'X' para fechar o modal, caso tenha um botão que o faça, mas para adicioná- lo basta colocar uma div com a classe 'close' e dentro o ícone de fechar.<br>
A segunda classe importante é a 'text-modal', onde poderão ser adicionados os textos.<br>
Por ultimo, a classe 'footer-modal', que serve principalmente para adicionar botões.</p>

```
<div class="modal" id="modal1">
    <div class="content-modal">
        <div class="close">
            <span class="material-symbols-outlined" onclick="closeModal('#modal1')">
                close
            </span>
        </div>
        <div class="title">
            <h3>Título Modal</h3>
        </div>
        <div class="text-modal">
            <p>Sou um texto dentro do Modal!</p>
        </div>
        <div class="footer-modal">
            <button class="btn-blue">Salvar</button>
            <button class="btn-red" onclick="closeModal('#modal1')">Fechar</button>
        </div>
    </div>
</div>
```
<h4>Como fazer cartões:</h4>

<p>É importante colocar os cartões dentro de um grupo de cartões, definindo uma div com a classe 'card-group'.<br>
Para criar o cartão, adicione a uma div a classe 'card'. Neste cartão você pode colocar primeiro uma imagem, separada por uma div com a classe 'image-card'. Depois, adicionar o conteúdo do cartão com a classe 'content-card'. Por fim, adionar preços ou botões dentro de uma div com classe 'footer-card'.</p>

```
<div class="card-group">
    <div class="title">
        <h4>Grupo de cartões</h4>
    </div>
    <div class="card">
        <div class="image-card">
            <img src="imgteste.png" alt="teste">
        </div>
        <div class="title">
            <h3>Título</h3>
        </div>
        <div class="content-card">
            conteúdo aqui...
        </div>
        <div class="footer-card">
            <h2>R$ 10,00</h2
            <a href="#" class="btn-blue">Editar</a>
        </div>
    </div>
</div>
```

<h4>Como fazer Listas:</h4>

<p>As listas podem ser criadas colocando na tag 'ul' a classe 'list', apenas isso basta para criar uma lista simples, porém, para acrescentar botões, utilizamos uma separação com uma div, levando a classe 'list-btn', como no exemplo abaixo:</p>

```
<ul class="list">
    <li>
        <p>Exemplo 1</p>
        <div class="list-btn">
            <button class="btn-green">
                <span class="material-symbols-outlined">
                    done
                </span>
            </button>
            <button class="btn-red">
                <span class="material-symbols-outlined">
                    close
                </span>
            </button>
        </div>
    </li>
</ul>
```

<p>Para criar lista com detalhes, basta colocar a classe 'list-details' na tag 'li' em questão, depois adicionar a tag 'details' e dentro a tag 'summary'.</p>

```
<li class="list-details">
    <details>
        <summary>
            Ver mais
        </summary>
        <p>1</p>
        <p>2</p>
        <p>3</p>
    </details>
</li>
```
<p>Exemplo com botões:</p>

```
<li class="list-details">
    <details>
        <summary>
            Ver mais
        </summary>
        <p>1</p>
        <p>2</p>
        <p>3</p>
    </details>
    <div class="list-btn">
        <button class="btn-green">
            <span class="material-symbols-outlined">
                done
            </span>
        </button>
        <button class="btn-red">
            <span class="material-symbols-outlined">
                close
            </span>
        </button>
    </div>
</li>
```
<h4>Como fazer formulário:</h4>

<p>Na tag 'form' inclua a classe 'form'. Para cada input a ser colocado, adicione dentro de uma 'div' com a classe 'input'.<br>*Nesta versão ainda não há estilização para inputs com type = checkbox, color e radio, portanto, não é recomendado colocá- lo dentro da 'div' com classe 'input'.*<br> O input do tipo file, pode ser colocado numa 'div' de classe 'input', mas em breve terá atualizações em sua aparência</p>

```
<form action="" method="" class="form">
    <div class="input">
        <input type="text" name="texto" placeholder="texto">
        <label for="texto">Texto</label>
    </div>
    <div class="input">
        <input type="number" name="numero" placeholder="numero">
        <label for="numero">Número</label>
    </div>
    <div class="input">
        <input type="email" name="email" placeholder="email">
        <label for="email">Email</label>
    </div>
    <div class="input">
        <input type="date" name="data" placeholder="data">
        <label for="data">data</label>
    </div>
    <div class="input">
        <input type="file" name="file" placeholder="file">
        <label for="file">Arquivo</label>
    </div>
    <div class="input">
        <textarea name="textarea" id="textarea" cols="30" rows="10"></textarea>
        <label for="textarea">Àrea de Texto</label>
    </div>
    <input type="submit" value="Cadastrar" class="btn-green">
</form>
```
