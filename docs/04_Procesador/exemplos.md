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

---

### Resumo de conceptos

1.  **Diferenza de Potencia:** A igualdade de gama (i7 vs i7), o modelo de sobremesa sempre será entre un **15% e un 30% máis potente** en tarefas longas (como renderizar un vídeo de 1 hora) porque non ten as restricións térmicas do portátil.
2.  **Eficiencia:** O procesador de portátil está deseñado para ser eficiente baixo carga; o de sobremesa está deseñado para ser "bruto" mentres haxa enerxía dispoñible.
3.  **Mobilidade vs. Escalabilidade:** O procesador de portátil prioriza a integración nun chasis fino (BGA), mentres que o de sobremesa prioriza que o usuario poida mantelo ou melloralo (LGA).