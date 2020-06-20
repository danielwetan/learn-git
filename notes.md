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
- Move to some directory => cd directory-name
- Create directory => mkdir folder-name
- Create file => echo "Hello Git" > hello.txt 
- Delete directory or file => rm -rf folder-name

-----

## Basic Operation
# Membuat repository
Inisialisasi Git pada project
- git init
- git clone => git clone https://github.com/google/web-starter-kit
Cek isi dari folder .git 
- ls .git

# Git Lifecycle
Working directory -> (git add) Staging / index -> (git commit) Local repo 
* Ketika melakukan git commit maka history akan tersimpan, berisi informasi siapa yang mengubah dll

# Commit Pertama
- git status => informasi branch, history commit, file yang sudah dicommit
- git add => memasukan file ke staging / index 
  ex. git add hello.md
  gunakan * untuk memilih seluruh file
- git commit -> memasukan file ke local repo
  ex. git commit -m "first commit" 
  -m => message

# Git History
- git log => menampilkan history dari commit sebelumnya 
  ex. git log --oneline => log dalam satu baris

  HEAD -> Master ==> sedang aktif di commit 

# Setup Vscode
- install vscode extension "Git Graph" to display git flow

# Delete & Ignore
Delete file
 Contoh jika ingin menghapus city.md
 - Delete file city.md
 - git add city.md
 - git commit -m "delete city.md"
Ignore file => file yang tidak ingin diupload ke Local repo
 Ex. Ignore file nation.md
 - buat file .gitignore
 - ketik file yang ingin diignore, pada kasus ini "nation.md" didalam .gitignore
 

-----

## Branch

## Undoing

## Collaboration
