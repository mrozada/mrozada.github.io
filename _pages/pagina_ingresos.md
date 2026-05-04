---
permalink: /ingresos/
title: "INGRESOS"
header:
  image: /assets/images/header-git5.png
---

## Salario real del sector público formal: ¿el +5,8% es estadísticamente distinguible de cero?

Los microdatos de la EPH-INDEC del 4T2025 muestran que el salario medio real
del sector público formal habría subido +5,8% real entre 3T-2023 y 4T-2025.
Sin embargo, el intervalo de confianza al 95% para esa estimación —construido
mediante bootstrap estratificado por región con 1.000 replicaciones— va desde
−1,1% hasta +13,3% e incluye al cero. El crecimiento puntual no es
estadísticamente distinguible de cero. Aún tomando el +5,8% como estimador
puntual, el análisis empírico muestra que esa cifra se compone de cuatro
factores que no representan un aumento generalizado al empleado público
formal típico.

---

![Trayectoria del salario real del público formal con intervalos de confianza al 95%](https://mrozada.github.io/assets/images/grafico_ic95.png)

*Trayectoria del salario medio real del público formal en EPH con intervalo de
confianza al 95% por bootstrap estratificado por región. El rectángulo rojo en el
extremo derecho marca la zona de superposición entre los intervalos de 3T-2025 y
4T-2025. Base 3T-2023 = 100.*

---

## Hallazgos principales

* El intervalo de confianza al 95% del salario real en 4T-2025 va desde el
  índice **98,9** hasta el **113,3** (base 3T-2023 = 100). El intervalo
  **incluye al 100 y se solapa con el del 3T-2025**: estadísticamente, no se
  puede rechazar al 5% que el salario real promedio en 4T-2025 sea igual al
  de 3T-2025 ni al de 3T-2023.
* El **salto de +8 puntos del último trimestre se modera sustancialmente**
  con medidas robustas: la media trimada al 5% sin ponderar muestra apenas
  +1,9 puntos. En el panel intra-individuo (mismas personas en 3T-25 y 4T-25),
  **4 personas explican el 100%** del salto de la media ponderada del panel.
  Las cinco personas con mayor contribución al salto pertenecen al aglomerado
  Gran Buenos Aires y mayoritariamente a Administración pública.
* **Más de la mitad del crecimiento anual proviene de composición** del panel
  rotativo de la EPH. Entre 4T-24 y 4T-25, la variación cross-section del
  salario real es +12,4%, pero la variación intra-individuo (mismas personas
  en ambos trimestres) es de solo +4,3%. La rotación 2-2-2 introduce en el
  último trimestre entrantes con una cola alta sustancialmente superior a la
  de los salientes.
* La **heterogeneidad por rama y ocupación es muy fuerte**. Mientras Bancos
  públicos (+33,9%), Funcionarios y dirección (+20,8%) y personal
  Administrativo (+13,5%) muestran crecimientos reales sustanciales,
  Investigación científica (−20,7%), Fuerzas Armadas y Gendarmería (−23,0%),
  Docentes (−3,5%) y Policía (−0,5%) perdieron en términos reales.
* La hipótesis de que el aguinaldo de diciembre explica el salto del último
  trimestre **fue descartada empíricamente**: la EPH capta el SAC casi
  enteramente en los trimestres 1 y 3 de cada año, no en los trimestres 2 y 4.
  En el panel del público formal de 4T-2025, solamente 1 de 1.062 personas
  reporta haber cobrado aguinaldo en los tres meses anteriores a la entrevista.

---

## Documento

* [Reporte de resultados (PDF)](https://mrozada.github.io/assets/pdf/Salario_publico_eph_final.pdf)

---

## Índice de Salarios del Sector Privado No Registrado

Una réplica metodológica del Índice de Salarios (IS) del sector privado no registrado que publica INDEC, construida desde los microdatos de la EPH siguiendo la Metodológica N°16/2002. El trabajo tiene tres objetivos: traducir las variaciones porcentuales en magnitudes monetarias absolutas por grupo ocupacional, validar la construcción del IS INDEC mediante reproducción independiente, e investigar la estabilidad del índice frente a la estructura muestral de la EPH.

---

![Índice de salarios del sector privado no registrado: construcción propia vs INDEC](/assets/images/fig_web_is_no_reg.png)

---

## Hallazgos principales

* La réplica propia alcanza gaps en niveles menores a **3 pp** con el IS INDEC oficial en el **83%** de los trimestres comparables desde 2016, con un máximo de 7,7 pp. La construcción nominal interanual del 3T2025 arroja +76,2%, prácticamente idéntica al +75,1% publicado por INDEC en febrero de 2026.
* La recuperación salarial nominal del sector no registrado post-devaluación de diciembre de 2023 es **real y reproducible**; no es un artefacto del cambio de cuestionario EPH de 4T2023.
* Las variaciones reales por grupo son muy **heterogéneas**. En pesos reales de nov-2023, comparando 3T2025 vs 3T2024, los operativos de sectores primarios e industria ganaron +$73.161 mensuales (+55%), mientras que los profesionales apenas recuperaron +$20.878 (+7,9%).
* El grupo de servicio doméstico, con +47% real interanual, representa el aumento en **valores absolutos más bajo** del universo no registrado (+$26.120 mensuales), reflejando una precariedad estructural detrás de los porcentajes altos.
* El IS agregado es **vulnerable a pocas observaciones de CABA con ponderador muestral alto**: entre 13 y 19 observaciones del grupo profesional concentran 27%-39% del peso muestral del grupo. El "efecto CABA" sobre la variación interanual del grupo profesional es de +22 pp, y de +24 pp sobre el grupo no calificado en primarios+industria.

---

## Documentos

* [Reporte de resultados (PDF)](/assets/pdf/reporte_IS_no_registrado.pdf)

---

## Salarios informales en Argentina: ¿Recuperación real o ilusión estadística?

Desde el cuarto trimestre de 2023, el Índice de Salarios del INDEC muestra una
pronunciada recuperación del salario del sector privado no registrado. Un argumento
que circuló con fuerza en el debate público atribuye esa recuperación al cambio
metodológico que el INDEC introdujo en el cuestionario de la EPH en ese mismo
trimestre, y no a una mejora real en los ingresos de los trabajadores informales.
Este documento evalúa esa hipótesis de manera sistemática utilizando microdatos de
la EPH (Bases Comparables, 2T2016–3T2025) y concluye que **la recuperación es real**.

---

![Índice de Salarios real por sector](/assets/images/graf_IS_real.png)

*Índice de Salarios INDEC deflactado por IPC NG. Base noviembre 2023 = 100.
La serie del privado no registrado se deflacta por el IPC del período que representa
(publicación mes M → período M−5 → IPC de M−5). Fuente: INDEC. Elaboración: UTDT.*

---

## Hallazgos principales

* El cambio de cuestionario de la EPH en 4T2023 **no modifica la variable p21**
  (ingreso de la ocupación principal) — la única variable a partir de la cual se
  mide el salario informal. Las nuevas preguntas clasifican el tipo de empleador
  pero no alteran lo que el trabajador declara como ingreso.

* Un **análisis de series de tiempo interrumpidas** sobre la variable efectivamente
  modificada (desagregación de ingresos por subsidios) muestra que los 7 trimestres
  post-intervención se encuentran dentro del intervalo de confianza proyectado por
  la tendencia previa. No hay evidencia de mejora en la captación donde sí hubo
  cambio metodológico.

* Una **descomposición contable** demuestra que el efecto de composición del cambio
  de definición opera en dirección contraria a la que requeriría el argumento crítico:
  el subgrupo más estricto de informales (los que trabajan en empresas del sector
  informal) representa el 10% del universo sin DJ y tiene ingresos sistemáticamente
  **más bajos** que el promedio — el cambio de cuestionario subestima la recuperación,
  no la sobreestima.

* La recuperación del salario real de los asalariados sin registro fue de
  aproximadamente **28 puntos del índice** desde el piso del 1T2024 hasta el 3T2025,
  resultado **robusto** a la definición de informalidad utilizada, a la unidad de
  medida (mensual u horaria) y consistente con el IS INDEC una vez corregido el
  rezago de cinco meses de esa publicación.

* Los asalariados sin registro en empresas del **sector informal** tuvieron una caída
  más profunda y una recuperación más lenta que los del **sector formal**, revelando
  heterogeneidad relevante para el diseño de políticas laborales.

---

## Documento

* [Salarios informales en Argentina: ¿Recuperación real o ilusión estadística? (PDF)](/assets/pdf/reporte_salarios_informales_v310326.pdf)

---

## Ingreso Disponible

El ingreso total familiar (ITF) que releva la EPH no refleja el ingreso que los hogares tienen disponible para gastar libremente. Una parte del ingreso está comprometida en gastos recurrentes e ineludibles: alquiler, energía, comunicaciones, transporte y salud. Esta serie mide el **ingreso disponible (YD)** descontando esos compromisos, para Argentina entre el primer trimestre de 2017 y el tercer trimestre de 2025.

---

![Ingreso disponible vs. ITF nacional 2017-2025](/assets/images/fig_web_yd_itf.png)

---

## Hallazgos principales

- El YD real cayó un **41%** entre 2017 y el primer trimestre de 2024, acumulando tres episodios de contracción: la crisis cambiaria de 2018, la pandemia de 2020 y el shock de diciembre de 2023.

- La recuperación posterior fue la más rápida de los tres ciclos: en **seis trimestres** el YD superó el nivel pre-pandemia (4T2019) en un 13%.

- La carga de gastos fijos es estructuralmente **regresiva**: el quintil más pobre destina más del doble de su ingreso a gastos fijos que el quintil más rico.

- Los **inquilinos** exhiben un YD sistemáticamente inferior al de los propietarios del mismo quintil, con una brecha que se mantuvo por encima del 35% durante toda la serie.

- El impacto del shock de 2023 fue **heterogéneo regionalmente**: el Noreste acumuló la caída más profunda (−22%), GBA la menor (−8%).

---

## Documentos

- [Reporte de resultados (PDF)](/assets/pdf/reporte_yd_evolucion_v3.pdf)
- [Nota metodológica (PDF)](/assets/pdf/metodologia_ingreso_disponible.pdf)
- [Resumen de la metodología (PDF)](/assets/pdf/presentacion_yd_utdt_v2.pdf)
