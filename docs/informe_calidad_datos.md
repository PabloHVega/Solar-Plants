# Informe de Calidad de Datos - Plantas Solares

**Fecha:** Mayo 2026  
**Proyecto:** Análisis de Eficiencia de Plantas Solares  
**Fase:** Importación y Validación de Calidad de Datos

---

## 1. Resumen Ejecutivo

Análisis de calidad de datos sobre cuatro datasets de dos plantas solares fotovoltaicas (período: 15/05-17/06/2020). Se identificaron **tres problemas críticos** corregidos o documentados.

**Estado:** Datos utilizables con irregularidades temporales documentadas que requieren consideración en fases posteriores.

---

## 2. Datasets Analizados

Cuatro datasets CSV de 2 plantas (período: 15/05-17/06/2020, 34 días):
- **Generación:** Planta1 (68,778 reg.), Planta2 (67,698 reg.)
- **Sensores:** Planta1 (3,182 reg.), Planta2 (3,259 reg.)

---

## 3. Hallazgos Principales

### 🔴 INSIGHT 1: Error Sistemático en Datos de Potencia DC - Planta 1

**Problema:** Valores de `potencia_dc_kw` en `Planta1_Generacion.csv` con punto decimal desplazado (10x superior a valores esperados).

**Corrección aplicada:**
```python
p1g["potencia_dc_kw"] = p1g["potencia_dc_kw"] / 10
```

**Impacto:** Error crítico que habría distorsionado análisis de eficiencia y comparativas entre plantas.

---

### ⚠️ INSIGHT 2: Irregularidad en Registros Temporales

**Problema:** Datasets **NO contienen los mismos registros temporales**. Solo 3,154 fechas comunes de 3,263 posibles.

| Dataset | Fechas únicas | Faltantes |
|---------|---------------|-----------|
| Planta1_Generacion | 3,158 | 105 |
| Planta1_Sensores | 3,182 | 81 |
| Planta2_Generacion | 3,259 | 4 |
| Planta2_Sensores | 3,259 | 4 |

**Patrones:**
- **Planta 1:** Mayor pérdida (~105 intervalos). Días críticos: 20, 21, 29/05/2020
- **Planta 2:** Problemas focalizados (20-29/05/2020) en generación

**Decisión:** NO regularizar. Considerar irregularidades en análisis posteriores

---

### 📊 INSIGHT 3: Pérdida de Datos por Inversor

**Planta 1:** Distribución homogénea entre 22 inversores → Problema sistémico (cortes generales afectan a todos).

**Planta 2:** Distribución heterogénea → **4 inversores específicos** con mayor pérdida (posibles fallos de comunicación/hardware).

**Acción requerida:** Investigar en EDA los 4 inversores problemáticos de Planta 2.

---

## 4. Estado Actual

**✅ Fortalezas:** Período coherente, error corregido, ~68k reg/planta  
**⚠️ Limitaciones:** Irregularidad temporal (P1: ~105 faltantes; P2: 4 inversores problemáticos), días críticos 20-21-29/05

---

## 5. Próximos Pasos

1. Investigar causas datos faltantes y patrones temporales
2. Analizar 4 inversores P2: rendimiento y decisión inclusión/exclusión

---

## 6. Conclusiones

**3 hallazgos críticos:**
1. Error punto decimal Planta 1 → Corregido
2. Irregularidad temporal → Documentada (mayor en Planta 1)
3. 4 inversores Planta 2 → Requiere investigación en EDA

**✅ Datos listos para EDA**. Precauciones: irregularidades temporales, menor calidad P1, validar inversores P2.

---


