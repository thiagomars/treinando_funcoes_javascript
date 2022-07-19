
//Questão 01
quest1 = a => (a % 3 == 0) ? console.log(true) : console.log(false);

//Questão 02
quest2 = (plano, salario) => {
    if(plano == "A"){
        console.log(salario * 0.1 + salario);
    } else if (plano =="B"){
        console.log(salario * 0.15 + salario);
    } else if(plano == "C"){
        console.log(salario * 0.2 + salario);
    } else{
        console.log("nada inserido");
    }
}

//Questão 03
function quest3(valor){
    let cem = 0, cinquenta = 0, dez = 0, cinco = 0, hum = 0;
    let result = "";

    if(valor >= 100){
        while(valor >= 100){
            cem++;
            valor = valor - 100;
        }
        result = cem + " nota(s) de R$ 100. ";
    }
    
    if(valor >= 50){
        while(valor >= 50){
            cinquenta++;
            valor = valor - 50;
        } 
        result = result + cinquenta + " nota(s) de R$ 50. ";
    }

    if(valor >= 10){
        while(valor >= 10){
            dez++;
            valor = valor - 10;
        } 
        result = result + dez + " nota(s) de R$ 10. ";
    }

    if(valor >= 5){
        while(valor >= 5){
            cinco++;
            valor = valor - 5;
        } 
        result = result + cinco + " notas(s) de R$ 5. ";
    }

    if(valor >= 1){
        while(valor >= 1){
            hum++;
            valor = valor - 1;
        }
        result = result + hum + " notas(s) de R$ 1. ";
    }
    
    console.log(result);
}

//Questão 04
function quest4(codigo, nota1, nota2, nota3){
    if(nota1 > nota2 && nota1 > nota3){
        console.log("Código do aluno: " + codigo);
        console.log("Notas: " + nota1 + " - " + nota2 + " - " + nota3);
        
        let media = ((nota1 * 4) + (nota2 * 3) + (nota3 * 3)) / 10;
        console.log("Média: " + media);
        
        if(media >= 5){
            console.log("Aluno Aprovado");
        } else{
            console.log("Aluno Reprovado");
        }
    } else if(nota2 > nota1 && nota2 > nota3){
        console.log("Código do aluno: " + codigo);
        console.log("Notas: " + nota1 + " - " + nota2 + " - " + nota3);
        
        let media = ((nota2 * 4) + (nota1 * 3) + (nota3 * 3)) / 10;
        console.log("Média: " + media);
        
        if(media >= 5){
            console.log("Aluno Aprovado");
        } else{
            console.log("Aluno Reprovado");
        }
    } else if(nota3 > nota1 && nota3 > nota2){
        console.log("Código do aluno: " + codigo);
        console.log("Notas: " + nota1 + " - " + nota2 + " - " + nota3);
        
        let media = ((nota3 * 4) + (nota2 * 3) + (nota1 * 3)) / 10;
        console.log("Média: " + media);
        
        if(media >= 5){
            console.log("Aluno Aprovado");
        } else{
            console.log("Aluno Reprovado");
        }
    } else if(nota1 == nota2 && nota2 == nota3){
        console.log("Código do aluno: " + codigo);
        console.log("Notas: " + nota1 + " - " + nota2 + " - " + nota3);
        
        let media = ((nota3 * 4) + (nota2 * 3) + (nota1 * 3)) / 10;
        console.log("Média: " + media);
        
        if(media >= 5){
            console.log("Aluno Aprovado");
        } else{
            console.log("Aluno Reprovado");
        }
    }
}

//Questão 05
function quest5(inicio, fim){
    if(inicio > fim){
        let auxiliar = inicio;
        inicio = fim;
        fim = auxiliar;
    }

    let aux = Object.keys(new Array(fim - inicio + 1).fill());
    for(let i in aux){
        aux[i] = parseInt(aux[i]) + parseInt(inicio);
        if(aux[i] % 2 == 1){
            console.log(">> " + aux[i]);
        }
    }
}

//Questão 06
function quest6(notas){
    let conceito = [];
    for(var i in notas){
        if(notas[i] >= 0.0 && notas[i] <= 4.9){
            conceito[i] = "D";
        }
        if(notas[i] >= 5.0 && notas[i] <= 6.9){
            conceito[i] = "C";
        }
        if(notas[i] >= 7.0 && notas[i] <= 8.9){
            conceito[i] = "B";
        }
        if(notas[i] >= 9.0 && notas[i] <= 10.0){
            conceito[i] = "A";
        }
    }
    
    for(var e in notas){
        console.log("Nota: " + notas[e] + " - Conceito: " + conceito[e]);
    }
}

//Questão 07
function quest7(){
    let vetorPilha = [1, 2, 3, 4, 5];
    let vetorAdiciona = [6, 7, 8, 9, 10];

    for(let i in vetorPilha){
        vetorPilha.push(vetorAdiciona[i]);
    }

    console.log(vetorAdiciona);
    console.log(vetorPilha);
}

//Questão 08
function quest8A(vetor, valor){
    let vetorResult = [];
    for(var i in vetor){
        vetorResult[i] = vetor[i] * valor;
    }
    console.log(vetorResult);
}

function quest8B(vetor, valor){
    let vetorResult = [];
    if(valor > 5){
        for(var i in vetor){
            vetorResult[i] = vetor[i] * valor;
        }
    } else{
        vetorResult = vetor;
    }
        console.log(vetorResult);
}

//Questão 09
class carro {
    constructor(velocidadeAtual, velocidadeMaxima){
        this.velocidadeAtual = velocidadeAtual;
        this.velocidadeMaxima = velocidadeMaxima;
    }

    acelerar(qtd){
        if(this.velocidadeAtual < this.velocidadeMaxima){
            this.velocidadeAtual = this.velocidadeAtual + qtd;
            if(this.velocidadeAtual > this.velocidadeMaxima){
                this.velocidadeAtual = this.velocidadeMaxima;
            }
        }
    }

    statusVelocidade(){
        console.log(this.velocidadeAtual);
    }
}

class ferrari extends carro {
    constructor(velocidadeAtual, velocidadeMaxima, cor, modelo){
        super(velocidadeAtual) = velocidadeAtual;
        super(velocidadeMaxima) = velocidadeMaxima;

        this.cor = cor;
        this.modelo = modelo;
    }
}

class volvo extends carro {
    constructor(velocidadeAtual, velocidadeMaxima, cilindradas){
        super(velocidadeAtual) = velocidadeAtual;
        super(velocidadeMaxima) = velocidadeMaxima;

        this.cilindradas = cilindradas;
    }
}


//Questão 10
class quest11 {
    constructor(valor){
        this.valor = valor;
    }

    divisivel(){
        if(this.valor % 3 == 0){
            return true;
        } else{
            return false;
        }
    }
}

//Questão 11
class produto {
    constructor(codigo, nome, preco, qtd){
        this.codigo = codigo;
        this.nome = nome;
        this.preco = preco;
        this.qtd = qtd;
    }

    comprar(quantidade){
        if(quantidade <= this.qtd){
            this.qtd = this.qtd - quantidade;
            console.log("Compra efetuada. Atualização do produto abaixo: ");
            console.log(this.codigo);
            console.log(this.nome);
            console.log(this.preco);
            console.log(this.qtd);
        } else{
            console.log("Quantidade indisponivel.");
        }
    }
}

const produto1 = new produto(11, "Produto Um", 11.45, 10);
const produto2 = new produto(12, "Produto Dois", 1.10, 20);
const produto3 = new produto(13, "Produto Tres", 8.88, 30);
const produto4 = new produto(14, "Produto Quatro", 3.75, 40);
const produto5 = new produto(15, "Produto Cinco", 111.99, 50);

let produtos = [produto1, produto2, produto3, produto4, produto5];

function buscar(codProduto, quantidades){
    for(let i in produtos){
        if(codProduto == produtos[i].codigo){
            produtos[i].comprar(quantidades);
        }
    }
}

//Executar a Questão 01 
//quest1(4);

//Executar a Questão 02
//quest2("A", 1000);

//Executar a Questão 03
//quest3(18);

//Executar a Questão 04
//quest4(412645,5,5,5);

//Executar a Questão 05
//quest5(10, 20)

//Executar a Questão 06
//quest6([10, 9 , 8 , 7 , 6 , 0, 5 , 4 , 1]);

//Executar a Questão 07
//quest7();

//Executar a Questão 08
//quest8A([1, 2, 3, 4], 10);
//quest8B([1, 2, 3, 4], 10);

//Executar a Questão 09
//questao 09

//Executar a Questão 10
//qust10
//const questDez = new quest11(10);
//console.log(questDez.divisivel());

//Executar a Questão 11
//questão 11
//buscar(12, 10);
