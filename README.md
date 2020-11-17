# teste-descomplica
Teste para entrevista 

O teste foi solucionado em Jascript. Para executar basta colar o código no console de qualquer navegador que tenha esse suporte, e executar a função como abaixo:



let aulas = [
    { discipline: "math", startHour: 11, startMinute: 0 },
    { discipline: "biology", startHour: 12, startMinute: 15 }
];
this.listAulasIniciadasEmMinutoImpar(aulas);

/**
 * Retorna uma lista de aulas que se iniciam em minuto ímpar
 */
function listAulasIniciadasEmMinutoImpar(aulas) {
    let aulasImpar = [];

    aulas.forEach(function (aula) {
        if (aula.startMinute) {
            //Converte número informado em Array, pega a primeira ocorrência do array e converte novamente em inteiro
            let minutoArray = aula.startMinute.toString(10).split("");
            let primeiroNumero = parseInt(minutoArray[0]);

            if (this.isNumeroImpar(primeiroNumero)) {
                aulasImpar.push(aula);
            }
        }
    });
    return aulasImpar;
}

/**
 * Valida se o número infomado é um número impar
 */
function isNumeroImpar(numero) {
    let isImpar = false;

    if (Number.isInteger(numero)) {
        var resto = numero % 2;
        isImpar = resto != 0;
    }
    return isImpar;
}
