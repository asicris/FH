# Microprocesadores 

## 1. Definición e Fundamentos Técnicos

O **Microprocesador (CPU)** é o circuíto integrado central que actúa como o "cerebro" do sistema. A súa función é executar instrucións mediante operacións lóxicas e aritméticas a velocidades de nanosegundos.

### 1.1. O Ciclo de Vida da Instrución

O funcionamento baséase no ciclo **Fetch-Decode-Execute**, coordinado polo reloxo do sistema:

1.**Fetch (Lectura):** Captura a instrución dende a memoria.
2.**Decode (Decodificación):** Traduce a instrución en sinais eléctricos.
3.**Execute (Execución):** Realiza a operación a través da ALU (Unidade Aritmético-Lóxica).

### 1.2. Arquitecturas: CISC vs RISC

* **CISC (Complex Instruction Set Computer):** Instrucións complexas e potentes. É a base da **arquitectura x86** (Intel/AMD) en PCs e servidores.
* **RISC (Reduced Instruction Set Computer):** Instrucións simples e ultra-rápidas. É a base da **arquitectura ARM** (móbiles, Apple M-Series e Qualcomm Snapdragon X), destacando pola súa eficiencia enerxética.

---

## 2. Características Físicas e Estruturais

### 2.1. Conexión e Sockets

O **socket** é a interface física entre o procesador e a placa base:

* **LGA :** Os pins están no socket da placa base. Estándar en Intel e nos novos AMD (AM5). Reduce o risco de danar o CPU.
* **PGA :** Os pins están no propio procesador. Tradicional en AMD (AM4).
* **BGA :** Soldado directamente á placa mediante bólas de estaño. Común en portátiles, consolas e SoCs (*System on Chip*).


### 2.2. Xerarquía de Memoria Caché

Memoria ultra-rápida que evita as esperas pola RAM:

* **L1:** Moi pequena e a máis rápida. Integrada en cada núcleo.
* **L2:** Intermedia en velocidade e capacidade.
* **L3:** A máis grande e lenta da xerarquía, compartida entre todos os núcleos. É vital en tarefas de gaming e renderizado.

---

## 3. O Paradigma Moderno: CPU, GPU e NPU

Os procesadores actuais son **heteroxéneos**, delegando tarefas en aceleradores específicos:

1.**CPU :** Poucos núcleos moi potentes. Ideal para o **Sistema Operativo** e a lóxica de control complexa (*Single-Core*).
2.**GPU (Paralelo):** Millares de núcleos simples. Especializado en **matemáticas vectoriais, gráficos, vídeo** e cálculo masivo.
3.**NPU (Neural Processing Unit):** Acelerador especializado en multiplicar matrices de baixa precisión (tensores). É fundamental para a **IA en local**, permitindo tarefas como o desenfoque de fondos en vídeo ou tradución instantánea con consumo mínimo. Os procesadores modernos con NPU son :

* **Intel** identifíca os procesadores con IA na serie **Core Ultra**
* **AMD** identifícaos na serie **Ryzen AI** (7040/8040 en diante).
* **Snapdragon** - **X Elite**: Todos os modelos desta gama teñen unha NPU dedicada denominada Qualcomm Hexagon. **X Plus**: Tamén inclúen NPU de alto rendemento. En móbiles **Snapdragon 8 Gen X**


---

## 4. Intel vs AMD: Evolución e Rivalidade

### 4.1. Perspectiva Histórica

* **1980s-90s:** Hexemonía de **Intel** coas familias **x86 e Pentium**.
* **2000s:** AMD lanza o Athlon 64, superando a Intel en 64 bits. Intel responde coa exitosa arquitectura **Core 2 Duo**.
* **2017-Actualidade:** AMD revoluciona o mercado co deseño de *chiplets* nos **Ryzen**, forzando a Intel a innovar coa **arquitectura híbrida** (P-Cores de rendemento e E-Cores de eficiencia).

### 4.2. Comparativa de Fabricantes: Intel, AMD, Qualcomm e NVIDIA

| Aspecto | **Intel** | **AMD** | **Snapdragon (Qualcomm)** | **NVIDIA** |
| :--- | :--- | :--- | :--- | :--- |
| **Arquitectura** | **Híbrida** (P-Cores + E-Cores). Baseada en x86. | **Chiplets** (MCM). Énfase en Zen e Zen-c (x86). | **ARM** (Kryo/Oryon). Arquitectura RISC ultra-eficiente. | **ARM + GPU**. Arquitectura Grace (CPU) e Hopper/Blackwell (GPU). |
| **Punto Forte** | Mellor rendemento en *single-core* e ecosistema de software maduro. | Mellor relación núcleos/prezo e gran eficiencia grazas aos chiplets. | Autonomía de batería extrema e NPUs líderes para IA en portátiles. | Liderazgo absoluto en IA, centros de datos e procesamento paralelo (GPU). |
| **Socket / Montaxe** | **LGA** (Pins na placa). Cambia cada 2 xeracións aprox. | **AM5 (LGA)**. Moi duradeiro (soporte por moitos anos). | **BGA** (Soldado). Non intercambiable, integrado en SoC. | **BGA ou Propios**. Deseños integrados para servidores e IA. |
| **IA (NPU)** | **Intel AI Boost** (integrada en Core Ultra). | **Ryzen AI** (tecnoloxía XDNA). | **Hexagon NPU** (Líder actual en TOPs para Windows). | **Tensor Cores** (Líder en adestramento de IA masiva). |
| **Uso Ideal** | Gaming, estacións de traballo e empresa estándar. | Gaming (3D V-Cache), servidores (EPYC) e multitarea. | Ultraportátiles (Always Connected PCs) e móbiles. | Supercomputación, adestramento de LLMs e Cloud. |

**Outros fabricantes:**

| Fabricante | Que fabrica principalmente? | Descrición e Enfoque |
| :--- | :--- | :--- |
| **Samsung** | Procesadores Exynos para móbiles e fabricación para terceiros. | Ademais de deseñar os seus propios chips para móbiles, é un dos poucos no mundo con **fundicións propias** (fábricas) capaces de crear chips en procesos avanzados de 3nm e 4nm. |
| **TSMC** | Non deseña, pero **fabrica** para case todos os anteriores (Apple, AMD, NVIDIA). | Aínda que non vende procesadores coa súa marca, é a empresa máis crítica: sen as súas fábricas en Taiwán, o 90% dos procesadores avanzados do mundo non existirían. |
| **ARM Holdings** | Deseña a **arquitectura** e as licenzas, pero non fabrica chips físicos. | É a empresa que "debuxa os planos". Apple, Qualcomm ou Samsung páganlle por usar a súa arquitectura RISC, que é a base de case tódolos procesadores de móbiles e portátiles de baixo consumo actuais. |

**En resumo:**

* **Deseñadores "Fabless":** Empresas como **AMD, Apple ou NVIDIA** que deseñan os chips pero non teñen fábricas propias; mándanos fabricar a TSMC ou Samsung.
* **Fabricantes Integrados (IDM):** **Intel** é un dos poucos que aínda deseña e fabrica os seus propios chips nas súas propias instalacións (aínda que recentemente comezou a externalizar algunhas partes a TSMC).
* **Arquitectura:** O mercado divídese hoxe entre o mundo **x86 (Intel/AMD)**, onde prima a compatibilidade de software de escritorio, e o mundo **ARM (Apple/Qualcomm)**, onde prima a autonomía e a integración.

### 5.2 Recomendacións procesador segundo finalidade do PC

| Perfil | Fabricantes Clave | Recomendación Técnica |
| :--- | :--- | :--- |
| **Ofimática / Home Office** | Intel, AMD | Intel i3 ou Ryzen 3. Abondo para tarefas web. |
| **Sistemas / Virtualización** | AMD, Intel | **Ryzen 7 / Core i7**. Necesitas moitos fíos (Threads) para VMs. |
| **Gaming de Alto Nivel** | AMD | **Ryzen 7 7800X3D** (pola súa memoria 3D V-Cache). |
| **Portabilidade Extrema** | Apple, Qualcomm | **Apple M3 / Snapdragon X Elite** (Arquitectura ARM). |
| **Servidores / Cloud** | Intel, AMD, NVIDIA | **Xeon, EPYC ou NVIDIA Grace**. Soporte para RAM ECC. |

---

## 6. Que debo mirar á hora de mercar un ordenador? (En relación ao procesador)

Se vas mercar un equipo, non te fixes só no nome da gama (i5, Ryzen 7...). O máis importante é saber ler a "matrícula" do procesador. Mira estes catro puntos clave:

### 1. A Xeración (Un factor determinante)

A arquitectura mellora cada ano. Un procesador de gama media actual adoita ser máis potente que un de gama alta de hai 4 anos.

* **En Intel:** O primeiro ou os dous primeiros números tras o guión indican a xeración.
  * *Exemplo:* i7-**14**700K (Xeración 14). Un i5-**14**400 é superior a un i7-**11**700.
* **En AMD:** O primeiro número indica a serie/xeración (aínda que AMD cambiou a nomenclatura recentemente, a regra xeral mantense).
  * *Exemplo:* Ryzen 7 **7**800X (Serie 7000, arquitectura Zen 4). Un Ryzen 5 **7**600 adoita render mellor que un Ryzen 9 **3**900.

### 2. O Sufixo (U|H|K|X...)(Para que serve ese procesador?)

A letra ao final do modelo indica o escenario para o que foi deseñado:

* **U (Ultra Low Power):** Deseñados para **portátiles finos**. Prioriza a batería e **consume moi pouco**, pero ten **menos potencia** bruta.
* **H / HS / HX (High Performance):** Procesadores de alto rendemento para **portátiles *gaming* ou estacións de traballo**. Consomen moita máis batería e requiren mellor ventilación.
* **K (Intel) / X (AMD):** **Versións de sobremesa** optimizadas para acadar frecuencias máis altas. Os "K" de Intel están desbloqueados para facer *overclock*.
* **F (Intel):** Indica que o procesador **non ten gráficos integrados**. É obrigatorio mercar unha tarxeta gráfica dedicada (NVIDIA ou Radeon).
* **G (AMD):** Indica que o **procesador ten gráficos integrados potentes (APU)**, ideais se non vas mercar unha tarxeta gráfica aparte.

### 3. A NPU e a IA 
Se queres un equipo preparado para as novas ferramentas de IA local (Copilot+, edición de vídeo intelixente, etc.):

* **En Intel:** Busca a nova denominación **Core Ultra** (Series 1 ou 2).
* **En AMD:** Busca modelos coa etiqueta **Ryzen AI** (como as series 7040, 8040 ou os novos Ryzen AI 300).
* **Dato técnico:** Verifica que a NPU teña máis de **40 TOPs** se queres a certificación completa de Microsoft.

### 4. TDP, Refrixeración e "Thermal Throttling"

O **TDP (Thermal Design Power)** indica cantos vatios consome e **cantos vatios de calor debe disipar** o ventilador.

* Se compras un portátil moi fino cun procesador "HX" ou un i9, é moi probable que sufra **Thermal Throttling**: o **procesador baixa a súa velocidade bruscamente porque se quenta demasiado** (supera os 95-100°C), facendo que o rendemento real sexa inferior ao esperado.

---

### 7. Tipos de Núcleos en AMD e en Intel

### 7.1. Intel: A arquitectura híbrida real (P-Cores + E-Cores)

Desde a 12ª xeración (Alder Lake), Intel introduciu o concepto de **núcleos heteroxéneos**. No mesmo chip hai dous tipos de núcleos:

* **P-Cores (Performance):** Núcleos grandes e potentes, con Hyper-Threading (2 fíos por núcleo). Encárganse das tarefas pesadas (xogos, edición).
* **E-Cores (Efficiency):** Núcleos pequenos, sen Hyper-Threading (1 fío por núcleo). Encárganse de tarefas de fondo e aforro de enerxía.

    Xeralmente, os modelos de gama alta (i7, i9) teñen moitos E-Cores. Un i9-14900K, por exemplo, ten 8P + 16E.

### 7.2. AMD: Núcleos "Zen" e "Zen c"

AMD non usa P-Cores e E-Cores ao estilo de Intel. Ata hai pouco, todos os núcleos de AMD eran iguais e de alto rendemento. Recentemente, introduciu os núcleos **"c" (como o Zen 4c)**.

A diferenza de Intel, os núcleos "c" de AMD teñen o **mesmo conxunto de instrucións e a mesma potencia por ciclo** que os núcleos estándar. Simplemente están deseñados de forma máis compacta físicamente, é dicir algúns son máis pequenos, **para meter máis núcleos en menos espazo** e consumir algo menos.
  
Estes núcleospoden verse nos novos procesadores de portátiles (**Ryzen 8000/9000** ou **Ryzen AI 300**).

---

## 8. Procesadores de Portátil vs. Sobremesa

Aínda que un procesador de portátil e un de sobremesa poidan ter o mesmo nome (por exemplo, un "Intel Core i7"), o seu rendemento e comportamento son moi diferentes debido a dous factores críticos: o **espazo** e a **capacidade de refrixeración**.

### 8.1. Diferenzas Técnicas Clave

| Característica | Procesador de Sobremesa (Desktop) | Procesador de Portátil (Laptop) |
| :--- | :--- | :--- |
| **Consumo (TDP)** | Alto (65W - 250W). Prioriza a potencia bruta. | Baixo (15W - 45W). Prioriza a duración da batería. |
| **Encapsulado** | **LGA/PGA**: Instálase nun socket e pode substituírse. | **BGA**: Vai soldado á placa base. Non se pode ampliar. |
| **Refrixeración** | Disipadores grandes e moito fluxo de aire. | Sistemas compactos (heatpipes finos). Moi limitado. |
| **Frecuencia (GHz)** | Frecuencias base e turbo máis altas e estables. | Frecuencias máis baixas para evitar o sobrequecemento. |
| **Gráficos (iGPU)** | Adoitan ser básicos (suponse que usarás unha GPU externa). | Adoitan ser potentes (para non depender de gráficas extra). |

### 8.2. O fenómeno do Thermal Throttling

Nos portátiles, debido ao pouco espazo, o procesador alcanza temperaturas críticas axiña. Para evitar que o chip se queime, o sistema aplica o **Thermal Throttling**: reduce drasticamente a velocidade do reloxo (GHz). Por iso, **un i9 nun portátil ultra-fino pode chegar a render menos que un i5 nun ordenador de sobremesa** ben refrixerado.

## 9. Protocolos de Seguridade Técnica para manipular procesadores

* **Protección ESD:** Uso de pulseira antiestática ou descarga previa en chasis.
* **Pasta Térmica:** Aplicar a cantidade xusta (tamaño dun chícharo). O exceso reduce a disipación.
* **Manipulación:** Nunca tocar os contactos de ouro nin aplicar forza excesiva sobre o socket.

