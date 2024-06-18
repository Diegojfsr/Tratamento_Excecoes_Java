Estruturas excepcionais
Exceções
Ao executar o código Java, diferentes erros podem acontecer: erros de codificação feitos pelo programador, erros devido a entrada errada ou outros imprevistos.

Quando ocorre um erro, o Java normalmente para e gera uma mensagem de erro. O termo técnico para isso é: Java lançará uma exceção (jogará um erro).

De forma interpretativa em Java, um erro é algo irreparável, a aplicação trava ou é encerrada drásticamente. Já exceções é um fluxo inesperado da nossa aplicação, exemplo: Querer dividir um valor por zero, querer abrir um arquivo que não existe, abrir uma conexão de banco, com usuário ou senha inválida. Todos estes cenários e os demais, não são erros mas sim fluxos, não previstos pela aplicação.

É ai que entra mais uma responsabilidade do desenvolvedor, prever situações iguais a estas e realizar o que denominamos de Tratamento de Exceções.

Mão na massa!
Vamos trazer o cenário que estudamos na aula, sobre Terminal e Argumentos onde via terminal informamos alguns dados pessoais.

import java.util.Locale;
import java.util.Scanner;

public class AboutMe {
    public static void main(String[] args) {
        //criando o objeto scanner
        Scanner scanner = new Scanner(System.in).useLocale(Locale.US);
        
        System.out.println("Digite seu nome");
        String nome = scanner.next();
        
        System.out.println("Digite seu sobrenome");
        String sobrenome = scanner.next();

        System.out.println("Digite sua idade");
        int idade = scanner.nextInt();
        
        System.out.println("Digite sua altura");
        double altura = scanner.nextDouble();

        
        //imprimindo os dados obtidos pelo usuario
        System.out.println("Olá, me chamo " + nome.toUpperCase() + " " + sobrenome.toUpperCase());
        System.out.println("Tenho " + idade + " anos ");
        System.out.println("Minha altura é " + altura + "cm ");
        scanner.close();   
    }
}

Aparentemente é um programa simples, mas vamos listar algumas possíveis exceções, que podem acontecer.
- Não informar o nome e sobrenome;
- O valor da idade ter um caractere NÃO numérico;
- O valor da altura ter uma vírgula ao invés de ser um ponto (conforme padrão americano);
Executando o nosso programa com os valores abaixo, vamos entender qual exceção acontecerá:


Entrada	             Valor	      Exceção	                        Causa
Digite seu nome:     Marcelo



Digite seu sobrenome: Azevedo



Digite sua idade:     quinze (15)  java.util.InputMismatchException   O programa esperava o valor do tipo numérico inteiro.


Digite sua altura:    1,65          java.util.InputMismatchException  O programa esperava o valor do tipo numérico decimal no formato americano, exemplo: 1.65




Conhecendo algumas exceções já mapeadas
A linguagem Java, dispõe de uma vasta lista de classes que representam exceções, abaixo iremos apresentar as mais comuns:


Nome	
java.lang.NullPointerException
Causa
Quando tentamos obter alguma informação de uma variável nula.

Nome
java.lang.ArithmeticException
Causa
Quando tentamos dividir um valor por zero.

Nome
java.sql.SQLException
Causa
Quando existe algum erro, relacionado a interação com banco de dados.

Nome
java.io.FileNotFoundException
Causa
Quando tentamos ler ou escrever, em um arquivo que não existe.

