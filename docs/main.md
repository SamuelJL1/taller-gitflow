# Documento de Pruebas

## 1. Descripcion del Sistema

## 2. Requerimientos a Evaluar

## 3. Tecnicas de Prueba Aplicadas
### RF3-Inscripción a Evento
#### Condiciones

- C1: ¿El estudiante está registrado?
- C2: ¿El evento tiene cupos disponibles?
- C3: ¿El estudiante ya está inscrito?

#### Acciones

- A1: Permitir inscripción
- A2: Rechazar inscripción



#### Tabla de Decisión

| Regla | C1 Registrado | C2 Cupos | C3 Ya inscrito | Resultado |
|--------|--------------|----------|---------------|------------|
| R1     | Sí           | Sí       | No            | Permitir   |
| R2     | No           | Sí       | No            | Rechazar   |
| R3     | Sí           | No       | No            | Rechazar   |
| R4     | Sí           | Sí       | Sí            | Rechazar   |
| R5     | No           | No       | No            | Rechazar   |
| R6     | No           | Sí       | Sí            | Rechazar   |
| R7     | Sí           | No       | Sí            | Rechazar   |
| R8     | No           | No       | Sí            | Rechazar   |

## 4. Casos de Prueba Diseñados

## 5. Trazabilidad

## 6. Gestion de Versiones (GitFlow)
