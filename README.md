***1. How many data your publlsher program will send to the message broker in one run?***

Program publisher yang tertera dalam kode akan mengirim lima buah data ke message broker dalam satu kali eksekusi. Data tersebut adalah instance dari `UserCreatedEventMessage` yang masing-masing memiliki atribut `user_id` dan `user_name`. Pada fungsi `main`, ada lima pemanggilan fungsi `publish_event` yang setiap kali memanggilnya, akan mengirimkan satu event baru ke message broker.

***2. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?***

URL "amqp://guest:guest@localhost:5672" yang digunakan baik pada program publisher maupun subscriber menunjukkan bahwa kedua program tersebut terhubung ke message broker yang sama. Komponen URL ini terdiri dari beberapa bagian:
- **amqp://** adalah skema yang digunakan, menandakan bahwa koneksi menggunakan protokol AMQP (Advanced Message Queuing Protocol), yang umum digunakan untuk komunikasi antar aplikasi melalui message broker.
- **guest:guest** adalah username dan password yang digunakan untuk autentikasi ke server AMQP. Dalam konteks pengembangan, biasanya ini adalah credential default yang tidak disarankan untuk produksi.
- **localhost:5672** menunjukkan bahwa message broker berjalan pada host lokal (mesin yang sama dengan program yang berjalan) dan mendengarkan pada port 5672.

Jadi, URL yang sama pada program publisher dan subscriber mengindikasikan bahwa mereka berinteraksi dengan exchange yang sama di dalam broker untuk mengirim dan menerima pesan.

***Interface RabbitMQ***
<img width="1440" alt="Screenshot 2024-04-23 at 8 39 36 AM" src="https://github.com/wahyuhiddayat/advprog-module8-publisher/assets/119432989/60771198-807c-4b5a-8f58-41cf1a3c47be">

***Connection on RabbitMQ***
<img width="1440" alt="Screenshot 2024-04-23 at 12 48 22 PM" src="https://github.com/wahyuhiddayat/advprog-module8-publisher/assets/119432989/010cca40-c11f-4180-810f-ade556e06778">

***Try to Run the Publisher Again***

`Publisher` mengirim 5 event messages:

<img width="709" alt="Screenshot 2024-04-23 at 12 52 14 PM" src="https://github.com/wahyuhiddayat/advprog-module8-publisher/assets/119432989/9461f7c9-c2db-4d1d-979d-083a177933d9">

Terminal dari `Publisher` ketika sedang dijalankan:

<img width="852" alt="Screenshot 2024-04-23 at 12 53 30 PM" src="https://github.com/wahyuhiddayat/advprog-module8-publisher/assets/119432989/87e553d8-a808-4839-b02d-38445661a23b">

Proses yang terjadi yaitu operasi dari publisher yang mengirim data melalui RabbitMQ dan subscriber yang menerima data tersebut. Publisher menghubungkan diri ke message server RabbitMQ lalu mengirim pesan ke exchange yang bertugas mendistribusikan pesan tersebut ke queue yang sesuai. Selanjutnya, subscriber menerima pesan dari queue ini. Output yang muncul di terminal subscriber menunjukkan pesan yang berhasil diambil, sedangkan terminal publisher menampilkan hasil dari eksekusi programnya.

