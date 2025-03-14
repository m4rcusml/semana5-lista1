# Semana 5 - Lista 1
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

b) A saída será 5 seguido de 10

c) A saída será undefined seguido de undefined

d) A saída será erro em ambas as linhas que utilizam console.log

> Resposta: **a)**
>
> Justificativa: a primeira saída será undefined pois o javascript, ao iniciar a execução de um código, prioriza a inicialização das variáveis declaradas com `var`, mas ela só atribui o valor quando a linha de código em que ocorre a atribuição chegar. Portanto, na linha 1, `var x` já existe, mas seu valor ainda é undefined.
>
> A segunda saída dará erro pois o let não é inicializado antes da execução do código, então na linha 3, `let y` ainda não existe, o que resulta no erro.

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

b) Substituir if (a || b === 0) por if (a === 0 && b === 0)

c) Substituir if (a || b === 0) por if (a && b === 0)

d) Remover completamente a verificação if (a || b === 0)

> Resposta: **a)**
>
> Justificativa: Dentro de um if, quando não há uma condicional explícita como `b === 0`, o javascript por padrão transforma a variável em um valor boleano com base nos conceitos de truthy e falsy. Então, no código acima o que está acontecendo é: ele está verificando se a variável `a` é diferente de valores falsy como 0, null, undefined.
>
> A lógica requisitada pelo código é que quando o valor de a ou b for 0, o código dentro do if seja executado, mas caso o a seja 0, ele será transformado em false e o código dentro do if não será executado.
>
> Solução: if (a === 0 || b === 0)

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

c) O código imprime 50.

d) O código gera um erro.

> Resposta: **b)**
>
> Justificativa: O certo seria imprimir 1000, mas o `case "eletrônico"` não possui um `break`, portanto, o javascript continua lendo o próximo caso, que é o de vestuário, onde 200 é atribuido a variavel preço, e só nesse momento o `break` surge, deixando a variavel `preco` com um valor final de 200.

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

> Resposta: **d)**
>
> Justificativa: o map percorre o array, multiplica todos os valores por 2 e retorna um array com todos os elementos duplicados. Depois, o filter percorre todo o array e retorna uma lista somente com os elementos que forem maiores que 5. Por fim, o reduce realiza uma soma de todos os elementos, retornando um número, que é 24, e atribuindo à variável `resultado`.

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

d) ["banana", "maçã", "uva", "abacaxi", "manga"]

> Resposta: **c)**
>
> Justificativa: o `splice()` serve para remover itens de uma lista e substituí-los por novos e funciona assim: o primeiro parâmetro é o índice onde vai começar a substituição dos itens no enunciado, a substituição começa no segundo elemento (index 1), o segundo parâmetro é a quantidade de elementos a serem substituídos a partir do index, no enunciado 2 itens foram substituidos (index 1 e 2), e os outros parâmetros são os elementos que substituirão os elementos antigos.

______
**6) Abaixo há duas afirmações sobre herança em JavaScript. Indique a alternativa correta e justifique sua resposta**

**I. A herança é utilizada para compartilhar métodos e propriedades entre classes em JavaScript, permitindo que uma classe herde os métodos de outra sem a necessidade de repetir código.**

**II. Em JavaScript, a herança é implementada através da palavra-chave `extends`.**

a) As duas afirmações são verdadeiras, e a segunda justifica a primeira.

**b) As duas afirmações são verdadeiras, mas a segunda não justifica a primeira.**

c) A primeira afirmação é verdadeira, e a segunda é falsa.

d) A primeira afirmação é falsa, e a segunda é verdadeira.

> Resposta: **b)**
>
> Justificativa: As duas são verdadeiras, mas a segunda não justifica a primeira, pois a segunda só explica como criar uma herança e não fala nada relacionado a primeira afirmação.

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

**I) A classe Funcionario herda de Pessoa e pode acessar os atributos nome e idade diretamente.**

**II) O método `apresentar()` da classe Funcionario sobrepõe o método `apresentar()` da classe Pessoa, mas chama o método da classe pai usando `super`.**

~~III) O código não funciona corretamente, pois Funcionario não pode herdar de Pessoa como uma classe, já que o JavaScript não suporta herança de classes.~~

Quais das seguintes afirmações são verdadeiras sobre o código acima?

**a) I e II são verdadeiras.**

b) I, II e III são verdadeiras.

c) Apenas II é verdadeira.

d) Apenas I é verdadeira.

> Resposta: **a)**
>
> Justificativa: A III é falsa pois o javascript suporta sim herança entre classes.
>
>A II é verdadeira pois ao chamar o método `apresentar()` a partir da classe Funcionário, será executado o método apresentar que dessa classe e não da classe Pessoa, o que significa que foi sobrescrito, mas também é verdade que o método apresentar da classe pai (Pessoa) está sendo chamado por meio do super, pois esse super acessa diretamente a classe pai. 
>
> A I também é verdadeira pois uma herança faz justamente isto: dá acesso à classe filho os atributos e métodos da classe pai.

______

**8) Analise as afirmações a seguir. Indique a alternativa correta e justifique sua resposta.**

**Asserção:** O conceito de polimorfismo em Programação Orientada a Objetos permite que objetos de diferentes tipos respondam à mesma mensagem de maneiras diferentes.  
**Razão:** Em JavaScript, o polimorfismo pode ser implementado utilizando o método de sobrecarga de métodos em uma classe.

a) A asserção é falsa e a razão é verdadeira.

**b) A asserção é verdadeira e a razão é falsa.**

c) A asserção é verdadeira e a razão é verdadeira, mas a razão não explica a asserção.

d) A asserção é verdadeira e a razão é verdadeira, e a razão explica a asserção.

> Resposta: **b)**
>
> Justificativa: A asserção está correta, pois esse é o conceito de polimorfismo, porém a razão está errada, já que o javascript não suporta sobrecarga de métodos.

______

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

> Reposta: O erro está na linha `soma = 2*numeros[i];`. Nessa linha, está sendo atribuido somente o dobro do valor do último index lido, sobrescrevendo o resultado anterior pois não há nenhum sinal de +.
> Além disso, a variável `soma` não está sendo declarada em lugar nenhum.
>
> Código corrigido:

```javascript
function somaArray(numeros) {
    let soma;
    for (i = 0; i < numeros.size; i++) {
        soma += 2*numeros[i];
    }
    return soma;
}
console.log(somaArray([1, 2, 3, 4]));
```

______
10) Crie um exemplo prático no qual você tenha duas classes:

- Uma classe `Produto` com atributos `nome` e `preco`, e um método `calcularDesconto()` que aplica um desconto fixo de 10% no preço do produto.
- Uma classe `Livro` que herda de `Produto` e modifica o método `calcularDesconto()`, aplicando um desconto de 20% no preço dos livros.

Explique como funciona a herança nesse contexto e como você implementaria a modificação do método na classe `Livro`.

**Classe Produto:**
```javascript
class Produto {
  constructor(nome, preco) {
    this.nome = nome;
    this.preco = preco;
  }

  calcularDesconto() {
    return this.preco - this.preco * 0.1;
  }
}
```

**Classe Livro:**
```javascript
class Livro extends Produto {
  constructor(nome, preco) {
    super(nome, preco);
  }

  calcularDesconto() {
    return this.preco - this.preco * 0.2;
  }
}
```

**Explicação**

A classe Livro herda todos os métodos e atributos da classe Produto, ou seja, uma instância da classe Livro também possuiria os atributos de nome e de preço e também possuiria o método de calcular desconto. No entando, a classe Livro sobrepoe o funcionamento do método calcularDesconto da classe Produto para que em vez de 10%, aplique 20% de desconto.