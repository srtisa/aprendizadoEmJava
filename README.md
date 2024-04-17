# Aprendizado em Java 
Esse repositório é para documentar minha evolução em Java.
***
##### Tabuada De Multiplicação
Esse é um dos meus queridinhos, gosto de ver no console os resultados aparecendo. Nesse programa o usuário pode escolher até qual número vai a tabuada. Também usei um  `interface` como o exercício pedia.
        
        
        
        public interface Tabuada {
    void mostraTabuada(double numeroEscolhido);
    }

    //interface ^^ 
    //classe:

     public class TabuadaDeMultiplicacao implements Tabuada {
    Scanner sc = new Scanner(System.in);
    @Override
    public void mostraTabuada(double numeroEscolhido) {
        System.out.println("Até qual número você quer sua tabuada?");
        double numeroLimite = sc.nextDouble();
        for (int i = 0; i < numeroLimite; i++) {
            System.out.println(numeroEscolhido + "x" + i + " = " + numeroEscolhido * i);
        }
    }}   

***
##### Validações com Usuário
Nesse exercício com loops fiz validações de Strings e valores. Usei métodos da classe Usuário.
        
        
        //classe Usuário
        public class Usuario {
    private String nome;
    private int idade;
    private double salario;
    private String sexo;
    private String  estadoCivil;
    private String senha;


    public String getNome() {
        return nome;
    }

    public void setNome(String nome) {
        this.nome = nome;
    }

    public int getIdade() {
        return idade;
    }

    public void setIdade(int idade) {
        this.idade = idade;
    }

    public double getSalario() {
        return salario;
    }

    public void setSalario(double salario) {
        this.salario = salario;
    }

    public String getSexo() {
        return sexo;
    }

    public void setSexo(String sexo) {
        this.sexo = sexo;
    }

    public String getEstadoCivil() {
        return estadoCivil;
    }

    public void setEstadoCivil(String estadoCivil) {
        this.estadoCivil = estadoCivil;
    }

    public String getSenha() {
        return senha;
    }

    public void setSenha(String senha) {
        this.senha = senha;
    }


    public void mostrarUsuario () {
        System.out.println("++++++++++++++++++++++++++++++++++++++++++++++");
        System.out.println("Nome: " + getNome());
        System.out.println("Idade: " + getIdade());
        System.out.println("Salario: " + getSalario());
        System.out.println("Sexo: " + getSexo());
        System.out.println("Estado Civil: " + getEstadoCivil());
        System.out.println("Senha: " + getSenha());
        System.out.println("++++++++++++++++++++++++++++++++++++++++++++++");
    }
}

      //main
      import java.util.Scanner;
public class SenhaDiferenteNomeUsuario extends Usuario {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        Usuario usuario1 = new Usuario();

        System.out.println("Digite seu nome: ");
        usuario1.setNome(sc.nextLine());
        while (usuario1.getNome().length() < 3) {
            System.out.println("Inválido, seu nome precisa ter mais de 3 caracteres");
            usuario1.setNome(sc.nextLine());
        }

        System.out.println("Digite sua idade: ");
        usuario1.setIdade(sc.nextInt());
        while (usuario1.getIdade() < 0 || usuario1.getIdade() >= 100) {
            System.out.println("Inválido! Sua idade precisa estar entre 0 e 100.");
            usuario1.setIdade(sc.nextInt());
        }

        System.out.println("Digite seu salário: ");
        usuario1.setSalario(sc.nextDouble());
        while (usuario1.getSalario() < 0) {
            System.out.println("Seu salário precisa ser maior que 0.");
            usuario1.setSalario(sc.nextDouble());
        }

        System.out.println("Digite seu sexo: ");
        usuario1.setSexo(sc.nextLine().toUpperCase());
        while (!(usuario1.getSexo().equals("M") || usuario1.getSexo().equals("F"))) {
            System.out.println("Inválido! Digite M ou F");
            usuario1.setSexo(sc.nextLine().toUpperCase());
        }

        System.out.println("Digite seu estado civil: ");
        usuario1.setEstadoCivil(sc.nextLine().toLowerCase());
        while (!(usuario1.getEstadoCivil().equals("casado") || usuario1.getEstadoCivil().equals("solteiro") || usuario1.getEstadoCivil().equals("viúvo") || usuario1.getEstadoCivil().equals("divorciado"))) {
            System.out.println("Inválido, digite se é casado, solteiro, viúvo ou divorciado.");
            usuario1.setEstadoCivil(sc.nextLine().toLowerCase());
        }

        System.out.println("Digite uma senha de acesso: ");
        usuario1.setSenha(sc.nextLine());
        while (usuario1.getSenha().equals(usuario1.getNome())) {
            System.out.println("Não pode ter a senha igual ao seu nome!");
            usuario1.setSenha(sc.nextLine());
        }

        usuario1.mostrarUsuario();
    }
    }

      
