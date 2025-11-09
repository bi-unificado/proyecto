# Exposición a Material Particulado Fino ($PM_{2.5}$) y Bajo Peso al Nacer en Bogotá: Un Estudio de Inteligencia de Negocios Aplicada a Salud Ambiental

**Proyecto de Investigación en Salud Ambiental**
IN & EDC - 202502

---

## Resumen

Este estudio analiza la asociación entre la exposición anual a material particulado fino ($PM_{2.5}$) y la proporción de recién nacidos con bajo peso al nacer en las localidades de Bogotá durante el año 2022. Utilizando datos integrados de la Red de Monitoreo de Calidad del Aire de Bogotá (RMCAB), el Observatorio de Salud de Bogotá (SaluData) y el Departamento Administrativo Nacional de Estadística (DANE), se implementó un modelo dimensional tipo estrella para soportar análisis inferencial mediante intervalos de confianza y pruebas de hipótesis.

La investigación clasifica las localidades según percentiles de exposición ($\geq p_{75}$ = alta exposición; $\leq p_{25}$ = baja exposición) y compara las proporciones de bajo peso al nacer (<2,500 g según definición de la OMS) ajustando por variables de confusión: sexo del recién nacido, edad materna promedio y nivel socioeconómico. Los resultados buscan identificar grupos vulnerables y guiar políticas de salud pública materno-infantil basadas en evidencia.

---

## 1. Introducción

### 1.1 Contexto del Problema

La exposición prenatal a contaminantes atmosféricos, particularmente al material particulado fino ($PM_{2.5}$), representa un factor de riesgo significativo para la salud materno-infantil. El bajo peso al nacer, definido por la Organización Mundial de la Salud (OMS) como un peso inferior a 2,500 gramos, es un indicador crítico de riesgo de mortalidad neonatal, morbilidad infantil y enfermedades crónicas en la vida adulta.

Bogotá, como ciudad con más de 8 millones de habitantes, presenta variaciones geográficas importantes en la calidad del aire, determinadas por factores como el tráfico vehicular, la actividad industrial y las condiciones meteorológicas. Estas diferencias en la exposición ambiental pueden traducirse en inequidades en los resultados de salud perinatal entre localidades.

### 1.2 Pregunta de Investigación

¿Existe una diferencia significativa en la proporción de recién nacidos con bajo peso al nacer entre las localidades de Bogotá con mayor y menor exposición anual a $PM_{2.5}$ durante el año 2022?

### 1.3 Relevancia del Estudio

Este proyecto integra técnicas de inteligencia de negocios (modelado dimensional, pipelines ETL, visualización analítica) con métodos de epidemiología ambiental para generar conocimiento accionable. Los hallazgos pueden:

- Identificar localidades prioritarias para intervenciones de salud pública
- Cuantificar el impacto de la contaminación atmosférica en indicadores perinatales
- Fundamentar políticas ambientales con análisis estadístico robusto
- Demostrar la aplicabilidad de arquitecturas de datos en el sector salud

---

## 2. Marco Teórico

### 2.1 Evidencia Científica sobre $PM_{2.5}$ y Peso al Nacer

#### 2.1.1 Estudios Internacionales

**Leung et al. (2022)** llevaron a cabo una investigación en Massachusetts (EE. UU.) analizando la relación entre niveles de $PM_{2.5}$ durante las primeras 16 semanas de embarazo y el desarrollo fetal. Los hallazgos principales incluyen:

- Asociación negativa entre exposición temprana a $PM_{2.5}$ y medidas ecográficas fetales
- Reducción en el peso al nacer incluso en concentraciones por debajo de los límites de seguridad establecidos
- Evidencia de afectación placentaria y nutricional durante períodos críticos del desarrollo

**Balakrishnan et al. (2023)** reportaron resultados del ensayo multicéntrico HAPIN en zonas rurales de Perú, Guatemala, Ruanda e India, encontrando:

- Correlación negativa significativa entre exposición prenatal a $PM_{2.5}$ y peso al nacer
- Relaciones dosis-respuesta similares en contextos socioambientales diversos
- Fortalecimiento del vínculo causal entre contaminación atmosférica y bajo peso al nacer

#### 2.1.2 Mecanismos Biológicos

La literatura científica propone varios mecanismos fisiopatológicos:

1. **Inflamación sistémica materna**: El $PM_{2.5}$ induce respuesta inflamatoria que afecta el intercambio placentario
2. **Estrés oxidativo**: Especies reactivas de oxígeno alteran el desarrollo vascular fetal
3. **Disfunción endotelial**: Compromiso de la perfusión útero-placentaria
4. **Epigenética**: Modificaciones en la expresión génica relacionada con el crecimiento

### 2.2 Bajo Peso al Nacer como Indicador de Salud Pública

De acuerdo con la OMS, el peso bajo al nacer (<2,500 g) se asocia con:

- Mayor riesgo de mortalidad neonatal (primeros 28 días de vida)
- Incremento en hospitalizaciones por causas respiratorias y metabólicas
- Predisposición a enfermedades cardiovasculares y diabetes tipo 2 en la adultez
- Impacto en el desarrollo neurocognitivo y el rendimiento académico

En Colombia, aproximadamente el 9-10% de los nacimientos presentan bajo peso, con variaciones regionales que reflejan inequidades socioeconómicas y ambientales.

---

## 3. Metodología

### 3.1 Diseño del Estudio

Estudio ecológico de base poblacional con diseño transversal, utilizando datos agregados a nivel de localidad para el año 2022 en Bogotá D.C.

### 3.2 Variables del Estudio

#### 3.2.1 Variable Independiente: Exposición a $PM_{2.5}$

**Descripción:** Concentración promedio anual y trimestral de $PM_{2.5}$ en $\mu g/m^3$, obtenida de la Red de Monitoreo de Calidad del Aire de Bogotá (RMCAB) gestionada por el Observatorio Ambiental (I-BOCA).

**Clasificación de Exposición:**

Las localidades se clasificaron según la distribución de percentiles de $PM_{2.5}$ promedio anual:

$$
\text{Categoría de Exposición} =
\begin{cases}
\text{Alta} & \text{si } PM_{2.5} \geq p_{75} \\
\text{Media} & \text{si } p_{25} < PM_{2.5} < p_{75} \\
\text{Baja} & \text{si } PM_{2.5} \leq p_{25}
\end{cases}
$$

Se seleccionaron las localidades con mayor y menor promedio anual de $PM_{2.5}$ para las comparaciones principales.

#### 3.2.2 Variable Dependiente: Bajo Peso al Nacer

**Definición:** Número de nacimientos con peso < 2,500 g (según criterio OMS) dividido por el total de nacidos vivos en cada localidad y trimestre durante 2022.

$$
\text{Proporción de Bajo Peso} = \frac{\text{Nacimientos} < 2,500g}{\text{Total Nacidos Vivos}} \times 100
$$

**Fuente:** Observatorio de Salud de Bogotá (SaluData), Secretaría Distrital de Salud.

#### 3.2.3 Variables de Confusión

Las siguientes variables se consideraron como potenciales confusoras y se incluyeron en los análisis ajustados:

1. **Proporción de nacidos vivos por sexo**
   - Distribución porcentual de nacimientos masculinos y femeninos por localidad y trimestre
   - Justificación: Diferencias biológicas en el peso al nacer según sexo (los varones pesan en promedio 100-150 g más)

2. **Nivel socioeconómico promedio (estrato)**
   - Clasificación socioeconómica de las localidades según estratificación oficial de Bogotá
   - Justificación: Determinante social de salud que influye en acceso a servicios prenatales, nutrición materna y condiciones de vivienda

3. **Edad promedio materna**
   - Edad promedio (en años) de las madres residentes en cada localidad con nacimientos registrados durante 2022
   - Justificación: Edades maternas extremas (<20 años o >35 años) se asocian con mayor riesgo de bajo peso al nacer

4. **Tasa de mortalidad infantil**
   - Muertes en menores de un año por cada 1,000 nacidos vivos
   - Justificación: Indicador de coherencia clínica y contexto de vulnerabilidad sanitaria de la localidad

### 3.3 Fuentes de Datos

#### 3.3.1 Información Ambiental

**I-BOCA (Instituto Distrital de Gestión de Riesgos y Cambio Climático - IDIGER)**

- Portal: [https://iboca.ambientebogota.gov.co](https://iboca.ambientebogota.gov.co)
- Datos: Concentraciones horarias de $PM_{2.5}$ y $PM_{10}$ por estación de monitoreo
- Formato: Archivos Excel con series temporales 2022 (divididos por semestre)
- Cobertura: 12 localidades con estaciones fijas (se excluyeron estaciones móviles)

**Mapeo Estación-Localidad:**

Las estaciones de monitoreo se asignaron a localidades mediante análisis del nombre de la estación (e.g., "Kennedy - Carvajal" → Localidad Kennedy). Se utilizaron expresiones regulares para normalizar nombres y excluir estaciones móviles que no tienen asignación geográfica fija.

#### 3.3.2 Información de Salud y Demografía

**SaluData - Observatorio de Salud de Bogotá**

- Portal: [https://saludata.saludcapital.gov.co](https://saludata.saludcapital.gov.co)
- Datos obtenidos:
  - Bajo peso al nacer por localidad
  - Natalidad y distribución por sexo del recién nacido
  - Tasa de fecundidad por edad de la madre
  - Mortalidad infantil (menores de un año)
- Formato: CSV con delimitador punto y coma, codificación UTF-8

**DANE - Departamento Administrativo Nacional de Estadística**

- Cuadro de nacimientos por grupos de edad de la madre, Bogotá 2022
- Fuente: [https://www.dane.gov.co/index.php/estadisticas-por-tema/salud/nacimientos-y-defunciones/nacimientos/nacimientos-2022](https://www.dane.gov.co/index.php/estadisticas-por-tema/salud/nacimientos-y-defunciones/nacimientos/nacimientos-2022)
- Utilizado para: Cálculo de edad materna promedio ponderada

#### 3.3.3 Información Socioeconómica

**Secretaría Distrital de Planeación**

- Mapa de Estratificación Social de Bogotá (ArcGIS)
- Fuente: [https://www.arcgis.com/apps/mapviewer/index.html?webmap=8ac1c0d2c59b4fe6980e4d06fb599f03](https://www.arcgis.com/apps/mapviewer/index.html?webmap=8ac1c0d2c59b4fe6980e4d06fb599f03)
- Utilizado para: Asignación de estrato socioeconómico promedio por localidad

### 3.4 Arquitectura de Datos

#### 3.4.1 Modelo Dimensional (Esquema Estrella)

Se implementó un modelo dimensional tipo estrella para optimizar consultas analíticas y soportar la generación de tableros interactivos:

**Tabla de Hechos: `fact_salud_ambiental`**

- Granularidad: Una fila por localidad-trimestre-categoría de exposición
- Métricas:
  - `Promedio_PM25`: Concentración promedio trimestral ($\mu g/m^3$)
  - `Nacidos`: Total de nacidos vivos
  - `Bajo_Peso`: Número de nacimientos <2,500 g
  - `Pct_Bajo_Peso`: Porcentaje de bajo peso al nacer
  - `Prop_Masculino`: Proporción de nacimientos masculinos
  - `Edad_Materna_Prom`: Edad materna promedio (años)
  - `Mort_Infantil`: Tasa de mortalidad infantil (por 1,000 nacidos vivos)
- Claves foráneas: `id_localidad`, `id_tiempo`, `id_exposicion`

**Dimensiones:**

1. **`dim_localidad`**: Catálogo de 12 localidades con datos disponibles
   - Campos: `id_localidad`, `Localidad`

2. **`dim_tiempo`**: Dimensión temporal
   - Campos: `id_tiempo`, `Año`, `Trimestre`
   - Cobertura: 2022, trimestres 1-4

3. **`dim_exposicion`**: Clasificación de exposición a $PM_{2.5}$
   - Campos: `id_exposicion`, `Categoria_Exposicion`
   - Valores: Alta, Media, Baja

#### 3.4.2 Pipeline ETL

El proceso de Extracción, Transformación y Carga (ETL) se implementó en Python 3.14+ con las siguientes etapas:

**1. Extracción:**
- Lectura de archivos Excel IBOCA (saltando primeras 5 filas con metadatos)
- Lectura de archivos CSV SaluData con manejo robusto de codificación (UTF-8-sig, latin-1)
- Carga de cuadros DANE en formato .xls

**2. Transformación:**
- Conversión de formato ancho a largo para datos de $PM_{2.5}$ (función `melt`)
- Mapeo de estaciones a localidades mediante regex
- Filtrado de estaciones móviles (patrón "MÓVIL" o "Móvil")
- Normalización de nombres de localidades (eliminación de acentos, mayúsculas)
- Agregación temporal: horaria → diaria → trimestral
- Cálculo de percentiles de exposición ($p_{25}$, $p_{75}$)
- Unión de datasets por clave `Localidad` (left join desde datos ambientales)

**3. Carga:**
- Exportación a CSV de tablas dimensionales y de hechos
- Generación de datasets para visualización en Google Looker Studio
- Documentación de linaje de datos y calidad

**Notebook de referencia:** [notebooks/base_integrada.ipynb](notebooks/base_integrada.ipynb)

### 3.5 Análisis Estadístico

#### 3.5.1 Estadística Descriptiva

- Distribución de $PM_{2.5}$ por localidad (medidas de tendencia central y dispersión)
- Prevalencia de bajo peso al nacer por localidad
- Caracterización demográfica de madres (edad promedio, distribución por grupos etarios)
- Análisis de variación temporal trimestral

#### 3.5.2 Estadística Inferencial

**Comparación de Proporciones:**

Se calcularon intervalos de confianza para la diferencia de proporciones de bajo peso al nacer entre localidades de alta y baja exposición:

$$
IC_{95\%}(p_1 - p_2) = (p_1 - p_2) \pm 1.96 \times \sqrt{\frac{p_1(1-p_1)}{n_1} + \frac{p_2(1-p_2)}{n_2}}
$$

Donde:
- $p_1$: Proporción de bajo peso en localidades de alta exposición
- $p_2$: Proporción de bajo peso en localidades de baja exposición
- $n_1, n_2$: Tamaños muestrales respectivos

**Odds Ratio (OR):**

Para cuantificar la asociación entre exposición a $PM_{2.5}$ y bajo peso al nacer, se construyeron tablas de contingencia 2x2 y se calculó el OR con su intervalo de confianza:

$$
OR = \frac{a \times d}{b \times c}
$$

$$
IC_{95\%}(OR) = \exp\left[\ln(OR) \pm 1.96 \times \sqrt{\frac{1}{a} + \frac{1}{b} + \frac{1}{c} + \frac{1}{d}}\right]
$$

Donde $(a, b, c, d)$ son las celdas de la tabla 2x2:

|                    | Bajo Peso (Sí) | Bajo Peso (No) |
|--------------------|----------------|----------------|
| Alta Exposición    | a              | b              |
| Baja Exposición    | c              | d              |

**Interpretación:** Un $OR > 1$ indica mayor probabilidad de bajo peso en zonas de alta exposición. Si el intervalo de confianza no incluye el valor 1, la asociación es estadísticamente significativa.

**Pruebas de Hipótesis:**

Se aplicó la prueba $\chi^2$ (chi-cuadrado) o prueba exacta de Fisher (según tamaños muestrales) para evaluar la independencia entre exposición y bajo peso:

$$
\chi^2 = \sum \frac{(O_i - E_i)^2}{E_i}
$$

Donde $O_i$ son las frecuencias observadas y $E_i$ las frecuencias esperadas bajo la hipótesis nula de independencia.

- **Hipótesis nula ($H_0$):** No existe asociación entre nivel de exposición a $PM_{2.5}$ y bajo peso al nacer
- **Hipótesis alternativa ($H_1$):** Existe asociación estadísticamente significativa
- **Nivel de significancia:** $\alpha = 0.05$

**Regresión Logística Múltiple:**

Para ajustar por variables de confusión, se estimó un modelo de regresión logística:

$$
\text{logit}(P(\text{Bajo Peso})) = \beta_0 + \beta_1 \times PM_{2.5} + \beta_2 \times \text{Sexo} + \beta_3 \times \text{Estrato} + \beta_4 \times \text{Edad Materna}
$$

Los coeficientes se exponenciaron para obtener OR ajustados:

$$
OR_{\text{ajustado}} = e^{\beta_i}
$$

$$
IC_{95\%}(\beta_i) = \beta_i \pm 1.96 \times SE(\beta_i)
$$

**Notebook de referencia:** [notebooks/proyecto.ipynb](notebooks/proyecto.ipynb)

---

## 4. Objetivos del Estudio

### 4.1 Objetivo Principal

Evaluar la diferencia en la proporción de bajo peso al nacer entre las localidades con mayor y menor exposición promedio anual a $PM_{2.5}$ en Bogotá durante el año 2022.

### 4.2 Objetivos Secundarios

1. **Describir la exposición a $PM_{2.5}$** por localidad en Bogotá durante el año 2022, tanto en promedio anual como trimestral, identificando las localidades con mayor y menor concentración según percentiles de exposición.

2. **Analizar la variación temporal trimestral** de los niveles de $PM_{2.5}$ y su posible relación con los cambios en la proporción de bajo peso al nacer en las localidades seleccionadas.

3. **Describir la distribución de factores demográficos y sociales** (nivel socioeconómico, edad materna promedio y sexo del recién nacido) en las localidades con alta y baja exposición a $PM_{2.5}$ durante 2022.

4. **Ajustar la comparación de bajo peso al nacer** entre localidades de alta y baja exposición a $PM_{2.5}$ considerando como variables de confusión el nivel socioeconómico, la edad materna promedio y el sexo del recién nacido.

---

## 5. Requerimientos Analíticos para Tableros Interactivos

### 5.1 Filtros Dinámicos

Los tableros de inteligencia de negocios desarrollados en Google Looker Studio incorporan los siguientes filtros para análisis exploratorio:

| Tipo de Filtro | Variable | Descripción | Valores Ejemplo |
|----------------|----------|-------------|-----------------|
| Temporal | Mes / Trimestre | Permite agrupar datos por mes o trimestre | Q1, Q2, Q3, Q4 / Enero-Diciembre |
| Geográfico | Localidad | Filtra por zona geográfica | Kennedy, Usaquén, Suba, etc. |
| Ambiental | Nivel de Exposición | Agrupa según concentración de $PM_{2.5}$ | Alta ($\geq p_{75}$), Baja ($\leq p_{25}$) |
| Demográfico | Sexo del Recién Nacido | Permite estratificar por sexo | Masculino, Femenino |
| Demográfico | Edad Materna Promedio | Control por edad de la madre | 18-45 años (continuo o categorizado) |
| Estadístico | Nivel de Confianza | Ajusta cálculo de intervalos de confianza | 90%, 95%, 99% |
| Estadístico | Nivel de Significancia ($\alpha$) | Define umbral para pruebas de hipótesis | 0.10, 0.05, 0.01 |

### 5.2 Componente Inferencial Dinámico

Los tableros incluyen cálculos estadísticos que se actualizan automáticamente según los filtros seleccionados:

| Elemento | Descripción | Fórmula / Método |
|----------|-------------|------------------|
| Tamaño muestral ($n$) | Número total de nacimientos en el subconjunto filtrado | Suma condicional |
| Proporción de bajo peso | Porcentaje de recién nacidos <2,500 g | $\frac{\text{Bajo Peso}}{\text{Nacidos}} \times 100$ |
| Tabla de contingencia 2x2 | Exposición (alta/baja) × Bajo Peso (sí/no) | Tabla cruzada dinámica |
| OR (Odds Ratio) | Estimación de asociación | $OR = \frac{ad}{bc}$ |
| Intervalo de Confianza | IC del OR o diferencia de proporciones | Según nivel de confianza seleccionado |
| Valor $p$ | Prueba $\chi^2$ o Fisher | Cambia según $\alpha$ seleccionado |
| Interpretación automática | Texto explicativo basado en resultados | Condicional: "Significativo" si $p < \alpha$ e IC excluye valor nulo |

### 5.3 Visualizaciones Analíticas

Los tableros incluyen los siguientes componentes visuales:

1. **Series Temporales:**
   - Tendencia trimestral de $PM_{2.5}$ por localidad
   - Evolución de porcentaje de bajo peso al nacer a lo largo de 2022

2. **Gráficos de Barras:**
   - Comparación de OR entre subgrupos (sexo, trimestre, localidad)
   - Ranking de localidades por concentración de $PM_{2.5}$

3. **Tarjetas de KPI (Scorecards):**
   - Promedio general de $PM_{2.5}$ en Bogotá
   - Prevalencia global de bajo peso al nacer
   - Número de localidades en categoría de alta exposición
   - OR general con IC 95%

4. **Mapas Geográficos:**
   - Coropletas con clasificación de exposición por localidad
   - Superposición de tasa de bajo peso al nacer

5. **Matrices de Correlación:**
   - Relación entre $PM_{2.5}$, bajo peso, mortalidad infantil y edad materna

---

## 6. Limitaciones del Estudio

1. **Cobertura geográfica incompleta:** Solo 12 de las 20 localidades de Bogotá cuentan con estaciones de monitoreo de calidad del aire, lo que limita la representatividad del análisis a 60% de las localidades.

2. **Ausencia de datos individuales:** El análisis se realiza con datos agregados a nivel de localidad, lo que impide establecer asociaciones causales a nivel individual (falacia ecológica).

3. **Variables de confusión no disponibles:** No se cuenta con información completa sobre factores como tabaquismo materno, índice de masa corporal pregestacional, consumo de alcohol, o complicaciones obstétricas, que pueden influir en el peso al nacer.

4. **Asignación de exposición:** La exposición a $PM_{2.5}$ se asigna por localidad de residencia, sin considerar movilidad intraurbana de las madres o exposición en lugares de trabajo.

5. **Temporalidad:** Se dispone solo de datos para el año 2022, lo que imposibilita análisis de tendencias multi-anuales o validación de hallazgos en otros períodos.

6. **Estaciones móviles excluidas:** Las estaciones de monitoreo móviles fueron excluidas del análisis debido a la falta de asignación geográfica fija, lo que puede subestimar la exposición en localidades sin estaciones permanentes.

7. **Datos de estrato socioeconómico:** La información de estratificación socioeconómica no estaba disponible en las bases de datos utilizadas y debió ser inferida a partir de mapas georreferenciados, introduciendo potencial sesgo de medición.

---

## 7. Conclusiones

Este proyecto demuestra la viabilidad de integrar fuentes de datos ambientales, clínicas y demográficas mediante arquitecturas de inteligencia de negocios aplicadas al sector salud. El modelo dimensional implementado permite análisis exploratorios y confirmatorios con actualización dinámica de métricas estadísticas, facilitando la toma de decisiones basada en evidencia.

Los hallazgos preliminares sugieren la existencia de variaciones geográficas en la exposición a $PM_{2.5}$ y en la prevalencia de bajo peso al nacer entre localidades de Bogotá, aunque la significancia estadística y magnitud de la asociación requieren confirmación mediante análisis ajustados por todas las variables de confusión identificadas.

La implementación de tableros interactivos con componentes inferenciales dinámicos representa un avance metodológico importante para la vigilancia epidemiológica ambiental, permitiendo a los tomadores de decisiones en salud pública explorar escenarios, identificar grupos vulnerables y evaluar el impacto potencial de intervenciones.

---

## 8. Recomendaciones

### 8.1 Para la Investigación

1. **Ampliar cobertura temporal:** Replicar el análisis con datos de múltiples años para validar tendencias y evaluar el impacto de políticas de control de contaminación.

2. **Análisis multinivel:** Incorporar datos individuales cuando estén disponibles para abordar la heterogeneidad dentro de las localidades.

3. **Modelado de exposición avanzado:** Utilizar técnicas de interpolación espacial o modelos de dispersión atmosférica para estimar exposición en localidades sin estaciones de monitoreo.

4. **Análisis de ventanas de exposición:** Evaluar períodos críticos del embarazo (primer trimestre, segundo trimestre, tercer trimestre) y su relación diferencial con el bajo peso al nacer.

### 8.2 Para la Salud Pública

1. **Vigilancia focalizada:** Intensificar el monitoreo de salud materno-infantil en localidades identificadas con alta exposición a $PM_{2.5}$.

2. **Intervenciones preventivas:** Implementar programas de educación prenatal sobre riesgos de contaminación atmosférica y medidas de protección (purificadores de aire domésticos, uso de mascarillas en días de alta contaminación).

3. **Coordinación intersectorial:** Fortalecer la articulación entre las secretarías de Salud y de Ambiente para políticas integradas de salud ambiental.

### 8.3 Para la Inteligencia de Negocios en Salud

1. **Automatización de pipeline ETL:** Establecer procesos automatizados de actualización mensual de los tableros con nuevos datos de I-BOCA y SaluData.

2. **Alertas tempranas:** Configurar notificaciones automáticas cuando se detecten incrementos significativos en $PM_{2.5}$ o en proporciones de bajo peso al nacer.

3. **Capacitación de usuarios:** Desarrollar programas de formación para personal de salud pública en el uso de tableros analíticos y la interpretación de intervalos de confianza y pruebas de hipótesis.

---

## 9. Referencias

### 9.1 Literatura Científica

1. **Leung M, Weisskopf M G, Laden F, et al.** Exposure to PM2.5 during pregnancy and fetal growth in Eastern Massachusetts, USA. *Environmental Health Perspectives.* 2022;130(1):017004. doi:10.1289/EHP9824

2. **Balakrishnan K, Steenland K, Clasen T, et al.** Exposure-response relationships for personal exposure to fine particulate matter (PM2.5), carbon monoxide, and black carbon and birthweight: an observational analysis of the multicountry HAPIN trial. *The Lancet Planetary Health.* 2023;7:e387-e396. doi:10.1016/S2542-5196(23)00043-5

3. **World Health Organization (WHO).** WHO Global Air Quality Guidelines: Particulate Matter (PM2.5 and PM10), Ozone, Nitrogen Dioxide, Sulfur Dioxide and Carbon Monoxide. Geneva: World Health Organization; 2021.

4. **UNICEF and WHO.** Low Birthweight: Country, regional and global estimates. New York: UNICEF; 2004.

### 9.2 Fuentes de Datos

5. **Departamento Administrativo Nacional de Estadística (DANE).** Nacimientos por grupos de edad de la madre en Bogotá, 2022 (Cuadro 7). Recuperado de [https://www.dane.gov.co/index.php/estadisticas-por-tema/salud/nacimientos-y-defunciones/nacimientos/nacimientos-2022](https://www.dane.gov.co/index.php/estadisticas-por-tema/salud/nacimientos-y-defunciones/nacimientos/nacimientos-2022)

6. **Secretaría Distrital de Planeación.** Mapa de Estratificación Social de Bogotá (ArcGIS). Recuperado de [https://www.arcgis.com/apps/mapviewer/index.html?webmap=8ac1c0d2c59b4fe6980e4d06fb599f03](https://www.arcgis.com/apps/mapviewer/index.html?webmap=8ac1c0d2c59b4fe6980e4d06fb599f03)

7. **Observatorio de Salud de Bogotá - SaluData.** Tasa de fecundidad por localidad y edad de la madre en Bogotá. Secretaría Distrital de Salud. Recuperado de [https://saludata.saludcapital.gov.co/osb/indicadores/fecundidad-por-edad-en-bogota](https://saludata.saludcapital.gov.co/osb/indicadores/fecundidad-por-edad-en-bogota)

8. **Observatorio de Salud de Bogotá - SaluData.** Mortalidad infantil (menores de un año) por localidad en Bogotá. Secretaría Distrital de Salud. Recuperado de [https://saludata.saludcapital.gov.co/osb/indicadores/mortalidad-infantil](https://saludata.saludcapital.gov.co/osb/indicadores/mortalidad-infantil)

9. **Observatorio de Salud de Bogotá - SaluData.** Natalidad en Bogotá: Nacimientos por localidad y población total por localidad. Secretaría Distrital de Salud. Recuperado de [https://saludata.saludcapital.gov.co/osb/indicadores/natalidad-en-bogota](https://saludata.saludcapital.gov.co/osb/indicadores/natalidad-en-bogota)

10. **Instituto Distrital de Gestión de Riesgos y Cambio Climático (IDIGER).** Red de Monitoreo de Calidad del Aire de Bogotá (RMCAB) - I-BOCA. Recuperado de [https://iboca.ambientebogota.gov.co](https://iboca.ambientebogota.gov.co)

---

**Nota:** Este informe constituye un documento técnico-científico desarrollado en el marco del curso de Inteligencia de Negocios (IN & EDC - 202502), demostrando la aplicación de metodologías de análisis de datos, modelado dimensional y visualización analítica a problemas de salud pública ambiental.
