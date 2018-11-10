# Session 2: Python I/O

## Membaca dan Menulis File
Untuk bermain dengan file, pada python kita bisa menggunakan built-in function open().
```python
# Membaca file
file = open('file.txt', 'r')
text = file.read()
print(text)
# Output: Apapun isi file.txt!

# Menulis file
file = open('file.txt', 'w')
file.write('Halo Halo Pangandaran')
# Output: File file.txt akan berisi text Halo Halo Pangandaran
```
### Membaca dan menulis bersamaan
```python
file = open('file.txt', 'a+')
file.write('\nHalo Halo Bogor')

# untuk mengembalikan pointer ke posisi semula
file.seek(0)
text = file.read()
print(text)
```
### Membuat daftar belanja
```python
file = open('list.txt', 'a+')

def add_to_list(text):
    file.write('\n' + text)
    file.seek(0)
    text = file.read()
    print(text)
    ask_user()

def ask_user():
    add_to_list(input('Mau beli apa aja? '))

ask_user()
```
