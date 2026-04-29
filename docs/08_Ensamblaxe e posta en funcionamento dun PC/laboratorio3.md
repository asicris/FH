

### 1) Proba de RAM con Memtest86+ desde o GRUB
Se tes unha distribución Linux instalada (como Ubuntu ou Debian), o menú de GRUB adoita incluír unha entrada para esta ferramenta.

* **Acceso**: Reinicia o equipo e mantén premida a tecla **Shift** (ou **Esc** nalgunhas BIOS) para que apareza o menú de GRUB.
* **Execución**: Selecciona a opción denominada `Memory test (memtest86+)`. O sistema cargará un binario que toma o control total da CPU e a memoria.
* **Procedemento**: Memtest86+ executará unha serie de tests (Test 0 a Test 10). O obxecto é detectar fallos de direccionamento, erros en bits específicos ou problemas térmicos nos módulos DIMM.
* **Cando parar**: Unha proba técnica estándar require polo menos unha "pass" (pasada completa), pero en contornas de enxeñaría recoméndase deixar o test durante varias horas (ou unha noite enteira) para detectar erros intermitentes. Se aparecen liñas vermellas, a memoria está defectuosa.



---

### 2) Proba S.M.A.R.T.: HDD vs. SSD
A análise SMART (*Self-Monitoring, Analysis and Reporting Technology*) varía lixeiramente na súa interpretación dependendo da tecnoloxía de almacenamento.

#### En HDD (Disco Mecánico)
O obxectivo é detectar fallos físicos e mecánicos.
* **Comando**: `smartctl -a /dev/sda`
* **Parámetros críticos**: Fixate en `Reallocated_Sector_Count` (sectores movidos por danos físicos) e `Spin_Retry_Count` (problemas co motor). Un aumento nestes valores indica que o disco debe ser substituído inmediatamente.

#### En SSD (Unidade de Estado Sólido)
**É igual a proba?** O comando é o mesmo, pero a interpretación dos datos cambia radicalmente.
* **Diferenza técnica**: Nun SSD non hai partes mecánicas, polo que atributos como o "Spin Up" non existen ou non teñen sentido.
* **Parámetros críticos**:
    * **Percentage Used / Media Wearout Indicator**: Indica a vida útil restante baseada nos ciclos de escritura (TBW).
    * **Available Spare**: Os SSDs teñen celas de reserva. Se este valor baixa do limiar do fabricante, o disco está ao final da súa vida.
* **Conclusión**: No SSD buscamos "desgaste químico" das celas NAND, mentres que no HDD buscamos "desgaste mecánico".



---

### 3) Comprobación de temperatura
Para monitorizar o estado térmico do hardware desde a liña de comandos de Linux, utilizamos o paquete `lm-sensors`.

* **Configuración previa**:
    ```bash
    sensors-detect
    ```
    *(Debes responder "YES" a todas as preguntas para que o sistema identifique os chips de monitorización na placa base).*
* **Execución**:
    ```bash
    sensors
    ```
* **Interpretación técnica**:
    * **CPU (Package/Core)**: En carga de traballo, temperaturas superiores a 85-90°C adoitan provocar *thermal throttling* (redución da frecuencia do reloxo para protexer o silicio).
    * **HDD/SSD**: Podes ver a temperatura específica do disco con `smartctl -l error /dev/sda | grep Temperature`. Un disco mecánico non debería superar os 45-50°C de forma sostida.



---

**Resumo da práctica para un técnico:**
1.  **RAM**: Memtest86+ desde GRUB (mínimo 1 pasada).
2.  **Disco**: `smartctl`. En HDD vixiar sectores; en SSD vixiar o desgaste (% used).
3.  **Térmico**: `sensors` para validar que o sistema de refrixeración (pasta térmica, ventiladores) funciona correctamente baixo estrés.