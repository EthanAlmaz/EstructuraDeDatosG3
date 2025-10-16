```java
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Class.java to edit this template
 */
package estructuraDatos;

import javax.swing.JOptionPane;

/**
 *
 * @author blu
 */
public class AppEstructuraDeDatos {

    public static void main(String[] args) {
        iniciar();
    }

    public static void iniciar() {
        String opcion = "";
        boolean sentinel = true;
        do {
            opcion = JOptionPane.showInputDialog(MenuEstructuraDeDatos.obtenerMenuPrincipal());
            switch (opcion) {
                case "1":
                    arreglos();
                    break;
                case "2":
                    JOptionPane.showMessageDialog(null, "Opcion 2");
                    break;
                case "3":
                    JOptionPane.showMessageDialog(null, "Opcion 3");
                    break;
                case "4":
                    JOptionPane.showMessageDialog(null, "Opcion 4");
                    break;
                case "5":
                    JOptionPane.showMessageDialog(null, "Opcion 5");
                    break;
                case "6":
                    JOptionPane.showMessageDialog(null, "I'll be back!");
                    sentinel = false;
                    break;
                default:
                    JOptionPane.showMessageDialog(null, "Opcion no valida!");
                    break;
            }

        } while (sentinel);
    }

    public static void arreglos() {
        String opcion = "";
        boolean sentinel = true;
        do {
            opcion = JOptionPane.showInputDialog(MenuEstructuraDeDatos.obtenerMenuPrincipal());
            switch (opcion) {
                case "1":
                    JOptionPane.showMessageDialog(null, "Vectores");
                    break;
                case "2":
                    JOptionPane.showMessageDialog(null, "Matrices");
                    break;
                case "3":
                    JOptionPane.showMessageDialog(null, "Gracias por utilizar Arreglos!");
                    sentinel = false;
                    break;
                default:
                    JOptionPane.showMessageDialog(null, "Gracias por utilizar Arreglos!");
                    break;
            }
        } while (sentinel);
    }
}
