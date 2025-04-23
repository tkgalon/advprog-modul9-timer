# advprog-modul9-timer

Nama: Muhammad Zaid Ats Tsabit <br>
NPM: 2306224410 <br>
Kelas: Advprog-B
<hr>

## Experiment 1.2: Understanding how it works.
![experiment 1.2](/media/experiment12.jpeg)

Output yang muncul `"hey hey"` terlebih dahulu baru masuk ke `"hody!"` dan `"done!"`. Urutan ini terjadi karena `println!("Zaid's Komputer: hey hey")` dijalankan secara langsung oleh thread utama sebelum executor mulai dijalankan. Sementara itu, `spawner.spawn(...)` hanya mendaftarkan task ke dalam queue dan task tersebut baru dieksekusi saat `executor.run()` dipanggil. Di dalam task, barulah muncul output `"howdy!"`, disusul oleh jeda dua detik dari TimerFuture, lalu dilanjutkan dengan `"done!"`.

