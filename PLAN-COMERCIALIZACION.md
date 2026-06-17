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

> Precios validados para Perú (junio 2026). TC referencial: 1 USD = S/ 3.75.

| Concepto | Costo único (S/) | Costo mensual (S/) |
|---|---|---|
| Desarrollo backend (FastAPI + PostgreSQL + WebSockets) — freelance Perú ~2 meses | 5,000 – 8,000 | — |
| Frontend web (React/Svelte + PWA responsive) — freelance Perú ~1.5 meses | 3,000 – 5,000 | — |
| Facturación Sunat (integración Nubefact API, S/ 69-129/mes + 1 semana dev) | 1,000 – 2,000 | 70 – 130 |
| Pasarela de pagos (Mercado Pago + Culqi, integración estándar) | 800 – 1,500 | — |
| Multi-sede + jerarquía + roles + permisos | 1,000 – 2,000 | — |
| IA Chat (OpenAI GPT-4o-mini: $0.15/1M input, $0.60/1M output — 50 clientes, ~500 msgs c/u = ~S/ 50-150/mes) | — | 50 – 150 |
| VPS DigitalOcean ($24-48/mo: 4GB-8GB RAM, 2-4 vCPU) | — | 90 – 180 |
| Dominio .pe (NIC.pe: ~S/ 35-40/año) + Let's Encrypt SSL gratis | 40 | 3 |
| Logo + identidad visual (freelance Perú) | 300 – 500 | — |
| Landing page + documentación (plantilla + ajustes) | 500 – 1,000 | — |
| Soporte técnico (dev freelance part-time, ~10h/sem) | — | 500 – 800 |
| Marketing inicial (Facebook + Google Ads para Lima) | 500 | 300 – 600 |
| **TOTALES** | **S/ 12,140 – 20,000** | **S/ 1,013 – 1,863** |

### Costos operativos promedio mensual estimado: **S/ 1,500/mes**

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
| 10 | S/ 750 | – S/ 750 |
| **20** | **S/ 1,500** | **≈ S/ 0 (Break-even)** |
| 30 | S/ 2,250 | + S/ 750 |
| 40 | S/ 3,000 | + S/ 1,500 |
| 50 | S/ 3,750 | + S/ 2,250 |
| 60 | S/ 4,500 | + S/ 3,000 |
| 80 | S/ 6,000 | + S/ 4,500 |

**Break-even:** ~20 clientes (o ~15 en plan Pro)
**Recuperación de inversión inicial (S/ 16k):** ~7 meses con 30 clientes

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
| Backend escalable (FastAPI + Redis + Workers + CDN) — freelance Perú ~3 meses | 8,000 – 12,000 | — |
| Frontend web (Next.js + SSR + PWA avanzada) — freelance Perú ~2 meses | 5,000 – 8,000 | — |
| App mobile nativa (Flutter/React Native, iOS + Android) — freelance Perú ~3 meses | 10,000 – 18,000 | — |
| Facturación Sunat (integración directa OSE + Nubefact backup) | 1,500 – 3,000 | 70 – 130 |
| Pasarela de pagos (Mercado Pago + Culqi + Yape) | 1,500 – 2,500 | — |
| Multi-sede + jerarquía + roles + permisos (full) | 1,500 – 3,000 | — |
| IA Chat (GPT-4o-mini fine-tuned, ~200 clientes) | — | 200 – 500 |
| Infraestructura cloud (AWS/GCP escalable) | — | 400 – 800 |
| Base de datos gerenciada (RDS/Cloud SQL) | — | 200 – 400 |
| CDN + Storage (CloudFront + S3) | — | 50 – 100 |
| Seguridad (WAF, pentesting, OWASP audit) | 3,000 – 5,000 | 100 – 200 |
| Dominio .pe + SSL + emails corporativos | 80 | 20 |
| UX/UI premium (diseño freelance Perú) | 1,500 – 3,000 | — |
| Landing page profesional + SEO + blog | 1,500 – 3,000 | — |
| Dashboard avanzado (reportes exportables) | 1,000 – 2,000 | — |
| Soporte técnico (1 persona part-time L1/L2) | — | 1,500 – 2,000 |
| Marketing (Ads + Google Play + TikTok) | 2,000 | 1,500 – 3,000 |
| **TOTALES** | **S/ 36,080 – 59,500** | **S/ 4,020 – 7,150** |

### Costos operativos promedio mensual estimado: **S/ 5,500/mes**

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
| 20 | S/ 1,500 | – S/ 4,000 |
| 50 | S/ 3,750 | – S/ 1,750 |
| **74** | **S/ 5,550** | **≈ S/ 0 (Break-even)** |
| 100 | S/ 7,500 | + S/ 2,000 |
| 150 | S/ 11,250 | + S/ 5,750 |
| 200 | S/ 15,000 | + S/ 9,500 |
| 500 | S/ 37,500 | + S/ 32,000 |

**Break-even:** ~74 clientes (o ~56 en plan Pro)
**Recuperación de inversión inicial (S/ 48k):** ~12 meses con 100 clientes

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
| **Inversión inicial** | **S/ 12k – 20k** | **S/ 36k – 60k** |
| **Costo operativo mensual** | **S/ 1k – 1.9k** | **S/ 4k – 7.2k** |
| **Costo promedio mensual** | **~ S/ 1,500** | **~ S/ 5,500** |
| **Capacidad máxima** | **50 – 80 restaurantes** | **500+ restaurantes** |
| **Break-even (a S/ 75 prom.)** | **~20 clientes** | **~74 clientes** |
| **Break-even (solo plan Pro S/ 99)** | **~15 clientes** | **~56 clientes** |
| **Recuperación inversión** | ~7 meses (30 clientes) | ~12 meses (100 clientes) |
| **Tiempo desarrollo** | **6 – 10 semanas** | **4 – 6 meses** |

---

# ESTRATEGIA RECOMENDADA

## Fase 1 — Básico (Mes 1–3)
- Invertir S/ 16k en desarrollo del MVP completo
- 10 clientes beta gratis para validación
- Costo mensual: S/ 1,500
- Objetivo: 15 – 20 clientes pagos

## Fase 2 — Crecimiento (Mes 4–8)
- Escalar a 40 – 50 clientes con marketing
- Costo mensual sube a ~S/ 2,000
- Ingreso mensual: S/ 2,250 – 3,750
- **Break-even alcanzado (~20 clientes en mes 4-5)**

## Fase 3 — Salto a Completo (Mes 9–12)
- Con el flujo de caja estable (~S/ 2,500+/mes con 40+ clientes)
- Evaluar si los clientes piden app nativa o la PWA es suficiente
- Inversión adicional para mobile + cloud: S/ 25k – 40k
- Objetivo: 100+ clientes en 12 meses

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
| Vendedor part-time (comisiones) | S/ 3,000 | S/ 9,000 | S/ 15,000 | S/ 27,000 |
| Facebook/Instagram Ads | S/ 600 | S/ 3,000 | S/ 4,500 | S/ 8,100 |
| Google Ads | S/ 600 | S/ 3,000 | S/ 4,500 | S/ 8,100 |
| Aliados estratégicos | S/ 300 | S/ 1,000 | S/ 1,500 | S/ 2,800 |
| TikTok (producción básica) | S/ 300 | S/ 1,000 | S/ 1,500 | S/ 2,800 |
| **Total distribución** | **S/ 4,800** | **S/ 17,000** | **S/ 27,000** | **S/ 48,800** |

> Nota: Estos costos están incluidos en los rubros de marketing y soporte de los costos generales.

> Nota: Estos costos de distribución están **incluidos** en los rubros de marketing y soporte de los costos generales.

---

# TIEMPO DE RECUPERACIÓN DE INVERSIÓN (ROI)

## Escenario Básico (Inversión: S/ 16,000 | Costo mensual: S/ 1,500)

| Mes | Clientes acum. | Ingreso (S/) | Costo (S/) | Flujo del mes | Deuda acumulada |
|---|---|---|---|---|---|
| 1 | 0 (desarrollo) | 0 | 1,500 | –1,500 | –17,500 |
| 2 | 0 (desarrollo) | 0 | 1,500 | –1,500 | –19,000 |
| 3 | 10 (beta) | 0 | 1,500 | –1,500 | –20,500 |
| 4 | 15 | 1,125 | 1,500 | –375 | –20,875 |
| 5 | 20 | 1,500 | 1,500 | 0 | –20,875 |
| 6 | 25 | 1,875 | 1,500 | +375 | –20,500 |
| 7 | 30 | 2,250 | 1,500 | +750 | –19,750 |
| 8 | 35 | 2,625 | 1,500 | +1,125 | –18,625 |
| 9 | 40 | 3,000 | 1,500 | +1,500 | –17,125 |
| 10 | 45 | 3,375 | 1,800 | +1,575 | –15,550 |
| 11 | 50 | 3,750 | 1,800 | +1,950 | –13,600 |
| 12 | 55 | 4,125 | 1,800 | +2,325 | –11,275 |
| 13 | 60 | 4,500 | 1,800 | +2,700 | –8,575 |
| 14 | 65 | 4,875 | 1,800 | +3,075 | –5,500 |
| **15** | **70** | **5,250** | **1,800** | **+3,450** | **–2,050** |
| **16** | **75** | **5,625** | **1,800** | **+3,825** | **≈ +1,775 ✅** |

**📊 Recuperación de inversión (Escenario Básico): ~16 meses (1 año 4 meses)**

> Asumiendo: precio promedio S/ 75/cliente, crecimiento de 5 clientes nuevos/mes.

### Escenario Básico — Sensibilidad por precio

| Precio promedio | Clientes p/ break-even | Tiempo recuperación |
|---|---|---|
| S/ 49 (solo básico) | 31 | ~24 meses |
| **S/ 75 (mix de planes)** | **20** | **~16 meses** |
| S/ 99 (todos Pro) | 15 | ~12 meses |
| S/ 129 (Pro + addons) | 12 | ~10 meses |

---

## Escenario Completo (Inversión: S/ 48,000 | Costo mensual: S/ 5,500)

| Mes | Clientes acum. | Ingreso (S/) | Costo (S/) | Flujo del mes | Deuda acumulada |
|---|---|---|---|---|---|
| 1-4 | 0 (desarrollo) | 0 | 5,500 | –22,000 | –70,000 |
| 5 | 10 (beta) | 0 | 5,500 | –5,500 | –75,500 |
| 6 | 15 | 1,125 | 5,500 | –4,375 | –79,875 |
| 7 | 22 | 1,650 | 5,500 | –3,850 | –83,725 |
| 8 | 30 | 2,250 | 5,500 | –3,250 | –86,975 |
| 9 | 40 | 3,000 | 5,500 | –2,500 | –89,475 |
| 10 | 50 | 3,750 | 5,500 | –1,750 | –91,225 |
| 11 | 60 | 4,500 | 5,500 | –1,000 | –92,225 |
| 12 | 70 | 5,250 | 5,500 | –250 | –92,475 |
| 13 | 80 | 6,000 | 5,500 | +500 | –91,975 |
| 14 | 90 | 6,750 | 5,500 | +1,250 | –90,725 |
| 15 | 100 | 7,500 | 5,500 | +2,000 | –88,725 |
| 16 | 110 | 8,250 | 5,500 | +2,750 | –85,975 |
| 17 | 120 | 9,000 | 5,500 | +3,500 | –82,475 |
| 18 | 130 | 9,750 | 5,500 | +4,250 | –78,225 |
| 19 | 140 | 10,500 | 5,500 | +5,000 | –73,225 |
| 20 | 150 | 11,250 | 5,500 | +5,750 | –67,475 |
| 21 | 160 | 12,000 | 5,500 | +6,500 | –60,975 |
| 22 | 170 | 12,750 | 5,500 | +7,250 | –53,725 |
| 23 | 180 | 13,500 | 5,500 | +8,000 | –45,725 |
| 24 | 190 | 14,250 | 5,500 | +8,750 | –36,975 |
| 25 | 200 | 15,000 | 5,500 | +9,500 | –27,475 |
| 26 | 210 | 15,750 | 5,500 | +10,250 | –17,225 |
| 27 | 220 | 16,500 | 5,500 | +11,000 | –6,225 |
| **28** | **230** | **17,250** | **5,500** | **+11,750** | **≈ +5,525 ✅** |

**📊 Recuperación de inversión (Escenario Completo): ~28 meses (2 años 4 meses)**

> Nota: Requiere 4 meses de desarrollo sin ingresos. Una vez superado el break-even a ~74 clientes, cada cliente adicional es ganancia neta del 85%.

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
