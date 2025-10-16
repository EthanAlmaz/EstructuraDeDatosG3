```java

package ejercicios;

import javax.swing.JOptionPane;

/**
 *
 * @author blu
 */
public class PromedioVector {

    // Atributos (vectores A y B que dará el usuario)
    private int[] vectorA;
    private int[] vectorB;

    // Constructor

    public PromedioVector() {
        int casillas=Integer.parseInt(JOptionPane.showInputDialog("Ingrese el tamaño de los vectores: "));
        this.vectorA=new int[casillas];
        this.vectorB=new int[casillas];
    }

    public void llenarCasillas(){
        int casilla=0;
        for (int i : vectorA) {
            this.vectorA[casilla]=Integer.parseInt(JOptionPane.showInputDialog("Ingrese el valor en vectorA de la casilla "+casilla));
            casilla++;
        }
        casilla=0;
        for (int j : vectorB) {
            this.vectorB[casilla]=Integer.parseInt(JOptionPane.showInputDialog("Ingrese el valor en vectorB de la casilla "+casilla));
            casilla++;
        }
    }

    public void setVectorA(int[] vectorA) {
        this.vectorA = vectorA;
    }

    public void setVectorB(int[] vectorB) {
        this.vectorB = vectorB;
    }

    public int[] getVectorA() {
        return vectorA;
    }

    public int[] getVectorB() {
        return vectorB;
    }

    
    
    // Suma de A y B
    public int[] sumar() {
        int[] resultado = new int[vectorA.length];
        for (int i = 0; i < vectorA.length; i++) {
            resultado[i] = vectorA[i] + vectorB[i];
        }
        return resultado;
    }

    // Resta
    public int[] restar() {
        int[] resultado = new int[vectorA.length];
        for (int i = 0; i < vectorA.length; i++) {
            resultado[i] = vectorA[i] - vectorB[i];
        }
        return resultado;
    }

    // Multiplicación
    public int[] multiplicar() {
        int[] resultado = new int[vectorA.length];
        for (int i = 0; i < vectorA.length; i++) {
            resultado[i] = vectorA[i] * vectorB[i];
        }
        return resultado;
    }

    // División
    public double[] dividir() {
        double[] resultado = new double[vectorA.length];
        for (int i = 0; i < vectorA.length; i++) {
            if (vectorB[i] != 0) {
                resultado[i] = (double) vectorA[i] / vectorB[i];
            } else {
                resultado[i] = 0; // evitar división entre 0
            }
        }
        return resultado;
    }

    // Potencias (A elevado a cada número de B)
    public double[] potencias() {
        double[] resultado = new double[vectorA.length];
        for (int i = 0; i < vectorA.length; i++) {
            resultado[i] = Math.pow(vectorA[i], vectorB[i]);
        }
        return resultado;
    }

    //Imprimir el vector
    public String imprimirInt(int[] vectorC) {
        String impresion = "";
        for (int i : vectorC) {
            impresion +="["+i+"] ";            
        }
      return impresion;
    }
    //Imprimir para double
    public String imprimirDouble(double[] vectorC) {
        String impresion = "";
        for (double i : vectorC) {
            impresion +="["+i+"] ";            
        }
      return impresion;
    }
}
