# torii-wiki

La wiki de Torii, en el formato que espera osu-web.

Generada desde las paginas de React de `torii-lazer-web/src/pages/wiki` con
`torii-wiki-convert.py` del fork de osu-web. El texto es el mismo, no se
reescribio: solo cambia el envoltorio.

## Como la lee osu-web

osu-web no guarda la wiki en la base. Le pide los archivos a la api de contents
de github, los renderiza y los deja en elasticsearch. La ruta de una pagina sale
del path del archivo:

    wiki/Rules/en.md        ->  /wiki/en/Rules
    wiki/Torii_points/en.md ->  /wiki/en/Torii_points

Para que apunte aca hacen falta cuatro variables en el contenedor (`WIKI_USER`,
`WIKI_REPOSITORY`, `WIKI_BRANCH`, `GITHUB_TOKEN`) y despues una corrida de
`php artisan es:index-wiki`. Sin el token, cualquier lectura devuelve
"Bad credentials" y el indice queda vacio, que es exactamente por que /wiki
daba 404.

## Editar una pagina

Se edita el markdown y se pushea. osu-web revisa si cambio cada cinco horas, o
en el momento si se configura el webhook de github. Los usuarios con permiso
tienen ademas un boton de refrescar en la propia pagina.

## Bloques de aviso

Los `:::` son de osu-wiki, no markdown estandar:

    ::: Tip
    Lo importante.
    :::

Valen `Tip`, `Note`, `Warning` y `Danger`.
