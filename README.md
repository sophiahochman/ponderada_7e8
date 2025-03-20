# Instruções

- Faça uma cópia deste arquivo .md para um repositório próprio
- Resolva as 6 questões objetivas assinalando a alternativa correta
- Resolva as 4 questões dissertativas escrevendo no próprio arquivo .md
  - lembre-se de utilizar as estruturas de código como ``esta aqui com ` `` ou
```javascript
//esta aqui com ```
let a = "olá"
let b = 10
print(a)
```
- Resolva as questões com uso do Visual Studio Code ou ambiente similar.
- Teste seus códigos antes de trazer a resposta para cá.
- Cuidado com ChatGPT e afins: entregar algo só para ganhar nota não faz você aprender e ficar mais inteligente. Não seja dependente da máquina! (E não se envolva em plágio!)
- ao final, publique seu arquivo lista_02.md com as respostas em seu repositório, e envie o link pela Adalove. 

# Questões objetivas

**1)** Considere o seguinte código JavaScript:

```javascript
//EX01
let p = 10;
let q = 3;
let r = 6;

let resultado = (p % q === 1) && (r * 2 > p) || (q + r < p);
console.log(resultado);

const valores = [3, 6, 9, 12, 15];
let produto = 1;

for (let j = 0; j < valores.length; j++) {
  produto *= valores[j];
}

console.log("O produto dos valores é:", produto);


```
Qual das seguintes alternativas melhor descreve o que o código faz?

A) O código avalia a expressão booleana, imprime `true`, calcula o produto dos números na lista e imprime o resultado no console.

B) O código avalia a expressão booleana, imprime `false`, calcula o produto dos números na lista e imprime o resultado no console.

C) O código avalia a expressão booleana, imprime `true` e, em seguida, verifica se o número 6 está na lista.

D) O código avalia a expressão booleana, imprime `false` e ordena os valores em ordem crescente.


**Reposta: Alternativa: A**

Justificativa:

O código avalia a expressão booleana, que, quando simplificada, resulta em true || true, ou seja, true. Em seguida, ele imprime true. Como não há necessidade de busca ou ordenação de elementos, a expressão foi resolvida calculando e exibindo o produto dos valores do array.
______

**2)** O código a seguir contém duas funções que calculam o limite de crédito de um cliente com base nos seus gastos e na renda mensal.

```javascript
// Versão 1 da função de análise de crédito
function analisarCredito1() {
    var compras = [2500, 1200, 800, 100];
    var totalCompras = compras[0];
    var limite = 5000;
    var status = 'aprovado';
    var saldoDisponivel = 0;
    var i = 1;

    do {
        totalCompras += compras[i];
        i++;
    } while (limite >= totalCompras && i < compras.length);

    saldoDisponivel = limite - totalCompras;

    if (saldoDisponivel < 0) {
        status = 'negado';
    }
    console.log(`Seu crédito foi ${status}. Saldo disponível: ${saldoDisponivel}.`);
}
```

```javascript
// Versão 2 da função de análise de crédito
function analisarCredito2() {
    var compras = [2500, 1200, 800, 100];
    var totalCompras = compras[0];
    var limite = 5000;
    var status = 'aprovado';
    var saldoDisponivel = 0;
    var i = 1;

    while (limite >= totalCompras && i < compras.length) {
        totalCompras += compras[i];
        i++;
    }

    saldoDisponivel = limite - totalCompras;

    if (saldoDisponivel < 0) {
        status = 'negado';
    }
    console.log(`Seu crédito foi ${status}. Saldo disponível: ${saldoDisponivel}.`);
}
```
Se ambas as funções forem executadas com os valores fornecidos, qual será a saída exibida no console?

A) Ambas as funções exibirão: 'Seu crédito foi aprovado. Saldo disponível: 400.'

B) analisarCredito1() exibirá: 'Seu crédito foi negado. Saldo disponível: -600.', enquanto analisarCredito2() exibirá: 'Seu crédito foi negado. Saldo disponível: -200.'

C) analisarCredito1() exibirá: 'Seu crédito foi negado. Saldo disponível: -200.', enquanto analisarCredito2() exibirá: 'Seu crédito foi aprovado. Saldo disponível: 100.'

D) Ambas as funções exibirão: 'Seu crédito foi aprovado Saldo disponível: 500.'


**Reposta: Alternativa: A**

Justificativa:

As duas funções avaliam um conjunto fixo de compras e determinam se o total excede o limite de crédito. A distinção entre do...while e while não influencia o resultado neste caso, pois o loop sempre começa com um valor que garante sua execução. Como o total das compras permanece dentro do limite permitido, o crédito é aprovado, mantendo um saldo disponível positivo.
______


**3)** Considere o seguinte trecho de código em JavaScript:
```javascript
//EX03
const idade = 21;

if (idade >= 18 && idade < 60) {
  console.log("Você é um adulto!");
} else if (idade < 18) {
  console.log("Você é menor de idade!");
} else {
  console.log("Você está na melhor idade!");
}
```
Qual das seguintes alternativas melhor descreve o comportamento do código?

A) O código verifica se a idade indica um adulto ou um idoso e exibe a mensagem correspondente.

B) O código verifica se a idade pertence à faixa adulta. Se for, exibe "Você é um adulto!". Caso contrário, verifica se é menor de idade e exibe "Você é menor de idade!". Se nenhuma das condições anteriores for verdadeira, exibe "Você está na melhor idade!".

C) O código verifica se a idade está entre 18 e 60 anos e, se for, imprime "Você é um adulto!". Se não estiver nesse intervalo, imprime "Você está na melhor idade!".

D) O código verifica se a idade é menor de 18, entre 18 e 60 ou acima de 60, imprimindo uma mensagem específica para cada caso.

**Reposta: Alternativa B**

Justificativa:

O código verifica a idade da pessoa e exibe uma mensagem específica:

idade = entre 18 e 59, a saída será "Você é um adulto!".
idade = menor que 18, imprime "Você é menor de idade!".
idade = 60 ou mais, imprime "Você está na melhor idade!".
______

**4)** Qual será o resultado impresso no console após a execução do seguinte código?
```javascript
//EX04
var energiaDisponivel = 1200;
var bateriaExtra = 400;
var consumoDispositivos = [300, 600, 500, 200, 400];

for (var i = 0; i < consumoDispositivos.length; i++) {
    var consumo = consumoDispositivos[i];

    if (consumo <= energiaDisponivel) {
        console.log("Dispositivo " + (i+1) + " ligado. Energia restante: " + (energiaDisponivel - consumo));
        energiaDisponivel -= consumo;
    } else if (consumo <= energiaDisponivel + bateriaExtra) {
        console.log("Dispositivo " + (i+1) + " ligado com bateria extra. Energia restante: " + ((energiaDisponivel + bateriaExtra) - consumo));
        energiaDisponivel = 0;
        bateriaExtra -= (consumo - energiaDisponivel);
    } else {
        console.log("Dispositivo " + (i+1) + " não pode ser ligado. Energia insuficiente.");
    }
}
```

Escolha a opção que responde corretamente:

A)
Dispositivo 1 ligado. Energia restante: 900

Dispositivo 2 ligado com bateria extra. Energia restante: 700

Dispositivo 3 ligado. Energia restante: 200

Dispositivo 4 ligado com bateria extra. Energia restante: 0

Dispositivo 5 ligado. Energia restante: -200

B)
Dispositivo 1 ligado. Energia restante: 900

Dispositivo 2 ligado com bateria extra. Energia restante: 700

Dispositivo 3 ligado. Energia restante: 200

Dispositivo 4 não pode ser ligado. Energia insuficiente.

Dispositivo 5 não pode ser ligado. Energia insuficiente.

C)
Dispositivo 1 ligado. Energia restante: 900

Dispositivo 2 ligado com bateria extra. Energia restante: 700

Dispositivo 3 ligado. Energia restante: 400

Dispositivo 4 não pode ser ligado. Energia insuficiente.

D)
Dispositivo 1 ligado. Energia restante: 900

Dispositivo 2 ligado. Energia restante: 300

Dispositivo 3 ligado com bateria extra. Energia restante: 200

Dispositivo 4 não pode ser ligado. Energia insuficiente.

Dispositivo 5 não pode ser ligado. Energia insuficiente.

**Reposta: Altenativa B**

Justificativa:

O Dispositivo 1: 300 pode ser ligado, pois a energia disponível (1200) é suficiente, restando 900 de energia.
O Dispositivo 2: 600 exige mais energia do que a disponível (900 - 600 = 300 restantes), então ele utiliza a bateria extra, deixando a energia total em 700.
O Dispositivo 3: 500 pode ser ativado normalmente, já que há energia suficiente (700 - 500 = 200 restantes).
O Dispositivo 4: 200 precisaria exatamente dessa energia, mas como a bateria extra já foi parcialmente usada e zerada, ele não pode ser ligado.
O Dispositivo 5: 400 também não pode ser ativado, pois a energia restante não é suficiente.
______

**5)** Qual é a principal função do método update() em um jogo desenvolvido com Phaser.js?

Escolha a opção que melhor descreve seu propósito:

A) O método update() é responsável por carregar os assets do jogo antes da cena ser exibida.

B) O método update() é chamado continuamente a cada quadro (frame) do jogo, sendo usado para atualizar a lógica, movimentação e interações dos objetos na cena.

C) O método update() renderiza todos os sprites na tela e garante que a física do jogo seja processada corretamente.

D) O método update() é chamado apenas uma vez após a criação da cena, sendo utilizado para configurar variáveis iniciais do jogo.

**Reposta: Alternativa B**

Justificativa:

No Phaser.js, o método update() faz parte do ciclo de vida do jogo e é chamado automaticamente a cada quadro (frame). Ele é usado, por exemplo, para atualizar a lógica do jogo, como o movimento dos personagens ou a alteração de estados.
______

**6)** Qual é o principal objetivo do módulo Matter.js Physics em Phaser.js?

Escolha a opção que responde corretamente:

A) Simular física avançada, incluindo corpos rígidos, colisões complexas e interação entre objetos com gravidade e forças.

B) Gerenciar eventos de entrada do usuário, como cliques e toques na tela, permitindo movimentação de personagens.

C) Renderizar gráficos otimizados para jogos 2D e garantir uma taxa de quadros estável.

D) Criar animações automáticas para sprites e objetos interativos sem necessidade de programação de movimentação.

**Reposta: Alternativa A**

Justificativa:

No Phaser.js, o módulo Matter.js Physics é um motor de física avançado que possibilita a simulação realista de corpos rígidos. Ele é usado, por exemplo, para lidar com colisões complexas entre objetos.


______

# Questões dissertativas

**7)** Uma loja online deseja implementar um sistema de classificação de pedidos com base no valor total da compra. O sistema deve determinar a categoria de um pedido com as seguintes regras:

```

Pedidos abaixo de R$50,00 → "Frete não disponível!"

Pedidos entre R$50,00 e R$199,99 (inclusive) → "Frete com custo adicional!"

Pedidos de R$200,00 ou mais → "Frete grátis!"
```
Implemente um pseudocódigo que receba o valor total da compra e exiba a classificação correta do frete para o cliente.

**resolução**
```INICIO
    ESCREVER "Digite o valor total da compra:"
    LER valorTotal

    SE valorTotal < 50 ENTAO
        ESCREVER "Frete não disponível!"
    SENAO SE valorTotal >= 50 E valorTotal <= 199.99 ENTAO
        ESCREVER "Frete com custo adicional!"
    SENAO
        ESCREVER "Frete grátis!"
    FIM SE
FIM
```
______

**8)** Considere a implementação da classe base Veiculo em um sistema de modelagem de veículos. Sua tarefa é implementar, utilizando pseudocódigo, as classes derivadas Carro e Moto, que herdam da classe Veiculo, adicionando atributos específicos e métodos para calcular o consumo de combustível de um carro e de uma moto, respectivamente.

```
Classe Veiculo:
Atributos:

modelo
ano
Método Construtor(modelo, ano):

Define os valores dos atributos modelo e ano com os valores passados como parâmetro.
Método CalcularConsumo():
```
Implementação genérica para cálculo de consumo, a ser sobrescrita pelas subclasses.
Agora, implemente as classes Carro e Moto, garantindo que ambas herdem de Veiculo e possuam métodos específicos para calcular o consumo de combustível com base na quilometragem e eficiência do veículo.

**resolução**

```
CLASSE Veiculo
    ATRIBUTOS:
        modelo
        ano

    MÉTODO Construtor(modelo, ano)
        ESTE.modelo ← modelo
        ESTE.ano ← ano

    MÉTODO calcularConsumo()
        ESCREVER "Método genérico de cálculo de consumo. Deve ser sobrescrito."

FIM CLASSE

CLASSE Carro HERDA Veiculo
    ATRIBUTOS:
        eficiencia  // Km por litro

    MÉTODO Construtor(modelo, ano, eficiencia)
        CHAMAR Construtor de Veiculo(modelo, ano)
        ESTE.eficiencia ← eficiencia

    MÉTODO calcularConsumo(quilometragem)
        SE eficiencia > 0 ENTAO
            RETORNAR quilometragem / eficiencia
        SENAO
            ESCREVER "Eficiência inválida!"
        FIM SE
FIM CLASSE

CLASSE Moto HERDA Veiculo
    ATRIBUTOS:
        eficiencia  // Km por litro

    MÉTODO Construtor(modelo, ano, eficiencia)
        CHAMAR Construtor de Veiculo(modelo, ano)
        ESTE.eficiencia ← eficiencia

    MÉTODO calcularConsumo(quilometragem)
        SE eficiencia > 0 ENTAO
            RETORNAR quilometragem / eficiencia
        SENAO
            ESCREVER "Eficiência inválida!"
        FIM SE
FIM CLASSE

// Exemplo de uso:
INICIO
    carro1 ← NOVO Carro("Sedan", 2020, 12)
    moto1 ← NOVO Moto("Esportiva", 2022, 25)

    ESCREVER "Consumo do carro para 240 km: ", carro1.calcularConsumo(240), " litros"
    ESCREVER "Consumo da moto para 240 km: ", moto1.calcularConsumo(240), " litros"
FIM
```
______

**9)** Você é um cientista da NASA e está ajudando no desenvolvimento de um sistema de pouso para sondas espaciais em Marte. Seu objetivo é calcular o tempo necessário para que a sonda reduza sua velocidade até um nível seguro para pouso, considerando uma velocidade inicial de entrada na atmosfera marciana e uma taxa de desaceleração constante causada pelo atrito atmosférico e retrofoguetes.

Entretanto, a sonda não pode ultrapassar um tempo máximo de descida para evitar desvios orbitais, nem pode desacelerar além de um limite mínimo, pois isso poderia causar instabilidade no pouso.

Implemente a lógica dessa simulação em pseudocódigo, considerando a seguinte equação para atualização da velocidade:

Considere a fórumla de atualização velocidade:
```
    velocidade = velocidadeInicial - desaceleracao * tempo
```
Seu programa deve determinar quanto tempo será necessário para que a sonda atinja uma velocidade segura de pouso, sem ultrapassar os limites estabelecidos.


**resolução**
```
INICIO
    // Definir os parâmetros da simulação
    ESCREVER "Digite a velocidade inicial da sonda (m/s):"
    LER velocidadeInicial
    
    ESCREVER "Digite a taxa de desaceleração (m/s²):"
    LER desaceleracao
    
    ESCREVER "Digite a velocidade segura de pouso (m/s):"
    LER velocidadeSegura
    
    ESCREVER "Digite o tempo máximo permitido para descida (s):"
    LER tempoMaximo

    // Inicializar variáveis
    tempo ← 0
    velocidade ← velocidadeInicial

    // Simulação da descida
    ENQUANTO velocidade > velocidadeSegura E tempo < tempoMaximo FAÇA
        velocidade ← velocidadeInicial - desaceleracao * tempo
        SE velocidade <= velocidadeSegura ENTAO
            ESCREVER "A sonda atingiu uma velocidade segura após ", tempo, " segundos."
            PARAR
        FIM SE
        tempo ← tempo + 1
    FIM ENQUANTO

    // Verificar se a sonda não conseguiu atingir a velocidade segura no tempo limite
    SE velocidade > velocidadeSegura ENTAO
        ESCREVER "A sonda não conseguiu reduzir a velocidade dentro do tempo máximo permitido!"
    FIM SE
FIM
```
______

**10)** Em um sistema de análise financeira, as operações de investimento de uma empresa podem ser representadas por matrizes, onde cada linha representa um tipo de investimento e cada coluna representa um período de tempo.

A seguir, é fornecida a implementação da função SomarMatrizesInvestimento(matrizA, matrizB), que soma os valores de duas matrizes de investimento. Sua tarefa é implementar uma função semelhante, porém que realize a multiplicação das matrizes de investimento, determinando como os investimentos afetam os resultados ao longo do tempo.

```
Função SomarMatrizesInvestimento(matrizA, matrizB):  
    # Verifica se as matrizes têm o mesmo número de linhas e colunas  
    Se tamanho(matrizA) ≠ tamanho(matrizB) então:  
        Retornar "As matrizes não podem ser somadas. Elas têm dimensões diferentes."  
    Senão:  
        linhas <- tamanho(matrizA)  
        colunas <- tamanho(matrizA[0])  
        matrizResultado <- novaMatriz(linhas, colunas)  

        # Loop para percorrer cada elemento das matrizes e calcular a soma  
        Para i de 0 até linhas-1 faça:  
            Para j de 0 até colunas-1 faça:  
                matrizResultado[i][j] <- matrizA[i][j] + matrizB[i][j]  

        Retornar matrizResultado  

# Exemplo de uso da função  
investimentosAno1 <- [[1000, 2000], [1500, 2500]]  
investimentosAno2 <- [[1200, 1800], [1300, 2700]]  

totalInvestimentos <- SomarMatrizesInvestimento(investimentosAno1, investimentosAno2)  
Escrever("Total de investimentos acumulados:")  
ImprimirMatriz(totalInvestimentos)  
```
Agora, implemente a função MultiplicarMatrizesInvestimento(matrizA, matrizB), que multiplica as duas matrizes, simulando o efeito de diferentes fatores de crescimento e impacto financeiro nos investimentos ao longo do tempo.


**resolução**
```
Função MultiplicarMatrizesInvestimento(matrizA, matrizB):  
    # Verifica se a multiplicação é possível (número de colunas da matriz A == número de linhas da matriz B)  
    Se tamanho(matrizA[0]) ≠ tamanho(matrizB) então:  
        Retornar "As matrizes não podem ser multiplicadas. O número de colunas de A deve ser igual ao número de linhas de B."  
    Senão:  
        linhasA <- tamanho(matrizA)  
        colunasA <- tamanho(matrizA[0])  
        colunasB <- tamanho(matrizB[0])  
        matrizResultado <- novaMatriz(linhasA, colunasB, 0)  

        # Loop para percorrer cada elemento das matrizes e calcular a multiplicação  
        Para i de 0 até linhasA - 1 faça:  
            Para j de 0 até colunasB - 1 faça:  
                Para k de 0 até colunasA - 1 faça:  
                    matrizResultado[i][j] <- matrizResultado[i][j] + (matrizA[i][k] * matrizB[k][j])  

        Retornar matrizResultado  

# Exemplo de uso da função  
investimentosAno1 <- [[1000, 2000], [1500, 2500]]  
fatoresCrescimento <- [[1.1, 0.9], [1.05, 1.2]]  

resultadoInvestimentos <- MultiplicarMatrizesInvestimento(investimentosAno1, fatoresCrescimento)  
Escrever("Impacto dos fatores de crescimento nos investimentos:")  
ImprimirMatriz(resultadoInvestimentos)
```
