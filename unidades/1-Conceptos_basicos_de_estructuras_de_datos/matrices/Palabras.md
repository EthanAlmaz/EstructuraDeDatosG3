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
public class Palabras {

    static char[][] palabras;

    public static void main(String[] args) {
        crearmatriz();
        llenarmatriz();
        imprimir();
        buscarPalabra();
    }

    static public void crearmatriz() {
        palabras = new char[3][5];
    }

    static public void llenarmatriz() {
        String p="";
        for (int i = 0; i < 3; i++) {
            p = JOptionPane.showInputDialog("Ingrese la palabra de 5 letras");
            for (int j = 0; j < 5; j++) {
                palabras[i][j]=p.charAt(j);
            }
        }
    }
    
    static public void imprimir(){
        String imprimir="";
        for (int i = 0; i < 3; i++) {
            imprimir+="|";
            for (int j = 0; j < 5; j++) {
                imprimir+=palabras[i][j]+"|";
            }
            imprimir+="\n";
        }
        JOptionPane.showMessageDialog(null, imprimir);
    }
    
    static public void buscarPalabra(){
        String buscar=JOptionPane.showInputDialog("Ingrese la palabra de 5 letras a buscar:");
        int contador=0;
        for (int i = 0; i < 3; i++) {
                if(palabras[i][0]==buscar.charAt(0)&&palabras[i][1]==buscar.charAt(1)&&
                        palabras[i][2]==buscar.charAt(2)&&palabras[i][3]==buscar.charAt(3)&&
                        palabras[i][4]==buscar.charAt(4))
                    JOptionPane.showMessageDialog(null, "La palabra se encuentra en la "+(i+1)+" fila");
                else
                    contador++;
        }
        if(contador==3)
                    JOptionPane.showMessageDialog(null, "La palabra no existe en la lista");
    }
}
