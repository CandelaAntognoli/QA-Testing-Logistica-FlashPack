# QA-Testing-Logistica-FlashPack
# Portfolio QA: Sistema de Envío "Flash-Pack" 📦

## 📌 Contexto del Proyecto
Este repositorio contiene el proceso de aseguramiento de calidad (QA) realizado sobre el módulo de cotización de la empresa de logística **Flash-Pack**. El objetivo principal fue validar que el cálculo de tarifas, recargos por prioridad y multiplicadores internacionales se ejecuten según las reglas de negocio establecidas.

## 🛠️ Metodología de Testing
Para maximizar la cobertura con el mínimo de casos, se aplicaron las siguientes técnicas:
* **Partición de Equivalencia (EP):** Se definieron clases válidas para los rangos de 1-5kg y 6-20kg, y clases inválidas para pesos negativos o iguales a cero.
* **Análisis de Valores Límite (BVA):** Se testearon los puntos críticos de cambio de tarifa (5kg/6kg) y el límite máximo de operación (20kg).

## 📊 Casos de Prueba Destacados
| ID | Descripción | Técnica | Resultado |
|----|-------------|---------|-----------|
| TC-001 | Tarifa base rango inicial ($500) | EP | Pass ✅ |
| TC-002 | Rango medio con recargo Express ($1.200) | EP | Pass ✅ |
| TC-003 | Multiplicador Internacional (x2) | EP | Pass ✅ |
| TC-011 | Límite crítico de peso (21kg) | BVA | Fail ❌ |

## 🐞 Hallazgo Crítico (Bug Report)
Durante la ejecución del **TC-011**, se detectó que el sistema permite procesar envíos de 21 kg en lugar de mostrar el mensaje de error "Exceso de peso". Este fallo de lógica representa un riesgo operativo de sobrecarga para la flota logística.

## 📁 Documentación Adjunta
* Informe Técnico Completo https://github.com/CandelaAntognoli/QA-Testing-Logistica-FlashPack/blob/main/Informe/Reporte-Testing-Flash-Pack%20Logística-Candela-Antognoli.pdf.
* [Presentación Visual de Impacto](./evidencias/Canva-Project-Slides.pdf).

---
**QA Tester:** Candela Antognoli
**Fecha:** 05/05/2026
