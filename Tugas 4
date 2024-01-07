/******************************************************************************

                              Online C++ Compiler.
               Code, Compile, Run and Debug C++ program online.
Write your code in this editor and press "Run" button to compile and execute it.

*******************************************************************************/

#include <iostream>
#include <string>

using namespace std;

class Musuh;  // Deklarasi kelas Musuh

class Karakter {
public:
    string nama;
    int kesehatan;
    int poinSerangan;

    Karakter(string n, int h, int ps) : nama(n), kesehatan(h), poinSerangan(ps) {}

    void serang(Karakter& target);
    void serangMusuh(Musuh& musuh);
    void pulih();
};

class Musuh {
public:
    string nama;
    int kesehatan;
    int poinSerangan;

    Musuh(string n, int h, int ps) : nama(n), kesehatan(h), poinSerangan(ps) {}

    void serang(Karakter& pemain);
};

class Senjata {
public:
    string nama;
    int kerusakan;

    Senjata(string n, int k) : nama(n), kerusakan(k) {}
};

void Karakter::serang(Karakter& target) {
    cout << nama << " menyerang " << target.nama << " dan mengurangi " << poinSerangan << " poin kesehatan.\n";
    target.kesehatan -= poinSerangan;
}

void Karakter::serangMusuh(Musuh& musuh) {
    cout << nama << " menyerang " << musuh.nama << " dan mengurangi " << poinSerangan << " poin kesehatan musuh.\n";
    musuh.kesehatan -= poinSerangan;
}

void Karakter::pulih() {
    cout << nama << " memulihkan diri dan menambah 10 poin kesehatan.\n";
    kesehatan += 10;
}

void Musuh::serang(Karakter& pemain) {
    cout << nama << " menyerang " << pemain.nama << " dan mengurangi " << poinSerangan << " poin kesehatan pemain.\n";
    pemain.kesehatan -= poinSerangan;
}

int main() {
    int pilihan;
    int pilihanMusuh;

    Karakter ksatria(" Ksatria", 100, 20);
    Karakter pemanah(" Pemanah", 80, 15);
    Karakter medis(" Medis", 120, 10);

    Musuh musuhPrabowo(" Goblin", 50, 15);
    Musuh musuhJokowi(" Demon", 60, 20);

    Senjata panah(" Panah", 15);
    Senjata pedang(" Pedang", 25);

    while (true) {
        cout << " Pilih karakter:\n";
        cout << " 1. Ksatria\n";
        cout << " 2. Pemanah\n";
        cout << " 3. Medis\n";
        cout << " 4. Keluar\n";
        cout << " Masukkan Pilihan: ";

        cin >> pilihan;
        cout << endl;

        Karakter* karakterTerpilih;

        if (pilihan == 4) {
            cout << " Terima kasih sudah bermain!\n";
            break;
        } else if (pilihan == 1) {
            karakterTerpilih = &ksatria;
        } else if (pilihan == 2) {
            karakterTerpilih = &pemanah;
        } else if (pilihan == 3) {
            karakterTerpilih = &medis;
        } else {
            cout << " Pilihan tidak valid. Silakan pilih lagi.\n";
            continue;
        }

        while (true) {
            cout << " Pilih musuh:\n";
            cout << " 1. Goblin\n";
            cout << " 2. Demon\n";
            cout << " 3. Keluar\n";
            cout << " Masukkan Pilihan: ";

            cin >> pilihanMusuh;
            cout << endl;

            Musuh* musuhTerpilih;

            if (pilihanMusuh == 3) {
                cout << " Terima kasih sudah bermain!\n";
                return 0;
            } else if (pilihanMusuh == 1) {
                musuhTerpilih = &musuhPrabowo;
            } else if (pilihanMusuh == 2) {
                musuhTerpilih = &musuhJokowi;
            } else {
                cout << " Pilihan tidak valid. Silakan pilih lagi.\n";
                continue;
            }

            while (true) {
                cout << " Aksi yang tersedia:\n";
                cout << " 1. Serang (-10 poin kesehatan musuh)\n";
                cout << " 2. Memulihkan (+10 poin kesehatan)\n";
                cout << " 3. Beli senjata\n";
                cout << " 4. Serang Pemain\n";
                cout << " 5. Keluar\n";
                cout << " Masukkan Pilihan: ";

                cin >> pilihan;
                cout << endl;

                switch (pilihan) {
                    case 1:
                        if (karakterTerpilih == &ksatria || karakterTerpilih == &pemanah) {
                            karakterTerpilih->serangMusuh(*musuhTerpilih);

                            if (musuhTerpilih->kesehatan <= 0) {
                                cout << " Permainan selesai Anda berhasil mengalahkan musuh " << musuhTerpilih->nama << "!\n";
                                return 0;
                            }
                        } else {
                            cout << " Hanya karakter ksatria dan pemanah yang dapat menyerang musuh.\n";
                        }
                        break;
                    case 2:
                        karakterTerpilih->pulih();
                        break;
                    case 3:
                        cout << " List Senjata:\n";
                        cout << " 1. Panah (15 kerusakan)\n";
                        cout << " 2. Pedang (25 kerusakan)\n";
                        cout << " Pilih senjata yang ingin dibeli: ";
                        cin >> pilihan;

                        Senjata* senjataTerpilih;

                        if (pilihan == 1) {
                            senjataTerpilih = &panah;
                        } else if (pilihan == 2) {
                            senjataTerpilih = &pedang;
                        } else {
                            cout << " Pilihan tidak valid. Silakan pilih lagi.\n";
                            continue;
                        }

                        cout << " Anda telah membeli " << senjataTerpilih->nama << "!\n";
                        karakterTerpilih->poinSerangan += senjataTerpilih->kerusakan;
                        break;
                     case 4:
                        if (karakterTerpilih == &ksatria || karakterTerpilih == &pemanah) {
                            musuhTerpilih->serang(*karakterTerpilih);

                            if (karakterTerpilih->kesehatan <= 0) {
                                cout << " Anda kalah! " << musuhTerpilih->nama << " berhasil mengalahkan Anda.\n";
                                return 0;
                            }
                        } else {
                            cout << " Hanya karakter ksatria dan pemanah yang dapat diserang musuh.\n";
                        }
                         break;
                    case 5:
                        cout << " Terimakasih sudah bermain!\n";
                        return 0;
                    default:
                        cout << " Pilihan tidak valid. Silakan pilih lagi.\n";
                        continue;
                }
                    
                cout << " Status karakter:\n";
                cout << " Nama: " << karakterTerpilih->nama << "\n";
                cout << " Kesehatan: " << karakterTerpilih->kesehatan << "\n";
                cout << " Poin Serangan: " << karakterTerpilih->poinSerangan << "\n";
                cout << endl;

                cout << " Status musuh:\n";
                cout << " Nama: " << musuhTerpilih->nama << "\n";
                cout << " Kesehatan: " << musuhTerpilih->kesehatan << "\n";
                cout << " Poin Serangan: " << musuhTerpilih->poinSerangan << "\n";
                cout << endl;
            }
        }
    }

    return 0;
}

