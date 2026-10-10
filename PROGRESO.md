# Progreso del portafolio — Julio García Jara

> Archivo para retomar el trabajo en cualquier sesión. Se actualiza al terminar cada etapa.

**GitHub:** [ego4men](https://github.com/ego4men) · **Dedicación:** ~10 h/semana · **Inicio:** 08/10/2026

## Estructura elegida

- **Este repo (`Portafolio-Julio`)**: sitio en GitHub Pages que reúne todos los proyectos (es el enlace para el CV y LinkedIn).
- **Repo de perfil (`ego4men/ego4men`)**: README de presentación en la portada de GitHub (texto listo en `perfil/README.md`).
- **Un repo por proyecto**: código, datos, consultas, dashboards y README técnico. Carpetas locales en `D:\Proyectos\`.

## Roadmap

**Meta:** 2 proyectos publicados al **15/10/2026**. Ritmo acelerado: Claude construyó los proyectos y Julio repasa los conceptos después.

| Fecha | Etapa | Estado |
|---|---|---|
| 08/10 | Entorno listo (Git, pandas, psql) | ✅ |
| 08–10/10 | P1 · Datos sintéticos, PostgreSQL, SQL avanzado, gráficos, guía de Power BI y README | ✅ |
| 10/10 | P2 · Fraude en seguros: EDA, estadística, XGBoost calibrado, app Streamlit y README | ✅ |
| 10/10 | Sitio del portafolio y README del perfil | ✅ (local) |
| ≤ 15/10 | Publicar en GitHub: 2 repos de proyecto, Pages y perfil (requiere confirmación de Julio) | ⬜ |
| ≤ 15/10 | Julio: construir el `.pbix` con `powerbi/GUIA_POWERBI.md` y desplegar la app en Streamlit Community Cloud | ⬜ |
| Después del 15/10 | Repasos pendientes (abajo) y luego P3 Power Platform → P4 Transformación digital → P5 ETL → P6 Modelo financiero | ⬜ |

## Proyectos

| # | Proyecto | Carpeta local | Repo | Estado |
|---|---|---|---|---|
| 1 | Análisis de cartera y morosidad | `D:/Proyectos/analisis-cartera-morosidad` | ego4men/analisis-cartera-morosidad (por crear) | ✅ Listo · falta `.pbix` |
| 2 | Detección de fraude en seguros | `D:/Proyectos/deteccion-fraude-seguros` | ego4men/deteccion-fraude-seguros (por crear) | ✅ Listo · falta desplegar la app |
| 3 | App de Power Platform | — | — | ⬜ |
| 4 | Caso de transformación digital | — | — | ⬜ |
| 5 | Pipeline ETL automatizado | — | — | ⬜ |
| 6 | Modelo financiero (opcional) | — | — | ⬜ |

## Repasos pendientes (retomar aquí)

Cada repaso usa el código ya construido como material de estudio.

**P1 · Cartera y morosidad**
1. [ ] **Lección 1 · Negocio y modelo de datos:** cuota francesa, TEA, días de atraso, tramos, castigo; PK/FK/1:N. Cargar la base `cartera` en tu PostgreSQL (`sql/01` a `03`). Ejercicio: % de mora > 30 por canal escrito por ti (Digital ≈ 5,66 %, Agencia ≈ 4,46 %).
2. [ ] **Lección 2 · Funciones de ventana:** `LAG` (roll rates), `RANK`/`NTILE` (agencias), `ROW_NUMBER` (top N por grupo), `SUM() OVER ()` usando `sql/04_analisis.sql`.
3. [ ] **Lección 3 · CTE y vistas materializadas:** reconstruir `cierre_mensual` paso a paso con `generate_series`.
4. [ ] **Lección 4 · Power BI:** Power Query, modelo estrella, `CALCULATE`, `DATEADD`, `VAR`, con `powerbi/GUIA_POWERBI.md`.

**P2 · Fraude en seguros**
5. [ ] **Lección 5 · Estadística:** chi-cuadrado, p-valor y V de Cramér (`src/eda.py`).
6. [ ] **Lección 6 · ML con datos desbalanceados:** validación temporal, PR-AUC frente a exactitud, `scale_pos_weight`, curva de captura.
7. [ ] **Lección 7 · Calibración y umbral por costo:** por qué un 57 % pasó a 10 %; simulador de costos en la app.

## Habilidades practicadas

| Habilidad | Dónde | Repasado por Julio |
|---|---|---|
| Git: configuración de identidad | Semana 0 | ✅ |
| Modelo relacional (PK, FK, CHECK, índices) | P1 | ⬜ |
| SQL: CTE, FILTER, CASE, LAG, RANK, NTILE, ROW_NUMBER, generate_series, vistas materializadas | P1 | ⬜ |
| Power BI: Power Query, modelo estrella, DAX | P1 (guía) | ⬜ |
| Simulación de datos sintéticos con pandas/numpy | P1 | ⬜ |
| Estadística: chi-cuadrado, V de Cramér | P2 | ⬜ |
| ML: XGBoost, validación temporal, PR-AUC, calibración, umbral por costo | P2 | ⬜ |
| Streamlit | P2 | ⬜ |

## Pendientes inmediatos

- [x] Configurar el nombre y el correo en Git (correo noreply de GitHub)
- [x] Instalar pandas, faker, psycopg2, scikit-learn, xgboost y streamlit
- [ ] Confirmar la publicación en GitHub (repos, Pages y perfil)
- [ ] Agregar los enlaces de LinkedIn y del CV en `index.html` (están comentados en el código)
- [ ] Construir el `.pbix` y agregar sus capturas al README de P1
- [ ] Desplegar la app de P2 en Streamlit Community Cloud y poner el enlace en su README y en el sitio
- [ ] Agregar `psql` al PATH (opcional; por ahora se usa la ruta completa)

## Líneas para el CV

**Análisis de cartera y morosidad (SQL · PostgreSQL · Power BI · Python)**
- Analicé una cartera simulada de 5 562 créditos (S/ 86 MM desembolsados) en PostgreSQL con CTE, funciones de ventana y vistas materializadas; calculé ratio de mora (4,91 %), roll rates y cosechas sobre 33 cierres mensuales.
- Identifiqué que el 47,6 % de los créditos en 61–90 días migra a 90+ y diseñé una lista de cobranza priorizada por agencia para el tramo de 1–60 días (S/ 380 mil vencidos en 286 créditos).

**Detección de fraude en seguros (Python · XGBoost · Streamlit)**
- Desarrollé un modelo XGBoost calibrado sobre 15 419 reclamos (6 % de fraude) con validación temporal: detecta el 47 % del fraude revisando el 20 % de los reclamos (PR-AUC 3,2 veces mayor que el azar).
- Definí el umbral de alerta por costo (recall de 92,5 %, −48 % de costo frente a no usar modelo) y lo publiqué en una app de Streamlit con simulador de costos.
