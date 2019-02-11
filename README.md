# pratikum09
# Latihan1 (Program Menentukan nilai maximum & minimum menggunkan array)


```
1. Alur algoritmanya
	-Mendeklarasikan int nilai sebagai variabel array
	-mendeklarasikan int a sebagai nilai input
	-int max sebagai nilai maximal
	-int min sebagai nilai minimal
	-membuat perulangan untuk menentukan banyak inputan
```

```
for (a=1;a<=5;a++)
        {
        cout<< "Masukan nilai ke-" << a <<": ";
        cin>> nilai[a];
        }
```

```
for(a=2;a<=5;a++)
    {
        if (nilai[a]<min)
        {
            min=nilai[a];
        }
        else if (nilai[a]>max)
        {
            max=nilai[a];
        }
    }

```

```
-Mendefinisikan class maxmin dengan kode :
   public:
          maxmin();
          int proses(int n,int max,int min,int jumlah);
   private:
          int n, max, min, jumlah, a;
-Mendefinisikan int maxmin::proses(int n, int max, int min, int jumlah) dengan kode :
   cout << "Nilai Maksimum       : " << max << endl;
   cout << "Nilai Minimum        : "<< min << endl;
   cout << "Jumlah Seluruh Deret : "<<jumlah<<endl<<endl;
-Memasukkan bilangan dengan kode cin >> a;
-Menghitung nilai max,min dan jumlah dengan rumus :
   jumlah+=a;

   if(a<min)
   {
      min=a;
   }

   if(a>max)
   {
      max=a;
   }
    return proses(n-1,max,min,jumlah);
 
-Mendefinisikan int main(int argc, char *argv[])
-Tampilkan hasil kelayar
```


2).Berikut Kode Lengkapnya

```
#include <iostream>

using namespace std;

int main()
{
    int nilai[5],a,min,max;
    for (a=1;a<=5;a++)
        {
        cout<< "Masukan nilai ke-" << a <<": ";
        cin>> nilai[a];
        }

    min=nilai[1];
    max=nilai[1];
    for(a=2;a<=5;a++)
    {
        if (nilai[a]<min)
        {
            min=nilai[a];
        }
        else if (nilai[a]>max)
        {
            max=nilai[a];
        }
    }
    cout<< "Nilai minimum adalah : "<< min<<endl;
    cout<< "Nilai maximum adalah : "<< max<<endl;

    return 0;
}

```

1).Berikut Flowchatnya

![img](https://github.com/fahmieka21/pratikum09/blob/master/flowchart1.png)

2).Berikut Screenshotnya:

![img](https://github.com/fahmieka21/pratikum09/blob/master/latihan1.png)

# Latihan 2 (Program menentukan modus dari n bilangan bulat)

```
-Mendefinisikan class Hitung Statistik :

friend ostream& operator<<(ostream&, HitungStatistik&);
friend istream& operator>>(istream&, HitungStatistik&);
public:
HitungStatistik();
void hitung_modus();
private:
void maksimum();
void frekuensi();
int maks, item;
int n;
int A[20];
int f[11];

-Menghitung modus dengan rumus :
  for (int i=0; i<20; i++) f[i] = 0;

-Memasukka banyaknya data dengan kode :

cout << "Banyaknya data : ";
cin >> a.n;
cout << endl;
for (int i = 0; i < a.n; i++)
{
cout << "Data ke- : " << i+1 << " = ";
cin >> a.A[i];
cout << endl;

-Mendefinisikan void hitung statistik :: maksimum() dengan kode :

maks = f[0];
item = 1;
for (int i=0; i<n; i++)
if (f[i] > maks)
{
maks = f[i];
item = i;

-Menampilkan modus kelayar dengan kode :

cout << "Modus : " << item << endl;
cout << endl;

-Mendefinisikan void hitung statistik :: frekuensi() dengan kode :
   for (int i=1; i<n; i++) ++f[A[i]];

-Mendefinisikan void hitung statistik :: hitung_modus() dengan kode :

cout << "===================" << endl;
cout << "|Frekuensi running|" << endl;
cout << "===================" << endl;
cout << endl;
frekuensi();
maksimum();
-Menampilkan nilai modus kelayar dengan kode :

ostream& operator<<(ostream& out, HitungStatistik& a)
{
cout << "============" << endl;
cout << "|Loading...|" << endl;
cout << "============" << endl;
cout << endl;
a.hitung_modus();
cout << "Nilai Modus : " << a.item << endl;
cout << endl;
return out;
}
2).Berikut kode lengkapnya:

#include <iostream>

using namespace std;

class HitungStatistik
{
friend ostream& operator<<(ostream&, HitungStatistik&);
friend istream& operator>>(istream&, HitungStatistik&);
public:
HitungStatistik();
void hitung_modus();
private:
void maksimum();
void frekuensi();
int maks, item;
int n;
int A[20];
int f[11];
};

HitungStatistik::HitungStatistik()
{
     for (int i=0; i<20; i++) f[i] = 0;
}

istream& operator>>(istream& in, HitungStatistik& a)
{
cout << "Banyaknya data : ";
cin >> a.n;
cout << endl;
for (int i = 0; i < a.n; i++)
{
cout << "Data ke- : " << i+1 << " = ";
cin >> a.A[i];
cout << endl;
}
return in;
}

void HitungStatistik::maksimum()
{
maks = f[0];
item = 1;
for (int i=0; i<n; i++)
if (f[i] > maks)
{
maks = f[i];
item = i;
}
cout << "Modus : " << item << endl;
cout << endl;
}

void HitungStatistik::frekuensi()
{
for (int i=1; i<n; i++) ++f[A[i]];
}

void HitungStatistik::hitung_modus()
{
cout << "===================" << endl;
cout << "|Frekuensi running|" << endl;
cout << "===================" << endl;
cout << endl;
frekuensi();
maksimum();
}

ostream& operator<<(ostream& out, HitungStatistik& a)
{
cout << "============" << endl;
cout << "|Loading...|" << endl;
cout << "============" << endl;
cout << endl;
a.hitung_modus();
cout << "Nilai Modus : " << a.item << endl;
cout << endl;
return out;
}

main()
{
HitungStatistik run;
cin >> run;
cout << run;
return 0;
}

```

1).Berikut Flowchatnya

![img](https://github.com/fahmieka21/pratikum09/blob/master/flowchart2.png)

2).Berikut Screenshotnya:

![img](https://github.com/fahmieka21/pratikum09/blob/master/latihan2.png)

# Latihan3 Perkalian Matriks

```
1.Alur Algoritmanya
	-Mendeklarasikan int a1,b1,temp sebagai variabel untuk mengambil baris dan kolom
	-Mendeklarasikan char pil sebagai variabel untuk membuat pilihan mengulang atau tidak
	-mendeklarasikan ulang sebagai pilihan ulang
	-mendeklarasikan int hasil untuk hasil perkalian matriks
	-mendeklarasikan int AA sebagai variabel matriksA
	-mendeklrasikan int BB sebagai variabel matriksB
```

```
#include <iostream>

using namespace std;

int main()
{
    int a1[2],b1[2],temp=-1; //Variabel yang digunakan untuk mengambil jumlah kolom dan baris
    char pil; // variabel untuk membuat pilihan mengulang atau berkhir
    ulang:  // deklerasi untuk pilihan mengulang
/////////////  Proses Memasukkan jumlah baris dan kolom matrik  /////////////////
cout<<"--------------------------------------------------\n";
for (char u='A'; u<='B'; u++)
    {
    temp+=1;

    cout<<"Masukan baris matrik "<<u<<" : "; cin>>a1[temp];
    cout<<"Masukan kolom Matrik "<<u<<" : "; cin>>b1[temp];
    cout<<endl;
    }
    if(b1[0]==a1[1])
    {
    cout<<"--------------------------------------------------\n";
    int AA [a1[0]][b1[0]];   //Variabel matrik A
    int BB [a1[1]][b1[1]];   // Variable Matrik B
    int hasil[a1[0]][b1[1]]; // Variabel untuk Hasil Perkalian Matrik
////////------- Memasukkan Array A --------////////////
    cout<<"\nMasukkan data array A\n";
    for(int i=0; i<a1[0]; i++)
    {
        for (int c=0;c<b1[0];c++)
        {
            cout<<"A ["<<i+1<<"]["<<c+1<<"] = ";
            cin>>AA[i][c];
        }
            cout<<endl;
    }
////////------- Memasukkan Array B --------////////////
cout<<"--------------------------------------------------\n";
cout<<"\nMasukkan data array B\n";
for(int i=0; i<a1[1]; i++)
    {
        for (int c=0;c<b1[1];c++)
        {
            cout<<"B ["<<i+1<<"]["<<c+1<<"] = ";
            cin>>BB[i][c];
        }
    cout<<endl;
    }
///////////////-------- Proses Perhitungan --------////////////////////////////
for(int i=0; i<a1[0]; i++)
    {
        for (int c=0;c<b1[1];c++)
        {
            hasil [i][c] = (AA[i][0] * BB[0][c] )+( AA[i][1] * BB[1][c]);
        }
            cout<<endl;
    }
cout<<"-----------------------------------------------\n";
cout<<"Hasil Perkalian Matrik A dan B adalah : \n";
cout<<"--------------------------------------------------\n";
///////// -------- Memampilkan hasil Perkalian Matrik ---------- ///////////
for(int i=0; i<a1[0]; i++)
    {
    cout<<endl;
        for (int c=0;c<b1[1];c++)
        {
            cout<<"["<<hasil[i][c]<<"] ";
        }
    }
cout<<"\n\nATAU\n";
for(int i=0; i<a1[0]; i++)
    {
    cout<<endl;
        for (int c=0;c<b1[1];c++)
        {
            cout<<"["<<i+1<<"]["<<c+1<<"] = "<<hasil[i][c]<<endl;
        }
    }
}
else
{
 /////////-------- Menanyakan Pilihan ---------//////////////////
 cout<<"Kolom Matrik A harus sama dengan Baris Matrik B";
 cout<<"\nUlangi..? (Y/N) : "; cin>>pil;
 if (pil=='Y'||pil=='y')
    {
        goto ulang;
    }
}
}

```

3).Berikut Screenshotnya:

![img](


#Latihan4 Trasnpose Matriks

```
1.Alur Algoritmanya
	-Mendeklarasikan int A sebagi variabel array
	-Mendeklarasikan int a,b,baris,kolo sebagai variabel inputan
	-mendeklrasikan cahr pil untuk pilihan mengulang
```

2.Berikut Kode lengkapnya

```
#include <iostream>

using namespace std;

int main()
{
    int A [10][10],b,c,baris,kolom;
    char pil;

    do
    {
        cout<<"=======TRANSPOSE MATRIKS======="<< endl;
        cout<<"Masukan Jumlah Baris";
        cin>> baris;
        cout<<endl;
        cout<<"Masukan Jumlah Kolom";
        cin>> kolom;
        cout<<endl;

        for(b=0;b<baris;b++)
        {
            for(c=0;c<kolom;c++)
            {
                cout<<"Matriks ["<<b+1<<","<<c+1<<"]=";
                cin>>A[b][c];
            }
        }
        cout<<endl;
        cout<<"Matriks Pertama : "<<endl;
        for(b=0;b<baris;b++)
        {
            for(c=0;c<kolom;c++)
            {
                cout<<" "<< A[b][c]<<" ";
            }
            cout<<endl;
        }
        cout<<"Matriks Transpose : "<<endl;
        for(b=0;b<kolom;b++)
        {
            for(c=0;c<baris;c++)
            {
                 cout<<" " << A[c][b]<< " ";
            }
            cout<<endl;
        }

    cout<<"Ingin Mengulang Program ? (Y/N) : ";
    cin>>pil;
    }
    while(pil=='Y'||pil=='y');
}

```

3).Berikut Screenshotnya:

![img](https://github.com/fahmieka21/pratikum09/blob/master/latihan3.png)
![img](https://github.com/fahmieka21/pratikum09/blob/master/latihan4.png)

