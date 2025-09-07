# Program-menghitung-umur-dan-menentukan-zodiak
Tugas 2 Algoritma dan Pemrograman

// Program Menghitung Umur dan Zodiak
#include <iostream>
using namespace std;

// Validasi Tahun Kabisat
bool kabisat (int tahun){
    return ((tahun % 4 == 0 && tahun % 100 != 0 ) || (tahun % 400  == 0));
}

int main() {
    // Deklarasi Variabel
    int tanggal;
    int bulan;
    int tahun_lahir;
    int tahun_sekarang;

    // Input Data
    cout << "Masukkan Tanggal : ";
    cin >> tanggal;
    cout << "Masukkan Bulan : ";
    cin >> bulan;
    cout << "Masukkan Tahun Lahir : ";
    cin >> tahun_lahir;
    cout << "Masukkan Tahun Sekarang : ";
    cin >> tahun_sekarang;

    // Jika Tahun Lahir Lebih Tinggi Angkanya
    if (tahun_lahir > tahun_sekarang){
        cout << "Tahun Lahir Tidak Boleh Lebih Tinggi dari Tahun Sekarang" << endl ;
        return 0;
    }

    // Jika Bulan Kurang Dari 1 dan Lebih Dari 12
    if (bulan < 1 || bulan > 12){
        cout << "Tidak Ada Bulan Kurang Dari 1 dan Lebih Dari 12" << endl ;
        return 0;
    }

    // Menentukan Maksimal Hari Dalam 1 Bulan
    int maksHari;
    if (bulan == 2) {
        if (kabisat(tahun_lahir)) maksHari = 29;
        else maksHari = 28;
    } 
    else if (bulan == 4 || bulan == 6 || bulan == 9 || bulan == 11) {
        maksHari = 30;
    } 
    else {
        maksHari = 31;
    }

    // Proses Validasi Tanggal
    if (tanggal < 1 || tanggal > maksHari) {
        cout << "Tanggal tidak valid untuk bulan tersebut!" << endl;
        return 0;
    }

    // Operator Penghitung Umur
    int umur = tahun_sekarang - tahun_lahir;

    // Under 17 Tahun = Bocil
    if (umur < 17) {
        cout << "Bocil" << endl;
    } else {
        //Deklarasi Variabel Zodiak
        string zodiak;

        //Menentukan Zodiak
        if ((tanggal >= 20 && bulan == 1) || (tanggal <= 18 && bulan == 2)) zodiak = "Aquarius";
        else if ((tanggal >= 19 && bulan == 2) || (tanggal <= 20 && bulan == 3)) zodiak = "Pisces";
        else if ((tanggal >= 21 && bulan == 3) || (tanggal <= 19 && bulan == 4)) zodiak = "Aries";
        else if ((tanggal >= 20 && bulan == 4) || (tanggal <= 20 && bulan == 5)) zodiak = "Taurus";
        else if ((tanggal >= 21 && bulan == 5) || (tanggal <= 20 && bulan == 6)) zodiak = "Gemini";
        else if ((tanggal >= 21 && bulan == 6) || (tanggal <= 22 && bulan == 7)) zodiak = "Cancer";
        else if ((tanggal >= 23 && bulan == 7) || (tanggal <= 22 && bulan == 8)) zodiak = "Leo";
        else if ((tanggal >= 23 && bulan == 8) || (tanggal <= 22 && bulan == 9)) zodiak = "Virgo";
        else if ((tanggal >= 23 && bulan == 9) || (tanggal <= 22 && bulan == 10)) zodiak = "Libra";
        else if ((tanggal >= 23 && bulan == 10) || (tanggal <= 21 && bulan == 11)) zodiak = "Scorpio";
        else if ((tanggal >= 22 && bulan == 11) || (tanggal <= 21 && bulan == 12)) zodiak = "Sagittarius";
        else zodiak = "Capricorn";

        // Output Umur dan Zodiak
        cout << "Umur Kamu : " << umur << endl;
        cout << "Zodiak Kamu : " << zodiak << endl;
    }
    return 0;
}
