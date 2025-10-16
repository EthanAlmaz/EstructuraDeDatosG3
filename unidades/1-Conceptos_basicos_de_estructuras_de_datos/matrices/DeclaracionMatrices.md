```java
package matrices;
/**
 *
 * @author blu
 */
public class DeclaracionMatrices {

    public static void main(String[] args) {
        //Declaracion de matrices (No confundir con instanciamiento)
        int numeroAlumnos[][];
        double[][] calificaciones;
        String[][] nombresMuejres, nombresHombres[][];
        //Instanciar matrices
        int i = 0, j = 0, fila = 5, columna = 4;
        numeroAlumnos = new int[3][3];
        calificaciones = new double[fila][columna];
        int numAlumnos = 15, numExamenes = 5;
        double[][] examenes = new double[numAlumnos][numExamenes];

        //Asignar valores a las matrices
        int[] vector = {1, 2, 3, 4, 5};
        int[][] matrix = {
            {1, 2, 3, 4},
            {4, 5, 6, 7},
            {7, 8, 9, 10},
            {10, 11, 12, 13}};
        char[][] grades;
        grades = new char[4][];
        grades[0] = new char[23];
        grades[1] = new char[16];

        //Accesar a los datos
        int valor = matrix[0][0];
        valor = matrix[0][j];
        valor = matrix[i][j];
        valor = matrix[matrix.length - 1][j];//Se obtiene la ultima fila con columna j
        valor = matrix[matrix.length - 1][matrix[matrix.length - 1].length - 1];//Se obtiene el valor de la ultima fila y la ultima columna

        //Instanciar varios objetos de auto
        Auto sedan1 = new Auto("BMW", 0, 0.0);
        Auto sedan2 = new Auto("Chevrolet", 100, 15.0);
        Auto sedan3 = new Auto("Pontiac", 0, 0.0);
        Auto sedan4 = new Auto("Toyota", 200, 0.0);
        Auto sedan5 = new Auto("Mazda", 50, 30.0);
        Auto sedan6 = new Auto("Volkswagen", 50, 30.0);

        //Declaracion e inicializacion de una matriz de autos
        Auto[][] cars = {
            {sedan1, sedan2, sedan3},
            {sedan4, sedan5, sedan6},
            {new Auto("Ford",200,30.0), new Auto(), new Auto()}
        };
        
        String modeloSedan5=cars[1][1].getModel();
        double galonesSedan5=cars[1][1].getGalonsOfGas();

    }
}
