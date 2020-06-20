###
Vendredi
19-06-2020
---
Belajar Menggunakan Git
###

## Intro

## Git Basic

## Installation & Config

## Terminal / Command Line
- cd directory-name => move to some directory
- mkdir folder-name => create directory
- echo "Hello Git" > hello.txt => create file hello.txt with value "Hello Git"
- rm -rf folder-name => delete directory or file
-----

## Basic Operation
# Membuat repository
Inisialisasi Git pada project
* git init
* git clone => git clone https://github.com/google/web-starter-kit
Cek isi dari folder .git => ls .git

# Git Lifecycle
Working directory -> (git add) Staging / index -> (git commit) Local repo 
Ketika melakukan git commit maka history akan tersimpan, berisi informasi siapa yang mengubah dll

# Commit Pertama
* git status => informasi branch, history commit, file yang sudah dicommit
* git add => memasukan file ke staging / index 
  ex. git add hello.md
  gunakan * untuk memilih seluruh file
* git commit -> memasukan file ke local repo
  ex. git commit -m "first commit" 
  -m => message

# Git History
* git log => menampilkan history dari commit sebelumnya 
* git log --oneline => log dalam satu baris (lebih simple)
HEAD -> Master ==> sedang aktif di commit Master

# Setup Vscode
Install vscode extension "Git Graph" to display git flow

# Delete & Ignore
Delete file
 Contoh jika ingin menghapus city.md
 - delete file city.md
 - git add city.md
 - git commit -m "delete city.md"
Ignore file => file yang tidak ingin diupload ke Local repo
 Ex. Ignore file nation.md
 - buat file .gitignore
 - ketik file yang ingin diignore, pada kasus ini "nation.md" didalam .gitignore.
   jika ingin meng-ignore folder, ganti "nation.md" menjadi nama folder
-----

## Branch
# Mengenal Branch
Secara default project Git akan berada pada branch master,
kita bisa membuat branch (cabang) baru ketika development, dengan tujuan tidak mengubah code pada branch master.
Ketika selesai kita bisa menggabungkan kode pada branch tertentu dengan branch master menggunakan => "git merge"
- Commit 1 (master)
- Commit 2
- Commit 3 (branch)
- Commit 4
- Commit 5 (merge) => code pada branch di merge dengan master

# Operasi dasar Branch
* git branch => menampilkan data branch
* git branch branch-name => membuat branch baru |||| "master *" artinya kita berada pada branch master
* git checkout branch-name => masuk ke branch branch-name
* git branch -D branch-name => delete branch
* git checkout -b another-nation => create and move to new branch

# Merge branch
Ketika di branch baru
* git merge master branch-name => merge new branch with master
Ketika di branch master
* git merge branch-name

# Merge strategy
Fast forward vs Recursive
IDK!!
* git commit -am "Text" => cara lain untuk commit

# Resolve merge conflict
Biasanya terjadi ketika ada suatu file yang isinya dirubah dikedua branch

Untuk mengatasinya, file yang conflict tersebut harus dirubah: baik menggunakan current, incoming, atau menggunakan keduanya

## Undoing
Git flow:
Working directory -> Staging / index -> Local repo

# Unstage Staging File
* git reset HEAD => Unstaging staging file
Working directory <- Staging / index

# Undo Modified File
* git checkout => Unmodify file
Working directory <- local repo

Jika file yang ingin di-undo sudah berada pada staging.
Maka fungsi ini tidak akan berfungsi.
Solusinya gunakan "git reset HEAD index.md" terlebih dahulu, kemudian baru gunakan "git checkout index.md"

# Update last commit
* git commit --amend


## Collaboration
