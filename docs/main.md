# Documento de Pruebas

## 1. Descripcion del Sistema

## 2. Requerimientos a Evaluar

## 3. Tecnicas de Prueba Aplicadas

## 4. Casos de Prueba Diseñados
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
| CP-18  | Sí           | Sí       | No            | Permitir   |
| CP-19  | No           | Sí       | No            | Rechazar   |
| CP-20  | Sí           | No       | No            | Rechazar   |
| CP-21  | Sí           | Sí       | Sí            | Rechazar   |
| CP-22  | No           | No       | No            | Rechazar   |
| CP-23  | No           | Sí       | Sí            | Rechazar   |
| CP-24  | Sí           | No       | Sí            | Rechazar   |
| CP-25  | No           | No       | Sí            | Rechazar   |

## 5. Trazabilidad

## 6. Gestion de Versiones (GitFlow)
