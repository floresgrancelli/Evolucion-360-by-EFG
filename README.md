# Evolución 360 by EFG — Demo interactiva

**Estado:** Prototipo demostrativo con datos enteramente ficticios. No es un producto sanitario ni recibe telemetría real.

## Cómo abrirla

- **Opción rápida:** abrir `Evolucion_360_by_EFG_demo.html` en Chrome, Safari u otro navegador actualizado de escritorio. No requiere instalar Python ni conectarse a ninguna plataforma.
- **Para alojarla como una página independiente:** utilizar `index.html` del ZIP en un repositorio **nuevo** y habilitar una plataforma de hosting estático, por ejemplo GitHub Pages. No mezclarlo con repositorios existentes.
- Funciona sin conexión a internet y **sin depender de un servidor**, salvo las restricciones que pudiera imponer un visor de archivos de dispositivos móviles. Para una mejor experiencia en iPhone, alojar el HTML como página web normal en el siguiente paso.

## Escenario

- 10 participantes **ficticios**: 5 mujeres y 5 hombres con parámetros iniciales distintos.
- 12 semanas, exactamente **2 sesiones full body por semana** para cada uno: **24 sesiones por paciente / 240 programadas en total**.
- Sesiones completadas en el conjunto sintético: **208 asistencias ficticias** (87 %); restantes marcadas como ausencias. **Este total grupal no se muestra como indicador principal**, porque la experiencia se centra en el seguimiento de cada paciente.
- 4 evaluaciones antropométricas y funcionales (semanas 0, 4, 8 y 12).
- Dos rutinas A/B adaptables por ejercicio con 7 segmentos por sesión.
- Variaciones simuladas de carga, frecuencia cardíaca y percepción de esfuerzo; no son mediciones clínicas.

## Secciones

1. **Panel general:** vista centrada en una persona elegible: asistencia hasta semana seleccionada, peso, carga de fuerza y última FC media; curvas individuales de peso y prensa, asistencia semanal A/B y lista de perfiles. No muestra el total de sesiones grupales.
2. **Pacientes:** perfiles, cambios antropométricos, fuerza y asistencia; formularios para editar participante y mediciones.
3. **Full body:** selección de semana, paciente y rutina A/B, registro completo por ejercicio; editar cada bloque y la sesión.
4. **PULSE demo:** monitor virtual de los 10 participantes, FC minuto a minuto simulada, RPE, minutos × RPE, calorías sintéticas por segmento.
5. **Resultados:** los indicadores principales son individuales (asistencia/24, evolución de peso o prueba funcional, carga de fuerza, FC media y carga interna); la tabla comparativa del grupo se oculta de manera predeterminada y puede desplegarse como información secundaria.
6. **Datos y PULSE:** importar CSV con mapeo de columnas, editar/exportar JSON, exportar sesiones CSV y reiniciar escenario.

## Importación PULSE

La app **no está conectada directamente a PULSE**. El primer puente implementado es un CSV descargado o preparado por el usuario. La app permite mapear las columnas sin suponer un formato oficial. Ejemplo de archivo:

```csv
patient_id,week,kind,hr_mean,hr_max,kcal_est,duration
P01,8,A,125,150,275,50
```

- `patient_id` identifica al paciente ficticio existente (P01–P10), o utilizar su nombre simulado.
- `week` es 1–12, `kind` es A o B.
- Las métricas incluyen FC media, FC máxima, kcal estimadas y minutos.
- Importar **sustituye las métricas de esa sesión demo** y marca su fuente como `PULSE_CSV`; no agrega ni inventa curvas minuto a minuto si el CSV no las contiene.
- Esta importación requiere que el archivo contenga las columnas necesarias. Es un **ejemplo**, no una afirmación del esquema de exportación real de PULSE. Para automatizar la conexión deberá confirmarse si el proveedor ofrece API oficial, credenciales y autorización para reutilizar datos.
- La app distingue la FC de la carga mecánica y etiqueta las calorías como **estimaciones**, no como gasto energético medido directamente.

## Edición y privacidad

- Todos los nombres, pesos, estaturas, sesiones, ejercicios y valores de demostración son sintéticos.
- Se puede editar sin contraseña, pero cada visitante modifica **su propia copia local**; no cambia la vista de los demás usuarios.
- Se intenta guardar en el almacenamiento local del navegador. Su disponibilidad depende del navegador y de si el HTML se abre como archivo o sitio web. **Exportar JSON** sirve para transportar o respaldar las modificaciones.
- El botón **Restablecer simulación** recupera los datos originales deterministas.
- No ingresar información real de pacientes: la demo pública **no posee medidas de seguridad sanitarias**, consentimiento ni roles.

## Limitaciones científicas

Los indicadores son simulaciones para probar el flujo visual y la edición. Ni FC ni calorías deben tratarse como medida directa de esfuerzo muscular; los ejemplos de masa libre de grasa, grasa porcentual y pruebas funcionales no provienen de DXA, BIA ni tests reales. Toda recomendación real debería supervisarse por profesionales competentes y ajustarse al estado clínico individual.

## Proyecto aislado

Este paquete corresponde a **Evolución 360 by EFG**. No modifica **EFG Training** ni **Edu Flores Grancelli Lab**.
