# UTS-NO-10
Jawaban UTS NO 10
todo = {
    "Belajar Python": "belum",
    "Cuci baju": "selesai"
}

def tampilkan_tugas(status_filter=None):
    print("\n--- Daftar Tugas ---")
    for tugas, status in todo.items():
        if status_filter is None or status == status_filter:
            print(f"- {tugas} [{status}]")
    print()

def tambah_tugas():
    tugas_baru = input("Masukkan nama tugas baru: ")
    if tugas_baru in todo:
        print("Tugas sudah ada!")
    else:
        todo[tugas_baru] = "belum"
        print("Tugas ditambahkan.")

def ubah_status():
    tugas = input("Masukkan nama tugas yang ingin diubah statusnya: ")
    if tugas in todo:
        status_baru = input("Masukkan status baru (belum/selesai): ").lower()
        if status_baru in ["belum", "selesai"]:
            todo[tugas] = status_baru
            print("Status tugas diperbarui.")
        else:
            print("Status tidak valid.")
    else:
        print("Tugas tidak ditemukan.")

while True:
    print("\n==== To-Do List ====")
    print("1. Tampilkan semua tugas")
    print("2. Tampilkan tugas 'belum'")
    print("3. Tampilkan tugas 'selesai'")
    print("4. Tambah tugas")
    print("5. Ubah status tugas")
    print("6. Keluar")

    pilihan = input("Pilih menu (1-6): ")

    if pilihan == "1":
        tampilkan_tugas()
    elif pilihan == "2":
        tampilkan_tugas("belum")
    elif pilihan == "3":
        tampilkan_tugas("selesai")
    elif pilihan == "4":
        tambah_tugas()
    elif pilihan == "5":
        ubah_status()
    elif pilihan == "6":
        print("Terima kasih! Sampai jumpa.")
        break
    else:
        print("Pilihan tidak valid.")
