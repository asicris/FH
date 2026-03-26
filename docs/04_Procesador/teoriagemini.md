Aquí tes a versión definitiva, coherente e sen recortes, que fusiona toda a información técnica, histórica e práctica. Está organizada para ser un recurso de consulta profesional para un alumno de ASIR, revisada lingüisticamente e en formato **Markdown**.

---

# Guía Mestra: Tecnoloxía de Microprocesadores

## 1. Definición e Fundamentos Técnicos
O **Microprocesador (CPU)** é o circuíto integrado central que actúa como o "cerebro" do sistema. A súa función é executar instrucións mediante operacións lóxicas e aritméticas a velocidades de nanosegundos.

### 1.1. O Ciclo de Vida da Instrución
O funcionamento baséase no ciclo **Fetch-Decode-Execute**, coordinado polo reloxo do sistema:
1.  **Fetch (Lectura):** Captura a instrución dende a memoria.
2.  **Decode (Decodificación):** Traduce a instrución en sinais eléctricos.
3.  **Execute (Execución):** Realiza a operación a través da ALU (Unidade Aritmético-Lóxica).

### 1.2. Arquitecturas: CISC vs RISC
* **CISC (Complex Instruction Set Computer):** Instrucións complexas e potentes. É a base da **arquitectura x86** (Intel/AMD) en PCs e servidores.
* **RISC (Reduced Instruction Set Computer):** Instrucións simples e ultra-rápidas. É a base da **arquitectura ARM** (móbiles, Apple M-Series e Qualcomm Snapdragon X), destacando pola súa eficiencia enerxética.

---

## 2. Características Físicas e Estruturais

### 2.1. Conexión e Sockets
O **socket** é a interface física entre o procesador e a placa base:
* **LGA (Land Grid Array):** Os pins están no socket da placa base. Estándar en Intel e nos novos AMD (AM5). Reduce o risco de danar o CPU.
* **PGA (Pin Grid Array):** Os pins están no propio procesador. Tradicional en AMD (AM4).
* **BGA (Ball Grid Array):** Soldado directamente á placa mediante bólas de estaño. Común en portátiles, consolas e SoCs (*System on Chip*).


### 2.2. Xerarquía de Memoria Caché
Memoria ultra-rápida que evita as esperas pola RAM:
* **L1:** Moi pequena e a máis rápida. Integrada en cada núcleo.
* **L2:** Intermedia en velocidade e capacidade.
* **L3:** A máis grande e lenta da xerarquía, compartida entre todos os núcleos. É vital en tarefas de gaming e renderizado.


---

## 3. O Paradigma Moderno: CPU, GPU e NPU
Os procesadores actuais son **heteroxéneos**, delegando tarefas en aceleradores específicos:

1.  **CPU (Geral):** Poucos núcleos moi potentes. Ideal para o Sistema Operativo e a lóxica de control complexa (*Single-Core*).
2.  **GPU (Paralelo):** Millares de núcleos simples. Especializado en matemáticas vectoriais, gráficos, vídeo e cálculo masivo.
3.  **NPU (Neural Processing Unit):** Acelerador especializado en multiplicar matrices de baixa precisión (tensores). É fundamental para a **IA en local**, permitindo tarefas como o desenfoque de fondos en vídeo ou tradución instantánea con consumo mínimo.

### Como saber se un procesador ten NPU?
* **Pola nomenclatura:** Intel identifícaos na serie **Core Ultra**; AMD na serie **Ryzen AI** (7040/8040 en diante).
* **No SO:** En Windows, o *Administrador de tarefas* amosa unha pestana "NPU" se o hardware está presente.
* **Certificación:** Os dispositivos **Copilot+ PC** esixen obrigatoriamente unha NPU potente (>40 TOPs).

---

## 4. Intel vs AMD: Evolución e Rivalidade

### 4.1. Perspectiva Histórica
* **1980s-90s:** Hexemonía de Intel coas familias x86 e Pentium.
* **2000s:** AMD lanza o Athlon 64, superando a Intel en 64 bits. Intel responde coa exitosa arquitectura **Core 2 Duo**.
* **2017-Actualidade:** AMD revoluciona o mercado co deseño de *chiplets* nos **Ryzen**, forzando a Intel a innovar coa **arquitectura híbrida** (P-Cores de rendemento e E-Cores de eficiencia).

### 4.2. Diferenzas de Filosofía (2024)
| Aspecto | **Intel** | **AMD** |
| :--- | :--- | :--- |
| **Arquitectura** | Híbrida (P+E Cores) en moitos modelos. | Énfase na eficiencia e deseño de chiplets. |
| **Punto Forte** | Mellor rendemento en *single-core* e multimedia. | Mellor relación prezo/núcleos e eficiencia térmica. |
| **Socket** | Ciclos curtos (cambia cada 2 xeracións). | Sockets moi duradeiros (AM4/AM5). |

---

## 5. Principais Fabricantes de Procesadores

| Fabricante | Que fabrica principalmente? | Descrición e Enfoque |
| :--- | :--- | :--- |
| **Intel** | CPUs para consumo (Core), servidores (Xeon) e gráficas (Arc). | O xigante histórico da arquitectura **x86**. O seu enfoque actual baséase na **arquitectura híbrida** (P-Cores e E-Cores) para optimizar o consumo en Windows sen perder potencia de pico. |
| **AMD** | CPUs para consumo (Ryzen), servidores (EPYC) e GPUs (Radeon). | Principal competidor de Intel en x86. Destaca polo seu deseño de **chiplets** (varios chips pequenos nun só encapsulado) e por ofrecer unha excelente relación entre número de núcleos, prezo e eficiencia enerxética. |
| **Apple** | SoCs (System on Chip) da serie M e serie A para os seus propios dispositivos. | Revolucionou o mercado co paso á arquitectura **ARM (Apple Silicon)**. Os seus procesadores destacan por unha integración total (memoria e NPU no mesmo chip) e unha eficiencia por vatio inigualable no sector portátil. |
| **Qualcomm** | Procesadores ARM para móbiles (Snapdragon) e agora para PCs (Snapdragon X Elite). | Líder indiscutible en dispositivos móbiles que agora busca romper o duopolio de Intel/AMD en portátiles Windows, ofrecendo NPUs moi potentes para intelixencia artificial e conectividade 5G nativa. |
| **NVIDIA** | GPUs de alto rendemento e CPUs para centros de datos (Grace). | Aínda que é famosa polas súas tarxetas gráficas, hoxe é o fabricante máis valioso en **IA**. Fabrica superprocesadores que combinan CPU e GPU para adestrar modelos como ChatGPT e sistemas de condución autónoma. |
| **Samsung** | Procesadores Exynos para móbiles e fabricación para terceiros. | Ademais de deseñar os seus propios chips para móbiles, é un dos poucos no mundo con **fundicións propias** (fábricas) capaces de crear chips en procesos avanzados de 3nm e 4nm. |
| **TSMC** | Non deseña, pero **fabrica** para case todos os anteriores (Apple, AMD, NVIDIA). | Aínda que non vende procesadores coa súa marca, é a empresa máis crítica: sen as súas fábricas en Taiwán, o 90% dos procesadores avanzados do mundo non existirían. |
| **ARM Holdings** | Deseña a **arquitectura** e as licenzas, pero non fabrica chips físicos. | É a empresa que "debuxa os planos". Apple, Qualcomm ou Samsung páganlle por usar a súa arquitectura RISC, que é a base de case tódolos procesadores de móbiles e portátiles de baixo consumo actuais. |

**En resumo:**

* **Deseñadores "Fabless":** Empresas como **AMD, Apple ou NVIDIA** que deseñan os chips pero non teñen fábricas propias; mándanos fabricar a TSMC ou Samsung.
* **Fabricantes Integrados (IDM):** **Intel** é un dos poucos que aínda deseña e fabrica os seus propios chips nas súas propias instalacións (aínda que recentemente comezou a externalizar algunhas partes a TSMC).
* **Arquitectura:** O mercado divídese hoxe entre o mundo **x86 (Intel/AMD)**, onde prima a compatibilidade de software de escritorio, e o mundo **ARM (Apple/Qualcomm)**, onde prima a autonomía e a integración.

### 5.2 Fabricantes Actuais e Recomendacións segundo o fin para o que van destinados

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

### 1. A Xeración (O factor determinante)
A arquitectura mellora cada ano. Un procesador de gama media actual adoita ser máis potente que un de gama alta de hai 4 anos.
* **En Intel:** O primeiro ou os dous primeiros números tras o guión indican a xeración.
    * *Exemplo:* i7-**14**700K (Xeración 14). Un i5-**14**400 é superior a un i7-**11**700.
* **En AMD:** O primeiro número indica a serie/xeración (aínda que AMD cambiou a nomenclatura recentemente, a regra xeral mantense).
    * *Exemplo:* Ryzen 7 **7**800X (Serie 7000, arquitectura Zen 4). Un Ryzen 5 **7**600 adoita render mellor que un Ryzen 9 **3**900.

### 2. O Sufixo (Para que serve ese procesador?)
A letra ao final do modelo indica o escenario para o que foi deseñado:
* **U (Ultra Low Power):** Deseñados para portátiles finos. Prioriza a batería e consome moi pouco, pero ten menos potencia bruta.
* **H / HS / HX (High Performance):** Procesadores de alto rendemento para portátiles *gaming* ou estacións de traballo. Consomen moita máis batería e requiren mellor ventilación.
* **K (Intel) / X (AMD):** Versións de sobremesa optimizadas para acadar frecuencias máis altas. Os "K" de Intel están desbloqueados para facer *overclock*.
* **F (Intel):** Indica que o procesador **non ten gráficos integrados**. É obrigatorio mercar unha tarxeta gráfica dedicada (NVIDIA ou Radeon).
* **G (AMD):** Indica que o procesador ten gráficos integrados potentes (APU), ideais se non vas mercar unha tarxeta gráfica aparte.

### 3. A NPU e a IA (Pensando no futuro)
Se queres un equipo preparado para as novas ferramentas de IA local (Copilot+, edición de vídeo intelixente, etc.):
* **En Intel:** Busca a nova denominación **Core Ultra** (Series 1 ou 2).
* **En AMD:** Busca modelos coa etiqueta **Ryzen AI** (como as series 7040, 8040 ou os novos Ryzen AI 300).
* **Dato técnico:** Verifica que a NPU teña máis de **40 TOPs** se queres a certificación completa de Microsoft.

### 4. TDP, Refrixeración e "Thermal Throttling"
O **TDP (Thermal Design Power)** indica cantos vatios consome e cantos vatios de calor debe disipar o ventilador.
* Se compras un portátil moi fino cun procesador "HX" ou un i9, é moi probable que sufra **Thermal Throttling**: o procesador baixa a súa velocidade bruscamente porque se quenta demasiado (supera os 95-100°C), facendo que o rendemento real sexa inferior ao esperado.
* **Consello:** Para traballar con máquinas virtuais ou deseño, busca un equilibrio; un procesador de serie "H" nun chasis con boa ventilación sempre renderá mellor que un "i9" afogado nun chasis ultra-fino.

---

### 7. Tipos de Núcleos en AMD e en Intel

### 7.1. Intel: A arquitectura híbrida real (P-Cores + E-Cores)
Desde a 12ª xeración (Alder Lake), Intel introduciu o concepto de **núcleos heteroxéneos**. No mesmo chip hai dous tipos de núcleos:
* **P-Cores (Performance):** Núcleos grandes e potentes, con Hyper-Threading (2 fíos por núcleo). Encárganse das tarefas pesadas (xogos, edición).
* **E-Cores (Efficiency):** Núcleos pequenos, sen Hyper-Threading (1 fío por núcleo). Encárganse de tarefas de fondo e aforro de enerxía.

**Como saber cantos teñen?**
* **Na web oficial (Intel ARK):** Debes buscar o modelo e verás que desglosa "Number of P-cores" e "Number of E-cores".
* **No nome:** Xeralmente, os modelos de gama alta (i7, i9) teñen moitos E-Cores. Un i9-14900K, por exemplo, ten 8P + 16E.
* **No Administrador de Tarefas:** Se ves que o número de fíos (Lóxicos) non é exactamente o dobre do número de núcleos físicos, é porque hai E-Cores (que só teñen 1 fío).

---

### 7.2. AMD: Núcleos "Zen" e "Zen c"
AMD non usa P-Cores e E-Cores ao estilo de Intel. Ata hai pouco, todos os núcleos de AMD eran iguais e de alto rendemento. Recentemente, introduciu os núcleos **"c" (como o Zen 4c)**.

* **A diferenza:** A diferenza de Intel, os núcleos "c" de AMD teñen o **mesmo conxunto de instrucións e a mesma potencia por ciclo** que os núcleos estándar. Simplemente están deseñados de forma máis compacta físicamente para meter máis núcleos en menos espazo e consumir algo menos.
* **Onde están?** De momento vense principalmente nos novos procesadores de portátiles (**Ryzen 8000/9000** ou **Ryzen AI 300**).

**Como saber cantos teñen?**
* AMD adoita ser menos clara no marketing inicial, pero nas especificacións técnicas detalladas da súa web indican se hai núcleos de tipo "Zen 5" e "Zen 5c". Por exemplo, o Ryzen AI 9 HX 370 ten 4 núcleos Zen 5 e 8 núcleos Zen 5c.

---


### Resumo:
* **Intel:** Usa núcleos **fisicamente distintos** (maiores/menores).
* **AMD:** Usa núcleos **idénticos en capacidades** pero uns máis compactos que outros (Zen vs Zen c).
* **Cómputo de fíos:** Lembra sempre que os E-Cores (Intel) e os Zen-c (nalgúns casos de aforro extremo) poden non ter multithreading, o que cambia o cálculo total de fíos do sistema.

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

---

## 8.3: Diferenzas principais entre sobremesa e portátil

Podemos destacar de forma breve estas diferenzas:

1.  **Finalidade:** O de sobremesa busca o **rendemento máximo** sen importar o consumo eléctrico; o de portátil busca o **equilibrio** entre potencia e autonomía.
2.  **Forma de montaxe:** Os de sobremesa son **intercambiables** (podes quitar un i3 e poñer un i7 se o socket coincida); os de portátil son **fixos** (veñen integrados de fábrica e non se poden actualizar).
3.  **Nomenclatura (Sufixos):** É a forma máis rápida de distinguilos. Se ves as letras **U, P ou H**, é de portátil. Se ves **K, F** ou ningunha letra, é de sobremesa.
4.  **Arquitectura de núcleos:** Os portátiles modernos dependen moito máis dos **E-Cores** (núcleos de eficiencia) para que o ordenador non se apague ás poucas horas de uso, mentres que os de sobremesa manteñen un número elevado de **P-Cores** (rendemento) para tarefas pesadas constantes.

## 9. Protocolos de Seguridade Técnica

* **Protección ESD:** Uso de pulseira antiestática ou descarga previa en chasis.
* **Pasta Térmica:** Aplicar a cantidade xusta (tamaño dun chícharo). O exceso reduce a disipación.
* **Manipulación:** Nunca tocar os contactos de ouro nin aplicar forza excesiva sobre o socket.

