# ConversorTemperatura

package main;

import java.util.Scanner;

public class Main {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Insira A Temperatura Em Graus Celsius: ");
        double temperaturaCelsius = scanner.nextDouble();

        ConversorTemperatura conversorTemperatura = new ConversorTemperatura(temperaturaCelsius);

        System.out.println("Temperatura Em Celsius: " + conversorTemperatura.getTemperaturaCelsius() + " °C");
        System.out.println("Temperatura Em Fahrenheit: " + conversorTemperatura.getTemperaturaFahrenheit() + " °F");
        System.out.println("Tipo De Clima: " + conversorTemperatura.getTipoClima());

        scanner.close();

    }
}

package main;

public class ConversorTemperatura {

    private double temperaturaCelsius;
    private double temperaturaFahrenheit;
    private String tipoClima;

    public ConversorTemperatura(double temperaturaCelsius) {
        this.temperaturaCelsius = temperaturaCelsius;
        this.temperaturaFahrenheit = (temperaturaCelsius * 9 / 5) + 32;

        if (temperaturaFahrenheit <= 64.4) {
            tipoClima = "Frio";
        } else if (temperaturaFahrenheit >= 66.2 && temperaturaFahrenheit <= 73.4) {
            tipoClima = "Agradável";
        } else if (temperaturaFahrenheit >= 75.2 && temperaturaFahrenheit <= 95) {
            tipoClima = "Quente";
        } else {
            tipoClima = "Muito quente";
        }
    }

    public double getTemperaturaCelsius() {
        return temperaturaCelsius;
    }

    public double setTemperaturaCelsius(double temperaturaCelsius) {
        this.temperaturaCelsius = temperaturaCelsius;
        return temperaturaCelsius;

    }

    public double getTemperaturaFahrenheit() {
        return temperaturaFahrenheit;
    }

    public double setTemperaturaFahrenheit(double TemperaturaFahrenheit) {
        this.temperaturaFahrenheit = temperaturaFahrenheit;
        return temperaturaFahrenheit;
    }

    public String getTipoClima() {
        return tipoClima;
    }

    public String settipoClima() {
        this.tipoClima = tipoClima;
        return tipoClima;
    }

}
