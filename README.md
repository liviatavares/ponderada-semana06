# Instruções
- Faça uma cópia deste arquivo .md para um repositório próprio
- Resolva as 8 questões objetivas assinalando a alternativa correta e **justificando sua resposta.**
- Resolva as 2 questões dissertativas escrevendo no próprio arquivo .md
- Lembre-se de utilizar as estruturas de código como ``esta aqui com ` `` ou
```javascript
//esta aqui com ```
let a = "olá"
let b = 10
print(a)
```
- Resolva as questões com uso do Visual Studio Code ou ambiente similar.
- Teste seus códigos antes de trazer a resposta para cá.
- Cuidado com o uso de ChatGPT (e similares), pois entregar algo só para ganhar nota não fará você aprender. Não seja dependente da máquina!
- Ao final, publique seu arquivo lista_01.md com as respostas em seu repositório, e envie o link pela Adalove. 

# Questões objetivas
**1) Considerando a execução do código abaixo, indique a alternativa correta e justifique sua resposta.**
```javascript
console.log(x);
var x = 5;
console.log(y);
let y = 10;
```
**a) A saída será undefined seguido de erro**

o console.log do x resultará em undefined pois o programa reconhece que x é uma variável existente posteriormente (pelo uso de var, que tem escopo global), mas não consegue acessá-la, pois o console.log vem antes da variável ser definida. no caso do console.log do y, ele não consegue acessar o valor de y pois ele foi definido depois do console.log, mas como let tem escopo menor, resultará em erro, e não em undefined.

b) A saída será 5 seguido de 10

c) A saída será undefined seguido de undefined

d) A saída será erro em ambas as linhas que utilizam console.log


**2) O seguinte código JavaScript tem um erro que impede sua execução correta. Analise e indique a opção que melhor corrige o problema. Justifique sua resposta.**

```javascript
function soma(a, b) {
    if (a || b === 0) {
        return "Erro: número inválido";
    }
    return a + b;
}
console.log(soma(2, 0));
```

**a) Substituir if (a || b === 0) por if (a === 0 || b === 0)**

do jeito que está escrito, apenas b === 0 retorna "erro: número inválido". para que a === 0 também retorne isso, deve-se substituir o valor do if para adicionar essa condição.

b) Substituir if (a || b === 0) por if (a === 0 && b === 0)

c) Substituir if (a || b === 0) por if (a && b === 0)

d) Remover completamente a verificação if (a || b === 0)

______
**3) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
function calcularPreco(tipo) {
    let preco;

    switch(tipo) {
        case "eletrônico":
            preco = 1000;
        case "vestuário":
            preco = 200;
            break;
        case "alimento":
            preco = 50;
            break;
        default:
            preco = 0;
    }

    return preco;
}

console.log(calcularPreco("eletrônico"));
```

a) O código imprime 1000.

**b) O código imprime 200.**

como não há um break após o case "eletrônico", o código continuará rodando até encontrar um break, mesmo que este não seja o pedido pelo console.log. como o próximo break está após a condição de "vestuário", o console.log, ao invés de imprimir 1000 como deveria, imprimirá 200. para que o código ficasse correto, seria necessário colocar um `break;` após o case "eletrônico".

c) O código imprime 50.

d) O código gera um erro.

______
**4) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
let numeros = [1, 2, 3, 4, 5];

let resultado = numeros.map(x => x * 2).filter(x => x > 5).reduce((a, b) => a + b, 0);

console.log(resultado);
```
a) 0

b) 6

c) 18

**d) 24**

o comando numeros.map(x => x * 2) cria uma nova lista que substitui todos os valores de x por x * 2. ou seja, o novo array será [2, 4, 6, 8, 10].
o comando numeros.filter(x => x > 5) filtra todos os números maiores que 5. ou seja, se colocasse um console.log(resultado) após apenas esses dois comandos, imprimiria [6, 8, 10].
o comando numeros.reduce((a, b) => a + b, 0) tem como forma (acumulador, valor atual) => (acumulador + valor atual, valor inicial). nesse caso, ao colocar (a,b) => (a+b, 0) o programa somará todos os números do array. então, o resultado do console.log será 0 + 6 + 8 + 10 = 24.

______
**5) Qual será o conteúdo do array lista após a execução do código? Indique a alternativa correta e justifique sua resposta.**

```javascript
let lista = ["banana", "maçã", "uva", "laranja"];
lista.splice(1, 2, "abacaxi", "manga");
console.log(lista);
```

a) ["banana", "maçã", "uva", "abacaxi", "manga", "laranja"]

b) ["banana", "abacaxi", "manga"]

**c) ["banana", "abacaxi", "manga", "laranja"]**

o comando lista.splice tem como forma .splice(índice do início, quantos números devem ser removidos a partir desse índice, e o(s) valor(es) a serem adicionados no lugar desses removidos). então, `lista.splice(1, 2, "abacaxi", "manga")` inicia do índice 1, ou seja, "maçã", remove 2 elementos, ou seja, "maçã" e "uva", e adiciona mais dois no lugar desses ("abacaxi" e "manga"). 

d) ["banana", "maçã", "uva", "abacaxi", "manga"]
______
**6) Abaixo há duas afirmações sobre herança em JavaScript. Indique a alternativa correta e justifique sua resposta**

I. A herança é utilizada para compartilhar métodos e propriedades entre classes em JavaScript, permitindo que uma classe herde os métodos de outra sem a necessidade de repetir código.  
II. Em JavaScript, a herança é implementada através da palavra-chave `extends`.


a) As duas afirmações são verdadeiras, e a segunda justifica a primeira.

**b) As duas afirmações são verdadeiras, mas a segunda não justifica a primeira.**

não há necessariamente uma relação de justificativa, mas sim de complemento, mas as duas são corretas. o extends serve para criar uma classe filha de uma classe pai já previamente existente. como exemplo, nos arquivos dos jogos de phaser, utilizamos comumente 
```javascript
 classe NomeDaClasse extends Phaser.Scene {}
```

c) A primeira afirmação é verdadeira, e a segunda é falsa.

d) A primeira afirmação é falsa, e a segunda é verdadeira.
______
**7) Dado o seguinte código. Indique a alternativa correta e justifique sua resposta.**

```javascript
class Pessoa {
  constructor(nome, idade) {
    this.nome = nome;
    this.idade = idade;
  }

  apresentar() {
    console.log(`Olá, meu nome é ${this.nome} e tenho ${this.idade} anos.`);
  }
}

class Funcionario extends Pessoa {
  constructor(nome, idade, salario) {
    super(nome, idade);
    this.salario = salario;
  }

  apresentar() {
    super.apresentar();
    console.log(`Meu salário é R$ ${this.salario}.`);
  }
}
```


I) A classe Funcionario herda de Pessoa e pode acessar os atributos nome e idade diretamente.  
II) O método `apresentar()` da classe Funcionario sobrepõe o método `apresentar()` da classe Pessoa, mas chama o método da classe pai usando `super`.  
III) O código não funciona corretamente, pois Funcionario não pode herdar de Pessoa como uma classe, já que o JavaScript não suporta herança de classes.

Quais das seguintes afirmações são verdadeiras sobre o código acima?

**a) I e II são verdadeiras.**

Funcionario é uma classe filha, enquanto Pessoa é uma classe pai. O super, nesse caso, está indicando, após o constructor, quais propriedades foram herdadas do constructor da classe pai (nesse caso, nome e idade). Apesar dos métodos terem o mesmo nome, o segundo apresentar funciona pois herda características do primeiro (via super).

b) I, II e III são verdadeiras.

c) Apenas II é verdadeira.

d) Apenas I é verdadeira.

______

**8) Analise as afirmações a seguir. Indique a alternativa correta e justifique sua resposta.**

**Asserção:** O conceito de polimorfismo em Programação Orientada a Objetos permite que objetos de diferentes tipos respondam à mesma mensagem de maneiras diferentes.  
**Razão:** Em JavaScript, o polimorfismo pode ser implementado utilizando o método de sobrecarga de métodos em uma classe.

a) A asserção é falsa e a razão é verdadeira.

b) A asserção é verdadeira e a razão é falsa.

c) A asserção é verdadeira e a razão é verdadeira, mas a razão não explica a asserção.

**d) A asserção é verdadeira e a razão é verdadeira, e a razão explica a asserção.**

O polimorfismo significa que um método de mesmo nome pode ser utilizado de várias maneiras diferentes, contanto que seus argumentos mudem toda vez. Uma das maneiras de aplicar o polimorfismo é a sobrecarga de métodos, em que a escolha de qual método irá ser chamado pelo programa principal dependerá de acordo com o seu tipo de objeto. Portanto, tanto a asserção quanto a razão são verdadeiras, e a razão complementa e explica a asserção, pois exemplifica como o polimorfismo na POO pode responder à mesma mensagem de jeitos diferentes (pela sobrecarga).


______

# Questões dissertativas
9) O seguinte código deve retornar a soma do dobro dos números de um array, mas contém erros. Identifique os problema e corrija o código para que funcione corretamente. Adicione comentários ao código explicado sua solução para cada problema.

```javascript
function somaArray(numeros) {
    //a soma não tem um valor inicial definido
    //numeros.size deveria ser numeros.length para significar o tamanho total do array
    for (i = 0; i < numeros.size; i++) {
        //soma não está definida, precisando ser declarada com um let
        soma = 2*numeros[i];
        //2 * numeros[i] está apenas multiplicando os valores por 2, mas não está somando-os
    }
    return soma;
}
console.log(somaArray([1, 2, 3, 4]));
```
o código consertado será:
```javascript
function somaArray(numeros) {
    let soma = 0;
    for (i = 0; i < numeros.length; i++) {
        soma += 2*numeros[i];
    }
    return soma;
}
console.log(somaArray([1, 2, 3, 4]));
//imprime 20
```


______
10) Crie um exemplo prático no qual você tenha duas classes:

- Uma classe `Produto` com atributos `nome` e `preco`, e um método `calcularDesconto()` que aplica um desconto fixo de 10% no preço do produto.
- Uma classe `Livro` que herda de `Produto` e modifica o método `calcularDesconto()`, aplicando um desconto de 20% no preço dos livros.

Explique como funciona a herança nesse contexto e como você implementaria a modificação do método na classe `Livro`.

Para essa resolução, interpretei que todos os produtos tinham desconto fixo de 10%, e todos os livros tinham desconto de 20%, além dos 10% já garantidos por serem produtos, ou seja, todos os livros têm 28% de desconto acima do preço original.

```javascript
//criando a classe Produto
class Produto {
    //adicionando as propriedades nome e preço
        constructor (nome, preco) {
            this.nome = nome;
            this.preco = preco;
        }
    
        //criando o primeiro método de calcular desconto
        calcularDesconto() {

        //criando uma nova variável que vai armazenar o valor do preço com desconto
          this.precoMenor = this.preco * 0.9

        //imprime o novo preço
          console.log("aqui, todos os produtos têm 10% de desconto!")
          console.log("preço do produto: " + this.precoMenor);
        }
    
        }
    
        //criando a outra classe Livro que herda da classe Produto
        class Livro extends Produto {
    
        //importando da classe pai as propriedades nome e preço
        constructor (nome, preco) {
            super(nome, preco);
        }
    
        //atualizando a função de calcular desconto
        calcularDesconto() {

        //importando o método do Produto
            super.calcularDesconto();

        //definindo o novo preço
            this.precoMenorAinda = this.precoMenor * 0.8

        //imprime o preço atualizado
            console.log("mas aqui, todos os livros tem 20% de desconto, além dos 10%!")
            console.log("preço final do livro: " + this.precoMenorAinda);
        }
    
        }
    
        //exemplo: criando um livro1
        const livro1 = new Livro("livro1", 50)
        livro1.calcularDesconto();
        //quando o código roda só com esse livro1, mostra o seguinte:
        //"aqui, todos os produtos têm 10% de desconto!
        //preço do produto: 45
        //mas aqui, todos os livros tem 20% de desconto, além dos 10%!
        //preço final do livro: 36"
        
        
        //exemplo: criando um produto1
        const produto1 = new Produto("produto1", 100)
        produto1.calcularDesconto();
        //quando o código roda só com esse produto1, mostra o seguinte:
        //"aqui, todos os produtos têm 10% de desconto!
        //preço do produto: 90"
```
