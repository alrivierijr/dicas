Simulador Novo Cnpj
```
https://servicos.receitafederal.gov.br/servico/cnpj-alfa/simular
```

JS para Validar Novo Cnpj
```
function cnpjValido(cnpj) {
    if (!cnpj) return false;

    // Remove espaços e pontuação, mantendo letras e números
    cnpj = cnpj.toString().toUpperCase().replace(/[^A-Z0-9]/g, '');

    // O tamanho precisa continuar sendo 14 caracteres
    if (cnpj.length !== 14) return false;

    // Elimina CNPJs inválidos conhecidos (todos os caracteres iguais)
    if (/^([A-Z0-9])\1{13}$/.test(cnpj)) return false;

    // Função auxiliar para converter o caractere em seu valor numérico correspondente
    // Conforme regra da Receita: Subtrai 48 do valor ASCII (Números mantêm o valor, A=17, B=18...)
    const obterValorCaractere = (char) => char.charCodeAt(0) - 48;

    // Validação do Primeiro Dígito Verificador
    let tamanho = 12;
    let numeros = cnpj.substring(0, tamanho);
    let digitos = cnpj.substring(tamanho);
    let soma = 0;
    let pos = 5; // O peso começa em 5 para o primeiro dígito

    for (let i = 0; i < tamanho; i++) {
        soma += obterValorCaractere(numeros.charAt(i)) * pos;
        pos--;
        if (pos < 2) pos = 9;
    }

    let resultado = soma % 11 < 2 ? 0 : 11 - (soma % 11);
    if (resultado !== parseInt(digitos.charAt(0), 10)) return false;

    // Validação do Segundo Dígito Verificador
    tamanho = 13;
    numeros = cnpj.substring(0, tamanho);
    soma = 0;
    pos = 6; // O peso começa em 6 para o segundo dígito

    for (let i = 0; i < tamanho; i++) {
        soma += obterValorCaractere(numeros.charAt(i)) * pos;
        pos--;
        if (pos < 2) pos = 9;
    }

    resultado = soma % 11 < 2 ? 0 : 11 - (soma % 11);
    if (resultado !== parseInt(digitos.charAt(1), 10)) return false;

    return true;
}

```

Máscara Novo Cnpj
```
    $('html').on('focus', '.mask-cnpj', function () {
        if ($(this).data("mask") === undefined)
            $(this).mask('AA.AAA.AAA/AAAA-00');
    });

```
