# Proyecto Salud Ambiental

> IN & EDC - 202502

## Tema Analítico

¿Existe una diferencia significativa en la proporción de recién nacidos con bajo peso al nacer entre las localidades de Bogotá con mayor y menor exposición anual a PM₂.₅ durante el año 2022?

---

## PRE-ENTREGA 1 (Ajustada)

### Variables del Estudio

#### Variable Independiente: Exposición a PM₂.₅

**Descripción:** Concentración promedio anual (y trimestral) de PM₂.₅ en µg/m³, obtenida de la Red de Monitoreo de Calidad del Aire de Bogotá (RMCAB).

**Clasificación:** Las localidades serán clasificadas en:
- **Alta exposición:** percentil ≥ 75
- **Baja exposición:** percentil ≤ 25

Se seleccionarán las 5 localidades con mayor y menor promedio anual de PM₂.₅ durante 2022.

#### Variable Dependiente: Bajo Peso al Nacer

**Definición:** Número de nacimientos con peso < 2,500 g (definido por OMS) dividido por el total de nacidos vivos en cada localidad y trimestre durante 2022.

#### Variables de Confusión

1. **Porcentaje de nacidos vivos hombres y mujeres** por localidad y trimestre
   - Para ajustar posibles diferencias de peso al nacer según sexo

2. **Nivel socioeconómico promedio (estrato)** por localidad

3. **Edad promedio** (en años) de las madres residentes en cada localidad de Bogotá con nacimientos registrados durante 2022

---

### Justificación Clínica

La exposición prenatal a material particulado fino (PM₂.₅) ha mostrado tener un impacto importante en el crecimiento del feto y en el peso al nacer, incluso cuando las concentraciones son más bajas que los niveles de seguridad establecidos.

**Evidencia científica:**

- **Leung et al. (2022)** llevaron a cabo una investigación en Massachusetts (EE. UU.) y encontraron que los niveles más altos de PM₂.₅ en las primeras 16 semanas del embarazo estaban relacionados con menores medidas ecográficas fetales y un peso más bajo al nacer, lo cual indica que la exposición temprana al PM₂.₅ puede afectar el desarrollo de la placenta y la nutrición del feto.

- **Balakrishnan et al. (2023)** reportó una correlación negativa entre el peso al nacer en mujeres y la exposición prenatal a PM₂.₅, el carbono negro y el peso al nacer en mujeres de zonas rurales de Perú, Guatemala, Ruanda e India, lo que fortalece el vínculo entre la contaminación atmosférica y el bajo peso al nacer en contextos con diferentes condiciones sociales y ambientales.

**Importancia en salud pública:**

De acuerdo con la OMS, el peso bajo al nacer (<2,500 g) es un indicador de riesgo significativo tanto de mortalidad y morbilidad neonatal como de enfermedades crónicas que se presentan en la vida adulta. Por lo tanto, tiene una gran importancia clínica y de salud pública determinar si hay variaciones en el porcentaje de bebés nacidos con peso bajo entre áreas de Bogotá que tienen diferentes grados de exposición a PM₂.₅ durante 2022, ya que esto permitiría identificar grupos más vulnerables y así guiar políticas perinatales y medioambientales para disminuir el impacto de la contaminación atmosférica sobre la salud materno-infantil.

---

### Justificación Técnica

**Viabilidad del análisis:**

El análisis es totalmente viable porque se basa en fuentes oficiales y actualizadas que permiten integrar información ambiental, clínica, demográfica y socioeconómica de Bogotá para 2022. Los datos provienen de entidades confiables como:
- DANE
- Observatorio Ambiental (I-Boca)
- Observatorio de Salud de Bogotá (SaluData)

Esto asegura calidad y consistencia en los resultados.

**Fuentes de datos:**

**Información clínica y demográfica (SaluData):**
- Datos sobre bajo peso al nacer
- Sexo del recién nacido
- Natalidad y fecundidad por edad de la madre
- Permite analizar el comportamiento reproductivo en cada localidad
- El sexo del bebé se usa como variable de confusión

**Información ambiental (I-Boca):**
- Reporta los niveles de PM₂.₅ por localidad
- Permite comparar las zonas más y menos contaminadas con las tasas de bajo peso al nacer en el mismo periodo

**Datos complementarios:**
- **Mapa de estratificación social de Bogotá (ArcGIS):** incluir el estrato socioeconómico
- **Cuadro de nacimientos por grupos de edad del DANE:** calcular la edad materna promedio
- **Base de natalidad de SaluData:** estimar la densidad poblacional
- **Tasa de fecundidad:** validar los patrones de edad materna
- **Mortalidad infantil:** indicador de coherencia clínica (si las localidades con mayor contaminación tienen más bajo peso al nacer y más mortalidad infantil, se refuerza la validez del análisis)

**Características de las bases de datos:**

En conjunto, estas bases ofrecen:
- Información compatible y abierta
- Metodologías estandarizadas
- Cobertura geográfica completa
- Datos públicos en formatos abiertos (CSV, XLSX o portales interactivos)
- Facilita la implementación de procesos de extracción, transformación y carga dentro del proyecto
- Alineación temporal y espacial que garantiza que los cruces de información puedan realizarse sin sesgos por diferencias de periodo

Esto asegura un análisis técnico sólido sobre la relación entre contaminación por PM₂.₅ y bajo peso al nacer en Bogotá.

---

## Objetivos del Estudio

### Objetivo Principal

Evaluar la diferencia en la proporción de bajo peso al nacer entre las localidades con mayor y menor exposición promedio anual a PM₂.₅ en Bogotá durante el año 2022.

### Objetivos Secundarios

1. **Describir la exposición a PM₂.₅** por localidad en Bogotá durante el año 2022, tanto en promedio anual como trimestral, identificando las localidades con mayor y menor concentración según percentiles de exposición.

2. **Analizar la variación temporal trimestral** de los niveles de PM₂.₅ y su posible relación con los cambios en la proporción de bajo peso al nacer en las localidades seleccionadas.

3. **Describir la distribución de factores demográficos y sociales** (nivel socioeconómico, edad materna promedio y sexo del recién nacido) en las localidades con alta y baja exposición a PM₂.₅ durante 2022.

4. **Ajustar la comparación de bajo peso al nacer** entre localidades de alta y baja exposición a PM₂.₅ considerando como variables de confusión el nivel socioeconómico, la edad materna promedio y el sexo del recién nacido.

---

## Fuentes de Datos

### Fuentes Principales

1. **Leung M, Weisskopf M G, Laden F, et al.** Exposure to PM₂.₅ during pregnancy and fetal growth in Eastern Massachusetts, USA. Environmental Health Perspectives. 2022;130(1):017004.

2. **Balakrishnan K, Steenland K, Clasen T, et al.** Exposure-response relationships for personal exposure to fine particulate matter (PM₂.₅), carbon monoxide, and black carbon and birthweight: an observational analysis of the multicountry HAPIN trial. The Lancet Planetary Health. 2023;7:e387--e396.

### Fuentes Complementarias

3. **Departamento Administrativo Nacional de Estadística (DANE). (2022).** Nacimientos por grupos de edad de la madre en Bogotá, 2022 (Cuadro 7). Recuperado de [https://www.dane.gov.co/index.php/estadisticas-por-tema/salud/nacimientos-y-defunciones/nacimientos/nacimientos-2022](https://www.dane.gov.co/index.php/estadisticas-por-tema/salud/nacimientos-y-defunciones/nacimientos/nacimientos-2022)

4. **Secretaría Distrital de Planeación. (2022).** Mapa de Estratificación Social de Bogotá (ArcGIS). Recuperado de [https://www.arcgis.com/apps/mapviewer/index.html?webmap=8ac1c0d2c59b4fe6980e4d06fb599f03](https://www.arcgis.com/apps/mapviewer/index.html?webmap=8ac1c0d2c59b4fe6980e4d06fb599f03)

5. **Observatorio de Salud de Bogotá -- SaluData. (2022).** Tasa de fecundidad por localidad y edad de la madre en Bogotá. Secretaría Distrital de Salud. Recuperado de [https://saludata.saludcapital.gov.co/osb/indicadores/fecundidad-por-edad-en-bogota](https://saludata.saludcapital.gov.co/osb/indicadores/fecundidad-por-edad-en-bogota)

6. **Observatorio de Salud de Bogotá -- SaluData. (2022).** Mortalidad infantil (menores de un año) por localidad en Bogotá. Secretaría Distrital de Salud. Recuperado de [https://saludata.saludcapital.gov.co/osb/indicadores/mortalidad-infantil](https://saludata.saludcapital.gov.co/osb/indicadores/mortalidad-infantil)

7. **Observatorio de Salud de Bogotá -- SaluData. (2022).** Natalidad en Bogotá: Nacimientos por localidad y población total por localidad. Secretaría Distrital de Salud. Recuperado de [https://saludata.saludcapital.gov.co/osb/indicadores/natalidad-en-bogota](https://saludata.saludcapital.gov.co/osb/indicadores/natalidad-en-bogota)

---

## Requerimientos Analíticos

1. **Comparar la proporción** de recién nacidos con bajo peso entre localidades de alta y baja exposición a PM₂.₅.

2. **Analizar la variación trimestral** de los niveles de PM₂.₅ y su relación con los cambios en la proporción de bajo peso al nacer.

3. **Comparar la distribución** de recién nacidos con bajo peso según nivel socioeconómico, localidad y edad materna promedio.

4. **Evaluar la influencia del sexo** del recién nacido sobre la proporción de bajo peso, diferenciando por nivel de exposición.

5. **Ajustar los análisis de asociación** (Odds Ratio y modelos de regresión logística) por las variables de confusión: sexo, nivel socioeconómico y edad materna.

---

## PRE-ENTREGA 2 - Diseño de Tableros

### Filtros de los Tableros

| Tipo de filtro | Variable / campo | Descripción / uso | Ejemplo de valores |
|----------------|------------------|-------------------|-------------------|
| **Mes o trimestre** | Fecha de nacimiento o registro ambiental | Permite agrupar o comparar los datos por mes o trimestre para analizar la variación temporal | Enero-Marzo / Abril-Junio / Julio-Septiembre / Octubre-Diciembre |
| **Localidad** | Localidad de Bogotá | Filtra los datos por zona geográfica | Kennedy, Usaquén, Suba |
| **Nivel de exposición a PM₂.₅** | Promedio anual o trimestral de PM₂.₅ (alta/baja exposición) | Agrupa localidades según su nivel de exposición | Alta ≥ percentil 75 / Baja ≤ percentil 25 |
| **Sexo del recién nacido** | Sexo | Permite analizar diferencias entre hombres y mujeres | Masculino / Femenino |
| **Nivel socioeconómico (opcional)** | Estrato o categoría | Permite controlar variables de confusión | Bajo / Medio / Alto |
| **Edad materna promedio** | Edad promedio de las madres por localidad o trimestre | Controla diferencias demográficas en el riesgo | 18-45 años |
| **Densidad poblacional** | Habitantes por km² | Permite evaluar la influencia del entorno urbano | Baja / Media / Alta |
| **Nivel de confianza (%)** | Control dinámico del usuario | Ajusta el cálculo de los intervalos de confianza | 90%, 95%, 99% |
| **Nivel de significancia (α)** | Control dinámico del usuario | Define el umbral de decisión en las pruebas de hipótesis | 0.10, 0.05, 0.01 |

---

## Componente Inferencial

El **componente inferencial** mostrará resultados estadísticos que se actualicen **de forma dinámica** según los filtros seleccionados y el nivel de confianza o significancia definido por el usuario.

### Elementos del Componente Inferencial

| Elemento | Descripción | Actualización dinámica |
|----------|-------------|------------------------|
| **Tamaño muestral (n)** | Número total de nacimientos o registros del subconjunto filtrado | Cambia según los filtros (localidad, año, sexo, etc.) |
| **Proporción de bajo peso** | Porcentaje de recién nacidos con <2500 g | Se recalcula según los filtros seleccionados |
| **Tabla de contingencia (2x2)** | Exposición (alta/baja PM₂.₅) × bajo peso (sí/no) | Se actualiza automáticamente con cada cambio de filtro |
| **OR (odds ratio)** | Estimación de la asociación entre exposición y bajo peso | Se recalcula con los datos filtrados |
| **Intervalo de confianza (IC)** | IC del OR o de proporciones, según el nivel de confianza elegido | Se actualiza según el valor de confianza (90, 95, 99%) |
| **Valor p** | Prueba χ² o Fisher para evaluar significancia | Cambia según α seleccionado |
| **Interpretación automática** | Texto explicativo basado en los resultados (p e IC) | Se genera dinámicamente |

---

### Intervalos de Confianza para OR

**Objetivo:** Evaluar la asociación entre exposición a PM₂.₅ y bajo peso al nacer.

**Fórmulas utilizadas:**
```
OR = (a × d) / (b × c)

IC 95% = exp[ln(OR) ± 1.96 × √(1/a + 1/b + 1/c + 1/d)]
```

Donde (a, b, c, d) corresponden a las celdas de la tabla 2x2 de exposición y bajo peso.

**Ejemplo de salida dinámica:**

| Grupo | OR | IC (95%) | Valor p | n |
|-------|-----|----------|---------|-----|
| Alta exposición PM₂.₅ | 1.72 | [1.10 - 2.68] | 0.018 | 845 |

**Interpretación dinámica:**

> A un nivel de confianza del 95%, los recién nacidos en zonas con alta exposición a PM₂.₅ tienen 1.72 veces más probabilidad de nacer con bajo peso que aquellos en zonas con baja exposición.
> 
> Como el IC no incluye 1 y p < 0.05, la asociación es estadísticamente significativa.

---

### Intervalo de Confianza para Diferencia de Proporciones

**Objetivo:** Comparar el porcentaje de bajo peso entre grupos con alta y baja exposición a PM₂.₅.

**Fórmulas:**
```
Diferencia = p₁ - p₂

IC 95% = (p₁ - p₂) ± 1.96 × √[(p₁(1-p₁)/n₁) + (p₂(1-p₂)/n₂)]
```

**Ejemplo:**

| Grupo | % bajo peso | n |
|-------|-------------|---|
| Alta exposición | 9.8% | 520 |
| Baja exposición | 6.1% | 470 |

**Resultado:**

> Diferencia = 3.7% (IC 95%: 0.8 - 6.6)
> 
> A 95% de confianza, la proporción de bajo peso es significativamente mayor en zonas de alta exposición.

---

### Intervalo de Confianza para Coeficientes de Regresión (Ajustado)

**Modelo utilizado:**
```
logit(P(bajo peso)) = β₀ + β₁(PM₂.₅) + β₂(sexo) + β₃(estrato) + β₄(edad_materna)
```

**Fórmula del IC:**
```
IC 95% = β ± 1.96 × SE(β)
```

**Ejemplo:**

| Variable | Coeficiente (β) | OR ajustado (e^β) | IC 95% | Valor p |
|----------|----------------|-------------------|---------|---------|
| PM₂.₅ (µg/m³) | 0.041 | 1.04 | [1.01-1.08] | 0.011 |
| Sexo (masculino) | 0.12 | 1.13 | [0.90-1.42] | 0.30 |

**Interpretación:**

> Por cada aumento de 10 µg/m³ en PM₂.₅, el riesgo de bajo peso aumenta en un 4% (IC95% 1-8%, p=0.011).
> 
> Este resultado es estadísticamente significativo.

---

## Pruebas de Hipótesis

Los tableros deben incluir **al menos una prueba de hipótesis** que responda dinámicamente a los filtros y al nivel de significancia seleccionado.

| Prueba | Objetivo | Tipo de variable | Actualización dinámica |
|--------|----------|------------------|------------------------|
| **Chi-cuadrado (χ²) o Fisher exacta** | Comparar proporciones de bajo peso entre grupos de exposición | Categóricas (sí/no) | Cambia con los filtros y el nivel α |
| **t de Student / ANOVA** | Comparar promedios de PM₂.₅ entre localidades o años | Continuas | Se recalcula con α elegido |
| **Regresión logística múltiple** | Evaluar el efecto de la exposición ajustando por sexo o estrato | Mixtas | Actualiza OR, IC y p |
| **Prueba de cambio de OR entre categorías** | Ver si el OR difiere entre subgrupos (p. ej., sexo o año) | Categóricas | Muestra variaciones del efecto |

---

## Diagrama Conceptual del Análisis

![Diagrama mostrando la relación entre exposición a PM₂.₅, variables de confusión y bajo peso al nacer](media/image3.png)

*Figura: Modelo conceptual del análisis multivariado ajustado por variables de confusión*