Proyek ini merupakan implementasi RESTful API sederhana menggunakan Express.js dan PostgreSQL untuk melakukan pengelolaan data mahasiswa.
Fungsi utamanya mencakup operasi CRUD (Create, Read, Update, Delete), dan seluruh endpoint diuji menggunakan Postman.

A. Fitur Utama
  | Method | Endpoint            | Keterangan                                |
  | ------ | ------------------- | ----------------------------------------- |
  | GET    | `/api/students`     | Mengambil semua data mahasiswa            |
  | GET    | `/api/students/:id` | Mengambil data mahasiswa berdasarkan ID   |
  | POST   | `/api/students`     | Menambahkan mahasiswa baru                |
  | PUT    | `/api/students/:id` | Memperbarui data mahasiswa berdasarkan ID |
  | DELETE | `/api/students/:id` | Menghapus data mahasiswa                  |

B. Teknologi yang Digunakan
  - Node.js (versi 18)
  - PostgreSQL (versi 14)
  - Visual Studio Code (VS Code)
  - Postman
  - Git & GitHub

C. Persiapan Database
  Sebelum menjalankan server, buat terlebih dahulu database di PostgreSQL:
  ```sql
  CREATE DATABASE kampus;
  
  \c kampus;
  
  CREATE TABLE students (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    major VARCHAR(50),
    age INT
  );
  ```

D. Cara Menjalankan Project
  1. Clone Repository
    ```bash
    git clone https://github.com/USERNAME/api_express_pg.git
    cd api_express_pg
    ```
  2. Install Dependencies
    ```bash
    npm install
    ```
  3. Buat File `.env`
    Isi file `.env` dengan konfigurasi berikut:
    ```bash
    PORT=5000
    DB_HOST=localhost
    DB_USER=postgres
    DB_PASS=your_password
    DB_NAME=kampus
    DB_PORT=5432
    ```
  
  4. Jalankan Server
    ```bash
    npm start
    ```
    Server akan berjalan di:
    `http://localhost:5000`

E. Struktur Folder Proyek
```
api_express_pg/
├── node_modules/
│
├── src/
│   ├── config/
│   │   └── db.js
│   ├── controllers/
│   │   └── studentsController.js
│   ├── models/
│   │   └── studentsModel.js
│   ├── routes/
│   │   └── studentsRoutes.js
│   └── server.js
│
├── .env
├── .gitignore
├── package.json
├── package-lock.json
└── README.md
```

F. Pengujian Menggunakan Postman
  1. Jalankan server dengan perintah `npm start`.
  2. Buka Postman.
  3. Uji semua endpoint berikut:
     
    ```
    GET     http://localhost:5000/api/students
    GET     http://localhost:5000/api/students/:id
    POST    http://localhost:5000/api/students
    PUT     http://localhost:5000/api/students/:id
    DELETE  http://localhost:5000/api/students/:id
    ```




