1. Comando utilizado en el paso 11 ¿Por qué?: Utilizo "git reset --hard HEAD~1" porque si lo utilizo sin el "--hard" me sitúa en el commit anterior pero mantiene los cambios realizados en el working copy.

2. Comando/s utilizado/s en el paso 12 ¿Por qué?: Primero, uso "git reflog" para poder ver la lista de los pasos que he dado y así localizar el SHA del commit que acabo de borrar. En segundo lugar, uso "git reset <SHADelCommitBorrado>" para situarme en él. Tercero, hago un "git add <nombreArchivo>". Y por último, "git commit" para rehacer el commit.

3. El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?: Como están en la misma línea, y styled contiene ya a master, no deja e indica que "is already up-to-date"(que está actualizada, es decir, que contiene todos los elementos). Por tanto, desplazo HEAD sobre la rama master (con un "git checkout") y hago un "git reset" hasta donde está la rama styled, he mergeado en el otro sentido (master mergea a styled).

4. El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?: Sí que causó conflicto, ya que el archivo git-nuestro en la rama htmlify difiere de la versión en styled, ofreciendo 2 versiones de cada una de las líneas y git no sabe cuál es el archivo correcto. Borro los nuevos cambios y la dejo como estaba en styled.

5. El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?: No causó ningún conflicto ya que styled contenía nuevos commits que la rama master no tenía. Si lo hubiese intentando al revés, con la rama styled absorver a master, hubiera saltado el mensaje de "Already up-to-date".

6. Comando/s utilizado/s en el paso 25: Utilizo "git log --graph", aunque si lo quiero más resumido y bonito puedo utilizar "git log --graph --decorate --pretty=oneline".

7. El merge del paso 26 ¿Podría ser fast forward? ¿Por qué?: Sí que podría serlo porque están en la misma línea, sería como subir master al nivel de title. Pero title no puede absorver a master porque ya le contiene (lo que he comentado anteriormente de "Already up-to-date").

8. ¿Qué comando/s utilizaste en el paso 27?: Utilizo "git reset HEAD~1". Si incluyese "--hard" perdería los cambios del working copy.

9. ¿Qué comando/s utilizaste en el paso 28?: Utilizo "git checkout -- git-nuestro.md".

10. ¿Qué comando/s utilizaste en el paso 29?: Utilizo "git branch -D title".

11. ¿Qué comando/s utilizaste en el paso 30?: Primero me posiciono en el commit donde estaba la rama, es decir, hago un "git checkout <SHA>" (lo sé, porque al eliminar la rama, te indica qué SHA tenía el commit), lo que me deja en un estado "detached Head", y ahora hago un "git checkout -b title" para restaurarla. Una vez restaurada, me sitúo en la rama master con un "git checkout master" y realizo un merge no fast-forward.

12. ¿Qué comando/s utilizaste en el paso 32?: Primero hago un "git log" para ver el SHA del commit inicial, y después un "git reset <SHA>".

13. ¿Qué comando/s utilizaste en el paso 33?: Utilizo "git reflog" y busco el SHA del commit del que procedo (que coincide con el del último merge) y me sitúo en él con "git reset <SHA>". 

