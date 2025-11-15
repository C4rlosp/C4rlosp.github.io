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

## 📋 Tablas de BIRD (estado real de los validadores)

![Tablas de BIRD para ROA4 y ROA6](images/rpki_tables.png)

*Figura 1 – Salida real de BIRD mostrando diferencias entre validadores antiguos y actualizados.*


## 📊 Comparación de ROAs importados

![ROAs importados por versión de validador](images/rpki_roa_imported_only.png)

*Figura 2 – Comparación del número de ROAs **importados** por FORT v1.0 y v1.6 (IPv4 e IPv6). La versión antigua pierde una gran cantidad de datos debido a soporte incompleto de RRDP.*

## 📊 ROAs importados vs preferidos (comparación completa)

![ROAs importados y preferidos por versión de validador](images/rpki_roa_comparison.png)

*Figura 3 – Comparación entre ROAs importados y ROAs preferidos. FORT v1.0 muestra inconsistencias fuertes que revelan validación degradada (“Ghost RPKI”).*

---

## ¿Por qué crees que ocurree esto?

  - Un validador obsoleto:
    - No interpreta los cambios modernos RRDP
    - Duplica o procesa mal objetos
    - Se acumulan estados inconsistentes utilizados solo rsync
    - No sabe reconocer los objetos introducidos después del 2021
    - Te da una falsa sensación de seguridad **("Ghost Security")**

---

## 🧩 Conclusión
En palabras simples **"Ghost RPKI"** es aquel validador que parece funcionar, pero en realidad esta protegiendo con datos incompletos, corruptos o antiguos.

y ahí es donde caemos en "La falsa seguridad es peor que no tener RPKI", porque cuando todo se ve "UP" en CLI y los validadores no muestra errores, el operador confía, pero ojo si el motor RRDP está roto, si los TALs están desactualizados, o el repositorio no sincroniza, déjame decirte que tu red está tomando decisiones basadas en datos falsos.

El verdadero fantasma es pensar que estas protegido cuando no lo estas.

Para terminar, te dejo estos consejos:
  - No confíes en que no da errores
  - No confíes en que "siempre ha funcionado así"
porque podrías estar tomando decisiones críticas de enrutamiento con información inconsistente. **"RPKI no es un servicio de "Instalar y Olvidar"**

---
## "El mayor riesgo no es no tener RPKI: es creer que lo tienes, cuando en realidad tu validador es un fantasma."

[⬅ Volver al inicio](index.md)
