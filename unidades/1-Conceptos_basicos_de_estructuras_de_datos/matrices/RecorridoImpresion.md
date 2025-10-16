```java
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Class.java to edit this template
 */
package matrices;

import javax.swing.JOptionPane;

/**
 *
 * @author blu
 */
public class RecorridoImpresion {

    public static void main(String[] args) {
        iniciar();
    }//Fin del main

    public static void iniciar() {
        double[][] matrix = new double[solicitarTamanio()][solicitarTamanio()];
        llenar(matrix);
        JOptionPane.showMessageDialog(null, imprimir(matrix));
    }

    public static int solicitarTamanio() {
        int valor = 0;
        boolean sentinel = true;
        //Validar que el usuario solo pueda introducir enteros
        do {
            try {
                valor = Integer.parseInt(JOptionPane.showInputDialog("Ingresa el número para la matriz:"));
                if (valor > 0) {
                    sentinel = false;
                } else {
                    JOptionPane.showConfirmDialog(null, "El número ingresado debe ser mayor a 0 (cero)");
                }
            } catch (NumberFormatException ex) {
                System.out.println(ex.getMessage());
                JOptionPane.showMessageDialog(null, "El dato ingresado debe ser un número");
            }
        } while (sentinel);
        return valor;
    }

    public static double solicitarValor() {
        double valor = 0;
        boolean sentinel = true;
        do {
            try {
                valor = Double.parseDouble(JOptionPane.showInputDialog("Ingrese el valor:"));
                sentinel=false;
            } catch (NumberFormatException ex) {
                JOptionPane.showMessageDialog(null, "El valor debe ser un número");
            }
        } while (sentinel);
        return valor;
    }

    public static void llenar(double[][] m) {
        int i = 0;
        int j = 0;
        while (i < m.length) {
            while (j < m[i].length) {
                m[i][j] = solicitarValor();
                j++;
            }
            i++;
            j = 0;
        }
    }

    public static String imprimir(double[][] m) {
        int i = 0;
        int j = 0;
        String resultado = "";
        do {
            do {
                resultado += "[" + m[i][j] + "] ";
                j++;
            } while (j < m.length);
            resultado += "\n";
            i++;
            j = 0;
        } while (i < m.length);
        return resultado;
    }

}//Fin de la clase
