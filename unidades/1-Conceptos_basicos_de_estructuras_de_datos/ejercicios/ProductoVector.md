```java

package ejercicios;

import javax.swing.JOptionPane;

/**
 *
 * @author blu
 */
public class ProductoVector {

    //Varable de instancia
    private Producto[] productos;
    private final int TAMANIO = 3;

    public ProductoVector() {
        productos = new Producto[TAMANIO];
    }

    public ProductoVector(int tamanio) {
        if (tamanio > 0) {
            productos = new Producto[tamanio];
        } else {
            productos = new Producto[TAMANIO];
        }
    }

    public void agregarProducto(Producto producto) {//Agregar un nueov producto
        if (estaLleno()) {
            JOptionPane.showMessageDialog(null, "El arreglo esta lleno, no se pueden agregar mas productos");
        } else {
            this.productos[obtenerPosicion()] = producto;
            JOptionPane.showMessageDialog(null, "Se agrego producto");
        }
    }

    public boolean estaLleno() {//Verificar que el vector aun tiene espacio para un nuevo producto
        boolean sentinel = true;
        for (Producto producto : this.productos) {
            if (producto == null) {
                sentinel = false;
                break;
            }
        }
        return sentinel;
    }

    private int obtenerPosicion() {//Buscar una posicion vacia para un nuevo producto
        int posicion = 0;
        for (int i = 0; i < this.productos.length; i++) {
            if (this.productos[i] == null) {
                posicion = i;
                break;
            }
        }
        return posicion;
    }

    public void buscarProducto(String nombre) {
        int i = 0;
        while (i < this.productos.length) {
            if (this.productos[i] != null) {
                if ((this.productos[i].getNombre()).equals(nombre)) {
                    JOptionPane.showMessageDialog(null, "El objeto " + nombre + " se encuentra en la posición " + i);
                    break;
                } else if (i == (this.productos.length) - 1) {
                    JOptionPane.showMessageDialog(null, "El objeto " + nombre + " no existe");
                }
            }
            i++;
        }

    }//CHECAR

    public void vaciarPocision() {
        int posicion = Integer.parseInt(JOptionPane.showInputDialog("Ingrese la posicion del vector a modificar"));
        if (posicion > this.productos.length || posicion < 0) {
            JOptionPane.showMessageDialog(null, "Posición invalida");
        } else {
            this.productos[posicion] = null;
        }
    }

    public void modificarObjeto() {
        int posicion = Integer.parseInt(JOptionPane.showInputDialog("Ingrese la posicion del vector a modificar"));
        if (posicion > this.productos.length || posicion < 0) {
            JOptionPane.showMessageDialog(null, "Posición invalida");
        } else {
            boolean sentinel = true;
            while (sentinel) {
                switch (JOptionPane.showInputDialog("Nombre: " + this.productos[posicion].getNombre()
                        + "\nPrecio: " + this.productos[posicion].getPrecio()
                        + "\nExistencias: " + this.productos[posicion].getExistencia()
                        + "\nQue desea modificar?\n(1)Nombre\n(2)Precio\n(3)Existencias\n(4)Cancelar")) {
                    case "1":
                        this.productos[posicion].setNombre(JOptionPane.showInputDialog("Ingrese el nuevo nombre:"));
                        sentinel = false;
                        break;
                    case "2":
                        this.productos[posicion].setPrecio(Double.parseDouble(JOptionPane.showInputDialog("Ingrese el nuevo nombre:")));
                        sentinel = false;
                        break;
                    case "3":
                        this.productos[posicion].setExistencia(Integer.parseInt(JOptionPane.showInputDialog("Ingrese el nuevo nombre:")));
                        sentinel = false;
                        break;
                    case "4":
                        JOptionPane.showMessageDialog(null, "Cancelando operación");
                        sentinel = false;
                        break;
                    default:
                        JOptionPane.showMessageDialog(null, "Opcion invalida");
                        break;
                }
            }
            JOptionPane.showMessageDialog(null, "Nuevos datos del objeto:\nNombre: " + this.productos[posicion].getNombre()
                    + "\nPrecio: " + this.productos[posicion].getPrecio()
                    + "\nExistencias: " + this.productos[posicion].getExistencia());
        }
    }

    public String imprimirVector() {
        //imprimir=this.productos[i].toString(); IMPRIMIR USANDO EL TOSTRING
        int i = 0;
        String imprimir = "Lista de productos:";
        while (i < this.productos.length) {
            if (productos[i] != null) {
                imprimir += "\nNombre: " + productos[i].getNombre()
                        + "\nExistencias: " + productos[i].getExistencia()
                        + "\nPrecios: " + productos[i].getPrecio()
                        + "\nImporte de inventario: " + productos[i].getPrecio() * productos[i].getExistencia() + "\n";
            } else {
                imprimir += "\nProducto" + i + "vacio\n";
            }
            i++;
        }

        return imprimir;
    }

}
