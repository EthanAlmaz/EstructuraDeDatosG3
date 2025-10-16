```java
package arreglos;

import javax.swing.JOptionPane;
/**
 *
 * @author blu
 */
public class OperacionesArreglos {
//Atributos=====================================================================

    private double vector[];
    private final int TAMANIO = 5; //NOTA: Los final deben de ir en mayusculas
//Constructores=================================================================

    public OperacionesArreglos() {//Constructor con tamanio fijo
        this.vector = new double[TAMANIO];
    }

    public OperacionesArreglos(int tamanio) {//Constructor  de tamanio variable por un int
        this.vector = new double[tamanio];
    }

    public OperacionesArreglos(double vector[]) {//Constructor de tamanio variable del mismo que otro vector
        this.vector = new double[vector.length];
    }
//Metodos=======================================================================

    public void llenarArreglo(double vector[]) {//Copia un arreglo de 1 en 1 con un while
        int i = 0;
        while (i < this.vector.length) {
            this.vector[i] = vector[i];//PREGUNTAR AL PROFE SI ESTE VECTOR[I] LLENA EL DE LA CLASE O EL INGRESADO EN LOS ATRIBUTOS DEL METODO
            i++;
        }
    }//Fin de llenar arreglo

    public void llenarArreglo() {//Llenar arreglo pero solicitando los valores de uno por uno INTEGER
        int i = 0;
        while (i < this.vector.length) {
            this.vector[i] = Double.parseDouble(JOptionPane.showInputDialog("Valor de la posicion [" + i + "]"));
            i++;
        }
    }//Fin de llenarArreglo

    public double sumarValores() {//Suma los valores dentro del arreglo
        double suma = 0;
        int i = 0;
        while (i < this.vector.length) {
            suma += this.vector[i];
            i++;
        }
        return suma;
    }//Fin de sumarValores

    public double obtenerValorMaximo() {
        double valorMax = 0;
        int i = 0;
        while (i < this.vector.length) {
            if (this.vector[i] > valorMax) {
                valorMax = this.vector[i];
            }
        }
        return valorMax;
    }//Fin de obtenerValorMaximo

    public double obtenerValorMinimo() {
        double valorMin = this.vector[0];
        int i = 1;
        while (i < this.vector.length) {
            if (this.vector[i] < valorMin) {
                valorMin = this.vector[i];
            }
        }
        return valorMin;
    }//Fin de obtenerValorMinimo

    public void cambiarTamanio() {
        int i = 0;
        int nuevoTamanio = Integer.parseInt(JOptionPane.showInputDialog("Ingrese el nuevo tamanio"));
        double[] arregloNuevo = new double[nuevoTamanio];
        while (i < nuevoTamanio) {
                arregloNuevo[i] = this.vector[i];
            i++;
        }
        this.vector=arregloNuevo;
        arregloNuevo=null;
    }

    public void compararTamanio(double vector[]) {
        if (this.vector.length != vector.length) {
            JOptionPane.showMessageDialog(null, "Los vectores son diferentes");
        } else {
            JOptionPane.showMessageDialog(null, "Los vectores son iguales");
        }
    }//Fin de compararTamanio

    public String buscarValor(double valorBuscado){
        int i=0;
        boolean sentinel= false;
        String stringSalida="";
        while(i<this.vector.length){
            if (this.vector[i]==valorBuscado){
                stringSalida="EL valor "+valorBuscado+" esta en la posicion ["+i+"]";
                sentinel=true;
                break;
            }
            i++;
        }
        if(!sentinel){
                stringSalida="EL valor buscado no existe en el arreglo";
        }
        return stringSalida;
    }
    
    public void imprimir() {
        String imprimir = "Su vector es:";
        int i = 0;
        while (i < this.vector.length) {
            imprimir += " [" + this.vector[i] + "]";
        }
        JOptionPane.showMessageDialog(null, imprimir);
    }
}
