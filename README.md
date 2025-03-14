PENJELASAN
# Tugas4_adinda
import java.util.ArrayList; // Mengimpor ArrayList dari perpustakaan Java untuk membuat daftar tugas.
import java.util.Scanner; // Mengimpor Scanner dari perpustakaan Java untuk membaca input pengguna.

public class TodoListApp { // Membuat kelas bernama TodoListApp yang akan menyimpan daftar tugas.
private ArrayList<String> todoList; // Membuat variabel todoList sebagai daftar tugas menggunakan ArrayList.
public TodoListApp() { // Konstruktor untuk kelas TodoListApp.
todoList = new ArrayList<>(); // Menginisialisasi variabel todoList sebagai daftar tugas baru.
    }
public void addTask(String task) { // Metode untuk menambahkan tugas baru ke dalam daftar.
todoList.add(task); // Menambahkan tugas yang diberikan ke dalam todoList.
System.out.println("Task added successfully!"); // Menampilkan pesan bahwa tugas berhasil ditambahkan.
    }
public void removeTask(String task) { // Metode untuk menghapus tugas berdasarkan nama.
if (todoList.remove(task)) { // Jika tugas ditemukan dalam daftar dan dihapus...
System.out.println("Task removed successfully!"); // Menampilkan pesan bahwa tugas berhasil dihapus.
    } else { // Jika tugas tidak ditemukan dalam daftar...
System.out.println("Task not found!"); // Menampilkan pesan bahwa tugas tidak ditemukan.
        }
    }
public void removeTaskByIndex(int index) { // Metode untuk menghapus tugas berdasarkan posisi indeks.
if (index >= 0 && index < todoList.size()) { // Jika indeks valid (dalam rentang daftar)...
todoList.remove(index); // Menghapus tugas pada indeks yang diberikan.
System.out.println("Task removed successfully!"); // Menampilkan pesan bahwa tugas berhasil dihapus.
    } else { // Jika indeks tidak valid (di luar rentang daftar)...
System.out.println("Invalid index!"); // Menampilkan pesan bahwa indeks tidak valid.
        }
    }
public void searchTask(String task) { // Metode untuk mencari tugas berdasarkan nama.
if (todoList.contains(task)) { // Jika tugas ditemukan dalam daftar...
System.out.println("Task found: " + task); // Menampilkan pesan bahwa tugas ditemukan.
} else { // Jika tugas tidak ditemukan dalam daftar...
System.out.println("Task not found!"); // Menampilkan pesan bahwa tugas tidak ditemukan.
        }
    }
public void displayTasks() { // Metode untuk menampilkan semua tugas dalam daftar.
if (todoList.isEmpty()) { // Jika daftar tugas kosong...
System.out.println("No tasks in the list."); // Menampilkan pesan bahwa tidak ada tugas.
} else { // Jika daftar tugas tidak kosong...
System.out.println("To-Do List:"); // Menampilkan judul daftar tugas.
for (int i = 0; i < todoList.size(); i++) { // Loop melalui setiap tugas dalam daftar...
System.out.println((i + 1) + ". " + todoList.get(i)); // Menampilkan nomor tugas dan nama tugas.
            }
        }
    }
public static void main(String[] args) { // Metode utama yang dijalankan saat program dimulai.
TodoListApp app = new TodoListApp(); // Membuat objek TodoListApp baru.
Scanner scanner = new Scanner(System.in); // Membuat objek Scanner untuk membaca input pengguna.
boolean running = true; // Variabel untuk menjaga aplikasi tetap berjalan.

        while (running) { // Loop utama aplikasi, berjalan terus selama running bernilai true.
            System.out.println("\nTo-Do List Application"); // Menampilkan judul aplikasi.
            System.out.println("1. Add Task"); // Menampilkan opsi untuk menambahkan tugas.
            System.out.println("2. Remove Task By Task Name"); // Menampilkan opsi untuk menghapus tugas berdasarkan nama.
            System.out.println("3. Remove Task By Index"); // Menampilkan opsi untuk menghapus tugas berdasarkan indeks.
            System.out.println("4. Search Task By Task Name"); // Menampilkan opsi untuk mencari tugas berdasarkan nama.
            System.out.println("5. Display Tasks"); // Menampilkan opsi untuk menampilkan semua tugas.
            System.out.println("6. Exit"); // Menampilkan opsi untuk keluar dari aplikasi.
            System.out.print("Enter your choice: "); // Meminta pengguna untuk memasukkan pilihan mereka.
            int choice = scanner.nextInt(); // Membaca pilihan pengguna sebagai angka.
            scanner.nextLine(); // Mengosongkan buffer input Scanner.

switch (choice) { // Memproses pilihan pengguna dengan pernyataan switch.

case 1: // Kasus untuk pilihan 1: Tambah tugas.
System.out.print("Enter task to add: "); // Meminta pengguna untuk memasukkan tugas yang ingin ditambahkan.
String taskToAdd = scanner.nextLine(); // Membaca tugas yang dimasukkan pengguna.
app.addTask(taskToAdd); // Menambahkan tugas ke dalam aplikasi.
break; // Mengakhiri kasus 1.


case 2: // Kasus untuk pilihan 2: Hapus tugas berdasarkan nama.
System.out.print("Enter task to remove: "); // Meminta pengguna untuk memasukkan tugas yang ingin dihapus.
String taskToRemove = scanner.nextLine(); // Membaca tugas yang dimasukkan pengguna.
app.removeTask(taskToRemove); // Menghapus tugas dari aplikasi.
break; // Mengakhiri kasus 2.

                
case 3: // Kasus untuk pilihan 3: Hapus tugas berdasarkan indeks.
System.out.print("Enter index to remove: "); // Meminta pengguna untuk memasukkan indeks tugas yang ingin dihapus.
int indexToRemove = scanner.nextInt(); // Membaca indeks yang dimasukkan pengguna.
app.removeTaskByIndex(indexToRemove - 1); // Menghapus tugas berdasarkan indeks (dikurangi 1 untuk indeks yang dimulai dari 0).
break; // Mengakhiri kasus 3.

                
case 4: // Kasus untuk pilihan 4: Cari tugas berdasarkan nama.
System.out.print("Enter task to search: "); // Meminta pengguna untuk memasukkan tugas yang ingin dicari.
String taskToSearch = scanner.nextLine(); // Membaca tugas yang dimasukkan pengguna.
app.searchTask(taskToSearch); // Mencari tugas dalam aplikasi.
break; // Mengakhiri kasus 4.


case 5: // Kasus untuk pilihan 5: Tampilkan semua tugas.
app.displayTasks(); // Menampilkan semua tugas dalam daftar.
break; // Mengakhiri kasus 5.

                
case 6: // Kasus untuk pilihan 6: Keluar dari aplikasi.
running = false; // Menghentikan loop dan keluar dari aplikasi.
System.out.println("Exiting the application..."); // Menampilkan pesan keluar aplikasi.
break; // Mengakhiri kasus 6.

                
default: // Kasus untuk pilihan yang tidak valid.
System.out.println("Invalid choice. Please try again."); // Menampilkan pesan pilihan tidak valid.
            }
        }
scanner.close(); // Menutup objek Scanner untuk membersihkan sumber daya.
    }
}


