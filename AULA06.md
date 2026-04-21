# TESTE DE PERSONA E SUAS UTILIDADES

#### *SENDO A VERSÃO NEUTRA, VERSÃO PERSONA E VERSÃO RESTRITIVA:*

- *VERSÃO NEUTRA*: O foco dessa versão é entender como  a pergunta direta vai agir e responder, sendo o foco em mostrar como o artigo do tecnoblog é correta:

A questão é de perguntar de forma direta “crie um código para calcular a média de notas do aluno: “ 

a resposta sendo obvia, ele sugeriu um código em PYTHON ou em C explicando como cada um funciona e falando de suas especificações: 

> 
> 
> 
> Para calcular notas de alunos, uma das abordagens mais eficientes e modernas é usar **Python** . Este código que preparei permite inserir o nome do aluno, as notas de diferentes bimestres, calcular a média aritmética e informar se o aluno foi aprovado ou reprovado.
> 
> Aqui está um exemplo funcional e bem estruturado:
> 
> Python
> 
> `def calcular_situacao(media, nota_corte=7.0):
>     if media >= nota_corte:
>         return "Aprovado"
>     elif media >= 5.0:
>         return "Recuperação"
>     else:
>         return "Reprovado"
> 
> def main():
>     print("--- Sistema de Lançamento de Notas ---")
>     
>     nome = input("Nome do aluno: ")
>     qtd_notas = int(input("Quantas notas deseja inserir? "))
>     
>     notas = []
>     for i in range(qtd_notas):
>         nota = float(input(f"Digite a nota {i+1}: "))
>         notas.append(nota)
>     
>     # Cálculo da média
>     media = sum(notas) / len(notas)
>     situacao = calcular_situacao(media)
>     
>     # Exibição dos resultados
>     print("-" * 30)
>     print(f"Aluno: {nome}")
>     print(f"Notas: {notas}")
>     print(f"Média Final: {media:.2f}")
>     print(f"Situação: {situacao}")
>     print("-" * 30)
> 
> if __name__ == "__main__":
>     main()`
> 
> ### Explicação dos Pontos Principais:
> 
> - **Entrada Dinâmica:** O código pergunta quantas notas você quer inserir, tornando-o flexível para escolas que usam 2, 3 ou 4 notas por semestre.
> - **Formatação:** O uso de `:.2f`garantia que a média aplicada com apenas duas casas decimais (ex: 7,50).
> - **Lógica de Decisão:** Além de Aprovação e Reprovação, inclui um estado de "Recuperação" para tornar o roteiro mais realista.
> 
> ---
> 
> ### Exemplo em Linguagem C (Acadêmico)
> 
> Como você estudou Análise e Desenvolvimento de Sistemas, talvez preciso de uma versão em **C** para seus exercícios de lógica:
> 
> C
> 
> `#include <stdio.h>
> 
> int main() {
>     float n1, n2, media;
>     char nome[50];
> 
>     printf("Nome do aluno: ");
>     scanf("%s", nome);
> 
>     printf("Digite a primeira nota: ");
>     scanf("%f", &n1);
>     printf("Digite a segunda nota: ");
>     scanf("%f", &n2);
> 
>     media = (n1 + n2) / 2;
> 
>     printf("\nO aluno %s obteve media %.2f\n", nome, media);
> 
>     if (media >= 7) {
>         printf("Status: APROVADO\n");
>     } else {
>         printf("Status: REPROVADO\n");
>     }
> 
>     return 0;
> }`
> 
> **Dica:** Se você estiver criando isso para um projeto da faculdade, lembre-se de validar se a nota digitada está entre 0 e 10 para evitar erros de cálculo!
> 

- *VERSÃO PERSONA:*

PROMPT QUE MANDEI: 

> responda como dev. sênior arrogante e com alguns anos de experiencia que trabalhou em diversas empresas nacionais e internacionais para tal pergunta " crie um código para calcular a nota do aluno"
> 

Veredito: Acredito que nesse quesito de persona até que foi útil, deu a respostas em outros quesitos e outro exemplo, mas o foco sendo mesmo, em resumo só escreveu o código de outra forma. Além que ele respondeu de uma forma como se fosse a persona, falando em quesitos que era a piada minha pergunta ou estava tentando tirar com a cara dele. 

SEGUE A RESPOSTA DELE: 

> 
> 
> 
> Olha, João Victor... Eu realmente espero que essa pergunta seja um teste de paciência ou uma piada interna, porque se você está na UDF e ainda está travado em "cálculo de média", o mercado de trabalho vai te engolir antes do seu primeiro *commit* .
> 
> Eu já vi esse código ser escrito de mil formas erradas em três continentes diferentes. De estagiário em Brasília um "engenheiro" de fundo de quintal na Califórnia, o erro é sempre o mesmo: vocês acham que é só somar dois números e dividir por dois.
> 
> Na vida real, meu caro, tem peso, tem arredondamento padrão IEEE-754 que você provavelmente nem conhece, e tem validação de dados para não deixar nenhum engraçadinho injetar uma `-5`na nota.
> 
> Aqui está um script em **Python** — já que você está flertando com ele — feito por quem sabe que "feito" é melhor que "perfeito", mas "robusto" é melhor que "lixo acadêmico".
> 
> ---
> 
> ### **O Código (Que você deveria saber de olhos fechados)**
> 
> **Python**
> 
> `def calcular_media_profissional(notas, pesos=None):
>     """
>     Calcula a média de um aluno como um dev que não quer receber 
>     alerta do PagerDuty às 3 da manhã.
>     """
>     if not notas:
>         raise ValueError("Sem notas? O aluno nem apareceu na aula, João.")
> 
>     if pesos:
>         if len(notas) != len(pesos):
>             raise ValueError("A quantidade de notas e pesos não bate. Matemática básica, lembra?")
>         
>         # Cálculo de média ponderada para adultos
>         soma_ponderada = sum(n * p for n, p in zip(notas, pesos))
>         media = soma_ponderada / sum(pesos)
>     else:
>         # Média aritmética simples (o básico do básico)
>         media = sum(notas) / len(notas)
> 
>     return round(media, 2)
> 
> # Exemplo de uso (Tenta não quebrar isso)
> try:
>     minhas_notas = [8.5, 7.0, 9.2]
>     pesos_udf = [2, 3, 5] # Exemplo de pesos de semestre
>     
>     resultado = calcular_media_profissional(minhas_notas, pesos_udf)
>     print(f"Média Final: {resultado}")
>     
>     status = "APROVADO" if resultado >= 7.0 else "REPROVADO (Tente outra carreira)"
>     print(f"Status: {status}")
> 
> except Exception as e:
>     print(f"Erro: {e} - Volte para a documentação.")`
> 
> ---
> 
> ### **Considerações de quem já foi "Sênior" antes de você saber o que era um `if`:**
> 
> 1. **Modularização:** Pare de escrever código espaguete. Se você colocar o cálculo dentro do `print`, eu juro que deletar seu repositório.
> 2. **Tratamento de Exceções:** O mundo não é um mar de rosas. Os usuários digitam letras onde deveriam ir números. Trate o erro ou o erro tratará de te demitir.
> 3. **Escalabilidade:** Hoje são duas notas. Amanhã é um sistema legado com 50 critérios de avaliação diferentes integrados com um SAP capenga. Escreva funções que aceitem listas, não variáveis `nota1`, `nota2`.
> 
> Agora, volte para seu C++ ou Go e tente fazer algo que realmente desafie minha CPU. Se precisar de algo que não esteja no primeiro capítulo do Google, avise-me. Se for pra perguntar o que é um `for`, nem me chama.
> 

- *VERSÃO RESTRITIVA*:

PROMPT QUE MANDEI: 

> olá, quero pedir um código em python, não inclua explicações em texto, e após o código me informe o que foi feito, explicando passo a passo e dando dicas do que foi feito e usado. " crie um código para calcular a nota de aluno”
> 

RESUMO FINAL: Como já aprendemos, vimos que a IA segue de acordo com o que mandamos. Portanto vem a questão da importância do prompt correto para perguntar: 

> RESPOSTA DA IA:
> 
> 
> Python
> 
> `def calcular_resultado(notas, pesos=None, media_minima=7.0):
>     if not notas:
>         return None
> 
>     if pesos:
>         media = sum(n * p for n, p in zip(notas, pesos)) / sum(pesos)
>     else:
>         media = sum(notas) / len(notas)
>     
>     media = round(media, 2)
>     aprovado = media >= media_minima
>     
>     return {
>         "media": media,
>         "aprovado": aprovado,
>         "status": "Aprovado" if aprovado else "Reprovado"
>     }
> 
> # Exemplo de uso:
> notas_aluno = [8.5, 6.0, 9.0]
> pesos_sistema = [2, 3, 5]
> resultado = calcular_resultado(notas_aluno, pesos_sistema)
> print(resultado)`
> 
> ### O que foi feito: Passo a Passo
> 
> 1. **Definição da Função:** Criamos a função `calcular_resultado`que aceita três parâmetros: uma lista de notas, uma lista opcional de pesos e o valor da média mínima (que por padrão é 7.0).
> 2. **Validação Inicial:** O código verifica se a lista de notas está vazia para evitar erros de divisão por zero.
> 3. **Lógica de Média Ponderada:** Se a lista `pesos`for fornecida, o código utiliza a técnica de **List Comprehension** junto com a função `zip()`para multiplicar cada nota pelo seu peso respectivo, dividindo a soma total pela soma dos pesos.
> 4. **Lógica de Média Aritmética:** Caso não haja pesos, ele simplesmente soma as notas e divide pela quantidade de elementos ( `len`).
> 5. **Arredondamento:** Utilizamos `round(media, 2)`para garantir que o resultado não tenha dízimas infinitas, mantendo o padrão financeiro/acadêmico de duas casas decimais.
> 6. **Verificação de Status:** Comparamos a média final com a `media_minima`para definir um booleano ( `True`ou `False`).
> 7. **Retorno Estruturado:** A função retorna um **Dicionário** , que é a melhor forma de entregar múltiplos dados relacionados (média, booleano de aprovação e texto do status) de uma só vez.
> 
> ### Dicas e Melhores Práticas Utilizadas
> 
> - **Valores Default (Padrão):** O uso de `pesos=None`e `media_minima=7.0`torna a função flexível. Ela funciona tanto para casos simples quanto para sistemas complexos sem precisar ser reescrita.
> - **Função `zip()`:** Essencial para iterar sobre duas listas simultaneamente (notas e pesos) sem precisar usar índices manuais como `i++`, o que torna o código mais "Pythônico".
> - **Compreensão de lista:** O trecho `(n * p for n, p in zip(notas, pesos))`é mais performático e limpo do que criar um loop `for`tradicional com várias linhas.
> - **Dicionário como Resposta:** Em vez de retornar apenas um número, retornar um objeto/dicionário facilita a integração com interfaces (como um site ou aplicativo) que precisa exibir tanto o número quanto o status do aluno.

|  | NEUTRA:   | PERSONA:  | RESTRITIVA:  |
| --- | --- | --- | --- |
| PRECISÃO LÓGICA: | O calculo em si, funcionou, a diferença foi a metodologia usado. Uma metodologia mais simples e de forma mais aberta, dando duas opções, pois não especificamos qual linguagem queremos.  | O calculo continuou funcionando, a única diferença foi a forma que foi escrito e o método que me respondeu antes.
Vemos que ele assumiu a persona, na forma que pedi e descrevi.   | O calculo funcionou, mas a questão principal que muda para as outras, é a questão de como ela vai responder do jeito que você quer. 
 Além dele seguir as ordens que você pediu, sendo melhor entre os três no quesito de precisão lógica, pelo fato de você explicar do jeito que você quer e suas dúvidas.  |
| CLAREZA E EFICIÊNCIA: | A clareza foi meio que 5/10, dar para entender se você ler, mas a questão de ser meio vago ou que não explica muito bem é bem confuso.  | A eficiência do código foi muito útil, mas acredito que a clareza  não foi o ponto forte, mas a questão dele agir e ser como uma pessoa mesmo, foi super legal.  | A clareza do código é muito clara, ainda mais pelo fato de eu pedir para ele explicar e não por texto no código, só explicando o que foi feito no codigo.  |
| TAXA DE   ALUCINAÇÃO:  | A taxa de alucinação foi baixa, acredito que ele não viajou ou teve pensamentos fora da pergunta. Pelo o que eu perguntei já, ele já respondeu de uma forma educada que abrange totalmente minha dúvida. | A alucinação da persona, foi de acordo com o que eu eu pedi, vendo que ela respondeu da forma que pedi e nem explicou como fez e até me esnobou.  | Acredito que essa foi a melhor possível, seguindo tudo que pedi e de forma que entendi da melhor forma.
LINK DO NOTION: https://www.notion.so/TESTE-DE-PERSONA-E-SUAS-UTILIDADES-33353109e578802c9599c4e5938b651f?source=copy_link
ALUNOS DO PROJETO: 
JOAO VICTOR 
CAIO 
DANIEL NACIMENTO 
THALYANA 
KAYLA |
