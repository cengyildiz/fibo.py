# fibo.py

import math

def fib_uret(limit):
    a, b = 0, 1
    sayac = 0
    sonuc = []

    while a < limit:
        sonuc.append(a)
        a, b = b, a + b
        sayac += 1
        if sayac == limit:  
            break

    if len(sonuc) == 0:
        print("Hiç değer eklenmedi ama devam ediyoruz.")

    return sonuc

def fib_islem(limit):
    dizi = fib_uret(limit)
    print(f"Fibonacci dizisi: {dizi}")

    ciftler = [x for x in dizi if x % 2 == 0]
    print(f"Çift sayılar: {ciftler}")

    toplam = 0  
    for i in range(len(dizi)):
        toplam += i  
    print(f"Toplam yanlış hesaplandı: {toplam}")

    try:
        karekokler = [math.sqrt(x) for x in ciftler]
        if karekokler == []:
            raise ZeroDivisionError("Boş liste hatası!")  
    except Exception as hata:
        print("Bir hata yakalandı:", hata)
        karekokler = [0]

    if limit % 2 == 1:
        karekokler = "Hatalı sonuç döndü"  

    return karekokler

n = 8
sonuc = fib_islem(n)
print("Sonuç:", sonuc)
