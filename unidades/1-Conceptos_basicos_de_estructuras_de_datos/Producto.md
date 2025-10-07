```java

package ejercicios;

/**
 *
 * @author blu
 */
public class Producto {

    //Variables de instancia
    private String nombre;
    private int existencia;
    private double precio;

    //Constructor
    public Producto() {
        this.nombre = "Sin nombre";
    }

    public Producto(String nombre, int existencia, double precio) {
        this.setNombre(nombre);
        this.setExistencia(existencia);
        this.setPrecio(precio);
    }

    //Metodo accesor de nombre
    public String getNombre() {
        return this.nombre;
    }

    //Metodo mutador de nombre
    public void setNombre(String nombre) {
        this.nombre = nombre.toUpperCase();
    }

    //Metodo accesor de existencia
    public int getExistencia() {
        return this.existencia;
    }

    //Metodo mutador de existencia
    public void setExistencia(int existencia) {
        if (existencia >= 0) {
            this.existencia = existencia;
        }
    }

    //Metodo accesor de precio
    public double getPrecio() {
        return this.precio;
    }

    //Metodo mutador de precio
    public void setPrecio(double precio) {
        if (precio >= 0.0) {
            this.precio = precio;
        }
    }
    
    @Override
    public String toString(){
        return "Nombre: "+this.nombre+
                "\nPrecio: "+this.getPrecio()+
                "\nExistencia: "+this.existencia;
    }
    
}//Fin de la clase
