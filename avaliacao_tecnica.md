Avaliação Técnica – Desenvolvedor


As tarefas para avaliação técnica foram desenvolvidas para que possamos avaliar sua lógica, interpretação de especificações, capacidade e criatividade em resolver problemas.

Na Paradigma, trabalhamos com SQL Server, C#, asp.net, javascript, mas você não precisa usar nenhuma linguagem específica para resolver suas tarefas. Utilize a forma que você entende que irá demonstrar o seu melhor.

Se você possui perfil no github informe ele como parte das suas respostas, assim nós poderemos conhecer um pouco mais sobre você e sua maneira de codar .

# Avaliação Técnica – Desenvolvedor

## Tarefa 1 (SQL)

```sql
SELECT 
    d.Nome AS Departamento,
    p.Nome AS Pessoa,
    p.Salario
FROM Pessoa p
JOIN Departamento d 
    ON p.DeptId = d.Id
WHERE p.Salario = (
    SELECT MAX(p2.Salario)
    FROM Pessoa p2
    WHERE p2.DeptId = p.DeptId
)
```

## Tarefa 2 (JavaScript)

```javascript
function construirArvore(nums) {
    if (!nums.length) return null;

    const maxIndex = nums.indexOf(Math.max(...nums));

    return {
        valor: nums[maxIndex],
        esquerda: construirArvore(nums.slice(0, maxIndex)),
        direita: construirArvore(nums.slice(maxIndex + 1))
    };
}

function imprimirArvore(node, nivel = 0) {
    if (!node) return;
    console.log(' '.repeat(nivel * 2) + node.valor);
    imprimirArvore(node.esquerda, nivel + 1);
    imprimirArvore(node.direita, nivel + 1);
}

console.log("Cenário 1:");
imprimirArvore(construirArvore([3, 2, 1, 6, 0, 5]));

console.log("\nCenário 2:");
imprimirArvore(construirArvore([7, 5, 13, 9, 1, 6, 4]));

Saída esperada:
Cenário 1:
6
  3
    2
      1
  5
    0

Cenário 2:
13
  7
    5
  9
    6
      4
        1
```

