---
layout: default
title: "RPKI Ghost: el riesgo invisible en la validación de rutas"
---

# RPKI Ghost: el riesgo invisible en la validación de rutas
**Por Carlos Pérez / NIC - CRIX Costa Rica**

Hoy en día, en un entorno donde la IA y los manuales de buenas prácticas están por todas partes, incluso siguiendo las normas de la comunidad podemos caer en una trampa peligrosa: **asumir que la seguridad de RPKI simplemente funciona**.

A esto se suma la mentalidad clásica de **“si funciona, no lo toques”** loc cual es muy común entre operadores y administradores.  
Y entonces surge la pregunta clave:

> Y entonces sugr la pregunta **¿Cuántos validadores obsoletos están hoy en producción creyendo que protegen la red mientras entregan datos incompletos?**

Aunque parezca descabellado es totalmente plausible que existan ISP —e incluso IXPs— que creen que estan protegidos simplemente porque su validador RPKI está encendido, sin errores aparentes y sin alertas visibles.

> Y justamente ahí es donde nace el problema:

## ⚠️ Un validador desactualizado puede convertirse en un “Ghost”: parece que funciona, pero realmente no valida.

Muchos operadores configuraron sus validadores hace años, cuando **RSYNC (RFC 9286)** era el método estándar de sincronización. Pero desde entonces los RIR —LACNIC, RIPE NCC, APNIC, AFRINIC, ARIN— han avanzado hacia **RRDP (RFC 8210)**, un mecanismo basado en más HTTPS mucho más rápido, eficiente y menos costoso para los repositorios.

El problema es que muchos **validadores antiguos no procesan correctamente RRDP, y aún siguen dependiendo casi por completo de RSYNC, que hoy en día solo se debería utilizar como un fallback. y lo mas grave **los operadores no se dan cuenta.** 

---

## 🔍 ¿Qué pasaría si tu validador dejó de validar hace años… pero nunca te diste cuenta porque la sesión RTR seguía “Established”?
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
