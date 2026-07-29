# torii-wiki

La wiki de Torii, en el formato que espera osu-web.

Las ocho paginas de `wiki/` salen de las paginas de React de
`torii-lazer-web/src/pages/wiki` con `torii-wiki-convert.py` del fork de
osu-web. El texto es el mismo, no se reescribio: solo cambia el envoltorio.

Las de `wiki/Legal/` NO: esas se escriben a mano aca y no tienen original en el
spa. **No borres `wiki/` entero antes de regenerar**, que te llevas los tres
archivos legales. El script sobreescribe lo suyo y no necesita que le limpien
nada.

## Como la lee osu-web

osu-web no guarda la wiki en la base. Le pide los archivos a la api de contents
de github, los renderiza y los deja en elasticsearch. La ruta de una pagina sale
del path del archivo:

    wiki/Rules/en.md        ->  /wiki/en/Rules
    wiki/Torii_points/en.md ->  /wiki/en/Torii_points

Las de Legal salen por otra ruta, aunque el pipeline sea el mismo: las lee
`LegalController` y van al pie de todas las paginas del sitio.

    wiki/Legal/Terms/en.md  ->  /legal/en/Terms

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

    ::: alert-tip
    Lo importante.
    :::

Valen `alert-tip`, `alert-note`, `alert-notice`, `alert-warning` y
`alert-caution`, y nada mas: la lista esta en `style_block_allowed_classes` del
preset `wiki` de `OsuMarkdown`. Si le pones otro nombre, el parser tira el
envoltorio y deja el texto suelto sin avisar.
