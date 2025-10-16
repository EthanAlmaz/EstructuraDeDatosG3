```java
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Class.java to edit this template
 */
package arreglos;

/**
 *
 * @author blu
 */
import javax.swing.JOptionPane;

public class VectoresDobles {

    public static void main(String[] args) {
        int tamanio = 0;
        tamanio = obtenerTamanio();
        double arreglo[] = new double[tamanio];
        llenarArreglo(arreglo);
        imprimir(arreglo);
    }

    public static int obtenerTamanio() {
        
        return Integer.parseInt(JOptionPane.showInputDialog("Introduce la cantidad de alumnos a registrar"));
    }

    public static void llenarArreglo(double[] vector) {
        for (int i = 0; i < vector.length; i++) {
            vector[i] = Double.parseDouble(JOptionPane.showInputDialog("Intriduce el valor de la posicion [" + i + "]"));
        }
    }

    public static void imprimir(double vector[]) {
        String salida = "";
        for (double valor : vector) {
            salida += "| " + valor + " |";
        }
        JOptionPane.showMessageDialog(null, salida);
    }
}
