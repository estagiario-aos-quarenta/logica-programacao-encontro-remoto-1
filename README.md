# logica-programacao-encontro-remoto-1
Entrega da atividade solicitada pelo tutor, durante o 'Encontro Remoto 1', da matéria lógica de programação.

## Atividade:
### Sistema de Cadastro de Peças 

A empresa Savinis, focada no desenvolvimento de software de alta performance, contratou você para realizar a programação de um sistema de cadastro de peças, que deverá atender os seguintes requisitos: 
Se a peça possuir um peso superior a 100gramas, pode cadastrar.
Dada a capacidade de cada caixa, caso a lista de peças seja superior a 10, imprima uma mensagem informando não ter capacidade suficiente.
Caso a peça tenha um nome com quantidade inferior a 3 caracteres, informe uma mensagem de erro.
Para criação desse sistema de cadastro, você, enquanto programador(a) responsável, deverá solucionar os seguintes desafios:
Aplicar técnicas de programação e ferramentas para desenvolvimento do código.
Aplicar linguagem de programação JavaScript para implementação do sistema.


### Primeira solução:

ALGORITMO DO PROGRAMA CADASTRO DE PEÇAS:
1º passo: ler e validar o nome do produto;
2º passo: ler e validar o peso do produto;
3º passo: incluir o produto na lista;
4º passo: perguntar se o usuário deseja cadastar um novo produto;
5º passo: verificar a resposta do usuário e o espaço disponível na caixa (de até 10 produtos). Caso o usuário queira fazer um novo cadastro e ainda haja espaço na caixa, repetir os passos anteriores, caso contrário, seguir para o próximo passo;
6º passo: informar ao usuário que o limite da caixa foi alcançado, caso o usuário queira cadastrar um novo produto e não haja mais espaço na caixa, caso contrário, seguir para o próximo passo;
7º passo: listar os produtos cadastrados;
8º passo: exibir o total de produtos cadastrados.


CODIFICAÇÃO EM PROTUGUÊS ESTRUTURADO

Algoritmo "cadastro_de_pecas"
tipo
    PRODUTO =  registro
                   NOME: literal
                   PESO: real
	           fimregistro

var 
    LISTA: vetor [1..10] de PRODUTO
    NOME_PRODUTO: literal
    PESO_PRODUTO: real
    NOVO_CADASTRO: literal
    VALOR_VALIDO: logico
    CONTADOR: inteiro
    I: inteiro   

inicio
    CONTADOR <--- 1
    NOVO_CADASTRO <--- "sim"
    
    enquanto (NOVO CADASTRO = "sim") e (CONTADOR <= 10) faca
        VALOR_VALIDO <--- falso
        
        enquanto (VALOR_VALIDO = falso) faca
            leia (NOME_PRODUTO)

            se (tamanho(NOME_PRODUTO) >= 3) entao
                VALOR_VALIDO <--- verdadeiro
            senao
                escreva("Atênção:  O nome do produto deve ter no  mínimo 3 caracteres!")
            fimse         

        fimenquanto             

        VALOR_VALIDO <--- falso
        
        enquanto (VALOR_VALIDO = falso) faca
            leia (PESO_PRODUTO)

            se (PESO_PRODUTO  > 100.00) entao
                VALOR_VALIDO <--- verdadeiro                
            senao
                escreva ("Atênção: o peso deverá ser maior do que 100 gramas!")
            fimse

        fimenquanto
        
        LISTA [CONTADOR] .NOME <--- NOME_PRODUTO
        LISTA [CONTADOR] .PESO <--- PESO_PRODUTO
        leia (NOVO_DADASTRO)

        se (NOVO_CADASTRO = "sim") entao
            CONTADOR <--- CONTADOR + 1
        fimse

    fimenquanto

    se (CONTADOR > 10) então
        escreva("Não é possível cadastrar mais produtos. Capacidade máxima da caixa é de 10 produtos.")
    fimse

    para I de 1 até CONTADOR passo 1 faca
        escreva (LISTA [ I ] .NOME, ",", LISTA [ I ] .PESO, "gramas.")
    fimpara

    escreva ( "Todatal de produtos: ", CONTADOR)

fimalgoritmo
