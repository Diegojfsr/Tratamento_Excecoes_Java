Hierarquia das exceções
A linguagem Java, dispõe de uma variedade de classes, que representam exceções e estas classes, são organizadas em uma hierarquia denominadas Checked and Unchecked Exceptions ou Exceções Checadas e Não Checadas.

O que determina uma exceção ser classificada como checada ou não checada ?
É o risco dela ser disparada, logo, você precisa tratá-la.

Vamos imaginar que precisamos realizar de duas maneiras, a conversão de uma String para um número, porém o texto contém Alfanuméricos.


public class ExemploExcecao {
    public static void main(String[] args) {
        Number valor = Double.valueOf("a1.75");

        valor = NumberFormat.getInstance().parse("a1.75");
        
        System.out.println(valor);
       
    }
}

As linhas 3 e 5, apresentarão uma exceção ao serem executadas, e a linha 5 contém 
um método que pode disparar uma exceção checada, logo, nós programadores que 
iremos usar este método, teremos que tratá-la explicitamente com try \ catch.



Exceções customizadas
Nós podemos criar nossas próprias exceções, baseadas em regras de negócio e assim melhor direcionar quem for utilizar os recursos desenvolvidos no projeto, exemplo:

Imagina que como regra de negócio, para formatar um cep, necessita sempre de ter 8 dígitos, caso contrário, lançará uma exceção que denominamos de CepInvalidoException.

Primeiro criamos nossa exceção:

public class CepInvalidoException extends Exception {}

Em seguida, criamos nosso método de formatação de cep:

Copy
static String formatarCep(String cep) throws CepInvalidoException{
        if(cep.length() != 8)
          throw new CepInvalidoException();
        
          //simulando um cep formatado
          return "23.765-064";
    }

