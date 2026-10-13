# Prueba Clase 3 — TS-01: Registro de usuarios

Paquete preparado para subir a un repositorio GitHub. Contiene los casos CP-01, CP-02 y CP-03 por separado, la app original v1, una copia corregida v2 para comprobar el resultado esperado y evidencias de ambas versiones.

## Contenido

- `app/registro_v1_original.html`: app entregada en la actividad, conservada sin modificar.
- `app/registro_v2_corregida.html`: copia de pruebas con RF-02 (correo obligatorio) y RF-03 (mínimo 8 caracteres) activadas. En esta copia la contraseña ficticia se ve en texto para que la captura permita demostrar que `Abcd123` tiene siete caracteres.
- `issues/CP-01.md`, `issues/CP-02.md`, `issues/CP-03.md`: texto completo de cada Issue.
- `.github/ISSUE_TEMPLATE/`: plantillas separadas para crear los tres Issues.
- `evidencias/CP-*_evidencia_v2.png`: capturas del resultado esperado según cada caso.
- `evidencias/v1_observado/`: capturas de lo que ocurre al ejecutar los mismos datos en la app original.

## Importante: v1 frente a v2

Las capturas que se incrustan en la hoja `Casos` son del **resultado esperado en la v2 corregida**, porque muestran los mensajes y contadores que especifica el enunciado. La aplicación original v1 tiene `VALIDAR_CORREO_Y_LONGITUD = false`; por eso CP-02 y CP-03 realmente fallan en ella y crean una cuenta. Las capturas de `evidencias/v1_observado/` documentan ese comportamiento real. No deben confundirse las capturas de resultado esperado con la ejecución de v1.

## Cómo publicar los casos en GitHub

1. Ingrese a GitHub y cree un repositorio nuevo, por ejemplo `prueba-clase-3-ts-01`.
2. Descomprima el ZIP. Entre en la carpeta `clase3_github/` y cargue **el contenido de esa carpeta en la raíz del repositorio** (no la carpeta contenedora como subcarpeta). Mantenga `.github/ISSUE_TEMPLATE/` en esa ruta exacta para que GitHub detecte las plantillas.
3. Abra **Issues → New issue** y seleccione por separado las plantillas CP-01, CP-02 y CP-03. Si GitHub no muestra las plantillas inmediatamente, abra el archivo Markdown correspondiente en `issues/` y copie su contenido al nuevo Issue.
4. Adjunte las capturas relacionadas: en CP-02 y CP-03, incluya la evidencia observada en v1 y el resultado esperado en v2 corregida.
5. Cree cada Issue y copie su URL real en la columna amarilla **Enlace GitHub** de la hoja `Casos` del Excel.

## Casos en breve

### CP-01 — Registro válido
- Datos: `Ana` / `ana@example.com` / `Abcd1234`.
- Esperado: `Registro exitoso`, cuenta `Sí`, total `1` y último registro con Ana.

### CP-02 — Correo vacío
- Datos: `Ana` / correo vacío / `Abcd1234`.
- Esperado: `El correo es obligatorio`, cuenta `No`, total `0`.
- Comportamiento observado en v1: incorrectamente acepta el registro.

### CP-03 — Contraseña de siete caracteres
- Datos: `Ana` / `ana@example.com` / `Abcd123`.
- Esperado: error de mínimo ocho caracteres, cuenta `No`, total `0`.
- Comportamiento observado en v1: incorrectamente acepta el registro.

## Nota sobre el Excel

Solo se ha diligenciado la hoja `Casos`; `Ejecuciones` y `Defectos` se dejan sin diligenciar por ahora, tal como se solicitó. Los enlaces amarillos están pendientes porque las URLs reales solo existen después de crear los Issues en el repositorio del usuario.
