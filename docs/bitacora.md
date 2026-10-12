# Bitácora · Anexo P11 · A01787550

## Ejercicio 0 · Fixtures

1. Si todas usaran `ana`, la segunda prueba falla al registrarla (409, ya existe), y la segunda corrida de pytest también. Con el sufijo cada prueba tiene sus personas y corren en cualquier orden.
2. Se gana: se prueba lo que de verdad hace el servidor con PostgreSQL real (constraints, permisos). Se pierde: velocidad, y hace falta Docker encendido.

## Ejercicio B4 · La carrera

- No se ejecuta el `except IntegrityError`: solo corre si dos envíos con la misma clave pasan `ya_publicado` al mismo tiempo.
- Prueba: varios threads que mandan el mismo POST con la misma clave a la vez (un `threading.Barrier` los suelta juntos), repetido varias veces; al final debe haber un solo aviso por clave.

## Ejercicio D2 · Tres filas del reto (Sonrisas de Cristal)

| ID | Requisito | Criterio de aceptación | Resultado | Estado | Prueba o evidencia |
| --- | --- | --- | --- | --- | --- |
| RF-01 | Acceso con dos tipos de perfil (seguridad) | Un familiar que intenta registrar la entrada de un niño recibe 403 y no se guarda nada | Sin probar | Pendiente: el backend todavía no está integrado | Ninguna todavía |
| RF-03 | Registro de entrada y salida (funcional) | Al registrar la llegada, el niño aparece en la lista de su sala con la hora de entrada | Sin prueba automatizada | Parcialmente cumplido: funciona en la UI con datos locales, sin backend ni prueba | Capturas del recorrido (Entrega 2) |
| RNF (Planner) | No guardar contraseñas, tokens ni llaves en texto plano (no demostrable hoy) | En la base el hash empieza con `$argon2id$`; en el teléfono el token no aparece en claro | Sin probar | Pendiente: no hay backend ni almacenamiento seguro todavía | Ninguna todavía |
