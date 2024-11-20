// calcula a média válida das notas dos atletas
function calcularMedia(atleta) {
    // coloca em ordem crescente
    let notasOrdenadas = atleta.notas.sort((a, b) => a - b);
    
    // retira a maior e menor nota
    let notasSelecionadas = notasOrdenadas.slice(1, 4);

    // Calcula a média das 3 notas restantes
    let somaNotas = notasSelecionadas.reduce((soma, nota) => soma + nota, 0);
    let media = somaNotas / notasSelecionadas.length;

    return media;
}

// mostra as informações dos atletas
function exibirAtletas(atletas) {
    atletas.forEach(atleta => {
        // Calcula a média válida para cada atleta
        let mediaValida = calcularMedia(atleta);

        // Exibe as informações formatadas
        console.log(`Atleta: ${atleta.nome}`);
        console.log(`Notas Obtidas: ${atleta.notas.join(", ")}`);
        console.log(`Média Válida: ${mediaValida.toFixed(6)}`);
        console.log("");
    });
}

// mostra os atletas com suas notas
let atletas = [
    {
        nome: "Maicon",
        notas: [10, 9.34, 8.42, 10, 7.88]
    },
    {
        nome: "Bernardo vingativo",
        notas: [8, 10, 10, 7, 9.33]
    },
    {
        nome: "Marquito",
        notas: [7, 10, 9.5, 9.5, 8]
    },
    {
        nome: "Corey Taylor",
        notas: [10, 10, 10, 9, 9.5]
    }
];

// Chama a função para exibir as informações dos atletas
exibirAtletas(atletas);
