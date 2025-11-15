---
layout: default
title: "RPKI Ghost: el riesgo invisible en la validación de rutas"
---

# RPKI Ghost: el riesgo invisible en la validación de rutas
**Por Carlos Pérez**

Hoy en día, en un entorno donde la IA y los manuales de buenas prácticas están por todas partes, incluso siguiendo las normas de la comunidad podemos caer en una trampa peligrosa: **asumir que la seguridad de RPKI simplemente funciona**.

A esto se suma la mentalidad clásica de *“si funciona, no lo toques”*, muy común entre operadores y administradores.  
Y entonces surge la pregunta clave:

> **¿Cuántos validadores obsoletos siguen hoy en producción creyendo que protegen la red mientras entregan datos incompletos?**

Aunque parezca improbable, es totalmente plausible que existan ISP —e incluso IXPs— que crean estar protegidos simplemente porque su validador RPKI está encendido, sin errores aparentes y sin alertas visibles.

## ⚠️ Un validador desactualizado puede convertirse en un “Ghost”
Un validador RPKI desactualizado puede seguir funcionando, pero **sin validar correctamente**.  
Y el operador no se da cuenta.

Muchos validadores se instalaron cuando **RSYNC (RFC 9286)** era el método principal.  
Pero hoy, los RIR —LACNIC, RIPE NCC, APNIC, AFRINIC, ARIN— han migrado a **RRDP (RFC 8210)**, un mecanismo más rápido y eficiente basado en HTTPS.

El problema:  
muchos validadores antiguos **no procesan bien RRDP** y siguen dependiendo de RSYNC.

---

## 🔍 ¿Qué pasaría si tu validador dejó de validar hace años… pero seguía con sesión “Established”?
Ese es el corazón de **Ghost RPKI**:  
Un validador aparentemente sano, pero con validación rota y sin síntomas visibles.

---

## 📊 Comparación real: FORT v1.0 vs FORT v1.6
A continuación se ilustran diferencias enormes en la cantidad de ROAs importados y preferidos entre un validador antiguo y uno actualizado.

(💡 Luego subimos tus imágenes aquí usando `/img/...`)

---

## 🧩 Conclusión
Ghost RPKI **no es un fallo exótico**, es un riesgo silencioso causado por falta de actualizaciones.  
Mantener los validadores al día es esencial para proteger el ecosistema global de enrutamiento.

---

[⬅ Volver al inicio](index.md)
