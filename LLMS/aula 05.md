## Revisão de Prompt

### Análise com IAs

***PERGUNTA VAGA: analise esse código.***

Percebe-se que a IA não tinha o que responder. Em vez de uma resposta, surgiu uma pergunta para ela conseguir compreender.

***SOLUÇÃO: enviei um código antigo meu feito em C:***

***Pergunta com Prompt e CoT:***

Através desse código, reformulei a pergunta da seguinte forma:

> "Refatore este código em JavaScript para torná-lo mais legível e eficiente. Utilize boas práticas de programação, como nomes de variáveis claras e funções reutilizáveis. Explique as mudanças realizadas."
> 

Depois, fui mais específico:

> "Quero que você faça uma explicação de cada função, se possível em formato YAML, para um estudante do segundo semestre de Análise e Desenvolvimento de Sistemas, que está aprendendo engenharia de prompt."
> 

## 1. O Código em C (Aprimorado)

O foco aqui foi **robustez** e **controle de memória/buffer**.

- **Validação de Tipo (`scanf != 1`):** No código original, se o usuário digitasse "abc", o programa entraria em loop infinito. A melhoria verifica se o que foi digitado é realmente um número.
- **Limpeza de Buffer (`getchar`):** Em C, o `\n` (Enter) fica "preso" no teclado. Criar uma função para limpar esse rastro evita que o programa pule perguntas.
- **Escalabilidade com `#define`:** Definir `NOTA_MAX` no topo segue o princípio **DRY (Don't Repeat Yourself)**. Se a regra de negócio mudar, você altera em um só lugar.

---

## 2. O Código em JavaScript (Refatorado)

Aqui, o foco mudou para **legibilidade**, **manutenibilidade** e **paradigmas modernos**.

### A. Separação de Responsabilidades (Modularização)

No original, tudo acontecia dentro da `main`. No JS, dividimos em:

1. **Validação (`ehNotaValida`):** Uma função "pura" que apenas testa um dado.
2. **Orquestração (`cadastrarNotas`):** Cuida da interação com o usuário.
3. **Processamento (`exibirResumo`):** Cuida da lógica matemática e saída.

### B. Estruturas de Dados Inteligentes

- **De Contador para Array:** No C, você apenas contava (`contador++`). No JS, usamos `notasCadastradas.push(nota)`. Isso transforma um simples contador em um **histórico de dados**, permitindo cálculos complexos (média, maior/menor nota) sem pedir novos inputs.

### C. Programação Funcional (`.reduce`)

Substituímos o loop clássico `for` por um método de alta ordem:

`const soma = notas.reduce((acc, curr) => acc + curr, 0);`

Isso é mais eficiente e menos propenso a erros de "índice fora do limite" (o famoso *erro off-by-one*).

---

## Comparativo de Melhorias

| **Conceito** | **Como estava (C)** | **Como ficou (JS Refatorado)** | **Benefício para o Desenvolvedor** |
| --- | --- | --- | --- |
| **Entrada de Dados** | `scanf`(instável) | `prompt`/`confirm` | Interface mais intuitiva e segura. |
| **Persistência** | Volátil (só contagem) | Armazenado em`Array` | Possibilidade de reutilizar os dados. |
| **Tratamento de Erro** | `if/else`simples | Validação funcional (`isNaN`) | Evita que dados "sujos" poluam o sistema. |
| **Estilo de Código** | Procedimental | Modular / Funcional | Facilita testes unitários e manutenção. |

---

## Conexão com Engenharia de Prompt

Como você está estudando essa área, observe que a **refatoração** seguiu uma "Cadeia de Pensamento" (Chain of Thought):

1. Analisei as **restrições** (0 a 10).
2. Defini o **formato de saída** (Template Strings).
3. Apliquei **regras de contexto** (Configurações globais).

Ao pedir para uma IA melhorar seu código, você pode usar termos técnicos como *"Refatore seguindo os princípios de Responsabilidade Única (SOLID) e utilize métodos de Array do ES6"* para obter resultados muito superiores.

<aside>

***Análise do estudante:***

Ao decorrer de tal pesquisa, pude perceber como ter acesso e realizar os estudos com base em refatoração e CoT trouxe uma melhoria gigantesca. Começando pelo fato do código ficar mais resumido — pedir em YAML, por exemplo, ajuda a diminuir o número de tokens.

</aside>
