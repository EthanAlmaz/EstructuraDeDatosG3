```java
package matrices;

import javax.swing.JOptionPane;

public class OperacionesMatrices {

    private double[][] m;

    public OperacionesMatrices(int filas, int columnas) {
        if (validarTamanio(filas) && validarTamanio(columnas)) {
            m = new double[filas][columnas];
        } else {
            m = new double[2][2];
        }
    }

    public double[][] getM() {
        return this.m;
    }

    public void setM(double[][] m) {
        if (m.length == this.m.length && m[m.length - 1].length == this.m[0].length) {
            for (int i = 0; i < m.length; i++) {
                for (int j = 0; j < m[i].length; j++) {
                    this.m[i][j] = m[i][j];
                }
            }
        }
    }

    private boolean esCuadrada() {
        return this.m.length == this.m[this.m.length - 1].length;
    }

    public double sumaDiagonal() throws Exception {
        if (!esCuadrada()) {
            throw new Exception("La matriz debe ser cuadrada");
        }
        double acum = 0.0;
        for (int i = 0; i < m.length; i++) {
            acum += m[i][i];
        }
        return acum;
    }

    public double sumaDiagonalInversa() throws Exception {
        if (!esCuadrada()) {
            throw new Exception("La matriz debe ser cuadrada");
        }
        double acum = 0.0;
        int columna = m.length - 1;
        for (int i = 0; i < m.length; i++) {
            acum += m[i][columna];
            columna--;
        }
        return acum;
    }

    public double[] sumaFilas() throws Exception {
        if (!esCuadrada()) {
            throw new Exception("La matriz debe ser cuadrada");
        }
        double[] resultado = new double[this.m.length];
        int acum;
        for (int i = 0; i < this.m.length; i++) {
            acum = 0;
            for (int j = 0; j < this.m.length; j++) {
                acum += this.m[i][j];
            }
            resultado[i] = acum;
        }
        return resultado;
    }

    public double[] sumaColumnas() throws Exception {
        if (!esCuadrada()) {
            throw new Exception("La matriz debe ser cuadrada");
        }
        double[] resultado = new double[this.m.length];
        double acum;
        for (int i = 0; i < this.m.length; i++) {
            acum = 0;
            for (int j = 0; j < this.m.length; j++) {
                acum += this.m[j][i];
            }
            resultado[i] = acum;
        }
        return resultado;
    }

    public String imprimir() {
        String salida = "";
        for (double[] fila : this.m) {
            for (double valor : fila) {
                salida += valor + " | ";
            }
            salida += "\n";
        }
        return salida;
    }

    public String imprimir2() {
        String salida = "";
        for (int i = 0; i < m.length; i++) {
            for (int j = 0; j < m[i].length; j++) {
                salida += m[i][j] + " | ";
            }
            salida += "\n";
        }
        return salida;
    }

    private boolean validarTamanio(int tamanio) {
        return (tamanio > 0);
    }

    public void imprimirSumaColumnasFilas(double[] filas,double[] columnas) {
        //double[] columnas=sumaColumnas()
        String imprimir="Filas: ";
        for (int i = 0; i < filas.length; i++) {
            imprimir+="| "+filas[i]+" |\t";
        }
        imprimir+="Columnas:\n";
        for (int i = 0; i < columnas.length; i++) {
            imprimir+="| "+columnas[1]+" |\n";
        }
        JOptionPane.showMessageDialog(null, imprimir);
    }
    
    public void sumaMatrices(double[][] m1,double[][] m2){
        int i=0, j=0;
        String salida="";
        double[][] suma;
        suma=new double[m1.length][m2[m2.length-1].length];
        while(i<m1.length){
            while(j<m2[m2.length-1].length){
                suma[i][j]=m1[i][j]+m2[i][j];
                salida+="|"+suma[i][j]+"| ";
                j++;
            }
            j=0;
            i++;
            salida+="\n";
        }
        JOptionPane.showMessageDialog(null, salida);
    }

        public void restaMatrices(double[][] m1,double[][] m2){
        int i=0, j=0;
        String salida="";
        double[][] suma;
        suma=new double[m1.length][m2[m2.length-1].length];
        while(i<m1.length){
            while(j<m2[m2.length-1].length){
                suma[i][j]=m1[i][j]-m2[i][j];
                salida+="|"+suma[i][j]+"| ";
                j++;
            }
            j=0;
            i++;
            salida+="\n";
        }
        JOptionPane.showMessageDialog(null, salida);
    }
    
    public void llenarMatrizRandom(double[][] matriz){
        String resultado="";
        for (int i = 0; i < matriz.length; i++) {
            for (int j = 0; j < matriz[matriz.length-1].length; j++) {
                matriz[i][j]=Math.random()*10;
                resultado+="| "+matriz[i][j]+" |";
            }
            resultado+="\n";
        }
        JOptionPane.showMessageDialog(null, "Matriz resultate= "+resultado);
    }

}//Fin de la clase
