# 🚖 Proyecto 2 – Diseño de pruebas de Urban Routes  

## 📌 Descripción  
En este proyecto trabajé sobre la funcionalidad de **compartir automóvil** de la aplicación Urban Routes.  
El objetivo fue **analizar requisitos, identificar zonas grises y diseñar pruebas** aplicando técnicas de QA.  

Las tareas principales incluyeron:  
- Análisis y descomposición de requisitos.  
- Identificación de zonas grises en la documentación.  
- Creación de un **mapa mental** para la función *Agregar licencia de conducir*.  
- Definición de **clases de equivalencia y valores límite** para validar los campos *Nombre* y *Apellido*.  
- Elaboración de un **diagrama de flujo** para la lógica de cálculo de duración y precio.  
- Diseño de **casos de prueba documentados en Google Sheets**.  

---

## 🛠️ Stack y herramientas utilizadas  
- **Técnicas de QA:** Partición de clases de equivalencia, análisis de valores límite, diseño de casos de prueba.  
- **Diagramación:** Draw.io (mapa mental y diagrama de flujo).  
- **Documentación:** Google Sheets y Google Docs.  

---

## 📊 Resultados  

### ✔️ Validación de campos (Nombre y Apellido)  
- Se definieron límites entre **2 y 14 caracteres**.  
- Se validó que solo se acepten **letras del alfabeto latino y espacios**.  
- Se probaron entradas con guiones, símbolos y caracteres no permitidos → correctamente rechazados.  
- Se detectaron **zonas grises** en el comportamiento frente a guiones en nombres/apellidos.  

### ✔️ Validación de distancia y hora de salida  
- **Distancia = 0 km:** el sistema devuelve correctamente precio y duración en 0.  
- **Distancia > 0 km:** se probaron casos cortos (0.89 km), intermedios (1.3 km) y largos (4.7 km).  
- **Hora de salida:**  
  - Madrugada (00:01–08:00) → 45 km/h  
  - Mañana (08:01–12:00) → 30 km/h  
  - Tarde (12:01–18:00) → 40 km/h  
  - Atardecer (18:01–22:00) → 25 km/h  
  - Noche (22:01–00:00) → 45 km/h  

### ✔️ Casos de prueba de cálculo (ejemplos)  
| ID   | Escenario | Distancia | Velocidad | Duración estimada | Precio estimado | Estado |
|------|-----------|-----------|-----------|------------------|-----------------|--------|
| P-1  | Viaje 00:01–08:00 | 0.89 km | 45 km/h | ≈ 1.19 min | $0.12 | ❌ No aprobado |
| P-2  | Viaje 09:00 | 1.3 km | 30 km/h | ≈ 2.6 min | $0.26 | ❌ No aprobado |
| P-3  | Viaje 14:20 | 0.89 km | 40 km/h | ≈ 1.34 min | $0.13 | ❌ No aprobado |
| P-4  | Viaje 19:14 | 0.89 km | 25 km/h | ≈ 2.14 min | $0.21 | ❌ No aprobado |
| P-5  | Viaje 23:00 | 1.5 km | 45 km/h | ≈ 2 min | $0.22 | ❌ No aprobado |
| P-6  | Distancia = 0 km | 0 km | 30 km/h | 0 min | $0.00 | ✅ Aprobado |

📌 **Hallazgos clave:**  
- El sistema **no calcula correctamente** la duración ni el precio en la mayoría de los escenarios probados.  
- Únicamente el caso de **distancia cero** fue aprobado.  
- Se recomienda revisión del algoritmo de cálculo de la aplicación.  

---

## 📎 Documentación  
📄 [[Mapa mental en PDF](https://drive.google.com/file/d/1BHuCDdV549O-XL4h1JMoJXrhiNOam_2S/view?usp=sharing)](#)  
📄 [[Diagrama de flujo en PDF](https://drive.google.com/file/d/1hz1fPRx76tAm0W3hFggSMPxjBBDsc0dU/view?usp=sharing)](#)  
📄 [[Casos de prueba en Google Sheets](https://docs.google.com/spreadsheets/d/1S4ByOc3d1arT1hRp3dx6XKBDoE8wI2ts/edit?usp=sharing&ouid=112657294087284506568&rtpof=true&sd=true)](#)  


---

✍️ **Autora:** Monica Vasco Dominguez – QA Engineer  
