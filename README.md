# *Analisis Web Aplication - Pyhton*



# 📍*Instalasi*
Langkah-langkah untuk menjalankan kode pada terminal pada Windows.

### **1. Clone Repository**
```bash
git clone https://github.com/leevydanomalik/python-sqlite.git
```
![image](https://github.com/user-attachments/assets/53444eb4-87ea-4845-9756-8534257d036c)
<br>

### **2. Membuka code pada Visual Code**
```bash
code .td
```
![image](https://github.com/user-attachments/assets/37433b2d-1edb-4f88-a30d-dc73fedc0859)
<br>

### **3. Buat Virtual Environment**
```bash
python -m venv .venv
```
![image](https://github.com/user-attachments/assets/b994df12-0ae4-4cf5-900e-75d338f644d6)
<br>

### **4. Aktifkan Virtual Environment**
```bash
.venv\Scripts\activate
```
![image](https://github.com/user-attachments/assets/df585e47-c8d6-40a5-9a18-6e1b6d6ffdcf)
<br>

### **5. Instal Dependensi**
```bash
pip install flask flask_sqlalchemy
```
![image](https://github.com/user-attachments/assets/3b5ac9ff-142f-498b-853f-0f77bcb86716)
<br>

### **7. Jalankan Aplikasi**
```bash
python app.py
```
![image](https://github.com/user-attachments/assets/fee42b31-7329-41e8-b810-788455758175)
<br>

---

# 📍*Treacing dan Analisis code*
Dalam Program yang diuji terdapat 5 Web Page atau bisa di sebut halaman individu yaitu *`index.html`*, *`login.html`*, *`index.html`*, *`student.html`*, *`edit.html`*, dan *`Criate_user.html`*. yang nantinya Web Site akan Route ke Dalam aplikasi berbasis Flask atau framework lain, Berikut adalah tampilan dari Web Site yang sedang diuji
- *`index.html`*
  Web page ini menampilkan Halaman Awal atau pusat yang nantinya akan Route ke halaman yang lain.
  
  ![image](https://github.com/user-attachments/assets/d600abb7-349c-414f-99e0-35dd7860988d)
<br>

- *`login.html`*
  Halaman ini adalah routes untuk Login user jika user sudah memiliki account
  
  ![image](https://github.com/user-attachments/assets/86ba268d-7827-41b2-98b4-c793dd553a11)
<br>

- *`student.html`*
  Halaman ini adalah routes dashboard manajemen data siswa yang memungkinkan user untuk menambahkan, mengedit, dan menghapus data siswa.
  
  ![image](https://github.com/user-attachments/assets/b0ce1713-1e8e-479d-ad2c-73ed64ebedc1)
<br>

- *`edit.html`*
  Halaman ini adalah routes formulir edit data siswa, yang memungkinkan user untuk memperbarui informasi siswa yang sudah ada.
  
  ![image](https://github.com/user-attachments/assets/1f8cc1f4-6d42-4395-9b9a-56b42b11265b)
<br>

- *`Criate_user.html`*
  Halaman ini adalah routes formulir pembuatan user baru yang memungkinkan user untuk mendaftarkan akun baru.
  
  ![image](https://github.com/user-attachments/assets/bd6cdf7c-eaac-4e06-b4b4-bce547abf1f7)
<br>

##  ❔*Bagaimana bisa Web page ini berinteraksi dengan program yang lainnya?*
pertama kita fokus pada program utama yaitu *`indeks.html`* karena web page ini adalah halaman utama yang di lihat oleh user selain itu juga halaman ini akan terhubung atau bisa di sebut Routes terhadap halaman halaman lain seperti *`login.html`*, *`index.html`*, *`student.html`*, *`edit.html`*, dan *`Criate_user.html`*.

Baik! Saya akan melakukan **tracing per blok kode** untuk memahami bagaimana setiap bagian bekerja dan ke mana arah navigasinya.


## **Tracing `index.html` Per Blok Kode**  


### **1. Struktur Dasar HTML (`<!DOCTYPE html>` - `</head>`)**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Welcome to Student Management System</title>
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css">
```
#### **Analisis:**
- **`<!DOCTYPE html>`** → Menandakan ini adalah dokumen HTML5.
- **`<html lang="en">`** → Mengatur bahasa utama ke bahasa Inggris.
- **`<meta charset="UTF-8">`** → Memastikan karakter yang digunakan sesuai UTF-8.
- **`<meta name="viewport" content="width=device-width, initial-scale=1.0">`** → Membuat tampilan responsif untuk berbagai perangkat.
- **`<title>`** → Judul halaman yang muncul di tab browser.
- **Bootstrap CSS** (`<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css">`) → Menggunakan Bootstrap versi 4.5.2 untuk styling.

### **2. CSS Internal**
```html
<style>
    body {
        background-color: #f8f9fa;
    }
    .hero {
        background-color: #007bff;
        color: white;
        padding: 50px 20px;
        text-align: center;
    }
    .hero h1 {
        font-size: 3rem;
    }
    .hero p {
        font-size: 1.2rem;
    }
    .cta-buttons {
        margin-top: 20px;
    }
</style>
```
#### **Analisis:**
- **`body`** → Warna latar belakang dibuat abu-abu terang `#f8f9fa`.
- **`.hero`** → Bagian utama yang memiliki:
  - Latar belakang biru (`#007bff`).
  - Teks putih (`color: white`).
  - Padding 50px atas & bawah, 20px kiri & kanan.
  - Teks rata tengah (`text-align: center`).
- **`.hero h1`** → Mengatur ukuran heading utama (`3rem`).
- **`.hero p`** → Mengatur ukuran teks paragraf (`1.2rem`).
- **`.cta-buttons`** → Mengatur margin atas 20px untuk tombol Call-To-Action.

### **3. Hero Section (Bagian Header Halaman)**
```html
<body>
    <div class="hero">
        <h1>Welcome to the Student Management System</h1>
        <p>Effortlessly manage your students' data with our simple and intuitive platform.</p>
        <div class="cta-buttons">
            <a href="/login" class="btn btn-light btn-lg mr-2">Login</a>
            <a href="/users/create" class="btn btn-outline-light btn-lg mr-2">Register</a>
            <a href="/students" class="btn btn-outline-light btn-lg">Students DB</a>
        </div>
    </div>
```
#### **Analisis:**
- **Judul (`<h1>Welcome to the Student Management System</h1>`)** → Menampilkan teks utama halaman.
- **Deskripsi (`<p>...</p>`)** → Memberikan gambaran singkat tentang sistem.
- **Navigasi dengan Tiga Tombol (`<a>`):**
  1. **`<a href="/login">`** → Mengarahkan pengguna ke halaman login.
  2. **`<a href="/users/create">`** → Mengarahkan pengguna ke halaman registrasi.
  3. **`<a href="/students">`** → Mengarahkan pengguna ke halaman database mahasiswa.

 **Tracing Navigasi:**
- Jika ini berbasis backend, halaman `/login`, `/users/create`, dan `/students` kemungkinan di-handle oleh sistem routing.
- Perlu dicek apakah ini diatur melalui framework seperti Flask (`app.route()`), Express.js (`app.get()`), atau Laravel (`Route::get()`).


### **4. Bagian "Why Choose Us?"**
```html
<div class="container mt-5">
    <h2>Why Choose Us?</h2>
    <p>
        Our system helps you to efficiently manage student records, including adding, editing, and deleting student details.
        With secure login and user management, your data is always protected. Join us today to experience seamless data management!
    </p>
    <hr>
    <h3>Features:</h3>
    <ul>
        <li>Secure Login and User Authentication</li>
        <li>Easy Student Record Management</li>
        <li>Responsive and Intuitive Design</li>
        <li>Free and Open Source</li>
    </ul>
</div>
```
#### **Analisis:**
- **Judul `Why Choose Us?`** → Menampilkan alasan mengapa pengguna harus memilih sistem ini.
- **Paragraf Deskripsi** → Menjelaskan keunggulan sistem.
- **Fitur Utama (`<ul>` - `<li>`)**:
  1. **Secure Login** → Berarti ada sistem autentikasi.
  2. **Student Record Management** → Kemungkinan ada fitur CRUD (Create, Read, Update, Delete) untuk mahasiswa.
  3. **Responsive Design** → Menggunakan Bootstrap agar tampilannya fleksibel.
  4. **Open Source** → Kemungkinan bisa diakses dan dikembangkan oleh publik.

 **Tracing Navigasi:**
- Perlu dicek apakah fitur CRUD ada di `/students` atau halaman lain.
- "Secure Login" menegaskan pentingnya mengecek bagaimana autentikasi ditangani di `/login`.

### **5. Footer**
```html
<footer class="text-center mt-5 py-3 bg-light">
    <p>© 2024 Student Management System. All rights reserved.</p>
</footer>
</body>
</html>
```
#### **Analisis:**
- **Footer (`<footer>`)** → Ditampilkan di bagian bawah halaman.
- **Teks Hak Cipta (`<p>© 2024 Student Management System. All rights reserved.</p>`)** → Menyatakan bahwa sistem ini dibuat pada tahun 2024.

## **Kesimpulan dan Arah Tracing Selanjutnya**
 **Navigasi Utama yang Harus Ditrace Lebih Lanjut:**
1. **`/login`** → Butuh file `login.html` atau backend handler untuk login.
2. **`/users/create`** → Butuh file `register.html` atau backend untuk registrasi user.
3. **`/students`** → Harus dicek apakah ini halaman daftar mahasiswa atau API yang mengembalikan data.

 **Hal yang Perlu Dicek di Backend:**
- Apakah autentikasi pengguna menggunakan session atau token-based authentication (JWT)?
- Bagaimana data mahasiswa dikelola di `/students`?
- Apakah ada middleware untuk membatasi akses halaman hanya bagi pengguna yang login?

---

##  ❔*Bagaimana cara kerja program code agar bisa menciptakan web application ini?*
Program ini adalah aplikasi web berbasis **Flask** dengan fitur **autentikasi pengguna** dan **CRUD data mahasiswa** menggunakan database **SQLite**.:  


### **1. Inisialisasi Aplikasi**
- **Flask** digunakan sebagai framework backend.  
- **Flask-SQLAlchemy** digunakan untuk mengelola database.  
- **HTTPBasicAuth** digunakan untuk autentikasi.  
- **Werkzeug security** digunakan untuk hashing dan verifikasi password.  
- `app.secret_key` digunakan untuk menyimpan session secara aman.  

Saat aplikasi pertama kali dijalankan (`python app.py`), program akan:  
1. **Membuat objek Flask (`app`)** dan mengatur konfigurasi database SQLite.  
2. **Inisialisasi database** dengan `db = SQLAlchemy(app)`.  
3. **Membuat tabel database jika belum ada** melalui `db.create_all()` dalam blok `if __name__ == '__main__'`.  
4. **Membuat user admin default** dengan username `admin` dan password `admin123`, jika belum ada di database.  

---

### **2. Struktur Database**
Program memiliki dua tabel utama:  
- **User** (untuk autentikasi)  
- **Student** (untuk menyimpan data mahasiswa)  

#### **User Model**
- Menyimpan `username` dan `password_hash` (bukan password asli, untuk keamanan).  
- Memiliki metode `set_password()` untuk hashing password saat registrasi.  
- Metode `check_password()` untuk verifikasi login.  

#### **Student Model**
- Menyimpan data mahasiswa (`id`, `name`, `age`, `grade`).  

---

### **3. Alur Proses Program**
**1. User Mengakses Halaman Utama**  
- Route `/` akan menampilkan halaman `index.html`.  

**2. User Login (`/login`)**  
- Jika metode **GET**, halaman login akan ditampilkan.  
- Jika metode **POST**, program akan:  
  - Mengambil `username` & `password` dari form.  
  - Mencari username di database.  
  - Jika username & password cocok, user **berhasil login** → **Session disimpan** (`session['user_id']` & `session['username']`).  
  - Jika gagal, pesan error ditampilkan.  

**3. Mengakses Data Mahasiswa (`/students`)**  
- Jika user belum login → redirect ke `/login`.  
- Jika sudah login → data mahasiswa ditampilkan.  

**4. Menambahkan Mahasiswa (`/add`)**  
- **User harus login** terlebih dahulu.  
- Data diambil dari form (`name`, `age`, `grade`).  
- Data baru ditambahkan ke database.  
- Redirect ke halaman `/students`.  

**5. Mengedit Data Mahasiswa (`/edit/<id>`)**  
- **User harus login** terlebih dahulu.  
- Jika **GET**, halaman edit akan ditampilkan dengan data mahasiswa berdasarkan `id`.  
- Jika **POST**, data diperbarui di database, lalu redirect ke `/students`.  

**6. Menghapus Mahasiswa (`/delete/<id>`)**  
- **User harus login** terlebih dahulu.  
- Mahasiswa dihapus dari database berdasarkan `id`.  
- Redirect ke `/students`.  

**7. Logout (`/logout`)**  
- Session dihapus (`session.clear()`).  
- Redirect ke halaman utama `/`.  

**8. Membuat Akun Baru (`/users/create`)**  
- Jika metode **GET**, halaman registrasi ditampilkan.  
- Jika metode **POST**, program akan:  
  - Memeriksa apakah username sudah ada.  
  - Jika belum ada, membuat user baru dengan **hashed password** dan menyimpannya di database.  
  - Redirect ke halaman utama `/`.  

---

### **4. Cara Kerja Secara Keseluruhan**
1. **Saat program dijalankan (`python app.py`)**  
   - Flask server dimulai (`app.run(host='0.0.0.0', port=8000, debug=True)`).  
   - Database dibuat (jika belum ada).  
   - User default `admin` dibuat (jika belum ada).  

2. **User mengakses halaman (`/`)**  
   - Tampil halaman utama (`index.html`).  

3. **User login (`/login`)**  
   - Jika sukses → disimpan di session, lalu redirect ke `/students`.  
   - Jika gagal → kembali ke halaman login dengan pesan error.  

4. **User mengakses halaman daftar mahasiswa (`/students`)**  
   - Jika sudah login → semua mahasiswa ditampilkan.  
   - Jika belum login → redirect ke `/login`.  

5. **User menambahkan, mengedit, atau menghapus mahasiswa**  
   - Harus dalam kondisi login.  
   - Data akan diperbarui di database.  

6. **User logout (`/logout`)**  
   - Session dihapus.  
   - Redirect ke halaman utama `/`.  

---

##  ❔*Bagaimana cara kerja program code agar bisa menciptakan web application ini?*
Analisis dan tracing kode program Flask ini:

## **1. Import Library**
```python
from flask import Flask, render_template, request, redirect, url_for, session, flash
from flask_sqlalchemy import SQLAlchemy
from sqlalchemy import text
from flask_httpauth import HTTPBasicAuth
from werkzeug.security import generate_password_hash, check_password_hash
```
- **Flask** → Framework untuk membangun aplikasi web.
- **render_template** → Untuk merender halaman HTML.
- **request** → Mengambil data dari formulir pengguna (input).
- **redirect, url_for** → Mengarahkan pengguna ke halaman lain.
- **session** → Menyimpan data sesi pengguna (misal: status login).
- **flash** → Menampilkan pesan notifikasi ke pengguna.
- **Flask_SQLAlchemy** → ORM untuk mengelola database menggunakan SQLAlchemy.
- **text** → Menjalankan query SQL secara langsung.
- **HTTPBasicAuth** → Untuk otentikasi dasar.
- **generate_password_hash, check_password_hash** → Mengenkripsi password dan memverifikasinya.


## **2. Inisialisasi Aplikasi dan Database**
```python
app = Flask(__name__)
app.secret_key = "your_secret_key"
app.config['SQLALCHEMY_DATABASE_URI'] = 'sqlite:///students.db'
app.config['SQLALCHEMY_TRACK_MODIFICATIONS'] = False
db = SQLAlchemy(app)
auth = HTTPBasicAuth()
```
- **app = Flask(__name__)** → Membuat instance aplikasi Flask.
- **app.secret_key** → Kunci untuk mengenkripsi sesi pengguna.
- **app.config['SQLALCHEMY_DATABASE_URI']** → Menggunakan SQLite sebagai database.
- **app.config['SQLALCHEMY_TRACK_MODIFICATIONS']** → Mencegah warning dari SQLAlchemy.
- **db = SQLAlchemy(app)** → Menghubungkan database ke aplikasi Flask.
- **auth = HTTPBasicAuth()** → Mengaktifkan otentikasi berbasis HTTP Basic.


## **3. Model User (Untuk Otentikasi)**
```python
class User(db.Model):
    id = db.Column(db.Integer, primary_key=True)
    username = db.Column(db.String(80), unique=True, nullable=False)
    password_hash = db.Column(db.String(128), nullable=False)

    def set_password(self, password):
        self.password_hash = generate_password_hash(password)

    def check_password(self, password):
        return check_password_hash(self.password_hash, password)
    
    def __repr__(self):
        return f'<User {self.username}>'
```
- **Membuat tabel User di database** dengan kolom:
  - `id` (Primary Key, tipe Integer)
  - `username` (String, unik, tidak boleh kosong)
  - `password_hash` (String, menyimpan hash password)
- **Fungsi `set_password`** → Mengubah password menjadi hash.
- **Fungsi `check_password`** → Mengecek apakah password yang dimasukkan cocok dengan hash.
- **Fungsi `__repr__`** → Untuk debugging (menampilkan objek User sebagai string).


## **4. Model Student (Menyimpan Data Siswa)**
```python
class Student(db.Model):
    id = db.Column(db.Integer, primary_key=True)
    name = db.Column(db.String(100), nullable=False)
    age = db.Column(db.Integer, nullable=False)
    grade = db.Column(db.String(10), nullable=False)

    def __repr__(self):
        return f'<Student {self.name}>'
```
- **Membuat tabel Student di database** dengan kolom:
  - `id` (Primary Key, tipe Integer)
  - `name` (String, wajib diisi)
  - `age` (Integer, wajib diisi)
  - `grade` (String, wajib diisi)
- **Fungsi `__repr__`** → Untuk debugging.


## **5. Otentikasi User**
```python
@auth.verify_password
def verify_password(username, password):
    user = User.query.filter_by(username=username).first()
    if user and user.check_password(password):
        return user
    return None
```
- **Mengecek username dan password** saat login.
- **Jika cocok**, user dikembalikan sebagai hasil otentikasi.
- **Jika tidak cocok**, mengembalikan `None`.

## **6. Route Login**
```python
@app.route('/login', methods=['GET', 'POST'])
def login():
    if request.method == 'POST':
        username = request.form['username']
        password = request.form['password']

        user = User.query.filter_by(username=username).first()
        if user and user.check_password(password):
            session['user_id'] = user.id
            session['username'] = user.username
            flash("Login successful!", "success")
            return redirect(url_for('student'))
        else:
            return render_template('login.html', error="Invalid username or password")
    
    return render_template('login.html')
```
- **Jika pengguna mengisi form (POST)**:
  - Mencari user berdasarkan username.
  - Memverifikasi password.
  - Jika benar, menyimpan `user_id` di sesi dan mengarahkan ke halaman `/students`.
  - Jika salah, menampilkan pesan error.
- **Jika hanya mengakses halaman (GET)**:
  - Merender halaman login.

## **7. Route Logout**
```python
@app.route('/logout')
def logout():
    session.clear()
    flash("Logged out successfully.", "info")
    return redirect(url_for('index'))
```
- **Menghapus sesi pengguna** agar keluar dari sistem.
- **Mengalihkan ke halaman utama (`index`)**.

## **8. Route Students**
```python
@app.route('/students')
def student():
    if 'user_id' not in session:
        flash("Please log in to access this page.", "warning")
        return redirect(url_for('login'))
    
    students = Student.query.all()
    return render_template('student.html', students=students)
```
- **Cek apakah user sudah login** (`'user_id' in session`).
- **Jika belum login**, diarahkan ke `/login`.
- **Jika sudah login**, menampilkan daftar siswa.

## **9. Route Menambahkan Student**
```python
@app.route('/add', methods=['POST'])
def add_student():
    if 'user_id' not in session:
        flash("Please log in to access this page.", "warning")
        return redirect(url_for('login'))
    
    name = request.form['name']
    age = request.form['age']
    grade = request.form['grade']
    new_student = Student(name=name, age=age, grade=grade)
    db.session.add(new_student)
    db.session.commit()
    flash("Student added successfully!", "success")
    return redirect(url_for('student'))
```
- **Hanya bisa diakses jika user login**.
- **Mengambil data dari form** dan menyimpannya ke database.
- **Menampilkan pesan sukses** dan mengalihkan ke halaman `/students`.


## **10. Route Menghapus Student**
```python
@app.route('/delete/<int:id>')
def delete_student(id):
    if 'user_id' not in session:
        flash("Please log in to access this page.", "warning")
        return redirect(url_for('login'))
    
    student = Student.query.get_or_404(id)
    db.session.delete(student)
    db.session.commit()
    flash("Student deleted successfully!", "success")
    return redirect(url_for('student'))
```
- **Cek login** sebelum menghapus data.
- **Hapus siswa berdasarkan ID**.
- **Menampilkan pesan sukses**.

## **11. Route Edit Student**
```python
@app.route('/edit/<int:id>', methods=['GET', 'POST'])
def edit_student(id):
    if 'user_id' not in session:
        flash("Please log in to access this page.", "warning")
        return redirect(url_for('login'))
    
    student = Student.query.get_or_404(id)
    if request.method == 'POST':
        student.name = request.form['name']
        student.age = request.form['age']
        student.grade = request.form['grade']
        db.session.commit()
        flash("Student updated successfully!", "success")
        return redirect(url_for('student'))
    
    return render_template('edit.html', student=student)
```
- **Menampilkan halaman edit** jika metode `GET`.
- **Memperbarui data siswa** jika metode `POST`.

## **12. Membuat User Baru**
```python
@app.route('/users/create', methods=['GET', 'POST'])
def create_user_form():
    if request.method == 'POST':
        username = request.form['username']
        password = request.form['password']
        
        if User.query.filter_by(username=username).first():
            return render_template('create_user.html', error="User already exists!")
        
        new_user = User(username=username)
        new_user.set_password(password)
        db.session.add(new_user)
        db.session.commit()
        flash("User created successfully!", "success")
        return redirect(url_for('index'))

    return render_template('create_user.html')
```
- **Membuat akun baru** dengan hash password.
- **Menampilkan error jika username sudah ada**.

##**13.Kode terakhir untuk menjalankan aplikasi Flask**:
```python
if __name__ == '__main__':
    with app.app_context():
        db.create_all()
        if not User.query.filter_by(username='admin').first():
            admin_user = User(username='admin')
            admin_user.set_password('admin123')
            db.session.add(admin_user)
            db.session.commit()
    app.run(host='0.0.0.0', port=8000, debug=True)
```

---

## *Diagram*

- Class Diagram
  *Class diagram ini masih dalam proses pembangunan belum benar 100%. proses pengerjaan class diagram masih di angka 60% 🛠️*
![image](https://github.com/user-attachments/assets/05607c29-afb0-485a-a844-2f9c0a4bbc6e)

  
- Sequence Diagram
![image](https://github.com/user-attachments/assets/7d3f16de-cfd6-4ec0-8fac-07d13c7e63f9)
<br>
## **Penjelasan Sequence Diagram**

Sequence diagram ini menggambarkan alur interaksi antara pengguna (*User*), sistem berbasis Flask (*Boundary*), pengendali logika bisnis (*Control*), dan basis data (*Entity*). Diagram ini menunjukkan bagaimana proses login, pengambilan data siswa, penambahan siswa, dan penghapusan siswa dilakukan dalam sistem.

### **Komponen dalam Sequence Diagram**
1. **User** → Pengguna yang berinteraksi dengan sistem melalui antarmuka web.
2. **Boundary (Flask Route)** → Endpoint API yang menangani permintaan dari pengguna.
3. **Control (Flask Handler)** → Fungsi di dalam Flask yang memproses logika bisnis.
4. **Entity (SQLAlchemy Model)** → Objek yang merepresentasikan tabel dalam database.

### **Alur Proses yang Ditampilkan**
1. **Proses Login**  
   - Pengguna mengirimkan kredensial login.
   - Sistem mencari user dalam database.
   - Jika password cocok, sesi user disimpan, dan diarahkan ke halaman daftar siswa.
   - Jika salah, sistem menampilkan pesan error.

2. **Pengambilan Data Siswa**  
   - Pengguna meminta halaman daftar siswa.
   - Sistem mengecek apakah user sudah login.
   - Jika sudah, sistem mengambil data siswa dari database dan menampilkannya.
   - Jika belum, pengguna diarahkan ke halaman login.

3. **Penambahan Siswa Baru**  
   - Pengguna mengisi formulir untuk menambahkan siswa baru.
   - Sistem memeriksa status login pengguna.
   - Jika login, data siswa disimpan ke dalam database dan halaman diperbarui.
   - Jika tidak, pengguna diarahkan ke halaman login.

4. **Penghapusan Data Siswa**  
   - Pengguna memilih siswa yang akan dihapus.
   - Sistem mengecek status login pengguna.
   - Jika sudah login, data siswa dihapus dari database.
   - Setelah berhasil, pengguna diarahkan kembali ke halaman daftar siswa.
   - Jika tidak, sistem mengarahkan ke halaman login.

---

- Use Case Diagram
  Pada use case diagram ini menunjukan bahwa pada program yang di uji semua user bisa menggunakan semua fitur yang ada
![Untitled Diagram](https://github.com/user-attachments/assets/07544d3a-2fa5-461e-a249-1fdbb067d149)


---
