 # Atividade Reflexiva produção individual:
- Elaborar um parecer sobre a Unidade II.O que foi praticado (sugestões de código, refatoração, automação).Relação com o conteúdo estudado (workflow, boas práticas, ética).Ferramentas utilizadas: Copilot, Replit, Ghostwriter

*Programação por pares: ( uma nova era ):*

- A nova era começa pelo fato de termos um agente disponível as 24 horas do dia e sete dias da semana..
- Mas com essa nova era, vem a questão de saber usar isso. Por tanto o caso de copiar e colar não serve mais, pois é algo padrão que todos fazem.
- Essa nova era permiti que o programador atinja altos níveis, que jamais poderia chegar, ela não vem com papel de te substituir, mas sim ampliar seus horizontes.
- Dentro disso vem a questão de responsabilidade e seu local, sendo navegador e a IA o piloto.
- Navegador vem com a função de não apenas copiar e colar, mas sim arquitetar, pensar em como melhorar, garantir ética e segurança e validar a solução do problema.
- O piloto vem para ser um a gente que vai estar disponível para nos ajudar, ou seja, alguém que tá lá sempre, serve para traduzir, criar e seguir seus pedidos.

Exemplo.:

Código inserido ( crie uma calculadora simples ) 

### Código da Calculadora Simples

Python

`# Título do 
print("="*20)
print(" CALCULADORA PYTHON ")
print("="*20)

# Entrada de dados
num1 = float(input("Digite o primeiro número: "))
print("Operações disponíveis: + , - , * , /")
operacao = input("Escolha a operação: ")
num2 = float(input("Digite o segundo número: "))

# Lógica de cálculo
if operacao == "+":
    resultado = num1 + num2
    simbolo = "+"
elif operacao == "-":
    resultado = num1 - num2
    simbolo = "-"
elif operacao == "*":
    resultado = num1 * num2
    simbolo = "*"
elif operacao == "/":
    # Verificação para não dividir por zero
    if num2 == 0:
        resultado = "Erro! Divisão por zero."
        simbolo = "/"
    else:
        resultado = num1 / num2
        simbolo = "/"
else:
    resultado = "Operação inválida"
    simbolo = "?"

# Exibição do resultado
print("-" * 20)
if isinstance(resultado, str):
    print(resultado)
else:
    print(f"Resultado: {num1} {simbolo} {num2} = {resultado}")
print("-" * 20)`

Código da refatoração ( Refatore esse código, melhore o código If para estabilidade para melhorar o código, tire os comentários e partes inuteis no código, transforme ele para simples e bom. ) 

Para refatorar e deixar o código mais "limpo" (o que chamamos de *Clean Code* ), vamos focar em remover redundâncias. Uma forma elegante de fazer isso em Python é usar um **Dicionário** para armazenar as operações, eliminando aquele monte de `if/elif`.

Aqui está a versão estável, simples e profissional:

Python

`import operator

# Mapeamento de operações para maior estabilidade
operacoes = {
    "+": operator.add,
    "-": operator.sub,
    "*": operator.mul,
    "/": operator.truediv
}

try:
    n1 = float(input("Primeiro número: "))
    op = input("Operação (+, -, *, /): ")
    n2 = float(input("Segundo número: "))

   if op in operacoes:
        if op == "/" and n2 == 0:
            print("Erro: Divisão por zero.")
        else:
            resultado = operacoes[op](n1, n2)
            print(f"Resultado: {resultado}")
    else:
        print("Operação inválida.")

except ValueError:
    print("Erro: Digite apenas números.")`
