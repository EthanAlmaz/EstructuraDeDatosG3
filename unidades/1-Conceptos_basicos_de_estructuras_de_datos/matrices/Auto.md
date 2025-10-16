```java
package matrices;
/**
 *
 * @author blu
 */
public class Auto {

    private String model;
    private int milesDriven;
    private double galonsOfGas;

    public Auto() {
        this.model = "Unknown";
    }

    public Auto(String model, int milesDriven, double galonsOfGas) {
        this.model = model;
        setMilesDriven(milesDriven);
        setGalonsOfGas(galonsOfGas);
    }

    public void setModel(String model) {
        this.model = model;
    }

    public void setMilesDriven(int milesDriven) {
        if (milesDriven >= 0) {
            this.milesDriven = milesDriven;
        } else {
            System.out.println("Miles driven can't be negative");
            System.out.println("Value not changed");
        }
    }

    public void setGalonsOfGas(double galonsOfGas) {
        if (galonsOfGas >= 0.0) {
            this.galonsOfGas = galonsOfGas;
        } else {
            System.out.println("Gallons of gas can't be negative");
            System.out.println("Value not changed");
        }
    }

    public String getModel() {
        return model;
    }

    public int getMilesDriven() {
        return milesDriven;
    }

    public double getGalonsOfGas() {
        return galonsOfGas;
    }

    @Override
    public String toString() {
        return "Auto{" + "model=" + model + ", milesDriven=" + milesDriven + ", galonsOfGas=" + galonsOfGas + '}';
    }

}
