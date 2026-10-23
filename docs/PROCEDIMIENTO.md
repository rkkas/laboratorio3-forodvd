# Procedimiento y resultados

Fecha de la práctica: 22 de octubre de 2026.
Sitio: https://www.forodvd.com/
Entorno: Ubuntu en VMware Workstation y Burp Suite Community.

1. Se creó una cuenta propia y se capturó POST /register.php?do=addmember.
2. Se observaron password_md5 y passwordconfirm_md5 y sus valores iguales.
3. En la consola de ForoDVD se ejecutó hex_md5 con la contraseña introducida mediante prompt.
4. Se comprobó que el resultado coincidía con el registro y con los dos campos MD5 del login.
5. Se verificó el acceso normal y se cerró la sesión.
6. Se envió una contraseña incorrecta sin cambiar sus hashes y se observó el rechazo.
7. Se repitió el intento incorrecto con Intercept on y se detuvo POST /login.php?do=login.
8. Se reemplazaron vb_login_md5password y vb_login_md5password_utf por el MD5 correcto, conservando los demás datos de la solicitud.
9. Se pulsó Forward y se dejó Intercept off. El sitio mostró el usuario y Finalizar sesión.
10. Se envió el formulario de cambio de contraseña con una nueva y su confirmación; el sitio confirmó la actualización del perfil.

## Comparación de controles

| Control | Valor enviado | Resultado |
| --- | --- | --- |
| Correcto | MD5 de la contraseña correcta | Sesión iniciada |
| Incorrecto | MD5 de otra contraseña | Acceso rechazado |
| Sustitución | Ambos campos reemplazados por el MD5 correcto | Sesión iniciada |

La cuenta mantuvo pendiente la activación por correo para participar.
El sitio anunció cinco intentos y un bloqueo de 15 minutos; no se agotaron los intentos.
No se inspeccionó el almacenamiento de contraseñas del servidor.
No se volvió a probar el hash antiguo después de cambiar la contraseña.

## Lectura de las capturas

Los recortes conservan el texto y los resultados visibles de las capturas originales.
Se excluyeron del material entregable las zonas que contenían contraseñas, correo, cookies y tokens.
La procedencia de los recortes está registrada en evidencias/procedencia_recortes.json.
No se incluyen exportaciones completas de sesión ni solicitudes con credenciales nuevas.
