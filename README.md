# exercicio01
a) No working dir, executar o comando: echo 01 > arquivo.txt
 
   Após comando aparece o arquivo.txt com status U(não controlado), pois não está no pré commit.


b) Adicionar o arquivo no staging e conferir o status

   Adicionado no staging(pré commit) com a situação new file: arquivo.txt | contendo valor texto 01 


c) Commitar o arquivo do staging com a descrição "git add example - arquivo.txt"

Adicionado no repositorio(commit) | contendo valor texto 01 


d) Sobrescrever o conteúdo do arquivo.txt: echo 02 > arquivo.

modificado contendo cdo arquivo.txt contendo valor texto 02


e) Verificar o diffing no arquivo

compara alteração de conteudo do mesmo arquivo.txt, sendo original representado com a letra A(valor texto 01) e a ultima alteração representado pela letra B(valor texto 02)


f) Adicionar novamente o arquivo no staging e conferir o status 

Adicionado no staging(pré commit) com a situação modified: arquivo.txt | contendo valor texto 02


g) Verificar o diffing no arquivo

Sem alterações. sendo original representado com a letra A(valor texto 02) e a ultima alteração representado pela letra B(valor texto 02)


h) Sobrescrever o conteúdo do arquivo.txt: echo 03 > arquivo.txt

modificado contendo cdo arquivo.txt contendo valor texto 03


i) Verificar o diffing no arquivo

compara com alteração, sendo original representado com a letra A(valor texto 02) e a ultima alteração representado pela letra B(valor texto 03)

j) Fazer o restore do arquivo da área de staging e verificar o status

 Realizado comando de restauração na area pré commit > git restore --stage arquivo.txt | restaura com valor texo 3 start de modified
 

k) Realizar o commit do arquivo e verificar o log

Adicionado no staging e realizado commit do arquivo.txt | contendo valor texto 03 


l) Adicionar um arquivo gitignore com o seguinte conteúdo: *.txt

criado o arquivo .gitignore com a descrição para regra *.txt


m) Criar um arquivo novo.txt e verificar o status

Ignora os arquivos *.txt



LOG DOS COMANDOS


@DenisImpacta ➜ /workspaces/exercicio01 (main) $ git config --global user.name "Denis Guedes"
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ 
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ git config --global user.email "denis.guedes@aluno.faculdadeimpacta.com.br"
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ git init
Reinitialized existing Git repository in /workspaces/exercicio01/.git/
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ ls -a
.  ..  .git  README.md
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ echo 01 > arquivo.txt
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        arquivo.txt

no changes added to commit (use "git add" and/or "git commit -a")
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ git add arquivo.txt
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   arquivo.txt

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

@DenisImpacta ➜ /workspaces/exercicio01 (main) $ cat arquivo.txt
01
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ git commit -m "git add example - arquivo.txt"
[main 41824a8] git add example - arquivo.txt
 1 file changed, 1 insertion(+)
 create mode 100644 arquivo.txt
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ cat arquivo.txt
01
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ echo 02 > arquivo.txt
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ 
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ cat arquivo.txt
02
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md
        modified:   arquivo.txt

no changes added to commit (use "git add" and/or "git commit -a")
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ git diff arquivo.txt
diff --git a/arquivo.txt b/arquivo.txt
index 8a0f05e..9e22bcb 100644
--- a/arquivo.txt
+++ b/arquivo.txt
@@ -1 +1 @@
-01
+02
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md
        modified:   arquivo.txt

no changes added to commit (use "git add" and/or "git commit -a")
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ git add arquivo.txt
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   arquivo.txt

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

@DenisImpacta ➜ /workspaces/exercicio01 (main) $ cat arquivo.txt
02
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ git diff arquivo.txt
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ git diff arquivo.txt
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   arquivo.txt

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

@DenisImpacta ➜ /workspaces/exercicio01 (main) $ git diff arquivo.txt
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ git diff
diff --git a/README.md b/README.md
index cb6c23a..cfa33fc 100644
--- a/README.md
+++ b/README.md
@@ -1 +1,48 @@
\ No newline at end of file
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ cat arquivo.txt
02
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ echo 03 > arquivo.txt
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ 
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ cat arquivo.txt
03
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   arquivo.txt

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md
        modified:   arquivo.txt

@DenisImpacta ➜ /workspaces/exercicio01 (main) $ git diff arquivo.txt
diff --git a/arquivo.txt b/arquivo.txt
index 9e22bcb..75016ea 100644
--- a/arquivo.txt
+++ b/arquivo.txt
@@ -1 +1 @@
-02
+03
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ dit status
bash: dit: command not found
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   arquivo.txt

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md
        modified:   arquivo.txt

@DenisImpacta ➜ /workspaces/exercicio01 (main) $ cat arquivo.txt
03
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ git restore --stage arquivo.txt
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md
        modified:   arquivo.txt

no changes added to commit (use "git add" and/or "git commit -a")
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ cat arquivo.txt
03
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ git commit -m "git add example - arquivo.txt v2"
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md
        modified:   arquivo.txt

no changes added to commit (use "git add" and/or "git commit -a")
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ cat arquivo.txt
03
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ git log
commit 41824a8d198f9e80d5093180c218884f02813c08 (HEAD -> main)
Author: Denis Guedes <denis.guedes@aluno.faculdadeimpacta.com.br>
Date:   Fri Aug 9 04:39:45 2024 +0000

    git add example - arquivo.txt

commit 922add64bfc0d64df0fff771493b0b0f6689c620 (origin/main, origin/HEAD)
Author: DenisImpacta <denis.guedes@aluno.faculdadeimpacta.com.br>
Date:   Fri Aug 9 01:07:36 2024 -0300

    Initial commit
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ cat arquivo.txt
03
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ git add arquivo.txt
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   arquivo.txt

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

@DenisImpacta ➜ /workspaces/exercicio01 (main) $ git commit -m "git add example - arquivo.txt v3"
[main a8ad938] git add example - arquivo.txt v3
 1 file changed, 1 insertion(+), 1 deletion(-)
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ git log
commit a8ad938757667ebf51fdd44992cc70186449885a (HEAD -> main)
Author: Denis Guedes <denis.guedes@aluno.faculdadeimpacta.com.br>
Date:   Fri Aug 9 05:57:57 2024 +0000

    git add example - arquivo.txt v3

commit 41824a8d198f9e80d5093180c218884f02813c08
Author: Denis Guedes <denis.guedes@aluno.faculdadeimpacta.com.br>
Date:   Fri Aug 9 04:39:45 2024 +0000

    git add example - arquivo.txt

commit 922add64bfc0d64df0fff771493b0b0f6689c620 (origin/main, origin/HEAD)
Author: DenisImpacta <denis.guedes@aluno.faculdadeimpacta.com.br>
Date:   Fri Aug 9 01:07:36 2024 -0300

    Initial commit
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ cat arquivo.txt
03
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ vi .gitignore
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ vi .gitignore
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ echo "novo arquivo" > novo.txt
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ git status
On branch main
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .gitignore

no changes added to commit (use "git add" and/or "git commit -a")
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ cat .gitignore
*.txt@DenisImpacta ➜ /workspaces/exercicio01 (main) $ 
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ git status
On branch main
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .gitignore

no changes added to commit (use "git add" and/or "git commit -a")
@DenisImpacta ➜ /workspaces/exercicio01 (main) $ cat .gitignore
*.txt@DenisImpacta ➜ /workspaces/exercicio01 (main) $ 
