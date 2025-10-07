```java

package ejercicios;

import javax.swing.JOptionPane;

public class TestPromedioVector {

    public static void main(String[] args) {
        
        PromedioVector vectorC = new PromedioVector();
        vectorC.llenarCasillas();
        JOptionPane.showMessageDialog(null,"Suma= "+(vectorC.imprimirInt(vectorC.sumar())));
        JOptionPane.showMessageDialog(null,"Resta= "+(vectorC.imprimirInt(vectorC.restar())));
        JOptionPane.showMessageDialog(null,"Multiplicación= "+(vectorC.imprimirInt(vectorC.multiplicar())));
        JOptionPane.showMessageDialog(null,"Divición= "+(vectorC.imprimirDouble(vectorC.dividir())));
        JOptionPane.showMessageDialog(null,"Potencia= "+(vectorC.imprimirDouble(vectorC.potencias())));
    }
}
