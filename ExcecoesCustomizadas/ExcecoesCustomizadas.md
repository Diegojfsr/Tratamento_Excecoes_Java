Exceções customizadas
Nós podemos criar nossas próprias exceções, baseadas em regras de 
negócio e assim melhor direcionar quem for utilizar os recursos 
desenvolvidos no projeto, exemplo:

Imagina que como regra de negócio, para formatar um cep, necessita 
sempre de ter 8 dígitos, caso contrário, lançará uma exceção que 
denominamos de CepInvalidoException.

Primeiro criamos nossa exceção:


public class CepInvalidoException extends Exception {}

Em seguida, criamos nosso método de formatação de cep:

static String formatarCep(String cep) throws CepInvalidoException{
        if(cep.length() != 8)
          throw new CepInvalidoException();
        
          //simulando um cep formatado
          return "23.765-064";
    }

