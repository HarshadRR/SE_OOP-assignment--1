# SE_OOP-assignment--1       [ Design a class ‘Complex ‘with data members for real and imaginary part. Provide default and
                              Parameterized constructors. Write a program to perform arithmetic operations of two complex numbers]


import java.util.Scanner;

class Complex_No {
    private float real, img;

    public Complex_No() {
        real = 0;
        img = 0;
    }

    public Complex_No(float real, float img) {
        this.real = real;
        this.img = img;
    }

    public void Display(Complex_No C1, Complex_No C2) {
        System.out.println("First Complex Number = (" + C1.real + ") + (" + C1.img + ")i");
        System.out.println("Second Complex Number = (" + C2.real + ") + (" + C2.img + ")i");
    }

    public void AddNumbers(Complex_No C1, Complex_No C2) {
        float real = C1.real + C2.real;
        float img = C1.img + C2.img;
        System.out.println("Addition of Complex Numbers = (" + real + ") + (" + img + ")i");
    }

    public void SubNumbers(Complex_No C1, Complex_No C2) {
        float real = C1.real - C2.real;
        float img = C1.img - C2.img;
        System.out.println("Subtraction of Complex Numbers = (" + real + ") + (" + img + ")i");
    }

    public void MultiNumbers(Complex_No C1, Complex_No C2) {
        float real = C1.real * C2.real - C1.img * C2.img;
        float img = C1.real * C2.img + C1.img * C2.real;
        System.out.println("Multiplication of Complex Numbers = (" + real + ") + (" + img + ")i");
    }

    public void DivNumbers(Complex_No C1, Complex_No C2) {
        float denominator = C2.real * C2.real + C2.img * C2.img;
        float real = (C1.real * C2.real + C1.img * C2.img) / denominator;
        float img = (C1.img * C2.real - C1.real * C2.img) / denominator;
        System.out.println("Division of Complex Numbers = (" + real + ") + (" + img + ")i");
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        Complex_No cal = new Complex_No();

        System.out.println("Enter the Complex number in a+bi format:");
        
        System.out.print("Enter real part of First Number: ");
        float num1 = sc.nextFloat();
        System.out.print("Enter imaginary part of First Number: ");
        float num2 = sc.nextFloat();
        Complex_No Com1 = new Complex_No(num1, num2);

        System.out.print("Enter real part of Second Number: ");
        num1 = sc.nextFloat();
        System.out.print("Enter imaginary part of Second Number: ");
        num2 = sc.nextFloat();
        Complex_No Com2 = new Complex_No(num1, num2);

        sc.close();

        cal.Display(Com1, Com2);
        cal.AddNumbers(Com1, Com2);
        cal.SubNumbers(Com1, Com2);
        cal.MultiNumbers(Com1, Com2);
        cal.DivNumbers(Com1, Com2);
    }
}
