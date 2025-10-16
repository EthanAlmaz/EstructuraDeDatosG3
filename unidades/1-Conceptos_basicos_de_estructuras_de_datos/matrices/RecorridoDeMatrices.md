```java
package matrices;

import javax.swing.JOptionPane;

/**
 *
 * @author blu
 */
public class RecorridoDeMatrices {

    public static void main(String[] args) {
        int[][] matrix = {
            {1, 3, 4},
            {3, 4, 5},
            {7, 6, 10},};
        imprimir(matrix);
    }

    public static void imprimir(int[][] m) {
        String salida = "";
        //Controla las fials
        for (int i = 0; i < m.length; i++) {
            //Controla las columnas
            for (int j = 0; j < m[i].length; j++) {
                salida += m[i][j] + " ";
            }
            salida+="\n";
        }
        JOptionPane.showMessageDialog(null, salida);
    }
}