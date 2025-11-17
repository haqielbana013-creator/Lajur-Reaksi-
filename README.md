# Lajur-Reaksi-
def hitung_konstanta_laju(laju_reaksi, konsentrasi_a, konsentrasi_b, orde_a, orde_b):
    """
    Menghitung konstanta laju (k) berdasarkan data eksperimen.

    Parameter:
    - laju_reaksi (float): Laju reaksi yang terukur (Misalnya: M/s)
    - konsentrasi_a (float): Konsentrasi reaktan A (Misalnya: M)
    - konsentrasi_b (float): Konsentrasi reaktan B (Misalnya: M)
    - orde_a (int/float): Orde reaksi terhadap reaktan A
    - orde_b (int/float): Orde reaksi terhadap reaktan B

    Return:
    - float: Nilai konstanta laju (k)
    """
    try:
        # Menghitung penyebut: [A]^x * [B]^y
        konsentrasi_orde = (konsentrasi_a ** orde_a) * (konsentrasi_b ** orde_b)

        # Menghitung k: k = Laju / ([A]^x * [B]^y)
        k = laju_reaksi / konsentrasi_orde
        return k
    except ZeroDivisionError:
        return "Error: Konsentrasi tidak boleh nol jika orde > 0."

# --- Contoh Penggunaan ---
# Data Eksperimen 1:
# Laju = 0.005 M/s
# [A] = 0.1 M
# [B] = 0.2 M
# Orde A (x) = 1 (Asumsi diketahui)
# Orde B (y) = 2 (Asumsi diketahui)

laju = 0.005
kons_a = 0.1
kons_b = 0.2
orde_x = 1
orde_y = 2

konstanta_k = hitung_konstanta_laju(laju, kons_a, kons_b, orde_x, orde_y)

print(f"Laju Reaksi: {laju} M/s")
print(f"Konsentrasi [A]: {kons_a} M")
print(f"Konsentrasi [B]: {kons_b} M")
print(f"Orde A: {orde_x}, Orde B: {orde_y}")
print(f"Hasil Konstanta Laju (k): {konstanta_k}")
