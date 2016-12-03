# ¿Qué comando utilizaste en el paso 11? *"Deshacer el último commit (perdiendo los cambios realizados en el working copy)"* ¿Por qué?

git checkout master

git checkout  mueve el HEAD  y modifica el working copy. Llevándolo a la rama master deshacemos el último commit y evitamos un detached.

# ¿Qué comando o comandos utilizaste en el paso 12? *"Rehacer el último commit (el que acabamos de deshacer)"* ¿Por qué?

git checkout styled

Al igual que en el punto anterior, git checkout  mueve el HEAD  y modifica el working copy. Llevándolo a la rama styled deshacemos el último commit y evitamos un detached.

# El merge del paso 13, ¿Causó algún conflicto? *"Hacer un merge con ‘master’ (styled absorbe a master)"* ¿Por qué?
No, porque ambas ramas compartían todos los commits realizados.

# El merge del paso 19, ¿Causó algún conflicto? *"Hacer un merge de “htmlify” en “styled” (styled absorbe a htmlify)"* ¿Por qué?
Si ha existido conflicto. 
La causa son commits de htmlify de los que styled no tiene constancia.
La rama htmlify se generó a partir de un commit anterior a la creación de la rama styled.


# El merge del paso 21, ¿Causó algún conflicto? *"Desde “master”, hacer un merge con “styled”* " ¿Por qué?
Este merge no ha generado ningún conflicto.
Ambas ramas comparten la secuencia de commits.

# ¿Qué comando o comandos utilizaste en el paso 25? *"Dibujar el diagrama"*

git log --graph

# El merge del paso 26, ¿Podría ser fast forward? *"Hacer un merge “no fast-forward” de “title” en “master” (master absorbe a title)"* ¿Por qué?

Si podría haber sido fast forward, porque el HEAD en este punto era un ancestro del commit que se quiere absorber.
Los cambios del HEAD ya estában incluidos y en lugar de generar un nuevo commit se podría haber movido el HEAD y la rama al commit de la rama title. 

# ¿Qué comando o comandos utilizaste en el paso 27? *"Deshacer el merge (sin perder los cambios del working copy)"*

git reflog / git log   para buscar el commit anterior a los cambios.
git reset  paracmover el puntero HEAD al commit donde se iniciaron los cambios de la rama title

# ¿Qué comando o comandos utilizaste en el paso 28? *"Descartar los cambios"*

git reset --hard 
o git checkout -- 

# ¿Qué comando o comandos utilizaste en el paso 29? *"Eliminar la rama “title”*

git branch -D title

# ¿Qué comando o comandos utilizaste en el paso 30? *"Rehacer el merge que hemos deshecho"*

git reflog  para buscar el commit creado anteriormente en el  git 
git diff para asegurar que contiene los cambios que queremos
git reset --hard   para mover HEAD y la rama master al commit con los cambios.

# ¿Qué comando o comandos usaste en el paso 32? *"Volver al commit inicial cuando se creó el poema"*

git checkout <hash commit>

# ¿Qué comando o comandos usaste en el punto 33? *"Volver al estado final, cuando pusimos título al poema"*

git checkout master
