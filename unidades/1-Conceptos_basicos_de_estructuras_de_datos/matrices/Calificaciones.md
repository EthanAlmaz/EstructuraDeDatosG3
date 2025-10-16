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
public class Calificaciones {

    static double[][] calificaciones;
    static String[] materias;
    static String[] alumnos;
    static int filas;
    static int columnas;
    static double[] promedioMaterias;
    static double[] promedioAlumnos;

    public static void main(String[] args) {
        pedirFilas();
        pedirColumnas();
        crearLlenarMatrices();
        promedioAlumnos();
        promedioMaterias();
        imprimir();
    }
    //--------------------------------------------------------------------------

    static public boolean validarDato(int dato) {
        if (!(dato > 0)) {
            JOptionPane.showMessageDialog(null, "Dato inválido");
        }
        return (dato > 0);
    }

    static public void pedirFilas() {
        do {
            filas = (Integer.parseInt(JOptionPane.showInputDialog("Ingrese la cantidad de alumnos:")));
        } while (!validarDato(filas));
    }

    static public void pedirColumnas() {
        do {
            columnas = (Integer.parseInt(JOptionPane.showInputDialog("Ingrese la cantidad de materias:")));
        } while (!validarDato(columnas));
    }

    static public void crearLlenarMatrices() {
        calificaciones = new double[filas][columnas];
        alumnos = new String[filas];
        materias = new String[columnas];
        for (int i = 0; i < filas; i++) {
            for (int j = 0; j < columnas; j++) {
                calificaciones[i][j] = Math.round(Math.random() * 10.0 * 10.0) / 10;
            }
        }
        for (int i = 0; i < filas; i++) {
            alumnos[i] = "A" + (i + 1);
        }
        for (int i = 0; i < columnas; i++) {
            materias[i] = "M" + (i + 1);
        }
        promedioAlumnos = new double[filas];
        promedioMaterias = new double[columnas];
    }

    static public void promedioAlumnos() {
        double promedio = 0;
        for (int i = 0; i < filas; i++) {
            promedio = 0;
            for (int j = 0; j < columnas; j++) {
                promedio += calificaciones[i][j];
            }
            promedioAlumnos[i] = promedio / columnas;
        }
    }
    
    static public void promedioMaterias() {
        double suma = 0;
        for (int i = 0; i < filas; i++) {
            suma = 0;
            for (int j = 0; j < columnas; j++) {
                suma += calificaciones[j][i];
            }
            promedioMaterias[i] = suma / filas;
        }
    }

    static public void imprimir() {
        String impresion = "|       |";
        for (int i = 0; i < columnas; i++) {
            impresion += " " + materias[i] + " |";
        }
        impresion += "Prom|\n";
        for (int i = 0; i < filas; i++) {
            impresion += "| " + alumnos[i] + "  |";
            for (int j = 0; j < columnas; j++) {
                impresion += " " + calificaciones[i][j] + " |";
            }
            impresion += promedioAlumnos[i]+"\n";
        }
        impresion += "|Prom|";
        for (int i = 0; i < columnas; i++) {
            impresion += " "+promedioMaterias[i]+" |";
        }
        JOptionPane.showMessageDialog(null, impresion);
    }

}
