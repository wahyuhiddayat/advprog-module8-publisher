***1. How many data your publlsher program will send to the message broker in one run?***

Program publisher yang tertera dalam kode akan mengirim lima buah data ke message broker dalam satu kali eksekusi. Data tersebut adalah instance dari `UserCreatedEventMessage` yang masing-masing memiliki atribut `user_id` dan `user_name`. Pada fungsi `main`, ada lima pemanggilan fungsi `publish_event` yang setiap kali memanggilnya, akan mengirimkan satu event baru ke message broker.

***2. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?***

URL "amqp://guest:guest@localhost:5672" yang digunakan baik pada program publisher maupun subscriber menunjukkan bahwa kedua program tersebut terhubung ke message broker yang sama. Komponen URL ini terdiri dari beberapa bagian:
- **amqp://** adalah skema yang digunakan, menandakan bahwa koneksi menggunakan protokol AMQP (Advanced Message Queuing Protocol), yang umum digunakan untuk komunikasi antar aplikasi melalui message broker.
- **guest:guest** adalah username dan password yang digunakan untuk autentikasi ke server AMQP. Dalam konteks pengembangan, biasanya ini adalah credential default yang tidak disarankan untuk produksi.
- **localhost:5672** menunjukkan bahwa message broker berjalan pada host lokal (mesin yang sama dengan program yang berjalan) dan mendengarkan pada port 5672.

Jadi, URL yang sama pada program publisher dan subscriber mengindikasikan bahwa mereka berinteraksi dengan exchange yang sama di dalam broker untuk mengirim dan menerima pesan.