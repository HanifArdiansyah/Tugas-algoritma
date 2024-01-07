/******************************************************************************

Welcome to GDB Online.
  GDB online is an online compiler and debugger tool for C, C++, Python, PHP, Ruby, 
  C#, OCaml, VB, Perl, Swift, Prolog, Javascript, Pascal, COBOL, HTML, CSS, JS
  Code, Compile, Run and Debug online from anywhere in world.

*******************************************************************************/
#include <iostream>

using namespace std;

int main()
{
    string namapemesan, namaorang, tempattujuan;
   
    int pilihan;
    int jumlahTiket;
    int hargaEkonomi = 100000;
    int hargaBisnis = 200000;
    int hargaEksekutif = 300000;
    double totalHarga;
    
    cout << "Masukkan Nama Pemesan: ";
    cin >> namaorang;
    cout << "asal tempat tujuan: ";
    cin >> tempattujuan;
    
    
 
    cout << "Pilih kelas tiket:" << endl;
    cout << "1. Ekonomi (Rp100,000/tiket)" << endl;
    cout << "2. Bisnis (Rp200,000/tiket)" << endl;
    cout << "3. Eksekutif (Rp300,000/tiket)" << endl;
    cout << "Masukkan pilihan (1-3): ";
    cin >> pilihan;
 
    cout << "Masukkan jumlah tiket yang ingin dipesan: ";
    cin >> jumlahTiket;
    cout << endl;

    switch (pilihan) {
        case 1:
            totalHarga = jumlahTiket * hargaEkonomi;
            break;
        case 2:
            totalHarga = jumlahTiket * hargaBisnis;
            break;
        case 3:
            totalHarga = jumlahTiket * hargaEksekutif;
            break;
        default:
            cout << "Pilihan tidak ada di pilihan menu" << endl;
            return 1;  
    }

    if (totalHarga > 500000) {
        totalHarga *= 0.9;  
    } else if (totalHarga > 300000) {
        totalHarga *= 0.95;  
    } else if (totalHarga > 200000) {
        totalHarga *= 0.98;  
    }

    cout << "pesanan tiket atas nama: " << namaorang << endl;
    cout << "tempat tujuan Kereta: " << tempattujuan << endl;
    cout << "Total harga tiket: Rp" << totalHarga << endl;

   

    return 0;
}
