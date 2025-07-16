import random

def lOWER():
    exercises = {
        "thigh": ["Front Squat", "Lunges", "Step Up", "Leg Extension", "Lunge Back Kick", "Cross Jack", "Gate Swing", "Frog Jump"],
        "calf": ["Calf Raise", "Inward Calf Raise", "Squat to Raised Heel", "Single-Leg Calf Raise", "Jumping Jacks", "Butt Kicks", "Lunges", "Skipping"]
    }
    while True:
        print("LOWER BODY")
        print("Bagian Tubuh Mana Yang Ingin Dilatih? (thigh/calf)")
        lowerbody = input().lower()
        if lowerbody in exercises:
            print(f"Berikut Beberapa Olahraga Untuk Membentuk Otot {lowerbody.capitalize()}:")
            for exercise in exercises[lowerbody]:
                print(exercise)
            break
        else:
            print("Bagian tubuh tidak ditemukan, silakan pilih kembali.")

def uPPER():
    exercises = {
        "chest": ["Cable Cross", "Incline Dumbbell Bench Press", "Push Up", "Weighted Push Up", "Plyometric Push Up", "Chair Dips", "Pull Up", "Flat Bench Press"],
        "arms": ["Push Up", "Bear Crawls", "Plank Press", "Biceps Curls", "Monkey Arms", "Pom-Pom Circle", "Shoulder Press", "Triceps Extension"],
        "abs": ["Bent Over Rows", "Bicycle Crunch", "Hanging Leg Raises", "Crunch", "Deadlift", "Fitness Ball Rollouts", "Seated Cable Rows", "Sit Up"]
    }
    while True:
        print("UPPER BODY")
        print("Bagian Tubuh Mana Yang Ingin Dilatih? (chest/arms/abs)")
        upperbody = input().lower()
        if upperbody in exercises:
            print(f"Berikut Beberapa Olahraga Untuk Membentuk Otot {upperbody.capitalize()}:")
            for exercise in exercises[upperbody]:
                print(exercise)
            break
        else:
            print("Bagian tubuh tidak ditemukan, silakan pilih kembali.")

def pilih_makanan():
    makanan = [
        ("Nasi Goreng", 300),
        ("Ayam Bakar", 250),
        ("Tahu Goreng", 100),
        ("Tempe Goreng", 150),
        ("Sate Ayam", 200),
        ("Gado-Gado", 180),
        ("Bakso", 220),
        ("Mie Goreng", 350),
        ("Rendang", 400),
        ("Soto Ayam", 150)
    ]

    makanan.sort(key=lambda x: x[1])
    print("Makanan yang disortir berdasarkan kalori:")
    for item in makanan:
        print(f"{item[0]}: {item[1]} kalori")
    input("Tekan enter untuk kembali ke menu utama...")

def main():
    while True:
        print("SUDAH SIAPKAH HIDUP SEHAT?")
        print("1. Hitung BMR dan Pilih Latihan")
        print("2. Exit")
        pilihan = input("Pilih menu: ")

        if pilihan == "1":
            print("Basal metabolic rate (BMR) adalah kalori yang tubuh Anda perlukan untuk melakukan aktivitas dasar tubuh.")
            print("Mari hitung BMR anda")
            print("Masukkan Gender (male/female):")
            gender = input().lower()
            if gender == "female":
                print("Masukkan BB (kg):")
                bB = int(input())
                print("Masukkan TB (cm):")
                tB = int(input())
                print("Masukkan usia:")
                usia = int(input())
                bMR = 655.1 + 9.563 * bB + 1.85 * tB - 4.676 * usia
                print("Nilai BMR anda adalah", bMR)
            else:
                print("Masukkan BB (kg):")
                bB = int(input())
                print("Masukkan TB (cm):")
                tB = int(input())
                print("Masukkan usia:")
                usia = int(input())
                bMR = 66.47 + 13.75 * bB + 5.003 * tB - 6.755 * usia
                print("Nilai BMR anda adalah", bMR)

            print("PILIH LEVELMU")
            print("Beginner, Advance, Pro")
            print("Choose your level")
            level = input().capitalize()
            if level == "Beginner":
                print("Lakukan gerakan selama 5 menit")
            elif level == "Advance":
                print("Lakukan gerakan selama 10 menit")
            elif level == "Pro":
                print("Lakukan gerakan selama 15 menit")

            print("AYO OLAHRAGA!")
            while True:
                print("Select Body Part: 1. Lower Body 2. Upper Body")
                bodypart = int(input())
                if bodypart == 1:
                    lOWER()
                    break
                elif bodypart == 2:
                    uPPER()
                    break
                else:
                    print("Pilihan tidak valid, silakan pilih kembali.")

            pilih_makanan()

        elif pilihan == "2":
            print("Terima kasih! Tetaplah hidup sehat.")
            break
        else:
            print("Pilihan tidak valid, silakan pilih kembali.")

if __name__ == "__main__":
    main()
