# *Analisis Web Aplication - Pyhton*



## *Instalasi*
Langkah-langkah untuk menjalankan kode pada terminal pada Windows.

### **1. Clone Repository**
```bash
git clone https://github.com/leevydanomalik/python-sqlite.git
```
![image](https://github.com/user-attachments/assets/53444eb4-87ea-4845-9756-8534257d036c)

### **2. Membuka code pada Visual Code**
```bash
code .td
```
![image](https://github.com/user-attachments/assets/37433b2d-1edb-4f88-a30d-dc73fedc0859)

### **3. Buat Virtual Environment**
```bash
python -m venv .venv
```
![image](https://github.com/user-attachments/assets/b994df12-0ae4-4cf5-900e-75d338f644d6)


### **4. Aktifkan Virtual Environment**
```bash
.venv\Scripts\activate
```
![image](https://github.com/user-attachments/assets/df585e47-c8d6-40a5-9a18-6e1b6d6ffdcf)

### **5. Instal Dependensi**
```bash
pip install flask flask_sqlalchemy
```
![image](https://github.com/user-attachments/assets/3b5ac9ff-142f-498b-853f-0f77bcb86716)

### **7. Jalankan Aplikasi**
```bash
python app.py
```
![image](https://github.com/user-attachments/assets/fee42b31-7329-41e8-b810-788455758175)

## *Treacing dan Analisis code*
Dalam Program yang diuji terdapat 5 Web Page atau bisa di sebut halaman individu yaitu *`index.html`*, *`login.html`*, *`index.html`*, *`student.html`*, *`edit.html`*, dan *`Criate_user.html`*. yang nantinya Web Site akan Route ke Dalam aplikasi berbasis Flask atau framework lain, Berikut adalah tampilan dari Web Site yang sedang diuji
- *`index.html`*
  Web page ini menampilkan Halaman Awal atau pusat yang nantinya akan Route ke halaman yang lain.
  ![image](https://github.com/user-attachments/assets/d600abb7-349c-414f-99e0-35dd7860988d)

- *`login.html`*
  Halaman ini adalah routes untuk Login user jika user sudah memiliki account 
  ![image](https://github.com/user-attachments/assets/86ba268d-7827-41b2-98b4-c793dd553a11)

- *`student.html`*
  Halaman ini adalah routes dashboard manajemen data siswa yang memungkinkan user untuk menambahkan, mengedit, dan menghapus data siswa.
  ![image](https://github.com/user-attachments/assets/b0ce1713-1e8e-479d-ad2c-73ed64ebedc1)

- *`edit.html`*
  Halaman ini adalah routes formulir edit data siswa, yang memungkinkan user untuk memperbarui informasi siswa yang sudah ada.
  ![image](https://github.com/user-attachments/assets/1f8cc1f4-6d42-4395-9b9a-56b42b11265b)

- *`Criate_user.html`*
  Halaman ini adalah routes formulir pembuatan user baru yang memungkinkan user untuk mendaftarkan akun baru.
  ![image](https://github.com/user-attachments/assets/bd6cdf7c-eaac-4e06-b4b4-bce547abf1f7)

---


## *Diagram*

- Class Diagram
- Sequence Diagram
- Use Case Diagram


---


Langkah-langkah untuk menjalankan kode ini di terminal Windows sedikit berbeda karena perbedaan dalam perintah aktivasi virtual environment. Berikut adalah cara yang benar:

### **1. Clone Repository (Jika Diperlukan)**
Jika belum memiliki proyeknya, kloning repositori terlebih dahulu:  
```bash
git clone <repository-url>
cd project_folder
```

### **2. Buat Virtual Environment**
Di Windows, gunakan perintah berikut untuk membuat virtual environment:
```bash
python -m venv .venv
```

### **3. Aktifkan Virtual Environment**
Di Windows, aktivasi virtual environment dilakukan dengan perintah berikut:

- **Command Prompt (CMD):**
  ```bash
  .venv\Scripts\activate
  ```

- **PowerShell:**
  ```powershell
  .venv\Scripts\Activate.ps1
  ```

  > ⚠ Jika mendapatkan error terkait eksekusi script, jalankan:
  ```powershell
  Set-ExecutionPolicy Unrestricted -Scope Process
  ```

### **4. Instal Dependensi**
Setelah virtual environment aktif, install dependensi:
```bash
pip install flask flask_sqlalchemy
```

### **5. Jalankan Aplikasi**
```bash
python app.py
```

### **6. Akses Aplikasi**
Buka browser dan akses:
```
http://127.0.0.1:5000
```

Dengan cara ini, aplikasi Flask akan berjalan dengan benar di Windows. 🚀
