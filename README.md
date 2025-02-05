# belajar-RegEx

Apa itu RegEx?
Regular Expressions, atau sering disingkat RegEx, adalah pola teks yang digunakan untuk menemukan, memeriksa, atau memanipulasi teks.

Mengapa RegEx Penting?
Dalam pemrograman, kita sering perlu:
1. Memvalidasi input: Memeriksa apakah format email atau nomor telepon yang dimasukkan pengguna sudah benar.
2. Mencari teks: Menemukan kata atau frasa tertentu dalam dokumen.
3. Mengganti teks: Mengubah kata atau karakter tertentu dalam teks.

RegEx memudahkan semua tugas ini dengan cara yang efisien dan fleksibel.

Contoh Penggunaan:
1. Validasi Email pada form
2. Validasi nomor telepon pada form
3. Mencari daftar email saat scrapping data
4. Mencari daftar nomor WA saat scrapping data
5. dll


Dasar-Dasar RegEx dalam JavaScript
Di JavaScript, RegEx adalah objek khusus yang bisa dituliskan dengan dua cara:

1. Literal RegEx: Ditulis di antara garis miring (/).
let greeting = /halo/;

2. Konstruktor RegExp: Menggunakan fungsi RegExp().
let greeting = new RegExp('halo');

Metakarakter dalam RegEx
1. dot(.) -> Mencocokkan dengan karakter tunggal kecuali bari baru.
contoh:
let text = "That's hot!";
let pattern = /h.t/g;
let result = text.match(pattern);

hasil : ['hat', 'hot']

2. [] -> Kelas karakter. Cocok dengan karakter apa pun yang terdapat di antara tanda kurung siku
contoh:
let text = "Is this all there is?";
let pattern = /[h,i]/g;

hasil: ['h, 'i', 'h', 'i']

3. ^ -> Awal string.
let text = "Is this his";
let pattern = /^this/g;

hasil: "Is"

4. [^] -> menentukan kecocokan untuk karakter apa pun TIDAK di antara tanda kurung
let text = "Is this all there is?";
let pattern = /[^h]/g;

hasil: I,s, ,t,i,s, ,a,l,l, ,t,e,r,e, ,i,s,?

let text = "I Scream For Ice Cream, is that OK?!";
let pattern = /[^a-s]/gi;

hasil: Pencarian global ada (i) yang tidak peka huruf besar/kecil untuk karakter TIDAK dalam rentang [a-s]:
, , , ,,, , ,t,t, ,?,!

5. * -> Cocok dengan 0 atau lebih pengulangan simbol sebelumnya.
Pencarian global untuk "l", diikuti dengan nol atau lebih "o" Karakter:
let text = "Hellooo World! Hello W3Schools!";
let pattern = /lo*/g;

hasil: l,looo,l,l,lo,l

Pencarian global untuk "1", diikuti oleh nol atau lebih karakter "0":
let text = "1, 100 or 1000?";
let pattern = /10*/g;

hasil: 1, 100, 1000

6. + -> Mencocokkan 1 atau lebih pengulangan simbol sebelumnya.
let text = "Hellooo World! Hello W3Schools!"; 
let pattern = /o+/g;

Pencarian global untuk setidaknya satu "o" dalam string:
hasil: o,o,o,o,o,o,o

let text = "Hellooo World! Hello W3Schools!"; 
let pattern = /\w+/g;

Pencarian global untuk setidaknya satu karakter kata:
Hellooo,World,Hello,W3Schools

7. ?	-> Membuat simbol sebelumnya (opsional).

let text = "1, 120 or 1000?";
let pattern = /10?/g;

Penelusuran global untuk "1", diikuti dengan nol atau satu karakter "0":
1,1,10

const text = "color colour";
const regex = /colou?r/g;

hasil: "color,colour"
Penjelasan: u? mencocokkan huruf "u" nol atau satu kali, sehingga mencocokkan kedua ejaan "color" dan "colour".

8. {x} -> Penghitung n{X} cocok dengan string apa pun yang berisi urutan X-n. X harus berupa angka.

let text = "100, 1000 or 10000?";
let pattern = /\d{4}/g;

Pencarian global untuk urutan empat digit:
hasil: 1000,1000

9. {x,y} -> Kuantifikasi n{X,Y} cocok dengan string apa pun yang berisi urutan X ke Y n.
let text = "100, 1000 or 10000?";
let pattern = /\d{3,4}/g; 

Pencarian global untuk urutan tiga hingga empat digit
hasil: 100,1000,1000

10. {x,} -> Penghitung n{X,} cocok dengan string apa pun yang berisi urutan setidaknya X n.
let text = "1000, 1000 or 10000?";
let pattern = /\d{5,}/g; 

Pencarian global untuk urutan setidaknya lima digit:
hasil: 10000

11. (xyz) ->	Grup karakter. Mencocokkan karakter xyz dalam urutan yang tepat.
13. |	-> Pergantian. Cocok dengan karakter sebelum atau karakter setelah simbol. 
14. $	-> akhir input.


 Character Sets
 1. .	Karakter apa pun kecuali baris baru
2. \w	-> karakter alfanumerik: [a-zA-Z0-9_]
3. \W	-> dengan karakter non-alfanumerik: [^\w]
4. \d	-> dengan digit: [0-9]
5. \D	-> dengan non-digit: [^\d]
6. \s	-> dengan karakter spasi kosong: [\t\n\f\r\p{Z}]
7. \S	-> dengan karakter non-spasi: [^\s]


Lookarounds
1. ?=	-> Pandangan Positif
2. ?!	-> Pandangan Negatif
3. ?<= ->	Melihat ke belakang positif
4. ?<!	-> Tampilan Negatif


Modifier
1. i	-> Tidak peka huruf besar/kecil: Match tidak peka huruf besar/kecil.
2. g	-> Pencarian Global: Cocokkan semua instans, bukan hanya yang pertama.
3. m	-> Multibaris: Karakter meta jangkar bekerja di setiap baris.
4. d ->  Menentukan awal dan akhir pertandingan dan peka huruf besar/kecil.


dokumen lengkap bisa akses disini: https://www.w3schools.com/jsref/jsref_obj_regexp.asp
