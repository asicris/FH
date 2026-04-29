# Ferramentas de diagnóstico de discos (Windows) - CrystalDiskMark

## 1. Obxectivo e Requisitos

* **Obxectivo:** Medir e comparar o rendemento dun **SSD SATA** e un **NVMe** en contornas Windows.
*  **Hardware:** 1 disco SSD SATA e 1 disco NVMe.
* **Software:** Descargar e instalar [CrystalDiskMark](https://crystalmark.info/en/software/crystaldiskmark/).

## 2. Preparación e Identificación dos Discos

Antes de comezar, asegúrate de:

*  Pechar programas innecesarios para non falsear os resultados[cite: 137].
*  Non copiar arquivos durante o test[cite: 137].
*  Identificar as letras das unidades (C:, D:, etc.) no Explorador de Arquivos.


## 3. Configuración do Test en CrystalDiskMark

 Unha vez aberto o programa, configura os parámetros:

1.**Número de pasadas (Runs):** Selecciona **5** (valor por defecto para estabilidade).
2.**Tamaño do test (Size):** Selecciona **1 GiB**.
3.**Unidade (Drive):** Escolle a letra correspondente ao disco que queres probar (SSD ou NVMe).

### 3.1 Entrega e reflexións sobre a práctica

**Recolle os resultados na seguinte táboa, e logo tenta facer un informe coa interpretación dos mesmos, contesta:**

- Que disco utilizarías para instalar o SO?
- Cal utilizarías para almacenar datos secundarios?

**para facer un informe segundo as indicacións que che indicamos debaixo**


### 3.2. Táboa Comparativa para cubrir

 Completa os datos tras pulsar o botón **"All"** en cada disco[cite: 206]:

| Tipo de Disco | Seq Read (MB/s) | Seq Write (MB/s) | 4K Read (MB/s) | 4K Write (MB/s) |
| :--- | :--- | :--- | :--- | :--- |
|  **SSD SATA** | | | | |
|  **NVMe** |  | | | |

---

## Interpretación dos Resultados

 CrystalDiskMark xera unha matriz de datos que debes interpretar do seguinte xeito:

### A. Lectura e Escritura Secuencial (SEQ1M Q8T1 / Q1T1)

*  **Que mide:** A velocidade ao mover arquivos moi grandes (películas, ISOs, instalacións de xogos).
* **Valores agardados:**
    *  **SSD SATA:** Arredor de **500 - 560 MB/s**.
    *  **NVMe:** Entre **1500 e 7000+ MB/s** (dependendo de se é PCIe 3.0, 4.0 ou 5.0).

### B. Acceso Aleatorio (RND4K Q32T1 / Q1T1)

* **Que mide:** A capacidade do disco para ler/escribir pequenos bloques de datos de 4 KB espallados polo disco.  É o parámetro máis importante para o **uso real do Sistema Operativo** e programas.
*  **Interpretación:** Un NVMe sempre debería ser superior aquí, o que se traduce nun sistema que "arranca" antes e programas que abren de forma máis instantánea.

---


## Diagnóstico Complementario (Equivalente a SMART)

 Mentres que en Linux usas a ferramenta **Discos** para ver o estado de saúde[cite: 21, 32], en Windows o complemento ideal para CrystalDiskMark é **CrystalDiskInfo**.

*  **Estado de saúde (Health):** Se aparece "Bueno" en azul, o disco está .
* **Atributos Críticos:** Fixate especialmente en:
    *  **Temperatura:** Valores por riba de $60\text{-}70^{\circ}\text{C}$ poden indicar falta de disipación no NVMe.
    *  **Horas de encendido:** Indica o tempo de uso acumulado[cite: 46].
    *  **Tasa de error CRC:** Se este valor é alto, pode haber un problema físico no cable SATA ou no conector.

 **Conclusión:** Aínda que o NVMe sexa moito máis rápido en probas secuenciais, o SSD SATA segue sendo unha opción válida para almacenamento secundario ou equipos de oficina onde a velocidade punta non é crítica.