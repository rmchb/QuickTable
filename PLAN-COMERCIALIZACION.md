# PLAN DE COMERCIALIZACIÓN — QuickTable

## Sistema de menú digital + cocina + inventario para restaurantes

> Documento de análisis de costos, capacidad, y rentabilidad para lanzar QuickTable como producto SaaS dirigido a restaurantes en Perú.

---

# VERSIÓN 1: BÁSICA (Solo Web — PWA)

## Descripción

Plataforma web progresiva (PWA) responsive que funciona desde el navegador en cualquier dispositivo (celular, tablet, PC). No necesita instalación desde App Store. Todo el backend corre en un solo VPS.

### Funcionalidades incluidas:
- Menú digital con QR por mesa (cliente escanea y pide)
- Panel empresa: Dashboard KPIs, Cocina, Chat con IA
- Inventario completo: Stock, Kardex, Recetas, Mermas, Kanban
- Facturación electrónica Sunat vía API (Nubefact / Facturador.com)
- Pasarela de pagos: Mercado Pago + Culqi
- Multi-sede con jerarquía, roles y permisos (Superadmin → Admin sede → Mozo → Cocina → Caja → Almacén)
- Chat con IA (OpenAI GPT-4o-mini)
- App responsive PWA (no necesita Google Play)

### Infraestructura:
- 1 VPS DigitalOcean/AWS Lightsail (8GB RAM, 4 vCPU, 160GB SSD)
- PostgreSQL en el mismo servidor
- SSL + dominio .pe

## Costos

| Concepto | Costo único (S/) | Costo mensual (S/) |
|---|---|---|
| Desarrollo backend (FastAPI + PostgreSQL + WebSockets) | 8,000 – 12,000 | — |
| Frontend web (React/Svelte + PWA responsive) | 5,000 – 8,000 | — |
| Facturación Sunat (integración Nubefact/Facturador.com) | 2,000 – 3,500 | — |
| Pasarela de pagos (Mercado Pago + Culqi) | 1,500 – 2,500 | — |
| Multi-sede + jerarquía + roles + permisos | 2,000 – 3,500 | — |
| IA Chat (OpenAI GPT-4o-mini para 50 clientes, ~500 msgs/cliente/mes) | — | 1,200 – 1,800 |
| VPS (8GB RAM, 4 vCPU) | — | 150 – 250 |
| Dominio .pe + SSL (1 año) | 120 | 10 |
| Logo + identidad visual | 500 | — |
| Landing page + documentación | 1,000 – 2,000 | — |
| Soporte técnico (dev freelance part-time) | — | 800 – 1,200 |
| Marketing inicial (Facebook + Google Ads) | 1,000 | 500 – 1,000 |
| **TOTALES** | **S/ 21,120 – 33,120** | **S/ 2,660 – 4,260** |

### Costos operativos promedio mensual estimado: **S/ 3,500/mes**

## Capacidad

| Recurso | Límite |
|---|---|
| Restaurantes (negocios) | 50 – 80 |
| Usuarios concurrentes | 100 – 150 |
| Pedidos por hora | 200 – 300 |
| Respuestas IA por minuto | ~10 – 15 |
| Archivos almacenados (fotos/PDF/audio) | ~5,000 |
| Artículos de inventario por negocio | 500+ |

## Rentabilidad

| Plan | Precio (S//mes) | Clientes target |
|---|---|---|
| Free (1 mesa, 10 pedidos/día) | 0 | Prueba |
| Básico (hasta 10 mesas, inventario básico) | 49 | Cafés, bodegas |
| Pro (hasta 30 mesas, todo incluido) | 99 | Rest. medianos |
| Enterprise (ilimitado, multi-sede) | 249 | Cadenas |

**Precio promedio ponderado estimado:** S/ 75 / cliente / mes

### Escenarios de ingresos

| Clientes | Ingreso mensual | Ganancia/pérdida |
|---|---|---|
| 10 | S/ 750 | – S/ 2,750 |
| 20 | S/ 1,500 | – S/ 2,000 |
| 30 | S/ 2,250 | – S/ 1,250 |
| **40** | **S/ 3,000** | **– S/ 500** |
| **47** | **S/ 3,525** | **≈ S/ 0 (Break-even)** |
| 50 | S/ 4,375 | + S/ 875 |
| 60 | S/ 4,500 | + S/ 1,000 |
| 80 | S/ 6,000 | + S/ 2,500 |

**Break-even:** ~47 clientes (o ~36 en plan Pro)
**Recuperación de inversión inicial (S/ 27k):** ~18 meses con 60 clientes

### Tiempo de desarrollo: 6 – 10 semanas

---

# VERSIÓN 2: COMPLETA (Web + App Mobile + Cloud Escalable)

## Descripción

Plataforma completa con app nativa iOS/Android (Flutter/React Native), infraestructura cloud escalable, seguridad profesional. Soporta cientos de restaurantes sin lentitud.

### Funcionalidades incluidas (las mismas que básico +):
- App nativa para clientes (pedir desde el celular con notificaciones push)
- App nativa para empresa (gestión desde el móvil sin abrir navegador)
- Dashboard avanzado con reportes exportables (PDF/Excel) y gráficos
- Infraestructura cloud escalable (auto-scaling, balanceo de carga)
- Integración directa OSE Sunat + backup
- Yape multilink como método de pago adicional
- IA Chat con fine-tuning (respuestas más precisas por restaurante)
- Seguridad profesional: WAF, pentesting, auditoría OWASP, rate limiting

### Infraestructura:
- AWS / Google Cloud (multi-AZ)
- RDS / Cloud SQL (base de datos gerenciada)
- CloudFront + S3 (CDN + almacenamiento)
- Auto-scaling según demanda
- Redis para WebSockets y caché

## Costos

| Concepto | Costo único (S/) | Costo mensual (S/) |
|---|---|---|
| Backend escalable (FastAPI + Redis + Workers + CDN) | 15,000 – 22,000 | — |
| Frontend web (Next.js + SSR + PWA avanzada) | 8,000 – 14,000 | — |
| App mobile nativa (Flutter/React Native, iOS + Android) | 16,000 – 28,000 | — |
| Facturación Sunat (integración directa OSE + backup) | 3,000 – 4,500 | — |
| Pasarela de pagos (Mercado Pago + Culqi + Yape multilink) | 2,500 – 4,000 | — |
| Multi-sede + jerarquía + roles + permisos (full) | 2,500 – 4,000 | — |
| IA Chat (GPT-4o-mini fine-tuned) | — | 1,500 – 2,500 |
| Infraestructura cloud (AWS/GCP escalable) | — | 600 – 1,200 |
| Base de datos gerenciada (RDS/Cloud SQL + backups) | — | 300 – 600 |
| CDN + Storage (CloudFront + S3) | — | 100 – 200 |
| Seguridad (WAF, pentesting, OWASP audit, rate limiting) | 4,000 – 8,000 | 200 – 400 |
| Dominio .pe + SSL + emails corporativos | 200 | 40 |
| UX/UI premium (diseño profesional) | 2,000 – 4,000 | — |
| Landing page profesional + SEO + blog + demo | 2,000 – 4,000 | — |
| Dashboard avanzado (reportes exportables) | 1,500 – 3,000 | — |
| Soporte técnico (1 persona full-time L1/L2) | — | 2,000 – 3,000 |
| Marketing (Ads + Google Play + ASO + TikTok) | 3,000 | 2,000 – 4,000 |
| **TOTALES** | **S/ 59,700 – 97,700** | **S/ 6,700 – 11,900** |

### Costos operativos promedio mensual estimado: **S/ 9,300/mes**

## Capacidad

| Recurso | Límite |
|---|---|
| Restaurantes (negocios) | 500+ (escalamiento horizontal) |
| Usuarios concurrentes | 2,000+ |
| Pedidos por hora | 5,000+ |
| Respuestas IA por minuto | 100+ (fine-tuned) |
| Archivos almacenados | Ilimitado (S3) |
| Facturación por minuto | ~50+ |

## Rentabilidad

| Plan | Precio (S//mes) |
|---|---|
| Free | 0 |
| Básico | 49 |
| Pro | 99 |
| Enterprise | 249 |

**Precio promedio ponderado:** S/ 75 / cliente / mes

### Escenarios de ingresos

| Clientes | Ingreso mensual | Ganancia/pérdida |
|---|---|---|
| 20 | S/ 1,500 | – S/ 7,800 |
| 50 | S/ 3,750 | – S/ 5,550 |
| 80 | S/ 6,000 | – S/ 3,300 |
| **124** | **S/ 9,300** | **≈ S/ 0 (Break-even)** |
| 150 | S/ 11,250 | + S/ 1,950 |
| 200 | S/ 15,000 | + S/ 5,700 |
| 500 | S/ 37,500 | + S/ 28,200 |

**Break-even:** ~124 clientes (o ~94 en plan Pro)
**Recuperación de inversión inicial (S/ 78k):** ~16 meses con 200 clientes

### Tiempo de desarrollo: 4 – 6 meses

---

# CUADRO COMPARATIVO

| Aspecto | Versión Básica | Versión Completa |
|---|---|---|
| **Plataforma** | Web PWA (navegador) | Web PWA + Apps nativas iOS/Android |
| **Instalación** | Sin tienda (solo URL) | Google Play + App Store |
| **Notificaciones push** | Solo web (navegador) | Push nativas en móvil |
| **Facturación Sunat** | ✅ vía API (Nubefact) | ✅ OSE directa + backup |
| **Pagos** | ✅ MP + Culqi | ✅ MP + Culqi + Yape multilink |
| **Multi-sede + roles + permisos** | ✅ Completo | ✅ Completo |
| **IA Chat** | ✅ GPT-4o-mini | ✅ GPT-4o-mini fine-tuned |
| **Seguridad** | SSL + básica | WAF + pentesting + OWASP |
| **Escalabilidad** | Limitada (1 VPS) | Ilimitada (cloud auto-scaling) |
| **Soporte** | Dev part-time | 1 persona full-time + SLA |
| **Dashboard** | Estándar | Avanzado con reportes exportables |
| **UX/UI** | Plantilla funcional | Diseño premium |
| **Inversión inicial** | **S/ 21k – 33k** | **S/ 60k – 98k** |
| **Costo operativo mensual** | **S/ 2.7k – 4.3k** | **S/ 6.7k – 11.9k** |
| **Costo promedio mensual** | **~ S/ 3,500** | **~ S/ 9,300** |
| **Capacidad máxima** | **50 – 80 restaurantes** | **500+ restaurantes** |
| **Break-even (a S/ 75 prom.)** | **~47 clientes** | **~124 clientes** |
| **Break-even (solo plan Pro S/ 99)** | **~36 clientes** | **~94 clientes** |
| **Recuperación inversión** | ~18 meses (60 clientes) | ~16 meses (200 clientes) |
| **Tiempo desarrollo** | **6 – 10 semanas** | **4 – 6 meses** |

---

# ESTRATEGIA RECOMENDADA

## Fase 1 — Básico (Mes 1–3)
- Invertir S/ 27k en desarrollo del MVP completo
- 10 clientes beta gratis para validación
- Costo mensual: S/ 3,500
- Objetivo: 15 – 20 clientes pagos

## Fase 2 — Crecimiento (Mes 4–8)
- Escalar a 40 – 50 clientes con marketing
- Al llegar a 50–60 clientes, evaluar si la app nativa es necesaria
- Ingreso mensual: S/ 3,000 – 4,500
- **Break-even alcanzado (~47 clientes)**

## Fase 3 — Salto a Completo (Mes 9–12)
- Con el flujo de caja de los 50+ clientes (~S/ 4,500+/mes)
- Financiar el desarrollo mobile y migración a cloud
- Inversión adicional: S/ 40k – 70k
- Objetivo: 150+ clientes en 12 meses

---

---

# PLAN DE DISTRIBUCIÓN

## Canales de adquisición de clientes

| Canal | Costo inicial (S/) | Costo recurrente (S//mes) | Alcance estimado | Tasa de conversión |
|---|---|---|---|---|
| **Venta directa** (visitando restaurantes) | 0 | 2,500 – 4,000 (1 vendedor + comisiones) | 30 – 50 visitas/mes | 15 – 25% |
| **Facebook / Instagram Ads** | 500 | 1,000 – 2,000 | 50k – 150k impresiones/mes | 2 – 5% |
| **Google Ads** ("menú digital restaurante", "sistema cocina Perú") | 500 | 1,000 – 2,000 | 20 – 50 clics/día | 5 – 10% |
| **TikTok orgánico** (tutoriales, casos de éxito, detrás de escena) | 0 | 0 (tiempo) | Viral potencial | Alto si el contenido engancha |
| **Aliados estratégicos** (distribuidoras de insumos, Cámaras de Comercio) | 300 | 200 – 500 | 10 – 30 leads/mes por aliado | 10 – 20% |
| **Marketplace** (Google Play, próximamente) | 0 | 0 (comisión 15% en pagos in-app) | Tráfico orgánico de tienda | Variable |
| **Referidos** (10% dto. al que refiere + 10% al nuevo) | 0 | 10% del MRR | Boca a boca entre dueños | 20 – 30% |

## Estrategia por fase

### Mes 1 – 3: Siembra
- **Venta directa intensiva** en Lima: Miraflores, Barranco, San Isidro, Surco, San Borja
- 1 vendedor visitando 8 – 10 restaurantes por día
- Objetivo: 15 – 20 clientes beta gratis → primeros 10 pagos
- Aliados estratégicos: contactar 3 distribuidoras de insumos (ej. Distribuidora Norte, Avícola San Fernando, Mercado Mayorista)
- Contenido TikTok: 4 – 6 videos/semana (cómo funciona, tips de inventario, cocina en acción)

### Mes 4 – 8: Crecimiento
- **Google Ads + Facebook Ads** activos con S/ 1,500 – 2,000/mes cada uno
- 2 vendedores en campo (Lima + Callao)
- Primeros casos de éxito → contenido para ads y TikTok
- Programa de referidos activo
- Objetivo: 40 – 60 clientes pagos

### Mes 9 – 12: Expansión
- Expandir venta directa a provincias: Arequipa, Trujillo, Cusco, Chiclayo (vía Zoom + viajes quincenales)
- Publicidad en Facebook segmentada por ciudad
- Aliados estratégicos a nivel nacional (Cámaras de Comercio regionales)
- Google Play Store si se lanza app nativa
- Objetivo: 100 – 150 clientes pagos

## Presupuesto de distribución (acumulado 12 meses)

| Rubro | Mes 1-3 | Mes 4-8 | Mes 9-12 | Total 12 meses |
|---|---|---|---|---|
| Vendedores | S/ 7,500 | S/ 20,000 | S/ 25,000 | S/ 52,500 |
| Facebook/Instagram Ads | S/ 1,500 | S/ 7,500 | S/ 9,000 | S/ 18,000 |
| Google Ads | S/ 1,500 | S/ 7,500 | S/ 9,000 | S/ 18,000 |
| Aliados estratégicos | S/ 600 | S/ 2,000 | S/ 2,000 | S/ 4,600 |
| TikTok (producción básica) | S/ 500 | S/ 1,500 | S/ 1,500 | S/ 3,500 |
| **Total distribución** | **S/ 11,600** | **S/ 38,500** | **S/ 46,500** | **S/ 96,600** |

> Nota: Estos costos de distribución están **incluidos** en los rubros de marketing y soporte de los costos generales.

---

# TIEMPO DE RECUPERACIÓN DE INVERSIÓN (ROI)

## Escenario Básico (Inversión: S/ 27,000 | Costo mensual: S/ 3,500)

| Mes | Clientes acumulados | Ingreso mensual (S/) | Costo mensual (S/) | Flujo del mes | Flujo acumulado | Inversión restante |
|---|---|---|---|---|---|---|
| 1 | 0 (desarrollo) | 0 | 3,500 | –3,500 | –30,500 | 30,500 |
| 2 | 0 (desarrollo) | 0 | 3,500 | –3,500 | –34,000 | 34,000 |
| 3 | 10 (beta gratis) | 0 | 3,500 | –3,500 | –37,500 | 37,500 |
| 4 | 15 (pagos) | 1,125 | 3,500 | –2,375 | –39,875 | 39,875 |
| 5 | 22 | 1,650 | 3,500 | –1,850 | –41,725 | 41,725 |
| 6 | 30 | 2,250 | 3,500 | –1,250 | –42,975 | 42,975 |
| 7 | 38 | 2,850 | 3,500 | –650 | –43,625 | 43,625 |
| 8 | 47 | 3,525 | 3,500 | +25 | –43,600 | 43,600 |
| 9 | 55 | 4,125 | 3,500 | +625 | –42,975 | 42,975 |
| 10 | 62 | 4,650 | 3,500 | +1,150 | –41,825 | 41,825 |
| 11 | 70 | 5,250 | 3,500 | +1,750 | –40,075 | 40,075 |
| 12 | 80 | 6,000 | 3,500 | +2,500 | –37,575 | 37,575 |
| 13 | 85 | 6,375 | 3,700 | +2,675 | –34,900 | 34,900 |
| 14 | 90 | 6,750 | 3,700 | +3,050 | –31,850 | 31,850 |
| 15 | 95 | 7,125 | 3,700 | +3,425 | –28,425 | 28,425 |
| 16 | 100 | 7,500 | 3,700 | +3,800 | –24,625 | 24,625 |
| 17 | 105 | 7,875 | 3,700 | +4,175 | –20,450 | 20,450 |
| 18 | 110 | 8,250 | 3,700 | +4,550 | –15,900 | 15,900 |
| 19 | 115 | 8,625 | 3,700 | +4,925 | –10,975 | 10,975 |
| 20 | 120 | 9,000 | 3,700 | +5,300 | –5,675 | 5,675 |
| **21** | **125** | **9,375** | **3,700** | **+5,675** | **≈ 0** | **✅ Recuperado** |
| 22 | 130 | 9,750 | 3,800 | +5,950 | +5,950 | Ganancia |

**📊 Recuperación de inversión (Escenario Básico): 21 meses (1 año 9 meses)**

> *Asumiendo: precio promedio S/ 75/cliente, crecimiento de 5-10 clientes nuevos/mes, costo mensual sube ligeramente con más clientes.*

### Escenario Básico — Sensibilidad por precio

| Precio promedio | Clientes necesarios | Tiempo recuperación |
|---|---|---|
| S/ 49 (solo plan básico) | 72 | ~36 meses |
| **S/ 75 (mix de planes)** | **47** | **~21 meses** |
| S/ 99 (todos en plan Pro) | 36 | ~16 meses |
| S/ 129 (Pro + addons) | 28 | ~13 meses |

---

## Escenario Completo (Inversión: S/ 78,000 | Costo mensual: S/ 9,300)

| Mes | Clientes acumulados | Ingreso mensual (S/) | Costo mensual (S/) | Flujo del mes | Flujo acumulado | Inversión restante |
|---|---|---|---|---|---|---|
| 1-4 | 0 (desarrollo) | 0 | 9,300 | –37,200 | –115,200 | 115,200 |
| 5 | 5 beta | 0 | 9,300 | –9,300 | –124,500 | 124,500 |
| 6 | 15 | 1,125 | 9,300 | –8,175 | –132,675 | 132,675 |
| 7 | 25 | 1,875 | 9,300 | –7,425 | –140,100 | 140,100 |
| 8 | 38 | 2,850 | 9,300 | –6,450 | –146,550 | 146,550 |
| 9 | 50 | 3,750 | 9,300 | –5,550 | –152,100 | 152,100 |
| 10 | 65 | 4,875 | 9,300 | –4,425 | –156,525 | 156,525 |
| 11 | 80 | 6,000 | 9,300 | –3,300 | –159,825 | 159,825 |
| 12 | 95 | 7,125 | 9,500 | –2,375 | –162,200 | 162,200 |
| 13 | 110 | 8,250 | 9,500 | –1,250 | –163,450 | 163,450 |
| 14 | 124 | 9,300 | 9,500 | –200 | –163,650 | 163,650 |
| 15 | 140 | 10,500 | 9,500 | +1,000 | –162,650 | 162,650 |
| 16 | 155 | 11,625 | 9,500 | +2,125 | –160,525 | 160,525 |
| 17 | 170 | 12,750 | 9,500 | +3,250 | –157,275 | 157,275 |
| 18 | 185 | 13,875 | 9,500 | +4,375 | –152,900 | 152,900 |
| 19 | 200 | 15,000 | 9,500 | +5,500 | –147,400 | 147,400 |
| 20 | 215 | 16,125 | 9,500 | +6,625 | –140,775 | 140,775 |
| 21 | 230 | 17,250 | 9,800 | +7,450 | –133,325 | 133,325 |
| 22 | 245 | 18,375 | 9,800 | +8,575 | –124,750 | 124,750 |
| 23 | 260 | 19,500 | 9,800 | +9,700 | –115,050 | 115,050 |
| 24 | 275 | 20,625 | 9,800 | +10,825 | –104,225 | 104,225 |
| 25 | 290 | 21,750 | 10,000 | +11,750 | –92,475 | 92,475 |
| 26 | 305 | 22,875 | 10,000 | +12,875 | –79,600 | 79,600 |
| 27 | 320 | 24,000 | 10,000 | +14,000 | –65,600 | 65,600 |
| 28 | 335 | 25,125 | 10,000 | +15,125 | –50,475 | 50,475 |
| 29 | 350 | 26,250 | 10,000 | +16,250 | –34,225 | 34,225 |
| 30 | 365 | 27,375 | 10,000 | +17,375 | –16,850 | 16,850 |
| **31** | **380** | **28,500** | **10,000** | **+18,500** | **≈ 0** | **✅ Recuperado** |

**📊 Recuperación de inversión (Escenario Completo): 31 meses (2 años 7 meses)**

> *Nota: El escenario completo requiere 4 meses de desarrollo sin ingresos y una base de clientes mayor para alcanzar el break-even. Sin embargo, una vez superado, las ganancias escalan mucho más rápido.*

---

# PRECIO ÓPTIMO PARA EL MERCADO PERUANO

## Análisis de competencia directa en Perú

| Competidor | Tipo | Precio (US$/mes) | Precio (S//mes) | Ideal para |
|---|---|---|---|---|
| **Venko** | ERP gastronómico completo | 50 – 150 | 185 – 555 | Rest. grandes, cadenas |
| **WasiPOS** | POS + inventario | 40 – 80 | 148 – 296 | Pequeños/medianos |
| **Zenda** | Delivery + POS | 30 – 70 | 111 – 259 | Delivery-first |
| **Urbaner POS** | POS + cocina | 25 – 60 | 93 – 222 | Fast food |
| **TuCarta.pe** | Solo menú digital QR | 8 – 25 | 30 – 93 | Muy pequeños |
| **Sisfoh** | ERP general (no especializado) | 20 – 50 | 74 – 185 | Cualquier rubro |
| **QuickTable** (propuesto) | Todo en uno | — | 49 – 249 | Pequeños / medianos |

## Elasticidad del mercado peruano

### Por segmento de restaurante

**Restaurante pequeño (1 – 5 mesas) — dueño opera solo**
- Presupuesto mensual para software: S/ 0 – 50
- Dolor principal: "no tengo tiempo para controles, quiero algo simple"
- Solo aceptaría pagar si ve ROI claro en ahorro de tiempo
- **Precio máximo: S/ 49/mes (plan Básico)**

**Restaurante mediano (6 – 20 mesas) — 2-5 empleados**
- Presupuesto mensual para software: S/ 50 – 150
- Dolor principal: "pierdo insumos, no sé cuánto gano, cocina se atrasa"
- Ya usan Excel o tienen POS básico y quieren algo mejor
- **Precio óptimo: S/ 99/mes (plan Pro)**

**Restaurante grande o cadena (20+ mesas, múltiples sedes) — 10+ empleados**
- Presupuesto mensual para software: S/ 150 – 500
- Dolor principal: "necesito control centralizado, facturación, reportes"
- Ya evalúan Venko o WasiPOS
- **Precio óptimo: S/ 249/mes (plan Enterprise)**

## Precio recomendado

| Plan | Precio (S//mes) | Posicionamiento |
|---|---|---|
| **Free** | S/ 0 | Gancho de entrada — 1 mesa, 10 pedidos/día, sin facturación |
| **Básico** | **S/ 49** | Para el restaurante pequeño que recién empieza |
| **Pro 🔥** | **S/ 99** | **Nuestro caballo de batalla — mejor relación valor/precio** |
| **Enterprise** | **S/ 249** | Para cadenas y restaurantes grandes |

**💡 Precio óptimo recomendado: S/ 99/mes (plan Pro)**

### ¿Por qué S/ 99?

1. **Por debajo de WasiPOS** (S/ 148) y **Venko** (S/ 185) — competimos en precio
2. **Por encima de TuCarta.pe** (S/ 30-93) — ofrecemos mucho más valor (cocina, inventario, facturación, IA)
3. **Precio psicológico**: S/ 99 suena a "menos de 100 soles" — umbral psicológico clave en Perú
4. **Margen saludable**: Con 50 clientes en plan Pro generamos S/ 4,950/mes, cubriendo costos del escenario básico (S/ 3,500) con 40% de margen
5. **Comparable a**: Una cena para dos en un restaurante de gama media, o 4 pollos a la brasa — los dueños lo entienden como "lo que gano en un día"

### Estrategia de precios a 12 meses

| Mes | Precio Pro | Estrategia |
|---|---|---|
| 1 – 6 | **S/ 69** (lanzamiento) | Penetración agresiva para ganar tracción y casos de éxito |
| 7 – 12 | **S/ 99** (regular) | Subida gradual, ya con casos de éxito y referencias |
| 12+ | **S/ 119 – 129** | Consolidación, con mejoras continuas y reconocimiento de marca |

### Posicionamiento competitivo

```
                  CARO
                    ↑
                    Venko (S/ 185+)
                    |
                    WasiPOS (S/ 148)
    MENOS         ←  |  →            MÁS
    VALOR          QuickTable (S/ 99)   VALOR
                    |
                    Urbaner (S/ 93)
                    |
                    TuCarta.pe (S/ 30-93)
                    ↓
                  BARATO
```

QuickTable se posiciona como **líder en valor** (más funcionalidades que TuCarta.pe y Urbaner, a menor precio que Venko y WasiPOS).

### Resumen de precio óptimo

| Variable | Valor |
|---|---|
| **Precio plan Pro** | **S/ 99/mes** |
| **Precio de lanzamiento** | S/ 69/mes (primeros 6 meses) |
| **Competidor directo** | WasiPOS (S/ 148/mes) + TuCarta.pe (S/ 30-93/mes) |
| **Ventaja diferencial** | Todo en uno: menú digital + cocina + inventario + facturación + IA |
| **Segmento target** | Restaurantes medianos (6-20 mesas) en Lima y principales ciudades |
| **Valor percibido** | S/ 99 = ~1 cubierto diario → "si me ahorra un plato robado al mes, ya pagó" |

---

*Documento generado el 17 de junio de 2026*
*QuickTable — Menú digital inteligente para restaurantes*
