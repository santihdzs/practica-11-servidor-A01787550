# Bitácora · Anexo P11 · A01787550

## Ejercicio 0 · Fixtures

1. Si todas usaran `ana`, la segunda prueba falla al registrarla (409, ya existe), y la segunda corrida de pytest también. Con el sufijo cada prueba tiene sus personas y corren en cualquier orden.
2. Se gana: se prueba lo que de verdad hace el servidor con PostgreSQL real (constraints, permisos). Se pierde: velocidad, y hace falta Docker encendido.

## Ejercicio B4 · La carrera

- No se ejecuta el `except IntegrityError`: solo corre si dos envíos con la misma clave pasan `ya_publicado` al mismo tiempo.
- Prueba: varios threads que mandan el mismo POST con la misma clave a la vez (un `threading.Barrier` los suelta juntos), repetido varias veces; al final debe haber un solo aviso por clave.
