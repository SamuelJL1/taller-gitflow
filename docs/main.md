# Documento de Pruebas

## 1. Descripcion del Sistema

## 2. Requerimientos a Evaluar
### Requerimiento Funcional 02 – Código de Estudiante

### 1. Análisis del requerimiento

El sistema debe permitir al usuario tener un codigo unico de estudiantes con las siguientes ensepecificaciones:

1. Tener exactamente 8 caracteres.
2. Iniciar con la letra "E".
3. Los 7 caracteres restantes deben ser numéricos (0–9).

Esto implica que:
- No puede tener menos ni más de 8 caracteres.
- No puede iniciar con otra letra.
- No puede contener letras después de la primera posición.
- No puede tener símbolos ni espacios.

---


## 3. Tecnicas de Prueba Aplicadas

### 2. Técnica de prueba seleccionada RF2

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

###  4. Casos de prueba RF2

#### Casos válidos

| Caso | Entrada     | Resultado Esperado |
|------|------------|-------------------|
| 1 | E1234567 | Válido |
| 2 | E0000000 | Válido |
| 3 | E9876543 | Válido |

Todos cumplen:
- 8 caracteres  
- Inician por E  
- 7 números después  

---
#### Casos inválidos

##### Longitud incorrecta

| Entrada | Resultado Esperado | Motivo |
|----------|-------------------|--------|
| E123456  | Inválido | 7 caracteres |
| E12345678 | Inválido | 9 caracteres |

---

##### No inicia con E

| Entrada | Resultado Esperado | Motivo |
|----------|-------------------|--------|
| A1234567 | Inválido | No inicia con E |
| 12345678 | Inválido | No inicia con E |

---

##### Caracteres no numéricos después de la E

| Entrada | Resultado Esperado | Motivo |
|----------|-------------------|--------|
| E1234A67 | Inválido | Contiene letra |
| E1234-67 | Inválido | Contiene símbolo |
| E1234 67 | Inválido | Contiene espacio |

---

##### E en minúscula (si el sistema distingue mayúsculas y minúsculas)

| Entrada | Resultado Esperado | Motivo |
|----------|-------------------|--------|
| e1234567 | Inválido | No cumple formato requerido |

---

Se cubren:

- Clases válidas
- Errores de longitud
- Errores de formato
- Errores de tipo de carácter
- Posible error por mayúscula/minúscula

La cobertura es adecuada porque se prueba al menos un representante de cada partición válida e inválida.

## 5. Trazabilidad

## 6. Gestion de Versiones (GitFlow)
