```java

package ejercicios;

import ejercicios.Producto;
import ejercicios.ProductoVector;
import javax.swing.JOptionPane;

/**
 *
 * @author blu
 */
public class TestProductoVector {

    public static void main(String[] args) {
        iniciar();
    }

    public static void iniciar() {
        int tamanio = Integer.parseInt(JOptionPane.showInputDialog("Intriduce el núemro de productos"));
        boolean sentinel = true;
        ProductoVector pv = new ProductoVector(tamanio);
        String opcion = "";
        do {
            opcion = JOptionPane.showInputDialog(obtenerMenu());
            switch (opcion) {
                case "1":
                    //Insertar producto
                    if (pv.estaLleno()) {
                        JOptionPane.showMessageDialog(null, "La lista está llena, no hay espacios disponibles");
                    } else {
                        pv.agregarProducto(llenarProducto());
                    }
                    break;
                case "2":
                    //Eliminar producto
                    pv.vaciarPocision();
                    break;
                case "3":
                    //Modificar producto (nombre, precio o la existencia)
                    pv.modificarObjeto();
                    break;
                case "4":
                    //Buscar producto
                    String buscar = JOptionPane.showInputDialog("Ingrese el nombre del producto a buscar:");
                    pv.buscarProducto(buscar);
                    break;
                case "5":
                    //Imprimir productos
                    JOptionPane.showMessageDialog(null, pv.imprimirVector());
                    break;
                case "6":
                    //Salir
                    sentinel = false;
                    JOptionPane.showMessageDialog(null, "Bye bye <3");
                    break;
                default:
                    JOptionPane.showMessageDialog(null, "Opción inválida");
                    break;
            }
        } while (sentinel);
    }

    public static String obtenerMenu() {
        return "Menú principal\n"
                + "1) Insertar producto\n"
                + "2) Eliminar producto\n"
                + "3) Modificar producto\n"
                + "4) Buscar producto\n"
                + "5) Imprimir producto\n"
                + "6) Salir\n"
                + "Elegir opción";
    }

    public static Producto llenarProducto() {
        String nombre = JOptionPane.showInputDialog("Introduce el nombre del producto");
        double precio = Double.parseDouble(JOptionPane.showInputDialog("Introduce el precio del producto"));
        int existencia = Integer.parseInt(JOptionPane.showInputDialog("Introduce la cantidad de productos"));
        Producto p1 = new Producto();
        p1.setNombre(nombre);
        p1.setPrecio(precio);
        p1.setExistencia(existencia);
        return p1;
    }
}
