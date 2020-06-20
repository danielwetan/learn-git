Command dasar paling sering digunakan pada Git.

## Table of Content

* Terminal / Command Line 
* Basic Operation
* Delete & Ignore
* Branch
* Undoing
* Collaboration

---

### Basic Terminal / Command Line
- `cd directory-name` ~> move to some directory
- `mkdir folder-name` ~> create directory
- `echo "Hello Git" > hello.txt` ~> create file `hello.txt` with value `"Hello Git"`
- `rm -rf folder-name` ~> delete directory or file

---

### Basic Operation
#### Membuat repository
Inisialisasi Git pada project
* `git init`
* `git clone` example: `git clone https://github.com/google/web-starter-kit`
Cek isi dari folder .git => ls .git

#### Git Lifecycle
Working directory ~> (git add) Staging / index ~> (git commit) Local repo 
Ketika melakukan git commit maka history akan tersimpan, berisi informasi siapa yang mengubah dll

#### Commit Pertama
* `git status` => informasi branch, history commit, file yang sudah dicommit
* `git add` ~> memasukan file ke staging / index 
  ex. `git add hello.md`
  gunakan * untuk memilih seluruh file
* git commit ~> memasukan file ke local repo
  ex. `git commit -m "first commit"` 
  -m = message

#### Git History
* `git log` ~> menampilkan history dari commit sebelumnya 
* `git log --oneline` ~> log dalam satu baris (lebih simple)
HEAD -> Master ==> sedang aktif di commit Master

#### Setup Vscode
Install vscode extension `Git Graph` to display Git flow

---

### Delete & Ignore
Delete file
Contoh jika ingin menghapus `city.md`
1. `delete file city.md`
2. `git add city.md`
3. `git commit -m delete city.md`
 
**Ignore file** ~> file tidak akan diupload ke Local repo
Ex. Ignore file `nation.md`

- buat file `.gitignore`
 - ketik file yang ingin diignore, pada kasus ini `nation.md` didalam `.gitignore`.
   jika ingin meng-ignore folder, ganti `nation.md` menjadi nama folder

----

### Branch
#### Mengenal Branch
Secara default project Git akan berada pada branch master,
kita bisa membuat branch (cabang) baru ketika development, dengan tujuan tidak mengubah code pada branch master.
Ketika selesai kita bisa menggabungkan kode pada branch tertentu dengan branch master menggunakan ~> `git merge`
- Commit 1 (master)
- Commit 2
- Commit 3 (branch)
- Commit 4
- Commit 5 (merge) ~> code pada branch di merge dengan master

#### Operasi dasar Branch
* `git branch` ~> menampilkan data branch
* `git branch branch-name` ~> membuat branch baru. "master *" artinya kita berada pada branch master
* `git checkout branch-name` ~> masuk ke branch branch-name
* `git branch -D branch-name` ~> delete branch
* `git checkout -b another-nation` ~> create and move to new branch

#### Merge branch
Menggabungkan branch baru dengan master branch.
Ketika di branch baru
* `git merge master branch-name` ~> merge new branch with master
Ketika di branch master
* `git merge branch-name`

#### Merge strategy
* `git commit -am "Text"` ~> cara lain untuk commit tanpa perlu menambahkan ke staging state terlebih dahulu

#### Resolve merge conflict
Biasanya terjadi merge conflict ketika ada suatu file yang isinya dirubah dikedua branch
Untuk mengatasinya, file yang conflict tersebut harus dirubah sehingga isinya sama pada kedua branch sama.

---

### Undoing
Git flow:
`Working directory ~> Staging / index ~> Local repo ~> Remote repo`

#### Unstage staging file
* `git reset HEAD` ~> Unstaging staging file
Ubah file dari `Working directory <~ staging / index`

#### Undo mdified file
* `git checkout` ~> Unmodify file
Ubah file dari `Working directory <~ local repo`

Jika file yang ingin di-undo sudah berada pada staging.
Maka fungsi ini tidak akan berfungsi.
Solusinya gunakan `git reset HEAD index.md` terlebih dahulu, kemudian baru gunakan `git checkout index.md`

#### Update last commit
Mengupdate value dan nama commit terakhir
* `git commit --amend`

#### Rollback commit
Kembali ke commit sebelumnya atau commit pilihan
* `git revert HEAD~0` ~> revert ke commit sebelumnya
* `git revert HEAD~1` ~> revert ke commit kedua sebelumnya
* `git revert HEAD~4` ~> revert ke commit kelima sebelumnya

#### Reset commit
Konsepnya sama seperti rollback commit, 
bedanya perintah ini akan menghapus history commit
* `git reset HEAD~1` ~> menghapus commit sebelumnya
* `git reset HEAD~2` ~> menghapus commit kedua sebelumnya
* `git reset HEAD~4` ~> menghapus commit keempat sebelumnya 

Ketika direset, file yang baru dibuat pada commit tersebut akan tersimpan di staging

* `git reset --hard HEAD~1` ~> menghapus commit sebelumnya dan mengubah isinya secara total tanpa ada yang ditambahkan ke staging
* `git reset --hard HEAD~2` ~> menghapus commit kedua sebelumnya dan mengubah isinya secara total tanpa ada yang ditambahkan ke staging

---

### Collaboration
Git lifecycle:
`Working directory -> Staging/index -> Local repo -> Remote repo`

* `git remote -v` ~> display git remote address

#### Git Push
* `git push origin master`~> push local repo ke remote repo

#### Git Fetch & Pull
* `git fetch origin master` ~> mengambil data di remote repo dan memasukannya ke local repo. Karena berada pada `origin branch` agar data pada local repo berubah, kita harus menjalankan `git merge`
* `git pull` ~> seperti fetch, namun lebih cepat karena tidak perlu menjalankan `git merge`

---

## Author
* [Daniel Saputra](https://www.linkedin.com/in/danielwetan/)

> Vendredi
> 19-06-2020
