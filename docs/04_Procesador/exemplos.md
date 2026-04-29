# Exemplos

## 1. Comparativa do mesmo modelo de procesador en sobremesa e portátil

Para ilustrar esta diferenza de forma práctica, imos comparar dous procesadores da mesma familia, mesma xeración e mesma gama, pero destinados a plataformas distintas: o **Intel Core i7-14700K** (Sobremesa) fronte ao **Intel Core i7-14700HX** (Portátil de alto rendemento).

Aínda que comparten o nome "i7-14700", as súas especificacións revelan estratexias de enxeñaría moi diferentes.

### Comparativa Técnica: i7-14700K vs. i7-14700HX

| Característica | **Intel Core i7-14700K (Desktop)** | **Intel Core i7-14700HX (Laptop)** |
| :--- | :--- | :--- |
| **Arquitectura** | Raptor Lake Refresh | Raptor Lake Refresh |
| **Núcleos Totais** | 20 (8P + 12E) | 20 (8P + 12E) |
| **Fíos (Threads)** | 28 | 28 |
| **Frecuencia Turbo Máx.** | **5.60 GHz** | **5.50 GHz** |
| **Frecuencia Base (P-Cores)** | **3.40 GHz** | **2.10 GHz** |
| **Caché L3** | 33 MB | 33 MB |
| **Consumo Base (TDP)** | **125 W** | **55 W** |
| **Consumo Máx. (Turbo)** | **253 W** | **157 W** |
| **Tipo de Socket** | LGA1700 (Intercambiable) | BGA1964 (Soldado) |

### Análise das Diferenzas Reais

#### 1. A fenda da Frecuencia Base
Fixate na **Frecuencia Base**. O modelo de sobremesa parte de 3.40 GHz, mentres que o de portátil baixa ata os 2.10 GHz. Isto faise para que, en tarefas lixeiras, o portátil consuma o mínimo posible e non quente o equipo, mentres que o de sobremesa pode permitirse manter unha velocidade alta constantemente porque está conectado á rede eléctrica e ten grandes ventiladores.

#### 2. O teito enerxético (TDP)
Esta é a diferenza máis crítica para un técnico de sistemas:
* O **i7-14700K** pode chegar a tragar **253 vatios** de enerxía. Para disipar esa calor necesítase un disipador de torre xigante ou refrixeración líquida.
* O **i7-14700HX**, sendo o máis potente para portátiles, ten un tope de **157 vatios**. Aínda que parece moito, son case 100W menos que o seu irmán de sobremesa. Isto limita canto tempo pode manter as frecuencias máximas antes de ter que baixar a velocidade por calor (**Thermal Throttling**).

#### 3. Capacidade de expansión
Se dentro de tres anos queres mellorar o teu PC de sobremesa, podes quitar o i7 e poñer un i9. No caso do portátil, o **i7-14700HX está soldado (BGA)** á placa base. Se queres un procesador mellor, terías que mercar un portátil novo.

#### Resumo de conceptos

1. **Diferenza de Potencia:** A igualdade de gama (i7 vs i7), o modelo de sobremesa sempre será entre un **15% e un 30% máis potente** en tarefas longas (como renderizar un vídeo de 1 hora) porque non ten as restricións térmicas do portátil.
2. **Eficiencia:** O procesador de portátil está deseñado para ser eficiente baixo carga; o de sobremesa está deseñado para ser "bruto" mentres haxa enerxía dispoñible.
3. **Mobilidade vs. Escalabilidade:** O procesador de portátil prioriza a integración nun chasis fino (BGA), mentres que o de sobremesa prioriza que o usuario poida mantelo ou melloralo (LGA).

---

## Exemplos de procesadores e características

### Suposto Práctico 1: Estación de Traballo para Virtualización e Servizos

**Escenario:** Unha empresa de desenvolvemento de software precisa un equipo para un técnico de sistemas que vai levantar múltiples máquinas virtuais (VMware/VirtualBox), bases de datos en local e contedores Docker simultaneamente.

### Identificación do Procesador: **AMD Ryzen 9 9950X**

* **Fabricante:** AMD.
* **Arquitectura:** x86 baseada en **Chiplets** (Zen 5). Proceso de fabricación de **4nm** (TSMC).
* **Características Técnicas:**
    * **Núcleos/Fíos:** 16 núcleos físicos e 32 fíos de execución (SMT). Todos os núcleos son de alto rendemento.
    * **Caché:** 80 MB de caché total (L2+L3). A gran cantidade de caché L3 reduce a latencia en procesos de compilación.
    * **Socket:** **AM5 (LGA)**. Permite futuras actualizacións sen cambiar a placa base ata 2027+.
    * **IA:** Inclúe aceleración **Ryzen AI** (NPU XDNA) para tarefas de asistencia intelixente.
* **Fin dirixido:** **Gama Entusiasta / Workstation**. É ideal para multitarefa pesada e virtualización, onde o número de fíos (threads) permite asignar recursos dedicados a cada máquina virtual sen colapsar o sistema anfitrión.

### Suposto Práctico 2: Ultraportátil Corporativo con IA Integrada

**Escenario:** Un directivo require un portátil que sexa extremadamente lixeiro, con autonomía para un voo transatlántico (12-15 horas) e que permita usar ferramentas de IA (Copilot+, transcrición en tempo real e tradución) sen depender de conexión á nube.

### Identificación do Procesador: **Intel Core Ultra 7 155H**

* **Fabricante:** Intel.
* **Arquitectura:** **Híbrida** (Raptor Lake / Meteor Lake). Proceso de fabricación **Intel 4**.
* **Características Técnicas:**
    * **Núcleos/Fíos:** 16 núcleos (6 P-cores para potencia, 8 E-cores para eficiencia e 2 LP E-cores de baixo consumo para tarefas ultra-lixeiras). Total de 22 fíos.
    * **NPU Dedicada:** **Intel AI Boost**. Unidade específica para tarefas de Machine Learning que aforra enerxía ao non usar a GPU para IA.
    * **Gráficos:** Intel Arc Graphics integrada (fai innecesaria unha tarxeta gráfica dedicada, reducindo peso e calor).
    * **Socket:** **BGA** (Soldado á placa base para permitir deseños de portátiles ultra-finos).
* **Fin dirixido:** **Gama Alta Portátil (Ultrabooks)**. Deseñado para usuarios que priorizan a mobilidade e as novas funcionalidades de IA sen sacrificar potencia cando se precisa executar aplicacións de análise de datos ou multimedia.

### Resumo Comparativo 

| Elemento | Caso 1 (AMD) | Caso 2 (Intel) |
| :--- | :--- | :--- |
| **Punto forte** | Rendemento bruto multitarefa (Virtualización). | Eficiencia enerxética e IA (Mobilidade). |
| **Deseño físico** | Varios chips pequenos (Chiplets). | Un único chip con núcleos mixtos (Híbrido). |
| **TDP (Calor)** | Alto (~170W). Require refrixeración potente. | Baixo (28W-115W). Refrixeración compacta. |

