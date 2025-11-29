[README.md](https://github.com/user-attachments/files/23833791/README.md)
# Implementacja Algorytmu AES-128 (Python)

Projekt zawiera kompletną, edukacyjną implementację standardu szyfrowania **Advanced Encryption Standard (AES)** z 128-bitowym kluczem, napisaną "od zera" w czystym Pythonie.

Kod został przygotowany w formie **Jupyter Notebook**, aby krok po kroku zilustrować wewnętrzne działanie algorytmu – od matematyki ciał skończonych po operacje na plikach.

## 🚀 Główne Cechy Projektu

* **Brak bibliotek kryptograficznych:** Cała logika (S-Box, MixColumns, Key Schedule) została zaimplementowana ręcznie bez użycia gotowych modułów typu `pycryptodome`.
* **Arytmetyka w GF(2^8):** Własna implementacja mnożenia wielomianów w ciele skończonym Galois (algorytm *Peasant's Algorithm*).
* **Pełny cykl:** Obsługa zarówno szyfrowania, jak i deszyfrowania (z wykorzystaniem odwrotnych transformacji `InvSubBytes`, `InvMixColumns` itp.).
* **Obsługa plików:** Funkcje pozwalające na szyfrowanie i deszyfrowanie dowolnych plików binarnych (np. obrazów).

## ⚙️ Specyfikacja Techniczna

* **Rozmiar bloku:** 128 bitów (16 bajtów).
* **Długość klucza:** 128 bitów (NK=4).
* **Liczba rund:** 10.
* **Padding:** PKCS#7 (dopełnianie bloków).
* **Tryb działania:** ECB (Electronic Codebook).

## 📂 Struktura Notebooka

1.  **Stałe Globalne:** Definicje tabel S-Box, Rcon oraz macierzy MDS.
2.  **Matematyka:** Operacje `xtime` i mnożenie w ciele Galois.
3.  **Key Expansion:** Generowanie 11 podkluczy rund.
4.  **Funkcje Rundy:** Implementacja `SubBytes`, `ShiftRows`, `MixColumns`, `AddRoundKey`.
5.  **Demo (Image Encryption):** Praktyczny przykład szyfrowania pliku `.jpeg`, wizualizujący cechy trybu ECB (widoczność wzorców w zaszyfrowanych danych).

## ⚠️ Ostrzeżenie

Jest to implementacja **wyłącznie edukacyjna**, stworzona w celu demonstracji architektury AES.
* Kod działa w trybie **ECB**, który nie zapewnia dyfuzji wzorców (identyczne bloki tekstu jawnego dają identyczny szyfrogram).
* Implementacja nie jest odporna na ataki kanałami bocznymi (Timing Attacks / Power Analysis).
* **Nie używać do zabezpieczania rzeczywistych, wrażliwych danych.**

## 🛠️ Wymagania

* Python 3.x
* Jupyter Notebook / Google Colab
* Biblioteka `Pillow` (PIL) - tylko do sekcji demonstracyjnej z obrazem.
