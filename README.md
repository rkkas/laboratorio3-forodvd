# Laboratorio 3 de Criptografía y Seguridad en Redes

Francisco Antonio Tapia Canales · CIT2113 · Sección 4 · Profesor Brayan Espina.
Correo: francisco.tapia1@mail.udp.cl.
Práctica realizada el 22 de octubre de 2026 en una cuenta propia de ForoDVD.

Repositorio: https://github.com/rkkas/laboratorio3-forodvd

El registro y el inicio de sesión enviaron MD5 calculado en el navegador.
El control con contraseña incorrecta fue rechazado. Al sustituir sus dos hashes por el MD5 correcto, se abrió una sesión con la cuenta de prueba.

## Informe y revisión

- [Informe PDF](informe/Informe_Laboratorio_3.pdf)
- [Fuente LaTeX](informe/lab03_informe.tex)
- [Verificación de los siete criterios de la rúbrica](docs/RUBRICA.md)
- [Procedimiento y resultados](docs/PROCEDIMIENTO.md)
- [Fuentes públicas](docs/FUENTES.md)

## Evidencias

### 2.1 Registro

![E01_registro_md5.png](evidencias/E01_registro_md5.png)
![E01_registro_confirmacion.png](evidencias/E01_registro_confirmacion.png)

### 2.2 Inicio de sesión

![E02_login_md5.png](evidencias/E02_login_md5.png)
![E02_login_md5_utf.png](evidencias/E02_login_md5_utf.png)

### 2.3 Consola del navegador

![E03_consola.png](evidencias/E03_consola.png)

### 2.4 Interceptación de login

![E04_intercept.png](evidencias/E04_intercept.png)
![E04_hash_incorrecto.png](evidencias/E04_hash_incorrecto.png)

### 2.5 Acceso mediante sustitución del hash

![E05_control_login_correcto.png](evidencias/E05_control_login_correcto.png)
![E06_control_login_incorrecto.png](evidencias/E06_control_login_incorrecto.png)
![E07_solicitud_modificada.png](evidencias/E07_solicitud_modificada.png)
![E08_resultado_hash.png](evidencias/E08_resultado_hash.png)

### Cierre con cambio de contraseña

![Confirmación de actualización](evidencias/E09_cambio_contrasena.png)

Los originales completos permanecen fuera del repositorio. Los archivos entregables incluyen únicamente las capturas seleccionadas y los recortes necesarios.

## Archivos de apoyo

- scripts/hash_en_consola.js contiene el comando usado en la consola de ForoDVD.
- evidencias/manifest.json registra las huellas SHA-256 de las imágenes.
- evidencias/procedencia_recortes.json identifica el origen y el rectángulo de cada recorte.

## Compilar la fuente

Desde la raíz del repositorio, con una instalación de LaTeX:

    pdflatex -interaction=nonstopmode -halt-on-error -output-directory=informe -jobname=Informe_Laboratorio_3 informe/lab03_informe.tex
    pdflatex -interaction=nonstopmode -halt-on-error -output-directory=informe -jobname=Informe_Laboratorio_3 informe/lab03_informe.tex

El PDF de entrega se compila directamente desde esta fuente LaTeX. Las dos pasadas actualizan el índice y los enlaces. Se deben conservar las carpetas `informe/` y `evidencias/` al compilar.

## Alcance

La cuenta permaneció pendiente de activación por correo para participar.
La práctica demuestra la reutilización del hash en el flujo probado y no permite inferir el almacenamiento interno del servidor.
El cambio de contraseña se envió al finalizar y el sitio confirmó la actualización.
