# Documento de Pruebas

## 1. Descripcion del Sistema
Plataforma de Gestion de eventos universitario.

La plataforma permite:

1.Registro de estudiantes.

2.Validación de código estudiantil.

3.Inscripción a eventos.

## 2. Requerimientos a Evaluar
### RF-01 regitros de estudiantes 



## 3. Tecnicas de Prueba Aplicadas
La tecnica usada seria pruebas por valor limite: 
Porque basicamente el Rf01 usa valores numericos y tiene un limite inferior y superior entonces el mejor a usar es el valor limite.

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

---

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

## 6. Gestion de Versiones (GitFlow)
