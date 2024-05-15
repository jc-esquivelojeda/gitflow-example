# Gitflow branching strategy
## with bugfix and hotfix example

A continuacion se muestra los comandos usados en terminal para realizar el proceso de alta del repositorio, la rama develop y los features con la estrategia gitflow:

```
juan.esquivel@digitalfemsa.com@MACD6GG6P5W % git clone git@github.com:jc-esquivelojeda/gitflow-example.git
juan.esquivel@digitalfemsa.com@MACD6GG6P5W % cd gitflow-example
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git branch
* main
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git checkout -b develop
Cambiado a nueva rama 'develop'
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git checkout -b feature/improved-readme
Cambiado a nueva rama 'feature/improved-readme'
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git branch
  develop
* feature/improved-readme
  main
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git status
En la rama feature/improved-readme
Cambios no rastreados para el commit:
  (usa "git add <archivo>..." para actualizar lo que será confirmado)
  (usa "git restore <archivo>..." para descartar los cambios en el directorio de trabajo)
        modificados:     README.md

sin cambios agregados al commit (usa "git add" y/o "git commit -a")
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git add .        
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git commit -m "[feature] added some improvements to README.md"
[feature/improved-readme a68b7d2] [feature] added some improvements to README.md
 1 file changed, 1 insertion(+), 1 deletion(-)
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git status
En la rama feature/improved-readme
nada para hacer commit, el árbol de trabajo está limpio
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git checkout develop
Cambiado a rama 'develop'
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git merge feature/improved-readme
Actualizando f08ee07..a68b7d2
Fast-forward
 README.md | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git push
fatal: La rama actual develop no tiene una rama upstream.
Para empujar la rama actual y configurar el remoto como upstream, usa

    git push --set-upstream origin develop

Para hacer que esto pase automáticamente para las ramas que no rastrean
un upstream, mira 'push.autoSetupRemote' en 'git help config'.

juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git push --set-upstream origin develop
Enter passphrase for key '/Users/juan.esquivel@digitalfemsa.com/.ssh/id_rsa': 
Enumerando objetos: 5, listo.
Contando objetos: 100% (5/5), listo.
Compresión delta usando hasta 10 hilos
Comprimiendo objetos: 100% (2/2), listo.
Escribiendo objetos: 100% (3/3), 1.01 KiB | 1.01 MiB/s, listo.
Total 3 (delta 0), reusados 0 (delta 0), pack-reusados 0
remote: 
remote: Create a pull request for 'develop' on GitHub by visiting:
remote:      https://github.com/jc-esquivelojeda/gitflow-example/pull/new/develop
remote: 
To github.com:jc-esquivelojeda/gitflow-example.git
 * [new branch]      develop -> develop
rama 'develop' configurada para rastrear 'origin/develop'.
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git branch                                                    
* develop
  feature/improved-readme
  main
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git checkout -b release/v1.0
Cambiado a nueva rama 'release/v1.0'
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git checkout -b bugfix/missing-dot-fix
Cambiado a nueva rama 'bugfix/missing-dot-fix'
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git status
En la rama bugfix/missing-dot-fix
Cambios no rastreados para el commit:
  (usa "git add <archivo>..." para actualizar lo que será confirmado)
  (usa "git restore <archivo>..." para descartar los cambios en el directorio de trabajo)
        modificados:     README.md

sin cambios agregados al commit (usa "git add" y/o "git commit -a")
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git add .
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git status
En la rama bugfix/missing-dot-fix
Cambios a ser confirmados:
  (usa "git restore --staged <archivo>..." para sacar del área de stage)
        modificados:     README.md

juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git commit -m "[bugfix] Added missing dot at the end"
[bugfix/missing-dot-fix 4ee4a81] [bugfix] Added missing dot at the end
 1 file changed, 1 insertion(+), 1 deletion(-)
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git push
fatal: La rama actual bugfix/missing-dot-fix no tiene una rama upstream.
Para empujar la rama actual y configurar el remoto como upstream, usa

    git push --set-upstream origin bugfix/missing-dot-fix

Para hacer que esto pase automáticamente para las ramas que no rastrean
un upstream, mira 'push.autoSetupRemote' en 'git help config'.

juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git push --set-upstream origin bugfix/missing-dot-fix
Enter passphrase for key '/Users/juan.esquivel@digitalfemsa.com/.ssh/id_rsa': 
Enumerando objetos: 5, listo.
Contando objetos: 100% (5/5), listo.
Compresión delta usando hasta 10 hilos
Comprimiendo objetos: 100% (2/2), listo.
Escribiendo objetos: 100% (3/3), 995 bytes | 995.00 KiB/s, listo.
Total 3 (delta 1), reusados 0 (delta 0), pack-reusados 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote: 
remote: Create a pull request for 'bugfix/missing-dot-fix' on GitHub by visiting:
remote:      https://github.com/jc-esquivelojeda/gitflow-example/pull/new/bugfix/missing-dot-fix
remote: 
To github.com:jc-esquivelojeda/gitflow-example.git
 * [new branch]      bugfix/missing-dot-fix -> bugfix/missing-dot-fix
rama 'bugfix/missing-dot-fix' configurada para rastrear 'origin/bugfix/missing-dot-fix'.
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git checkout release/v1.0
Cambiado a rama 'release/v1.0'
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git merge bugfix/missing-dot-fix
Actualizando a68b7d2..4ee4a81
Fast-forward
 README.md | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git status
En la rama release/v1.0
nada para hacer commit, el árbol de trabajo está limpio
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git checkout main  
Cambiado a rama 'main'
Tu rama está actualizada con 'origin/main'.
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git merge release/v1.0
Actualizando f08ee07..4ee4a81
Fast-forward
 README.md | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git checkout develop
Cambiado a rama 'develop'
Tu rama está actualizada con 'origin/develop'.
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git merge release/v1.0
Actualizando a68b7d2..4ee4a81
Fast-forward
 README.md | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git push
Enter passphrase for key '/Users/juan.esquivel@digitalfemsa.com/.ssh/id_rsa': 
Total 0 (delta 0), reusados 0 (delta 0), pack-reusados 0
To github.com:jc-esquivelojeda/gitflow-example.git
   a68b7d2..4ee4a81  develop -> develop
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git checkout main
Cambiado a rama 'main'
Tu rama está adelantada a 'origin/main' por 2 commits.
  (usa "git push" para publicar tus commits locales)
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git push
Enter passphrase for key '/Users/juan.esquivel@digitalfemsa.com/.ssh/id_rsa': 
Total 0 (delta 0), reusados 0 (delta 0), pack-reusados 0
To github.com:jc-esquivelojeda/gitflow-example.git
   f08ee07..4ee4a81  main -> main
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git branch -d bugfix/missing-dot-fix
Eliminada la rama bugfix/missing-dot-fix (era 4ee4a81).
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git push origin --delete bugfix/missing-dot-fix
Enter passphrase for key '/Users/juan.esquivel@digitalfemsa.com/.ssh/id_rsa': 
To github.com:jc-esquivelojeda/gitflow-example.git
 - [deleted]         bugfix/missing-dot-fix
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git branch
  develop
  feature/improved-readme
* main
  release/v1.0
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git checkout -b hotfix/missing-readme-title
Cambiado a nueva rama 'hotfix/missing-readme-title'
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git status
En la rama hotfix/missing-readme-title
Cambios no rastreados para el commit:
  (usa "git add <archivo>..." para actualizar lo que será confirmado)
  (usa "git restore <archivo>..." para descartar los cambios en el directorio de trabajo)
        modificados:     README.md

sin cambios agregados al commit (usa "git add" y/o "git commit -a")
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git add .
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git commit -m "[HOTFIX] fixed missing title and added subtitle"
[hotfix/missing-readme-title 687a30d] [HOTFIX] fixed missing title and added subtitle
 1 file changed, 2 insertions(+), 1 deletion(-)
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git push
fatal: La rama actual hotfix/missing-readme-title no tiene una rama upstream.
Para empujar la rama actual y configurar el remoto como upstream, usa

    git push --set-upstream origin hotfix/missing-readme-title

Para hacer que esto pase automáticamente para las ramas que no rastrean
un upstream, mira 'push.autoSetupRemote' en 'git help config'.

juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git push --set-upstream origin hotfix/missing-readme-title
Enter passphrase for key '/Users/juan.esquivel@digitalfemsa.com/.ssh/id_rsa': 
Enumerando objetos: 5, listo.
Contando objetos: 100% (5/5), listo.
Compresión delta usando hasta 10 hilos
Comprimiendo objetos: 100% (2/2), listo.
Escribiendo objetos: 100% (3/3), 1.03 KiB | 1.03 MiB/s, listo.
Total 3 (delta 0), reusados 0 (delta 0), pack-reusados 0
remote: 
remote: Create a pull request for 'hotfix/missing-readme-title' on GitHub by visiting:
remote:      https://github.com/jc-esquivelojeda/gitflow-example/pull/new/hotfix/missing-readme-title
remote: 
To github.com:jc-esquivelojeda/gitflow-example.git
 * [new branch]      hotfix/missing-readme-title -> hotfix/missing-readme-title
rama 'hotfix/missing-readme-title' configurada para rastrear 'origin/hotfix/missing-readme-title'.
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git checkout main
Cambiado a rama 'main'
Tu rama está actualizada con 'origin/main'.
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git status
En la rama main
Tu rama está actualizada con 'origin/main'.

nada para hacer commit, el árbol de trabajo está limpio
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git log   
commit 4ee4a818aac38f7cb48d6f21e39a3763d9940618 (HEAD -> main, origin/main, origin/develop, origin/HEAD, release/v1.0, develop)
Author: juan.esquivel <juan.esquivel@digitalfemsa.com>
Date:   Tue May 14 08:21:06 2024 -0600

    [bugfix] Added missing dot at the end

commit a68b7d23c1f77432c6a5eba105408a4dcad9d900 (feature/improved-readme)
Author: juan.esquivel <juan.esquivel@digitalfemsa.com>
Date:   Tue May 14 08:13:58 2024 -0600

    [feature] added some improvements to README.md

commit f08ee075560975360df06e5079b353542850a386
Author: jc-esquivelojeda <123103329+jc-esquivelojeda@users.noreply.github.com>
Date:   Tue May 14 08:05:23 2024 -0600

    Initial commit
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git merge hotfix/missing-readme-title
Actualizando 4ee4a81..687a30d
Fast-forward
 README.md | 3 ++-
 1 file changed, 2 insertions(+), 1 deletion(-)
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git checkout develop
Cambiado a rama 'develop'
Tu rama está actualizada con 'origin/develop'.
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git merge hotfix/missing-readme-title
Actualizando 4ee4a81..687a30d
Fast-forward
 README.md | 3 ++-
 1 file changed, 2 insertions(+), 1 deletion(-)
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git push
Enter passphrase for key '/Users/juan.esquivel@digitalfemsa.com/.ssh/id_rsa': 
Total 0 (delta 0), reusados 0 (delta 0), pack-reusados 0
To github.com:jc-esquivelojeda/gitflow-example.git
   4ee4a81..687a30d  develop -> develop
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git branch
* develop
  feature/improved-readme
  hotfix/missing-readme-title
  main
  release/v1.0
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git checkout main
Cambiado a rama 'main'
Tu rama está adelantada a 'origin/main' por 1 commit.
  (usa "git push" para publicar tus commits locales)
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git branch -d hotfix/missing-readme-title                      
Eliminada la rama hotfix/missing-readme-title (era 687a30d).
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git push origin --delete hotfix/missing-readme-title
Enter passphrase for key '/Users/juan.esquivel@digitalfemsa.com/.ssh/id_rsa': 
To github.com:jc-esquivelojeda/gitflow-example.git
 - [deleted]         hotfix/missing-readme-title
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git branch
  develop
  feature/improved-readme
* main
  release/v1.0
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git status
En la rama main
Tu rama está adelantada a 'origin/main' por 1 commit.
  (usa "git push" para publicar tus commits locales)

nada para hacer commit, el árbol de trabajo está limpio
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example % git push
Enter passphrase for key '/Users/juan.esquivel@digitalfemsa.com/.ssh/id_rsa': 
Total 0 (delta 0), reusados 0 (delta 0), pack-reusados 0
To github.com:jc-esquivelojeda/gitflow-example.git
   4ee4a81..687a30d  main -> main
juan.esquivel@digitalfemsa.com@MACD6GG6P5W gitflow-example %
```
