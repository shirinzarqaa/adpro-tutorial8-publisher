**a. How many data your publisher program will send to the message broker in one run?**

program publisher akan mengirim 5 pesan ke pesan broker karena dalam satu kali run terdapat 5 pemanggilan ke `publish_event method` yang dimana terdapat `UserCreatedEventMessage` di fungsi main.

**b. The url of: `amqp://guest:guest@localhost:5672` is the same as in the subscriber program, what does it mean?**

Hal ini berarti program subscriber dan publisher terkoneksi dengan message broker yang sama dan URL ini digunakan untuk membuat queue publisher yang baru.

**Screen of running RabbitMQ**
![RabbitMQ](image.png)

**Screenshot terminal subscriber yang telah berhasil menerima 5 even message**
![alt text](image-2.png)
**Screenshot terminal publisher yang telah berhasil menjalankan `cargo run` untuk mengirim 5 event**
![alt text](image-1.png)

**Screenshot interface RbbitMQ dimana ada spike pada message rates karena publisher di run berkali-kali**
![alt text](image-3.png)

**hal-hal yan perlu di improve dari kode tersebut.**
- Duplikasi kode pada metode publish_event yang di panggil beberapa kali sehingga bisa diganti dengan suatu fungsi atau loop.
- metode get_handler_action yang belum di implementasikan.
