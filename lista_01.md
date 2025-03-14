
# Questões objetivas
**1) Considerando a execução do código abaixo, indique a alternativa correta e justifique sua resposta.**
```javascript
console.log(x);
var x = 5;
console.log(y);
let y = 10;
```
a) A saída será undefined seguido de erro 

b) A saída será 5 seguido de 10

c) A saída será undefined seguido de undefined

d) A saída será erro em ambas as linhas que utilizam console.log

Resposta: a) A saída será undefined seguido de erro.

Justificativa: 
 A saída será undefined, porquê as variáveis do tipo var podem ser chamadas mesmo quando a sua declaração está em uma parte inferior do código, porém quando isso acontece ela é chamada sem um valor definido, porque ainda não houve essa atribuição. Já as variáveis do tipo let não possuem essa caracteristica, então ao serem chamadas antes de sua declaração no código há a apresentação de um erro em sua execução.



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

a) Substituir if (a || b === 0) por if (a === 0 || b === 0)

b) Substituir if (a || b === 0) por if (a === 0 && b === 0)

c) Substituir if (a || b === 0) por if (a && b === 0)

d) Remover completamente a verificação if (a || b === 0)

Resposta: a) Substituir if (a || b === 0) por if (a === 0 || b === 0).

Justificativa:

A expressão b === 0 é validada corretamente, mas a || b === 0 não está funcionando como esperado, pois 'a' está sendo questionado como verdadeiro ou falso, já as variáveis devem sempre ser expressas antes de símbolos comparadores nas condições do if.
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

b) O código imprime 200.

c) O código imprime 50.

d) O código gera um erro.

Resposta: b) O código imprime 200.

Justificativa:

No switch deve-se apresetar sempre um break após o case, porém o case "eletrônico" não apresenta, então ele cai no próximo case, atribuindo preco = 200 aos "eletrôncos" antes de sair do bloco.
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

d) 24

Resposta: d) 24.

Justificativa:
Nesse código, após declarar o array "numeros" reazlaizamos algumas funções com os seus valores, sendo o propósito de cada uma delas, em sua ordem de aplicação, multiplicar os valores do array (no exemplo apresentado os valores são multiplicados por 2), filtrar os elementos da lista ( no exemplo selecioanamos apenas os valores maiores que cinco), somar todos os elementos do array, ou seja, reduzilos a único número (no exemplo encontramos o valor 24, pois somamos 6, 8 e 10)

______
**5) Qual será o conteúdo do array lista após a execução do código? Indique a alternativa correta e justifique sua resposta.**

```javascript
let lista = ["banana", "maçã", "uva", "laranja"];
lista.splice(1, 2, "abacaxi", "manga");
console.log(lista);
```

a) ["banana", "maçã", "uva", "abacaxi", "manga", "laranja"]

b) ["banana", "abacaxi", "manga"]

c) ["banana", "abacaxi", "manga", "laranja"]

d) ["banana", "maçã", "uva", "abacaxi", "manga"]

Resposta: c) ["banana", "abacaxi", "manga", "laranja"]

Justificativa:

A função splice tem como função remover b elementos a partir do índice a e inserir novos elementos nessas posições(no exemplo, ela remove dois elementos a partir do elemento de índice 1, ou seja remove ("maçã" e "uva") e insere ("abacaxi" e "manga") no lugar.


______
**6) Abaixo há duas afirmações sobre herança em JavaScript. Indique a alternativa correta e justifique sua resposta**

I. A herança é utilizada para compartilhar métodos e propriedades entre classes em JavaScript, permitindo que uma classe herde os métodos de outra sem a necessidade de repetir código.  
II. Em JavaScript, a herança é implementada através da palavra-chave `extends`.


a) As duas afirmações são verdadeiras, e a segunda justifica a primeira.

b) As duas afirmações são verdadeiras, mas a segunda não justifica a primeira.

c) A primeira afirmação é verdadeira, e a segunda é falsa.

d) A primeira afirmação é falsa, e a segunda é verdadeira.

Resposta: a) As duas afirmações são verdadeiras, e a segunda justifica a primeira.

Justificativa:

A primeira afirmação está correta porquê a herança em JavaScript permite que uma classe herde métodos e propriedades de outra, evitando repetição de código.
A segunda afirmação está certa porquê em JavaScript, a palavra-chave extends é usada para criar uma classe filha que herda métodos e propriedades de uma classe pai.
A segunda afirmação é uma justificativa da primeira porquê ela explica o mecanismo utilizado na implementação do conceito apresentadado na primeira afirmação. 

A palavra-chave extends implementa herança entre classes em JavaScript.
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

a) I e II são verdadeiras.

b) I, II e III são verdadeiras.

c) Apenas II é verdadeira.

d) Apenas I é verdadeira.

Resposta: a) I e II são verdadeiras.

Justificativa:

A primeira afirmação está correta porquê 'Funcionario' herda 'Pessoa', podendo assim acessar os seus atributos, isso ocorre por meio da palavra-chave extends, que faz com que a classe 'Funcionario' se torne uma classe filha da classe 'Pessoa' e do super que cham os atributos da classse pai.

A segunda afirmação está correta porquê apresentar() da clase Funcionario chama o apresentar() da classe Pessoa utilizando o super, ou seja, ela se sobrepõe, porém ela chama e utiliza os atributos do método anterior.

A afirmação III é falsa, pois JavaScript é uma linguagem de programação que suporta herança com class.

______

**8) Analise as afirmações a seguir. Indique a alternativa correta e justifique sua resposta.**

**Asserção:** O conceito de polimorfismo em Programação Orientada a Objetos permite que objetos de diferentes tipos respondam à mesma mensagem de maneiras diferentes.  
**Razão:** Em JavaScript, o polimorfismo pode ser implementado utilizando o método de sobrecarga de métodos em uma classe.

a) A asserção é falsa e a razão é verdadeira.

b) A asserção é verdadeira e a razão é falsa.

c) A asserção é verdadeira e a razão é verdadeira, mas a razão não explica a asserção.

d) A asserção é verdadeira e a razão é verdadeira, e a razão explica a asserção.

Resposta: b) A asserção é verdadeira e a razão é falsa.

Justificativa: 
A primeira sentença está correta pois, o polimorfismo em Programação Orientada a Objetos (POO) permite que diferentes classes implementem um mesmo método de formas distintas. Ou seja, objetos de diferentes classes podem responder a um mesmo método, cada um com seu próprio comportamento.
A segunda sentença está errada, pois a linguagem de programação JavaScript não suporta sobrecarga de métodos da forma tradicional como em outras linguagens. Sendo assim, em JavaScript, se duas funções com o mesmo nome são definidas dentro de uma classe, a última definição substitui as anteriores.

# Questões dissertativas
9) O seguinte código deve retornar a soma do dobro dos números de um array, mas contém erros. Identifique os problema e corrija o código para que funcione corretamente. Adicione comentários ao código explicado sua solução para cada problema.

```javascript
function somaArray(numeros) {

    for (i = 0; i < numeros.size; i++) {
        soma = 2*numeros[i];
    }
    return soma;
}
console.log(somaArray([1, 2, 3, 4]));

```
Resposta:
```javascript
function somaArray(numeros) {
    let soma = 0; // Cria uma variável paar guardar o valor da soma dos números do array
    for (let i = 0; i < numeros.length; i++) { // Utiliza o .lenght, comando correto para determinar o tamanho de um array
        soma += 2 * numeros[i]; // Soma cada novo elemento ao valor da variável "soma"
    }
    return soma; // Retorna o valor da soma do dobro de todos os elementos 
}
console.log(somaArray([1, 2, 3, 4])); // Chama a função somaArray e imprime o seu valor de retorno 
```
______
10) Crie um exemplo prático no qual você tenha duas classes:

- Uma classe `Produto` com atributos `nome` e `preco`, e um método `calcularDesconto()` que aplica um desconto fixo de 10% no preço do produto.
- Uma classe `Livro` que herda de `Produto` e modifica o método `calcularDesconto()`, aplicando um desconto de 20% no preço dos livros.

Explique como funciona a herança nesse contexto e como você implementaria a modificação do método na classe `Livro`.
Resposta:
```javascript
class Produto { // Cria a classe Produto
    constructor(nome, preco) { // Cria os atributos da classe
        this.nome = nome; // define o atributo nome
        this.preco = preco; //define o atributo preço
    }
    calcularDesconto() { // Cria o método de desconto 
        return this.preco * 0.9; // Aplica 10% de desconto sobre o produto 
        // Retorna o valor final do produto
    }
}

class Livro extends Produto { // Cria a classe Livro que herda os atributos da classe Produto
    constructor(nome, preco) { // Cria s atributos da classe Livro
        super(nome, preco); // Chama os atributos herdados da classe Produto
    } 
    calcularDesconto() {
        return this.preco * 0.8; // Aplica 20% de desconto ao preço Livro
    }
}

var celular = new Produto("Celular", 1000); //Cria um objeto para classe Produto
var livro = new Livro("O pequeno príncipe", 100); // Cria um objeto para classe Livro

console.log(celular.calcularDesconto()); // Imprime o preço final do objeto criado na classe Produto
console.log(livro.calcularDesconto()); // Imprime o preço final do objeto criado na classe Livro
```
A herança nesse exemplo permite que os objetos da classe Livro recebam os atributos declarados na classe Produtos, de modo que não precise haver duplicação da declaração desse desses atributos. 
O novo método criado para a classe Livro aplica um novo valor de desconto, valor esse que é utilizado apenas para os objetos da classe Livro e não da classe Preodutos que possui um método que aplica um desconto menor sobre os seus objetos.
