# Documento de Pruebas

## 1. Descripcion del Sistema

## 2. Requerimientos a Evaluar
### RF-01 Registro de Estudiante:

- El sistema debe permitir el registro de estudiantes cuya edad esté entre 16 y 65 años inclusive.

### RF-02 Código de Estudiante:

El código del estudiante debe:

- Tener exactamente 8 caracteres.
- Iniciar con la letra “E”.
- Los 7 caracteres restantes deben ser numéricos.

### RF-03 Inscripción a Evento
Un estudiante podrá inscribirse a un evento solo si:

- Está registrado.
- El evento tiene cupos disponibles.
- No está previamente inscrito.
- Si alguna condición no se cumple, el sistema no debe permitir la inscripción.

## 3. Tecnicas de Prueba Aplicadas

## 4. Casos de Prueba Diseñados

## 5. Trazabilidad
| Requerimiento | Técnica | Casos Asociados |
|--------------|---------|----------------|
| RF-01 | Valor Limite | CP-01, CP-02 |
| RF-02 | Partición de equivalencia - Análisis de valores límite | CP-03, CP-04 |
| RF-03 | Tabla de desicion | CP-05, CP-06 |
## 6. Gestion de Versiones (GitFlow)
