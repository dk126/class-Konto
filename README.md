# class-Konto
using System;
using System.Collections.Generic;
using System.Text;

namespace Klasy_i_obiekty__2_
{
    public class Konto
    {
        public string wlasciciel { get; set; }
        public double saldoPoczatkowe { get; set; }
        private double przelewMiedzyKontami { get; set; }
        private double przelewZewnetrzny { get; set; }
        private double wplata { get; set; }
        private double wyplata { get; set; }


        public Konto(string w, double sP, double pMK, double pZ, double wp, double wy)
        {
            wlasciciel = w;
            saldoPoczatkowe = sP;
            przelewMiedzyKontami = pMK;
            przelewZewnetrzny = pZ;
            wplata = wp;
            wyplata = wy;
        }

        public void PokazKonto()
        {
            Console.WriteLine("Wlasciciel: {0}, Saldo początkowe: {1}, \r\nPrzelew miedzy kontami: {2}, Przelew zewnętrzny: {3}, \r\nWplata w dniu dzisiejszym: {4}, Wyplata w dniu dzisiejszym: {5}\r\n", wlasciciel, saldoPoczatkowe, przelewMiedzyKontami, przelewZewnetrzny, wplata, wyplata);
        }

        public Konto(string wlasciciel, double saldoPoczatkowe)
        {
            this.wlasciciel = wlasciciel;
            this.saldoPoczatkowe = saldoPoczatkowe;
        }

        public void Dodaj(double saldoPoczatkowe, double przelewZewnetrzny, double wyplata, double wplata)
        {
            double wynik;
            wynik = saldoPoczatkowe + przelewZewnetrzny - wyplata + wplata;
            Console.WriteLine("Aktualny stan konta: {0}", wynik);
        }
    }
}







using System;
/*   Stwórz klasę Konto z kilkoma polami, metodami i konstruktorami 
 *   (saldo początkowe, końcowe, przelew miedzy kontami, przelew zewnętrzny, 
 *   wplata, wyplata itd.) Następnie utwórz co najmniej 3 obiekty i wykonaj kilka metody na nich.*/
namespace Klasy_i_obiekty__2_
{
    class Program
    {
        static void Main(string[] args)
        {
            Konto firmowe = new Konto("Sklep sportowy", 5600, -3000, 0, 2000, 0);            
            firmowe.PokazKonto();           
            Konto prywatne = new Konto("Leszek Gawędziarz", 18000, 2500, 0, 3200, 1000);
            prywatne.PokazKonto();
            Konto Pjotera = new Konto("Piotr Kowalczyk", 1000000);
            Pjotera.PokazKonto();
            Console.ReadKey();
        }
    }
}
