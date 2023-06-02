# CalculadoraIMC
package app.unis.br;

import javax.swing.*;

public class CalculadoraIMC {
    public static void main(String[] args) {
        // Valores de peso e altura
        double peso = Double.parseDouble(JOptionPane.showInputDialog("Digite o peso em kg:"));
        double altura = Double.parseDouble(JOptionPane.showInputDialog("Digite a altura em cm:"));

        // Altura para metros
        altura /= 100; // Convertendo para metros

        // Cálculo do IMC
        double imc = peso / (altura * altura);

        // Classificação do IMC
        String classificacao = classificarIMC(imc);

        // Resultado
        String mensagem = "Seu IMC é: " + imc + "\n";
        mensagem += "Classificação: " + classificacao;
        
        JOptionPane.showMessageDialog(null, mensagem);
    }

    // Classificação do IMC
    public static String classificarIMC(double imc) {
        if (imc < 17) {
            return "Muito abaixo do peso";
        } else if (imc >= 17 && imc < 18.5) {
            return "Abaixo do peso";
        } else if (imc >= 18.5 && imc < 25) {
            return "Peso normal";
        } else if (imc >= 25 && imc < 30) {
            return "Acima do peso";
        } else if (imc >= 30 && imc < 35) {
            return "Obesidade Grau I";
        } else if (imc >= 35 && imc < 40) {
            return "Obesidade Grau II";
        } else {
            return "Obesidade Grau III";
        }
    }
}
