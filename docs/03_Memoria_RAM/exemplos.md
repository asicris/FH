# Memoria RAM: Exemplos Prácticos

## 1. Cálculo de Latencia e Ancho de Banda

### 1.1 Exemplo 1: Latencia Real en ns

**Datos:**
- Memoria: DDR4-3200 CL16
- Frecuencia: 3200 MHz
- Latencia CAS: 16 ciclos

**Cálculo:**
$$\text{Latencia (ns)} = \frac{\text{CL}}{f \text{ MHz}} \times 1000 = \frac{16}{3200} \times 1000 = 5 \text{ ns}$$

**Compare con DDR5-6000 CL36:**
$$\text{Latencia (ns)} = \frac{36}{6000} \times 1000 = 6 \text{ ns}$$

**Conclusión:** A pesar de que DDR5 ten maior CL en valores absolutos, a latencia real en ns é similar ou mellor debido á frecuencia máis alta.

---

### 1.2 Exemplo 2: Ancho de Banda Total

**Datos:**
- Memory Rate (MT/s): 3200 MT/s para DDR4-3200
- Canles de Datos: 64 bits = 8 bytes
- Número de Canles: 2 (Dual Channel)

**Cálculo para Canle Simple:**
$$\text{Ancho de Banda} = \text{MT/s} \times \text{Tamaño de Dato} = 3200 \text{ MT/s} \times 8 \text{ bytes} = 25.6 \text{ GB/s}$$

**Cálculo para Dual Channel:**
$$\text{Ancho de Banda Total} = 25.6 \text{ GB/s} \times 2 = 51.2 \text{ GB/s}$$

**Comprobación alternativa:**
$$\text{Ancho de Banda} = \frac{f \text{ MHz}}{1000} \times 2 \times 8 \text{ bytes} \times \text{num\_canles}$$
$$= \frac{3200}{1000} \times 2 \times 8 \times 2 = 51.2 \text{ GB/s}$$

---

### 1.3 Exemplo 3: Diferenza de Rendemento entre Canles

**Escenario:** Aplicación que require transferencia de datos masiva (p.e., renderizado 3D)

**Configuración Probe 1: Single Channel**
- 1 × 16 GB DDR4-3200
- Ancho de banda: 25.6 GB/s
- Tempo de transferencia para 1 GB: $\frac{1024 \text{ MB}}{25.6 \text{ GB/s}} = 40 \text{ ms}$

**Configuración Probe 2: Dual Channel**
- 2 × 8 GB DDR4-3200
- Ancho de banda: 51.2 GB/s
- Tempo de transferencia para 1 GB: $\frac{1024 \text{ MB}}{51.2 \text{ GB/s}} = 20 \text{ ms}$

**Beneficio:** **50% máis rápido** con Dual Channel

---

## 2. Comparativa de Compatibilidade XMP/EXPO

### 2.1 Exemplo: Selección de Memoria para Ryzen 7 5800X (Socket AM4)

**Situación:** O usuario compra DDR5 XMP para procesador que soporta DDR4.

| Aspecto | Resultado |
|--------|-----------|
| Compatibilidade Hardware | ❌ INCOMPATIBLE (Socket AM4 é DDR4 obrigatorio) |
| BIOS Detecta | Non (slot diferente, pines diferentes) |
| Dano Físico | ⚠️ Risco de rotura  |

**Solución Correcta:**
- Ryzen 5800X (AM4) → Usar DDR4-3600 com EXPO ou 3200 JEDEC

---

### 2.2 Exemplo: Selección de Memoria para Ryzen 7 7700X (Socket AM5)

**Situación:** Usuario quere máximo rendemento con Ryzen 7700X

**Opción 1: DDR5-6000 EXPO (Recomendado)**
- Especificacións: CORSAIR VENGEANCE DDR5-6000 CL30
- Precio: €150-180
- BIOS Setting: Activar "EXPO Profile" en UEFI
- Rendemento Esperado: +15-20% vs. JEDEC DDR5-4800

**Opción 2: DDR5-5600 (Alternativa Estable)**
- Especificacións: Kingston Fury Beast DDR5-5600
- Precio: €120-150
- BIOS Setting: Manual timing adjustment
- Rendemento Esperado: Estable, similar a DDR5-5600 EXPO

**Recomendación:** Opción 1 (melhor relación prezo-rendemento)

---

## 3. Cálculo de Timing Stack Completo

### 3.1 Exemplo: Perfil XMP G.Skill Trident Z5

**Memoria:** G.Skill Trident Z5 DDR5-6000 CL30

**Profile Cargado no BIOS:**
```
Frecuencia:       6000 MHz
CAS Latency (CL): 30 ciclos
RAS to CAS (tRCD): 32 ciclos
RAS Precharge (tRP): 32 ciclos
RAS Active (tRAS): 72 ciclos
Command Rate:      1T
Voltage:           1.25V (DDR5-6000 típico)
```

**Cálculo de latencia en ciclos:**
$$\text{Latencia Total} = CL = 30 \text{ ciclos}$$

**En nanosegundos:**
$$\text{Latencia (ns)} = \frac{30}{6000} \times 1000 = 5 \text{ ns}$$

---

### 3.2 Exemplo: Configuración Manual para Estabilidade

**Escenario:** O usuario tenta overclock manual a DDR5-6400 sen perfil XMP

**Pasos:**
1. **Estabelecer frecuencia:** 6400 MHz
2. **Timings iniciais conservadores:**
   - CL: 38 (en lugar de 36)
   - tRCD: 36
   - tRP: 36
   - tRAS: 76
3. **Voltaxe:** 1.35V (máximo seguro para DDR5)
4. **Proba:** MemTest86 o Cinebench durante 4 horas
5. **Se fallha:** Reducir frecuencia a 6200 MHz ou aumentar tRCD a 38

---

## 4. Impacto do Dual Channel en Aplicacións Reais

### 4.1 Exemplo: Gaming (1440p, Ray Tracing)

**Configuración A: Single Channel**
```
16 GB DDR4-3200 (1 DIMM en Slot A1)
GPU: RTX 4070
CPU: Intel Core i5-13600K
```

**Configuración B: Dual Channel**
```
16 GB DDR4-3200 (2× 8GB en Slots A1 + B1)
GPU: RTX 4070
CPU: Intel Core i5-13600K
```

**FPS (Cyberpunk 2077, Ultra Settings, 1440p):**
| Canle | FPS Promedio | Stuttering |
|-------|---|---|
| Single | 65 fps | Notóreo (1-2 fps drops) |
| Dual | 78 fps | Mínimo (~0.1 fps drops) |

**Diferenza:** +20% de FPS e eliminación de stuttering

---

### 4.2 Exemplo: Renderizado 3D (Blender - Cycles)

**Proxecto:** Renderizado de escena complexa (5000 × 5000 px, Ray Tracing)

**Configuración:**
```
CPU: Ryzen 9 7950X
Memoria: 32 GB DDR5-6000 EXPO
GPU: RTX 4090 (renderizado CUDA)
Tempo Base: 180 segundos
```

**Impacto da Velocidade de Memoria:**

| Tipo de Memoria | Tempo Render | Diferenza |
|---|---|---|
| DDR4-3200 Single | 210 seg | +16.7% |
| DDR4-3200 Dual | 195 seg | +8.3% |
| DDR5-6000 Dual | 180 seg | Baseline |

**Conclusión:** Dual Channel + frequencia alta = máximo rendemento en workloads CPU-intensivos

---

## 5. Diagnóstico de Problemas de Memoria

### 5.1 Exemplo: Computador non inicia (POST Error)

**Síntomas:**
- Beep repetido (patrón: 1 longo - 2 curtos)
- Pantalla en negro
- Ningún logo de fabricante

**Diagnóstico e Solución:**

| Paso | Acción | Resultado Esperado |
|------|--------|---|
| 1 | Desconecta todo (360 V, ±5 min) | Descargas electrostáticas disipadas |
| 2 | Reinserta DIMM coa presión uniforme | Clips laterais soan |
| 3 | Proba con 1 DIMM só | Si arranca, a outra está dañada |
| 4 | Limpa contactos con alcol isopropílico | Óxido eliminado |
| 5 | Reactiva en BIOS (auto-detect) | BIOS detecta memoria correcta |

---

### 5.2 Exemplo: Erros de Memoria en Carga de SO (BSOD - Windows)

**Mensaxe de Erro:** `MEMORY_MANAGEMENT` ou `KERNEL_MEMORY_INPAGE_ERROR`

**Causas Posibles:**
1. XMP/EXPO inestable (overclock fallido)
2. Memoria defectuosa (fallo en banco específico)
3. Incompatibilidade BIOS/placa base

**Protocolo de Solución:**

**Opción A: Desactivar XMP**
```
1. Reinicia e entra en BIOS (Del, F2, F12 segundo fabricante)
2. Navega a Overclocking → XMP Profile
3. Cambia a "Disabled" ou "JEDEC"
4. Garda e reinicia
5. Si arranca correctamente → XMP era o problema
```

**Opción B: MemTest86**
```
1. Descarga MemTest86 (gratuíto en memtest86.com)
2. Grava en pen drive USB
3. Arranca desde USB
4. Executa teste durante 8+ horas
5. Si hay erros → Memoria defectuosa (RMA/cambio)
```

---

## 6. Tabla de Compatibilidade Rápida

### 6.1 Socket de Procesador - Tipo de Memoria

| Socket | Xeneración | Tipo | Velocidade Estándar | Canles |
|--------|---|---|---|---|
| LGA1700 (Intel 12-14 Gen) | 12ª-14ª | DDR5 | 4800 MHz | 2 |
| AM5 (AMD Ryzen 7000+) | 7ª gen+ | DDR5 | 4800 MHz | 2 |
| AM4 (AMD Ryzen 5000) | 5ª gen | DDR4 | 3200 MHz | 2 |
| TRX50 (Threadripper) | Threadripper PRO | DDR5 | 5600 MHz | 12 |

---

## 7. Ferramentas de Diagnóstico

**Recomendadas (Código Aberto/Gratuítas):**
- **MemTest86+:** Teste de memoria integral (bootable)
- **Prime95 Blend Test:** Teste de estabilidade con memoria
- **CPU-Z (Memory Tab):** Verificación de velocidade e timing
- **Aida64 Memory Benchmark:** Comparativa de ancuro de banda
