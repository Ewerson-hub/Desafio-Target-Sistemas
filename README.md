# Desafio-Target-Sistemas

Fiz em Javascript, para rodar o codigo mais facil, sugiro esse site: https://www.mycompiler.io/pt/new/nodejs


## 1) Dado a sequência de Fibonacci, onde se inicia por 0 e 1 e o próximo valor sempre será a soma dos 2 valores anteriores (exemplo: 0, 1, 1, 2, 3, 5, 8, 13, 21, 34...), escreva um programa na linguagem que desejar onde, informado um número, ele calcule a sequência de Fibonacci e retorne uma mensagem avisando se o número informado pertence ou não a sequência.



```
function MeetInFibonnaci(num) {
    
    if(num < 0) return 'Não pertence a serie de fibonnaci'
    if(num == 0 || num == 1) return 'pertence a serie de fibonnaci'
    
    let FoundNumberInSequence = false
    let fibonnaci = [0,1]
    
    do{
        //adiciona o proximo numero a sequencia
        let nextNumber = sumFibonnaci(fibonnaci)

        if(num == nextNumber){
            FoundNumberInSequence = true
        } else if(num < nextNumber){
            break;
        }else{
            fibonnaci.push(nextNumber) //adicona mais um numero a sequencia
        }
        
    }while(FoundNumberInSequence == false)
    
  return (FoundNumberInSequence)? 'pertence a serie de fibonnaci' : 'Não pertence a serie de fibonnaci';
}

function sumFibonnaci(fibonnaci) {
    let final = fibonnaci.length;
    return fibonnaci[final - 1] + fibonnaci[final - 2]
}

console.log(MeetInFibonnaci(13))
```

## 2) Escreva um programa que verifique, em uma string, a existência da letra ‘a’, seja maiúscula ou minúscula, além de informar a quantidade de vezes em que ela ocorre.
```
function meetA(str) {
    let regex = /[aA]/g // regex p/ filtrar a ocorrencia de todo 'a' ou 'A' na str
    
    //checa se não existe 'a' na palavra
    if(!regex.test(str)) return 'A palavra não tem A'

    //retorna o tamanho de um array que contem todas as repetições de 'a' na palavra
    const occorrenceNumberOfA = str.match(regex).length
    
    return `A palavra repete a letra 'A' ${occorrenceNumberOfA} vezes` 
}

console.log(meetA('ceaaAa'))
```
