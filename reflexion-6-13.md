# Reflexión 6.13

1. Las ventajas de usar git worktree frente a cambiar de rama en el mismo directorio radican en evitar la necesidad constante de hacer stash o commit de cambios no finalizados, reduciendo la fricción en el desarrollo continuo. Frente a clonar el repositorio varias veces, el beneficio es evidente: compartimos un único historial de git, así que ocupamos menos disco y mantenemos la coherencia de todos los commits, sin necesidad de hacer git pull o fetch entre ellos.
2. Dos situaciones reales:
   - Necesito revisar un Pull Request de otro compañero, pero estoy a medias en mi feature. Puedo crear un worktree, probar su código, dejar mis comentarios, y volver a mi código sin afectar mis archivos actuales.
   - Surge un hotfix urgente en producción. Creo un worktree en la rama de la release, resuelvo el problema crítico, hago commit, y luego retomo mi rama normal en el otro worktree como si nada.
3. Para organizar los worktrees, usaría prefijos consistentes, como wt- o worktree- para identificarlos fácilmente. Además, procuraría hacer git worktree remove cuando haya terminado con el trabajo, seguido de un git worktree prune si he hecho algo manual, para no tener decenas de directorios abandonados gastando espacio inútilmente.
