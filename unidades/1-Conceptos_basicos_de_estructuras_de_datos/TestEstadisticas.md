```java

package ejercicios;

import javax.swing.JOptionPane;

/**
 *
 * @author blu
 */
public class TestEstadisticas {

    public static void main(String[] args) {
        
        int n = Integer.parseInt(JOptionPane.showInputDialog("Ingrese la cantidad de valores: "));
        
        Estadisticas estadisticas = new Estadisticas(n);
        estadisticas.llenarValores(n);
        estadisticas.imprimir();
        }
    }
