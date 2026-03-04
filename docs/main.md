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
Plataforma de Gestion de eventos universitario.

La plataforma permite:

1.Registro de estudiantes.

2.Validación de código estudiantil.

3.Inscripción a eventos.


## 3. Tecnicas de Prueba Aplicadas
### RF1
La tecnica usada seria pruebas por valor limite: 
Porque basicamente el Rf01 usa valores numericos y tiene un limite inferior y superior entonces el mejor a usar es el valor limite.

### RF2
Se utilizarán:

- Partición de equivalencia
- Análisis de valores límite

#### Partición de equivalencia

Permite dividir las entradas en:

- Clases válidas
- Clases inválidas (por longitud, formato o contenido)

Así se prueban representantes de cada grupo sin necesidad de evaluar todas las combinaciones posibles.


#### Análisis de valores límite

El requisito exige exactamente 8 caracteres, por lo tanto:

- 7 caracteres → inválido  
- 8 caracteres → válido  
- 9 caracteres → inválido  

Esto permite detectar errores comunes en validaciones de longitud.

### RF3
#### Tabla de Decision
Se selecciona esta tecnica porque el requerimiento establece múltiples condiciones booleanas que deben cumplirse simultáneamente para permitir la inscripción. La decisión final depende de la combinación de estas condiciones y no de un único dato de entrada. Esta técnica permite representar de manera estructurada todas las posibles combinaciones y garantizar una cobertura completa de las reglas del negocio.

## 4. Casos de Prueba Diseñados

### Valor limite del RF-01: 

| Numero de caso | Entrada   | valor esperado |
|----------------|-----------|----------------|
| Caso 1         | 15 años   | invalido       |
| Caso 2         | 16 años   | valido         |
| Caso 3         | 20 años   | valido         |
| Caso 4         | 30 años   | valido         |
| Caso 5         | 65 años   | valido         |
| Caso 6         | 66 años   | invalido       |

Se garantiza la cobertura completa del requerimiento RF-01 mediante la aplicación de partición de equivalencia y análisis de valores límite.




###  4. Casos de prueba RF2

#### Casos válidos

| Caso | Entrada     | Resultado Esperado |
|------|------------|-------------------|
| 7 | E1234567 | Válido |
| 8 | E0000000 | Válido |
| 9 | E9876543 | Válido |

Todos cumplen:
- 8 caracteres  
- Inician por E  
- 7 números después  

---
#### Casos inválidos

##### Longitud incorrecta

| Caso | Entrada | Resultado Esperado | Motivo |
|-----|-----|-------------------|--------|
| 10 | E123456  | Inválido | 7 caracteres |
| 11 | E12345678 | Inválido | 9 caracteres |

---

##### No inicia con E

| Caso | Entrada | Resultado Esperado | Motivo |
|------|----------|-------------------|--------|
| 12 | A1234567 | Inválido | No inicia con E |
| 13 | 12345678 | Inválido | No inicia con E |

---

##### Caracteres no numéricos después de la E

| Caso | Entrada | Resultado Esperado | Motivo |
|------|---------|--------------------|--------|
| 14 | E1234A67 | Inválido | Contiene letra |
| 15 | E1234-67 | Inválido | Contiene símbolo |
| 16 | E1234 67 | Inválido | Contiene espacio |

---

##### E en minúscula (si el sistema distingue mayúsculas y minúsculas)

| Caso | Entrada | Resultado Esperado | Motivo |
|-----|-----|-------------------|--------|
| 17 | e1234567 | Inválido | No cumple formato requerido |

---

Se cubren:

- Clases válidas
- Errores de longitud
- Errores de formato
- Errores de tipo de carácter
- Posible error por mayúscula/minúscula

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

La cobertura es adecuada porque se prueba al menos un representante de cada partición válida e inválida.

## 5. Trazabilidad
| Requerimiento | Técnica | Casos Asociados |
|--------------|---------|----------------|
| RF-01 | Valor Limite | CP-01, CP-02, CP-03, CP-04, CP-05, CP-06|
| RF-02 | Partición de equivalencia - Análisis de valores límite | CP-07, CP-08,CP-09,CP-10,CP-11,CP-12,CP-13,CP-14,CP-15,CP-16,CP-17 |
| RF-03 | Tabla de desicion | CP-18, CP-19,CP-20,CP-21,CP-22,CP-23,CP-24,CP-25 |
## 6. Gestion de Versiones (GitFlow)

## Ramas Creadas

Se implementó el modelo GitFlow utilizando las siguientes ramas:

- **main:** Rama principal que contiene la versión estable del proyecto.
- **develop:** Rama de integración donde se consolidan los avances de desarrollo.
- **feature/RF1:** Implementación del requerimiento funcional RF-01.
- **feature/RF2:** Implementación del requerimiento funcional RF-02.
- **feature/RF3:** Implementación del requerimiento funcional RF-03.
- **feature/trazabilidad:** Implementación de la matriz de trazabilidad del proyecto.

---

## Flujo Seguido

Se trabajó bajo el modelo GitFlow.  
Cada requerimiento funcional fue desarrollado en su propia rama `feature`, creada a partir de `develop`.  
Una vez finalizado el desarrollo y realizadas las pruebas correspondientes, los cambios fueron integrados a la rama `develop`.  
Finalmente, cuando el sistema alcanzó un estado estable, se realizó la integración hacia la rama `main`.

---

## Integración de Cambios

La integración se realizó mediante **pull requests** desde cada rama `feature` hacia `develop`, permitiendo la revisión previa del código antes de su consolidación.  
Posteriormente, se realizó el merge desde `develop` hacia `main` para publicar la versión estable del sistema.

---

## Conflictos y Resolución

Durante la integración de algunas ramas feature se presentaron conflictos menores debido a modificaciones simultáneas en archivos compartidos.  
Estos conflictos fueron resueltos manualmente revisando las diferencias entre versiones, asegurando que no se perdiera funcionalidad y validando el correcto funcionamiento del sistema antes de confirmar el merge.
