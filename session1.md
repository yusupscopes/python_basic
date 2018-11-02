# Session 1: Python Dasar

## Print
Syntax print digunakan untuk mencetak suatu output ke terminal
```python
print("Hi Python!")
# Output: Hi Python!
```

## Variabel
Variabel adalah cara kita menyimpan sebuah nilai ke dalam suatu huruf atau kata agar bisa kita pakai secara berulang. Aturan penulisan variabel di python yaitu menggunakan alfanumerik dan bisa menggunakan *underscore* (\_).
```python
_py1 = "Hi Python!"
print(_py1)
# Output: Hi Python!
```

## Tipe Data
Beberapa tipe data yang ada di python adalah Numbers, String, List, Tuple, Dictionary.
```python
#String
w = "Belajar Python"
x = '5'

#Number
y = 10.5
z = 9

# untuk cek tipe data
type(y)
# Output: <class 'float'>
```

### String
Menggabungkan string (concatenate) di python.
```python
x = 'belajar'
print(x + " python")
# Output: belajar python

y = 'python'
print(x + " " + y)
# Output: belajar python
```
Escape karakter khusus menggunakan backslash (\).
```python
print('hari ini hari jum\'at \n ini di baris kedua')
# Output: hari ini hari jum'at
#         ini di baris kedua
```
Beberapa method string di python.
```python
x = 'belajarpython'
x.capitalize()
# Output: Belajarpython

x.replace('belajar', 'kenalan')
# Output: kenalanpython
```

### Angka
Mengoperasikan tipe data angka di python.
```python
x = 10
y = 20
print(x*y)
# Output: 200

max(x, y, 50, 70)
# Output: 70

round(7.89)
# Output: 8

import math
math.pi
# Output: 3.1415xxxxxxxxx
```
Menggabungkan angka dengan string bersamaan (berbeda tipe data) bisa menggunakan tanda koma (,)
```python
harga = 5000
print("total belanja ", harga)
# Output: total belanja 5000

# konversi int ke string
str(harga)

# konversi dari string ke int
int(harga)
```

### Boolean
Tipe data yang nilai nya cuma ada 2, yaitu __*True*__ dan __*False*__.
```python
angka1 = 20
angka2 = 40
print(angka1 < angka2)
# Output: True

text = 'belajarpython'
print(text.isalnum())
# Output: True
```

## Komentar
```python
# ini komentar satu baris

"""
ini komentar beberapa baris
ini komentar juga
begitu juga dengan ini
"""
```

## Input
```python
nama = input("Siapa nama kamu? ")
umur = input("berapa umurmu? ")
print("salam kenal! boss " + nama + ", kamu sudah " + umur + " tahun")
```

## Percabangan
Cara kita menentukan kondisi
### If dan Else
```python
angka1 = 20
angka2 = 40

if angka1 == angka2:
    print('benar angka1 dan angka2 sama besar')
else:
    print('salah!')
```

### If, Elif, dan Else
```python
uang  = input('kamu punya uang berapa? ')
utang = 10000

if int(uang) < utang:
    print('wah maaf masih belum cukup')
elif int(uang) == utang:
    print('terimakasih sudah bayar!')
else:
    print('wah uangnya lebih bos')
```
