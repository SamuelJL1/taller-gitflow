# Documento de Pruebas

## 1. Descripcion del Sistema
### Plataforma de Gestión de Eventos Universitarios

La plataforma permite:

- Registro de estudiantes.
- Validación de código estudiantil.
- Inscripción a eventos.

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
| RF-01 | Valor Limite | CP-01, CP-02, CP-03, CP-04, CP-05, CP-06|
| RF-02 | Partición de equivalencia - Análisis de valores límite | CP-07, CP-08,CP-09,CP-10,CP-11,CP-12,CP-13,CP-14,CP-15,CP-16,CP-17 |
| RF-03 | Tabla de desicion | CP-18, CP-19,CP-20,CP-21,CP-22,CP-23,CP-24,CP-25 |
## 6. Gestion de Versiones (GitFlow)
