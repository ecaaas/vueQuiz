#### Kuis Vue 
![alt text](https://user-images.githubusercontent.com/47271571/54110378-d62f4400-4413-11e9-9be5-66c719664006.png)
![alt text](https://user-images.githubusercontent.com/47271571/54110382-d6c7da80-4413-11e9-9a3b-1915903306ec.png)

Membuat web dari vue.js dengan tema kuis, skor user dan total jawaban yang benar akan ditampilkan
# Cara Instal
1. Download/Clone

```sh
https://github.com/ecaaas/Ica_Quiz.git
```
2. klik ke direktori kuis berikut lalu: **npm instal**
3. Jika sudah menginstal *node modules*, jalankan kuis dengan: **npm install**
        App running at:
    - Local: http://localhost:8080/
    - Network: http://your.ip:8080/
4. buka *url* tersebut menggunakan *Browser*
### Bedah Koding
#### Inisialisasi Array
```
var quiz = {
    title: '', // Judul kuis
    questions: [
      {
        text: "Question", // Pertanyaan pertama dalam kuis
        responses: [
          { text: '', choice: 'A' }, // Pilihan ke-1
          { text: '', choice: 'B' }, // Pilihan ke-2
          { text: '', choice: 'C' }, // Pilihan ke-3
          { text: '', choice: 'D' }  // Pilihan ke-4
        ],
        correct: 'B'  // Jawaban yang benar
      }
    ]
};
```
#### Fungsi
| Koding  | Kegunaan |
| ------------- | ------------- |
| check(correct, picked) {}  | Dijalankan apabila tombol *Next* diklik. Perintah di dalamnya: **memberi 1 poin apabila jawaban yang dipilih merupakan jawaban yang benar**, ***uncheck* pada *radio button***, **dan mengganti pertanyaan** |
| scoreCal: function() {}  | Mengalkulasi jumlah jawaban benar hingga menjadi skor (**0 - 100**)  |
