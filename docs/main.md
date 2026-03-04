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




## 5. Trazabilidad

## 6. Gestion de Versiones (GitFlow)
