# Guía de sustentación · Tema 06

**Inteligencia Artificial**  
Integrante solicitante (nombre por completar), Juan Esteban Gallego y Luis Esteban Ospina.

## Agenda de 15 minutos

| Tiempo | Intervención propuesta | Material |
|---|---|---|
| 0:00–3:00 | Integrante solicitante · Plantear el caso de atención universitaria, la pregunta y el criterio de éxito. Mostrar qué se redondea en INT8. | Diapositivas 1–2 |
| 3:00–6:00 | Juan Esteban Gallego · Explicar los tres conjuntos, el etiquetado por petición principal y el diseño pareado. Explicar por qué las repeticiones sirven para medir tiempo. | Diapositiva 3 |
| 6:00–10:00 | Luis Esteban Ospina · Exponer métricas, comparar dificultades, explicar los límites y presentar la conclusión. | Diapositivas 4–6 |
| 10:00–12:00 | Presentación conjunta · Mostrar F06 y F23 con texto, etiqueta de referencia y salida. | Diapositiva 7 |
| 12:00–15:00 | Los tres · Responder las preguntas del docente. | Cuaderno y CSV |

## Demostración sin conexión

1. En F06, leer «Cuál es el plazo para renovar la beca de excelencia». Preguntar al público qué trámite corresponde. Mostrar que FP32 e INT8 predicen **BECAS**.
2. En F23, leer «Tengo el certificado de matrícula, solo quiero cambiar la franja de química». Señalar la petición explícita de cambiar una franja. La referencia es **HORARIOS** y ambas condiciones predicen **CERTIFICADOS**.
3. En el CSV final, filtrar por **F06** o **F23** y por repetición **1**. Comparar las dos filas de cada caso y sus tres puntuaciones. La diapositiva 7 contiene el respaldo si no es posible abrir el archivo.
4. Si el kernel ya está listo, usar opcionalmente `predict(final[22][1], models['B'])` para reproducir F23. Reservar el cierre para explicar cómo una comparación controlada con y sin la cláusula inicial pondría a prueba la explicación léxica.

## Preguntas de práctica

| Pregunta | Elementos para responder |
|---|---|
| ¿Qué distingue el estudio del tema general? | Compara dos precisiones de un clasificador específico en CPU. La intervención cambia el almacenamiento de los coeficientes aprendidos. |
| ¿Qué habría contradicho la hipótesis? | Ahorro paramétrico inferior al 70 % o dos o más aciertos perdidos por B frente a A. |
| ¿Cómo se asignaron las etiquetas? | Por la petición pendiente explícita de un texto sintético. Por ejemplo, F25 pide una constancia para renovar una beca y corresponde a CERTIFICADOS. La referencia requiere validación independiente en un estudio posterior. |
| ¿Dónde fallaron más? | Los distractores obtuvieron 5/9. F23 es un caso ilustrativo. Una comparación al retirar la primera cláusula ayudaría a comprobar su efecto. |
| ¿Por qué los pesos más pequeños no fueron más rápidos? | La vectorización domina parte de la ruta y el producto disperso mezcla flotantes e enteros. El reescalado añade una operación. La corrida registra medianas próximas y dispersión solapada. |
| ¿Por qué no afirmar que bajó la RAM del proceso? | Los bytes de los arreglos excluyen el vectorizador y el intérprete. La traza temporal excluye memoria preexistente y algunas asignaciones nativas. Medir RSS aislado respondería otra parte de la pregunta. |
| ¿Qué cambiarían con una semana adicional? | Ampliar el corpus, hacer una anotación doble y verificar peso de distractores mediante pares controlados. |
| ¿Qué hizo cada integrante? | Cada persona debe usar su bitácora real, señalar evidencia y explicar una decisión. El cuaderno declara el trabajo asistido por Codex y deja abiertas las reflexiones personales. |

Antes del ensayo, confirmar el número de grupo, el nombre faltante y el turno. Cada participante debe revisar una fuente primaria, verificar una afirmación del cuaderno y registrar su contribución concreta.
