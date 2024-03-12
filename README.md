1) Observe o trecho de código abaixo: 
```portugol
int INDICE = 13, SOMA = 0, K = 0; 
enquanto K < INDICE faça
{ 
  K = K + 1; 
  SOMA = SOMA + K; 
} 
imprimir(SOMA); 
```
Ao final do processamento, qual será o valor da variável SOMA? 

__Resposta:__ 91

Implementação melhor otimizada na linguagem Rust:

<details>

```rust
fn main() {
    let index = 13;
    let mut sum = 0;

    for k in 1..=index {
        sum += k;
    }

    println!("{}", sum);
}
```
  
</details>

___________

2) Dado a sequência de Fibonacci, onde se inicia por 0 e 1 e o próximo valor sempre será a soma dos 2 valores anteriores (exemplo: 0, 1, 1, 2, 3, 5, 8, 13, 21, 34...), escreva um programa na linguagem que desejar onde, informado um número, ele calcule a sequência de Fibonacci e retorne uma mensagem avisando se o número informado pertence ou não a sequência.

> IMPORTANTE:  Esse número pode ser informado através de qualquer entrada de sua preferência ou pode ser previamente definido no código;

Implementação na linguagem Rust:

<details>

```rust
fn is_fibonacci(num: u64) -> bool {
    let mut prev = 0;
    let mut curr = 1;

    while curr < num {
        let aux = prev + curr;
        prev = curr;
        curr = aux;
    }

    curr == num
}

fn main() {
    let choose_number = 15;
    
    if is_fibonacci(choose_number) {
        println!("O número {} pertence à sequência de Fibonacci.", choose_number);
    } else {
        println!("O número {} não pertence à sequência de Fibonacci.", choose_number);
    }
}

// Output: O número 15 não pertence à sequência de Fibonacci.
```
  
</details>

Implementação na linguagem Javascript:

<details>
  
```javascript
function is_fibonacci(num){
    let prev = 0;
    let curr = 1;
    
    while(curr < num){
        let aux = prev + curr;
        prev = curr;
        curr = aux;
    }
    
    return curr === num;
}

let choose_number = 8;

if(is_fibonacci(choose_number)){
    console.log(`O número ${choose_number} pertence à sequência de Fibonacci.`);
} else {
    console.log(`O número ${choose_number} não pertence à sequência de Fibonacci.`);
}

//Output: O número 8 pertence à sequência de Fibonacci.
```

</details>

___________

3) Descubra a lógica e complete o próximo elemento:  

a) 1, 3, 5, 7, ___

b) 2, 4, 8, 16, 32, 64, ____

c) 0, 1, 4, 9, 16, 25, 36, ____

d) 4, 16, 36, 64, ____

e) 1, 1, 2, 3, 5, 8, ____

f) 2, 10, 12, 16, 17, 18, 19, ____

__Respostas:__

a) 9

b) 128

c) 49

d) 100

e) 13

f) 200

___________

4) Você está em uma sala com três interruptores, cada um conectado a uma lâmpada em uma sala diferente. Você não pode ver as lâmpadas da sala em que está, mas pode ligar e desligar os interruptores quantas vezes quiser. Seu objetivo é descobrir qual interruptor controla qual lâmpada. Como você faria para descobrir, usando apenas duas idas até uma das salas das lâmpadas, qual interruptor controla cada lâmpada?

__Resposta:__  Ligo o interruptor A e espero por volta de 5 minutos. Apago o interruptor A e ligo o interruptor B. Após isso, vou até duas salas diferentes e faço as seguintes constatações: 
- Caso a lâmpada esteja apagada e quente, a associo ao interruptor A.
- Caso a lâmpada esteja acesa, a associo ao interruptor B.
- Caso a lâmpada esteja apagada e fria a associo ao interruptor C.

___________

5) Escreva um programa que inverta os caracteres de um string. 

> IMPORTANTE:
> a) Essa string pode ser informada através de qualquer entrada de sua preferência ou pode ser previamente definida no código;
> b) Evite usar funções prontas, como, por exemplo, reverse;

Implementação na linguagem Rust:

<details>

```rust

fn reverse_array(arr: &Vec<char>) -> String {
    let mut reversed = String::new();
    for i in (0..arr.len()).rev() {
        reversed.push(arr[i]);
    }
    reversed
}

fn invert_string(text: &str) -> String {
    let text_array: Vec<char> = text.chars().collect();
    let reversed_text = reverse_array(&text_array);
    reversed_text
}

fn main() {
    let inverted_text = invert_string("Marcell");
    println!("{}", inverted_text); // llecraM
}

```
  
</details>

Implementação na linguagem Javascript:

<details>

```javascript

function reverse_array(arr){
    let reversed_str = "";
    for(let i = arr.length - 1; i >= 0; i--) {
        reversed_str += arr[i];
    }
    return reversed_str;
}

function invert_string(str){
    let str_arr = str.split("");
    let reversed_string = reverse_array(str_arr);
    return reversed_string;
}

let inverted_str = invert_string("Marcell");
console.log(inverted_str); // llecraM

```
  
</details>
