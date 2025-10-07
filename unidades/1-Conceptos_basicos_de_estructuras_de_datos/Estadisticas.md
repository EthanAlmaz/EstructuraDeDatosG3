```java

package ejercicios;

import javax.swing.JOptionPane;

public class Estadisticas {

    private double[] valores;
    String listaMenores = "";

    public Estadisticas(int tamanio) {
        valores = new double[tamanio];
    }


    public void llenarValores(int n) {
        for (int i = 0; i < n; i++) {
            this.valores[i] = Integer.parseInt(JOptionPane.showInputDialog("Ingrese el valor " + (i + 1) + ": "));
        }

    }

    public double calcularPromedio() {
        double suma = 0;
        for (double valor : valores) {
            suma += valor;
        }
        double total = (valores.length > 0 ? suma / valores.length : 0);
        return total;
    }

    public int contarMayoresQuePromedio() {
        double promedio = calcularPromedio();
        int contador = 0;
        for (double valor : valores) {
            if (valor > promedio) {
                contador++;
            }
        }
        return contador;
    }

    public double obtenerMenoresQuePromedio() {
        double promedio = calcularPromedio();
        int contador = 0;
        for (double valor : valores) {
            if (valor < promedio) {
                contador++;
            }
        }

        for (double valor : valores) {
            if (valor < promedio) {
                listaMenores += valor + " ";
            }
        }
        return contador;
    }

    public void imprimir() {
        double promedio = calcularPromedio();
        int valoresMayores = contarMayoresQuePromedio();
        double valoresMenores = obtenerMenoresQuePromedio();
        JOptionPane.showMessageDialog(null, "\nResultados\nPromedio:" + promedio
                + "\nCantidad de valores mayores que el promedio: " + valoresMayores
                + "\nValores menores que el promedio: " + valoresMenores + " Lista: " + listaMenores);

    }

}