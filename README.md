# Tutorial 8 - Subscriber

Nama : Ilham Abdillah Alhamdi
NPM : 2206081194
Kelas : Advance Programming - A

1. Apa itu AMPQ ?
   AMQP singkatan dari Advanced Message Queuing Protocol. Ini adalah protokol lapisan aplikasi standar terbuka untuk middleware berorientasi pesan. Dalam istilah yang lebih sederhana, ini adalah protokol untuk pertukaran pesan antara aplikasi atau komponen.

    AMQP memungkinkan komunikasi antara sistem yang berbeda, memungkinkan mereka untuk bertukar pesan secara andal, asinkron, dan aman. Biasanya digunakan dalam skenario di mana bagian-bagian yang berbeda dari suatu sistem perlu berkomunikasi satu sama lain dengan cara yang terlepas dan dapat diskalakan, seperti dalam sistem terdistribusi, arsitektur mikro layanan, dan sistem pesan perusahaan.

2. Apa arti dari `guest:guest@localhost:5672`? Apa itu `guest` pertama dan apa maksud dari `guest` kedua? Apa arti `localhost:5672`?

    - `guest:guest@localhost:5672` adalah sebuah URI (Uniform Resource Identifier) yang digunakan untuk mengidentifikasi lokasi server yang menjalankan layanan AMQP (Advanced Message Queuing Protocol)
    - `guest:guest` mengacu pada _username_ dan _password_ yang digunakan untuk mengakses server AMQP. Dalam hal ini, "guest" digunakan sebagai _username_ dan _password_ default.
    - `localhost:5672` menunjukkan alamat host dan nomor port server AMQP

3. _Slow Customer Consume Simulation_
    - Terdapat 25 message yang dikirim oleh publisher dalam waktu yang bersamaan
    - Consumer membaca setiap message dalam interval 1 detik
      ![Slow Customer Simulation](./assets/images/rabbitmq-slow-customer-reading.png)
4. _Multi Customer Simulation_
    - Terdapat tiga customer dan satu publisher (kanan atas). Dalam sekali publish, publisher mengirimkan 5 messages. Setiap customer akan membaca message yang tersedia di queue. 
        ![Console of multi customer and one publisher](./assets/images/console-multi-consumer.png)

    - Garis customer ack (warna ungu) memiliki peningkatan yang lebih besar dibandingkan dengan kasus dimana hanya terdapat 1 customer. Tentunya hal ini merupakan suatu performance improvement dalam proses komunikasi antar publisher-customer 
        ![Chart of Multi Customer Simulation](./assets/images/rabbitmq-console-multi-consumer.png)