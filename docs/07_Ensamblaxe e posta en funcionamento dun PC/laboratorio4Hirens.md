Se decidiches utilizar **Hiren's BootCD PE** (a versión moderna baseada en Windows 10 PE), o procedemento técnico cambia dunha interface de liña de comandos a un contorno gráfico (GUI). Isto facilita a monitorización simultánea de varios parámetros.

Aquí tes a práctica estruturada para realizar estas probas no Hiren's:

---

### 1) Comprobación de memoria RAM
No Hiren's BootCD PE, tes dúas vías principais dependendo de se queres facer a proba dentro ou fóra do contorno de Windows:

* **Windows Memory Diagnostic**: Podes lanzalo desde o menú de ferramentas de Windows. Require reiniciar o equipo e executa un test similar ao de GRUB.
* **MemTest86+ (vía WinUpdate)**: Se prefires ferramentas de terceiros, dentro da carpeta `Utilities > Hard Disk > Diagnostics`, moitas veces inclúense versións de MemTest que se poden configurar para o seguinte reinicio.
* **Procedemento técnico**: Unha vez iniciada a proba, o sistema buscará fallos de integridade nos bancos de memoria. Ao ser un contorno PE, asegúrate de que o test teña acceso a toda a memoria física non reservada polo sistema operativo.

---

### 2) Comprobación do disco (HDD e SSD)
Hiren's é especialmente potente nesta sección porque inclúe as ferramentas estándar da industria con interface visual:

* **CrystalDiskInfo**: É a primeira ferramenta que debes abrir. Proporciónache unha lectura inmediata dos atributos SMART. 
    * **Interpretación**: Verás un indicador de "Saúde" (Azul = OK, Amarelo = Alerta, Vermello = Crítico).
    * **Diferenza HDD/SSD**: En HDDs, monitoriza sectores reasignados. En SSDs, fixate no "Vida restante" (Life Remaining) baseado en escrituras.
* **GSmartControl**: Moi útil se prefires unha vista máis técnica e próxima ao `smartctl` de Linux. Permite lanzar o **Short Self-test** (2 min) ou o **Extended Self-test** (proba de superficie, pode durar horas).
* **HDTune**: Úsase para ver a velocidade de transferencia e detectar "drops" (caídas) de rendemento que indican fallos físicos de lectura.



---

### 3) Comprobación de temperaturas
Para monitorizar os sensores en tempo real dentro do Hiren's, tes ferramentas dedicadas que len os chips I/O da placa base:

* **HWInfo / HWMonitor**: Son as ferramentas de referencia. 
    1.  Abre **HWMonitor** (situado en `Utilities > Others`).
    2.  Busca a sección da túa CPU. Verás as temperaturas *Core* e *Package*.
    3.  Busca a sección do teu disco NVMe/SATA.
* **Vantaxe técnica**: A diferenza do comando `sensors` de Linux, aquí verás tres columnas: **Value** (actual), **Min** (mínima detectada) e **Max** (máxima acadada). 
* **Uso práctico**: Podes deixar HWMonitor aberto mentres fas unha proba de disco ou RAM. Se a columna **Max** se achega aos 90°C-100°C na CPU, o sistema ten un problema de disipación que pode causar inestabilidade durante as probas.



---

### Resumo comparativo: SystemRescue vs. Hiren's BootCD

| Proba | SystemRescue (Linux) | Hiren's BootCD (WinPE) |
| :--- | :--- | :--- |
| **RAM** | `memtester` ou Memtest86+ | Windows Memory Diagnostic / MemTest86+ |
| **Disco** | `smartctl` (Liña de comandos) | CrystalDiskInfo / GSmartControl (GUI) |
| **Temperatura** | `sensors` (Texto plano) | HWMonitor (Gráfico con históricos Min/Max) |

Cal destas dúas ferramentas che resulta máis cómoda para traballar no teu día a día técnico?