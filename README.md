produk = [
    {"nama": "Headset", "harga": 150000, "stok": 12},
    {"nama": "Mouse", "harga": 85000, "stok": 25},
    {"nama": "Keyboard", "harga": 250000, "stok": 8},
    {"nama": "Webcam", "harga": 200000, "stok": 15},
    {"nama": "Flashdisk", "harga": 75000, "stok": 30},

    # 2 produk tambahan
    {"nama": "Monitor", "harga": 500000, "stok": 10},
    {"nama": "Speaker", "harga": 120000, "stok": 20}
]


# 1. Bubble Sort
# Harga termahal → termurah
def bubble_sort(produk):
    n = len(produk)

    for i in range(n - 1):
        for j in range(n - i - 1):
            if produk[j]["harga"] < produk[j + 1]["harga"]:
                produk[j], produk[j + 1] = produk[j + 1], produk[j]

    return produk


# 2. Selection Sort
# Nama Z → A
def selection_sort(produk):
    n = len(produk)

    for i in range(n - 1):
        max_index = i

        for j in range(i + 1, n):
            if produk[j]["nama"] > produk[max_index]["nama"]:
                max_index = j

        produk[i], produk[max_index] = produk[max_index], produk[i]

    return produk


# 3. Insertion Sort
# Stok tersedikit → terbanyak
def insertion_sort(produk):
    n = len(produk)

    for i in range(1, n):
        key = produk[i]
        j = i - 1

        while j >= 0 and produk[j]["stok"] > key["stok"]:
            produk[j + 1] = produk[j]
            j -= 1

        produk[j + 1] = key

    return produk


# Menampilkan hasil Bubble Sort
print("=== Bubble Sort: Harga Termahal → Termurah ===")
hasil_bubble = bubble_sort(produk.copy())

for item in hasil_bubble:
    print(item["nama"], item["harga"])


# Menampilkan hasil Selection Sort
print("\n=== Selection Sort: Nama Z → A ===")
hasil_selection = selection_sort(produk.copy())

for item in hasil_selection:
    print(item["nama"], item["harga"])


# Menampilkan hasil Insertion Sort
print("\n=== Insertion Sort: Stok Tersedikit → Terbanyak ===")
hasil_insertion = insertion_sort(produk.copy())

for item in hasil_insertion:
    print(item["nama"], item["stok"])
