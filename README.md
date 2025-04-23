# advprog-modul9-timer

Nama: Muhammad Zaid Ats Tsabit <br>
NPM: 2306224410 <br>
Kelas: Advprog-B
<hr>

## Experiment 1.2: Understanding how it works.
![experiment 1.2](/media/experiment12.jpeg)

Output yang muncul `"hey hey"` terlebih dahulu baru masuk ke `"hody!"` dan `"done!"`. Urutan ini terjadi karena `println!("Zaid's Komputer: hey hey")` dijalankan secara langsung oleh thread utama sebelum executor mulai dijalankan. Sementara itu, `spawner.spawn(...)` hanya mendaftarkan task ke dalam queue dan task tersebut baru dieksekusi saat `executor.run()` dipanggil. Di dalam task, barulah muncul output `"howdy!"`, disusul oleh jeda dua detik dari TimerFuture, lalu dilanjutkan dengan `"done!"`.

## Experiment 1.3: Multiple Spawn and removing drop.
#### Multiple Spawn:
![experiment 1.3](/media/multiplespawn.jpeg)
Dengan multiple spawn ini task berlajan secara bersamaan. Dimana terlihat `"done!"` terjadi setelah `"done2!"`, yang mana urutannya terbalik jika kita liat di codenya. Alhasil semua task tersebut dapat selesai dengan urutan yang tidak selalu sama.

### Without Drop Spawner:
![experiment 1.3 without drop](/media/withoutdrop.jpeg)
Setelah kita menghapus `drop(spawner)`, terlihat program masing berjalan. Hal tersebut disebabkan spawner kita terus menunggu untuk mengeksekusi tugas, yang mana dengan `drop(spawner)` kita bisa memberitahu `executor` bahwa sudah tidak ada tugas yang ada sehingga program bisa langsung distop.

