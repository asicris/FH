# Procesador: Fundamentos Técnicos

## Definición Técnica

O **Procesador (CPU - Central Processing Unit)** é o "cerebro" do computador. É un circuíto integrado que executa as instrucións dos programas, realizando operacións lóxicas e aritméticas a velocidades extremadamente altas. Funciona realizando ciclos de lectura-decodificación-execución (ciclo de Fetch-Decode-Execute) coordinado polo reloxo do sistema.

### Características Principais

- **Arquitectura de Cores:** Un procesador moderno pode ter múltiples núcleos (cores) que executan instrucións en paralelo
- **Frecuencia de Reloxo:** Medida en GHz (Gigahertzios), indica cantas operacións por segundo pode realizar
- **Caché:** Memoria ultrarápida integrada no procesador para acceso rápido aos datos máis frecuentemente usados
- **Nanómetros (nm):** Referencia ao tamaño dos transistores; menor tamaño = máis transistores, máis velocidade, menos consumo

---

## 1. Características Máis Importantes do Procesador

### 1.1 Número de Cores (Núcleos)

**Concepto:** Cada core é un executador independente de instrucións.

- **Mono-core (1 core):** Histórico (Intel Pentium 4). HOX: Non existen máis.
- **Multi-core (2-8 cores):** Portátiles e PCs estándar actuais
- **Many-core (8-128+ cores):** Workstations, servidores e procesadores HEDT

**Exemplo:**
- Intel Core Ultra 5 135U: **10 cores** (6 P-cores + 4 E-cores, veremos máis adiante)
- AMD Ryzen 7 7800X3D: **8 cores**
- Intel Xeon Platinum 8592+: **60 cores** (para servidores)

### 1.2 Frequency Threads (Fíos de Execución)

**Concepto:** Un core pode executar moitos "fíos" de forma simulada mediante **Hyperthreading** (Intel) ou **SMT** (AMD - Simultaneous Multithreading).

**Relación cores/threads:**
- Cada core tradicionalmente = 1 thread
- Con Hyperthreading/SMT: Cada core = 2 threads

**Exemplo:**
- Intel Core i7-13700K: **12 cores = 20 threads** (8 P-cores cOn 2 threads cada unha + 4 E-cores con 1 thread cada una)
- AMD Ryzen 5 7600X: **6 cores = 12 threads** (cada core cOn 2 threads)

### 1.3 Clock Speed (Velocidade Base e Turbo)

**Velocidade Base:** Frecuencia garantida en todas as condicións
- Exemplo: 2.4 GHz

**Velocidade Turbo (Boost):** Frecuencia máxima que pode alcanzar temporalmente se a térmica o permite
- Exemplo: 5.6 GHz (Intel Base Clock Boost - BLCK)

**Relación:** Máis GHz = máis instrucións por segundo, pero depende da arquitectura e do número de cores.

### 1.4 Caché

**L1 Cache:** Máis pequena, máis rápida (32 KB por core, típicamente)
- **Latencia:** ~2-3 ciclos de reloxo

**L2 Cache:** Intermediate (256 KB-512 KB por core)
- **Latencia:** ~10-20 ciclos

**L3 Cache:** Máis grande, máis lenta (8 MB-32 MB, compartida entre cores)
- **Latencia:** ~40-60 ciclos

> **Punto técnico:** A caché é crucial porque axuda o procesador a evitar ir continuamente á RAM. Se os datos están en caché, a execución é moito máis rápida.

### 1.5 Proceso de Fabricación (Nanómetros)

*Definición:** O tamaño físico dos transistores no chip.

- **7 nm:** Intel Core Ultra, AMD Ryzen 7000 (2022)
- **5 nm:** Apple M-series, NVIDIA H100
- **3 nm:** Intel Arrow Lake, TSMC next-gen (2024+)
- **Menores nm = máis transistores, máis velocidade, menos consumo enerxético**

**Comparativa simples:**
- Un Intel Pentium 4 (130 nm, 2000) tiña 42 millóns de transistores
- Un Intel Core i9 (7 nm, 2023) ten ~19 mil millóns de transistores

---

## 2. Evolución Simples dos Procesadores

### 2.1 Era Intel (1970s-1990s)

| Ano | Procesador | Velocidade | Transistores | Tecnoloxía |
|-----|-------------|-----------|--------------|-----------|
| 1974 | Intel 4004 | 108 kHz | 2,300 | 10 µm |
| 1985 | Intel 386 | 16-25 MHz | 275,000 | 1 µm |
| 1993 | Intel Pentium | 60-120 MHz | 3.1M | 0.8 µm |
| 2000 | Intel Pentium 4 | 1.3-2 GHz | 42M | 180 nm |

### 2.2 Era Multi-Core (2000s)

- **2006:** Intel Core Duo (2 cores)
- **2006:** AMD Athlon 64 X2 (2 cores)
- **2007:** Intel Core 2 Quad (4 cores)

### 2.3 Era Moderna (2010s-2020s)

**Intel:**
- Core i3/i5/i7 (4-10 cores)
- Xeon (servidores, até 60+ cores)

**AMD Ryzen:**
- Ryzen 5/7/9 (6-16 cores)
- EPYC (servidores, até 128 cores)

### 2.4 Era da Heterogeneidad (2020s-Actualidade)

Procesadores cOn núcleos de **diferentes tipos**:

- **P-cores (Performance cores):** Máis rápidos, máis consumo (para tarefas pesadas)
- **E-cores (Efficiency cores):** Máis lentos, menos consumo (para tarefas en background)

**Exemplos:**
- Intel Core i9-14900KS: 8 P-cores + 16 E-cores
- Apple M3: 8 P-cores + 2-6 E-cores (segundo modelo)

---

## 3. Marcas Máis Relevantes Actualmente

### 3.1 Intel

**Rangos actuais (2024):**

| Gama | Modelo | Cores/Threads | Uso |
|------|--------|----------------|-----|
| **Ultra-Básica** | Core Ultra 5 | 10 cores | Ofimática, streaming |
| **Básica** | Core i5 | 6-10 cores | Gaming casual, webs |
| **Media** | Core i7 | 8-12 cores | Gaming, editing |
| **Alta** | Core i9 | 14-24 cores | Renderizado, IA |
| **Servidor** | Xeon | 10-60 cores | Datacenters |

**Arquitetura:** Intel 7, Intel 4, Intel 20A (futuro)

### 3.2 AMD

**Rangos actuais (2024):**

| Gama | Modelo | Cores/Threads | Uso |
|------|--------|----------------|-----|
| **Básica** | Ryzen 5 | 5-6 cores | Ofimática, gaming casual |
| **Media** | Ryzen 7 | 8-12 cores | Gaming, workstation |
| **Alta** | Ryzen 9 | 12-16 cores | Renderizado, IA |
| **HEDT** | Ryzen Threadripper | 24-96 cores | VFX, CAD masivo |
| **Servidor** | EPYC | 12-128 cores | Cloud, AI training |

**Arquitectura:** Zen 5, Zen 5c (2024)

### 3.3 Apple Silicon

**Non só para Macs:**
- M3, M3 Pro, M3 Max
- **Características:** Arquitectura ARM, núcleos heteroxéneos, GPU integrada de alto rendemento
- **Uso:** MacBooks, Mac Studios

### 3.4 Outros Fabricantes Importantes

- **Qualcomm:** Snapdragon (móviles, tablets)
- **ARM (Holdings):** Arquitectura aberta (non fabrica, licencia)
- **NVIDIA:** Grace (servidores), Orin (IA/coches autónomos)

---

## 4. Procesadores de Portátiles vs. Sobremesa

### 4.1 Diferencias Principais

| Aspecto | Sobremesa | Portátil |
|--------|----------|----------|
| **Consumo (TDP)** | 65-250W | 15-55W (típicamente) |
| **Velocidad Base** | 3.5-4.5 GHz | 2.5-4.0 GHz |
| **Velocidad Turbo** | Até 5.8 GHz | Até 4.5-5.0 GHz |
| **Cores** | 6-24+ | 4-10 |
| **Socket** | Intel LGA1400, AM5 | BGA (soldado a placa base) |
| **Extraíble** | Sí | Non (está soldado) |
| **Refrigeración** | Ventiladores robustos | Sistemas pasivos/activos limitados |

### 4.2 Características que Debe Ter un Procesador de Portátil

✅ **Consumo Enerxético Baixo (15-55W TDP):**
- Decisivo para autonomía da batería

✅ **Gráficos Integrados:**
- Non necesita tarxeta gráfica discreta (facilita ultraportátiles)

✅ **Thermal Throttling Controlado:**
- O procesador redúce a velocidad se se sobrecalienta, pero sen apagarse

✅ **Arquitectura Eficiente (P+E cores):**
- P-cores para xogos/edición
- E-cores para tarefas correntes

✅ **Exemplo Intel Core Ultra 5 135U:**
- 10 cores (6P + 4E), 2.6-5.0 GHz
- TDP: 15W até 57W (depende da xunta térmica)
- GPU Intel Graphics

---

## 5. Procesadores Relevantes Actualmente (Exemplos Prácticos)

### 5.1 Gaming e Rendimiento Puro

| Procesador | Cores/TDP | Prezo Aprox. | Uso Ideal |
|-----------|-----------|-------------|----------|
| **Intel Core i9-14900KS** | 24 cores (8P+16E) / 150W | €600-700 | Renderizado, streaming, games 4K |
| **AMD Ryzen 9 7950X3D** | 16 cores / 162W | €450-550 | Renderizado 3D, modelaxe |
| **Intel Core i7-14700K** | 20 cores (8P+12E) / 125W | €300-400 | Gaming 1440p, editing |

### 5.2 Portátiles Modernos

| Procesador | TDP | Batería | Uso |
|-----------|-----|---------|-----|
| **Intel Core Ultra i7-165U** | 28W | 12-15 horas | Ultraportátil, ofimática |
| **Apple M3** | 8W-25W | 16-18 horas | MacBook Pro/Air |
| **AMD Ryzen 7 8840HS** | 35-55W | 8-10 horas | Portátil gaming |

### 5.3 Servidor e Datacenters

| Procesador | Cores | Uso |
|-----------|-------|-----|
| **Intel Xeon Platinum 8592+** | 60 cores | Cloud, virtualización masiva |
| **AMD EPYC 9755** | 128 cores | AI training, big data |
| **ARM-based Ampere Altra** | 80 cores | Servidores low-cost |

### 5.4 IA e Machine Learning

| Procesador | GPU Dedicada | TDP | Uso |
|-----------|-------------|-----|-----|
| **NVIDIA H200** | Hopper | 700W | Training de LLMs (GPT, Claude) |
| **Intel Gaudi3** | Si | 600W | Inferencia IA a escala |
| **AMD MI325X** | CDNA3 | 850W | IA empresarial |

---

## 6. AMD vs Intel: Breve Historia e Actualidade

### 6.1 A Rivalidade Histórica

**1980s-1990s: Hegemonía Intel**
- Intel dominaba cOn Pentium
- AMD era a alternativa máis barata cOn AMDs similares

**2000s: Ascenso de AMD**
- AMD lanza Athlon 64 (competitivo)
- Intel recupera con Core 2 Duo

**2010s: Era Intel**
- Core i3/i5/i7 dominan completamente
- AMD en segundo plano cOn A-series mediocres

**2020s: Renacimiento AMD**
- Ryzen 1000 (2017) revoluciona a industria
- Arquitectura Zen 3/4/5 gana en power-per-watt (W/watios)
- Intel pierde cuota de mercado

### 6.2 Estat Actual (2024)

| Aspecto | Intel | AMD |
|--------|-------|-----|
| **Domicilio HQ** | Santa Clara, California | Austin, Texas |
| **Arquitectura** | Intel 7/4nm (7 nm non oficial) | Zen 5 (TSMC 5nm) |
| **Ventaxa Principal** | Cores P+E heteroxéneos | Relación prezo-rendimiento |
| **Servidores** | Xeon (forte) | EPYC (forte) |
| **Gaming** | Core i9 excelente | Ryzen forte |
| **IA Nativa** | Intel Gaudi débil | MI300X forte |

### 6.3 Razóns da Rivalidade Técnica

**Intel Vantaxes:**
- Primeiro a sacar arquitectura P+E cores
- Moolers gráficos integrados (Intel Graphics)
- Ecosistema maduro

**AMD Vantaxes:**
- Menor consumo enerxético
- Relación cores-prezo mellor
- Arquitectura aberta cOn proveedores diversos (TSMC)

---

## 7. IA nos Procesadores: Cambios Recentes

### 7.1 Cambio de Paradigma

Historicamente, a IA executábase en **GPUs externas** (NVIDIA). Agora, **os propios CPUs teñen aceleradores IA integrados**.

### 7.2 Aceleradores IA Integrados

**Intel Neural Processing Unit (NPU):**
- En Intel Core Ultra (2023+)
- Capacidad: Ejecutar modelos IA pequenos en portátiles

**Apple Neural Engine:**
- En todos os MacBooks desde M1
- Optimizado para visión, procesamento de audio

**AMD Ryzen AI:**
- Integrado en Ryzen 7040U+ (portátiles)
- Acelerador de IA de XDNA

### 7.3 Exemplos Prácticos

**Caso 1: Portátil con NPU**
- Intel Core Ultra con NPU executar:
  - Reconocemento de voz en local (non na nube)
  - Edición de imaxes con IA nunca en segundo plano
  - Tradución en tempo real

**Caso 2: Servidor con IA Nativa**
- NVIDIA Grace Hopper:
  - CPU (arm64) + GPU Hopper
  - Máximo para training de LLMs 

---

## 8. Diferencia Entre CPU, GPU e Procesador de IA

### 8.1 CPU (Central Processing Unit)

**Definición:** O procesador principal. Executa instrucións secuencialmente.

**Características:**
- Poucos cores (2-24 típicamente), pero cada un é moi potente
- Espabillez cOn lóxica complexa e decisións
- Baixa latencia de acceso a memoria
- Rendimiento: ~GFLOPs (Giga Floating Operations per Second)

**Exemplo:** Intel Core i7 procesando un programa en Python

### 8.2 GPU (Graphics Processing Unit)

**Definición:** Procesador especializado en paralelo masivo. Millares de cores pequenos.

**Características:**
- Moitos cores (1000-10000+), cada un é simples
- Especializado en operacións vectoriales en paralelo
- Altíssimo throughput (capacidade de procesamento)
- Rendimiento: ~TFLOPs (Tera Floating Operations per Second)

**Exemplo:** NVIDIA RTX 4090 renderizando gráficos ou entrenando rede neuronal

### 8.3 NPU (Neural Processing Unit) / TPU (Tensor Processing Unit)

**Definición:** Acelerador especializado en multiplicacións de matrices, necesario para IA/ML.

**Características:**
- Cores ultra-especializados para operacións tensorials
- Consumo enerxético moi baixo
- Inferencia ultra-rápida, entrenamiento limitado
- Rendimiento: ~TOPs (Tera Operations per Second)

**Exemplo:** Apple Neural Engine procesando Face ID, o Intel NPU correndo Copilot Pro

### 8.4 Comparativa Visual

```
CPU:   ←→ [Core 1 (Complexo)] ←→ [Core 2 (Complexo)] ← Poucos cores, potentes

GPU:   [C][C][C][C][C][C][C][C]
       [C][C][C][C][C][C][C][C]
       [C][C][C][C][C][C][C][C] ← Millares de cores, simples

NPU:   [⨯][⨯][⨯][⨯][⨯][⨯][⨯][⨯] ← Cores tensor especializados
       [⨯][⨯][⨯][⨯][⨯][⨯][⨯][⨯]
```

### 8.5 Benchmarks Comparativos (Exemplos)

| Operación | CPU (i9-14900K) | GPU (RTX 4090) | NPU (Intel Gaudi) |
|-----------|-----------------|---|---|
| Matrix 1000x1000 (FP32) | 10 segundos | 0.1 segundos | 0.05 segundos |
| Inferencia LLM (4-bit) | 50 t/s | 500 t/s | 1000 t/s |
| Compilación C++ | Óptimo | Pobre | Non aplicable |
| OpenGL Rendering | Pobre | Óptimo | Pobre |

**Conclusión:** Cada un é especialista na súa área.

---

## 9. Tecnoloxías de Optimización

### 9.1 Thermal Throttling

**Concepto:** Cando a temperatura supera o límite, o procesador reduce automaticamente a velocidad para protexerse.

- Intel: ~90-100°C límite
- AMD: ~95°C límite

**Impacto:** Perda de rendimiento pero evita queimacións

### 9.2 Turbo Boost (Intel) / Precision Boost (AMD)

| Tecnoloxía | Fabricante | O que fai |
|-----------|-----------|----------|
| **Turbo Boost 5.0** | Intel | Aumenta frecuencia dinámicamente ata 5.8 GHz |
| **Precision Boost Overdrive 2** | AMD | Autoboost até máximo termal e enerxético |

### 9.3 Undervolting

**Técnica avanzada:** Reducir a voltaxe (V) mentres se mantén a frecuencia (GHz).

- Menos calor e consumo
- Máis autonomía en portátiles
- Requiere conocemento técnico e ferramentas como Throttlestop

---

## 10. Guía de Compra: Escoller o Procesador Axeitado

### 10.1 Para Ofimática e Navegación Web

**Requisitos:**
- CPU base: 2 GHz+
- Cores: 4-6
- RAM: 8 GB
- TDP: < 15W (se é portátil)

**Recomendación:**
- Intel Core i3-13100
- AMD Ryzen 5 5500
- Apple M3 (MacBook Air)

### 10.2 Para Gaming 1080p/1440p

**Requisitos:**
- CPU base: 3.5 GHz+
- Cores: 8-10
- Threads: 16+
- RAM: 16-32 GB
- GPU: Dedicada en portátil

**Recomendación:**
- Intel Core i7-14700K
- AMD Ryzen 7 7700X
- Portátil: Ryzen 7 8840HS

### 10.3 Para Renderizado 3D, Edición 4K

**Requisitos:**
- Cores: 12-16+
- Threads: 24-32+
- RAM: 32-64 GB
- TDP alto (150W+)

**Recomendación:**
- Intel Core i9-14900K
- AMD Ryzen 9 7950X3D

### 10.4 Para Servidor / Datacenter

**Requisitos:**
- Cores: 16-128
- ECC RAM soportada
- Socket estándar (LGA, EPYC)
- TDP: 200-700W

**Recomendación:**
- Intel Xeon Platinum 8592+
- AMD EPYC 9755

---

## 11. Configuracións Recomendadas (Resumen)

| Uso | CPU | Cores | Prezo Aprox. | Porto |
|-----|-----|-------|-------------|-------|
| **Ultraportátil** | Intel Core Ultra 5 135U | 10 | €600-800 | Sí |
| **Gaming Casual 1080p** | Intel i5-14400 | 10 | €200 | Sobremesa |
| **Gaming 1440p+ / Streaming** | Intel i7-14700K | 20 | €350 | Sobremesa |
| **Renderizado 3D** | AMD Ryzen 9 7950X3D | 16 | €500 | Sobremesa |
| **Servidor Web** | Intel Xeon Gold 6426Y | 32 | €3000+ | Datacenter |

---

## 12. Procedementos de Seguridade Específica para Procesador

### 12.1 Descarga Electrostática (ESD)

✅ **Antes de manipular o procesador:**
1. Ponte pulseira antiestática
2. Toca a carcasa metálica do case
3. Usa tapete antiestático

⚠️ **Non toques ningunha pista de ouro no processador**

### 12.2 Seguridade Térmica

⚠️ **Crítico:** Instalar correctamente a disipación térmica

1. **Aplicar Pasta Térmica:** Pequeña cantidade no centro do die
2. **Non sobrepasar:** Exceso de pasta reduce a disipación
3. **Venlar Correctamente:** Asegúrate de que os ventiladores funcionan

### 12.3 Manipulación Segura do Socket

⚠️ **Intel LGA (Land Grid Array):**
- A patas están na carcasa, non no procesador
- Se se dobra unha pata: procesador inútil

⚠️ **AMD AM5 (Pin Grid Array):**
- As patas están no procesador
- Manter protector de socket cando non hai procesador

**Pasos Seguros:**
1. Apaga o computador e desconecta a fonte
2. Abre o **retention mechanism** do socket
3. Inserta o procesador coidadosamente (COS con muesca)
4. Pecha a grella de retención
5. Instala o cooler cOn sistema de fixación correcto

---

## 13. Estándares e Órganos de Regulación

- **Intel:** Socket LGA (standards propios)
- **AMD:** Socket AM5 (estándar aberto)
- **ARM Holdings:** Licencia arquitectura (non fabrica)

> Os estándares abertos (como AM5 de AMD) permiten que múltiples fabricantes fagan coolers compatibles, reducindo custos.

---

## 14. Referencias Técnicas

- Intel Official: https://www.intel.com/content/www/es/es/ark.html
- AMD Spec Sheet: https://www.amd.com/es/products/specifications/processors
- Tom's Hardware CPU Hierarchy: https://www.tomshardware.com/reviews/cpu-hierarchy
- TechPowerUp CPU Database: https://www.techpowerup.com/cpu-specs/

---

## 15. Páxinas Interesantes para Profundizar

- [Anandtech (análises técnicas)](https://www.anandtech.com/)
- [Notebookcheck (parsers de portátiles)](https://www.notebookcheck.net/)
- [TechPowerUp (specs detalladas)](https://www.techpowerup.com/)
- [Gamers Nexus (benchmarks de calidade)](https://www.gamersnexus.net/)

---

