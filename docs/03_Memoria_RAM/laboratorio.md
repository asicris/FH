# Memoria RAM: Laboratorio Práctico

## 1. Práctica 1: Identificación e Análise de Memoria Instalada

### 1.1 Obxetivos
- ✅ Identificar tipo, capacidade e velocidade de memoria instalada
- ✅ Usar ferramentas de diagnóstico para comprobar especificacións
- ✅ Validar configuración de Dual Channel
- ✅ Documentar toda información en informe

### 1.2 Materiais Necesarios
- ✅ 1 × Computador con memoria RAM instalada
- ✅ Pulseira antiestática (para acceso interno, se é necesario)
- ✅ Desparafusador (se se abre a carcasa)

### 1.3 Procedementos

#### Paso 1: Identificación Visual (sen abrir carcasa)

**Tarefa:** Descobre os datos de memoria sen abrir a carcasa

```bash
# En Windows: Abre PowerShell como administrador e executa:
Get-WmiObject -Class Win32_PhysicalMemory | Format-Table Manufacturer, Capacity, Speed, ConfiguredClockSpeed

# En Linux:
sudo dmidecode --type 17
# ou
lsmem
```

**Responder:**
1. ¿Cantas DIMM están instaladas?
2. ¿Cal é a marca (Kingston, Corsair, G.Skill, etc.)?
3. ¿Cal é a capacidade total?
4. ¿Cal é a velocidade indicada en MHz?
5. ¿Está configurada en Dual Channel?

**Captura de datos:**
```
Número de DIMs: ___
Marca: ___
Capacidade Total: ___
Velocidade Detectada: ___
Dual Channel: Sí/Non
```

---

#### Paso 2: Inspeción Física (se se abre a carcasa)

⚠️ **PRECAUCIÓN DE SEGURIDADE:** Antes de abrir:
- Desconecta fonte de alimentación (360° completo)
- Espera 5 minutos
- Ponte pulseira antiestática

**Tarefa:** Verifica físicamente a memoria instalada

```
Procedementos:
1. Localiza slots de memoria (usualmente próimo ao procesador)
2. Observa:
   ├─ Número de DIMM inseridas
   ├─ Distancia entre slots (valida se están en slots alternos = Dual Channel)
   ├─ Presencia de clips laterais pechados (indica correcta instalación)
   └─ Disipadores de calor (indica memoria gaming ou overclocking)

3. Para cada DIMM, lee a etiqueta:
   ├─ Marca (Kingston, Corsair, G.Skill, etc.)
   ├─ Modelo exacto (p.e., FURY Beast DDR5-6000)
   ├─ Código de produción
   └─ Voltaxe recomendada (1.2V, 1.25V, etc.)

4. Documenta todo con fotos (se é posible)
```

---

### 1.4 Informe a Completar

**Nome do Alumno:** ___________________

**Data:** ___/__/____

**Computador Analizado:** ________________________

#### Resumo Técnico:
```
Tipo de Memoria:        DDR4 / DDR5
Capacidade Total:       __ GB
Número de DIMM:         __
Megahertz Base (JEDEC): ____ MHz
Megahertz Actual:       ____ MHz
Latencia CAS:           __
Configuración:          Single / Dual Channel
XMP/EXPO:               Enabled / Disabled
Marcas Identificadas:   _____________________
```

#### Análise Comparativo (se había diferentes modelos):
- ¿Están tódalas DIMM do mesmo fabricante?
- ¿Son do mesmo modelo exacto?
- ¿Funcionan en Dual Channel correctamente?

#### Conclusiones:
1. ¿A memoria detectada é a que che dixo o cliente?
2. ¿Está optimizada a configuración (Dual Channel, XMP)?
3. ¿Require actualización ou reemplazo?

---

---

## 2. Práctica 2: Diagnóstico de Subsistema de Memoria MemTest

**Obxectivos:**

* Crear medios de arrastre de diagnóstico mediante ferramentas de baixo nivel (`dd`) e multi-boot (`Ventoy`).
* Identificar a topoloxía da memoria instalada.
* Interpretar os algoritmos de estrés de *MemTest86+*.

## 1. Preparación do Medio de Arranque (Bootable USB)

Tes dúas opcións para preparar a túa ferramenta:

### Opción A: Método Ventoy (Recomendado para técnicos)

1. Descarga a ISO de **MemTest86+** (v7.0 ou superior) dende [memtest.org](https://www.memtest.org/).
2. Insire o teu pendrive con **Ventoy** xa instalado.
3. Copia o ficheiro `.iso` directamente á raíz do pendrive. Ao arrincar o PC, selecciona a ISO no menú de Ventoy.

### Opción B: Método `dd` (Unix/Linux Nativo)

Se estás nunha terminal de Linux, usa o comando de copia de bloques. **Coidado:** identifica correctamente a túa unidade con `lsblk` para non borrar o disco duro.

```bash
# Supoñendo que /dev/sdX é o teu pendrive
sudo dd if=mt86plus_64.iso of=/dev/sdX bs=4M status=progress oflag=sync
```

---

## 2. Procedemento de Testeo

### Fase I: Identificación do Hardware

Arranca o equipo dende o USB e, antes de que o test leve moito tempo, observa a pantalla principal e completa:

* **Arquitectura do Procesador:** __________________________
* **Capacidade Total de RAM:** ___________________________
* **Velocidade (MT/s) e Latencia CAS:** ___________________
* **Configuración de Canles (Single/Dual/Quad):** __________
* **Rango de enderezos de memoria (Memory Range):** _________
* **Tamaño caché L1 e velocidade:** _________
* **Tamaño caché L2 e velocidade:** ________
* **Tamaño caché L3 e velocidade:** _________

### Fase II: Execución de Algoritmos

O MemTest86+ executa unha serie de probas. Identifica e explica brevemente que busca detectar cada unha destas:

1. **Test 5 [Moving inversions, 8-bit pattern]:**
2. **Test 7 [Block move, 64 moves]:**
3. **Test 13 [Hammer Test]:**

### Fase III: Interpretación de Erros (Simulación Técnica)

Imaxina que tras 2 horas de test, o software amosa a seguinte liña en vermello:
`Failing Address: 0001A4C28F34 - 420.5 MB | Good: ffffffff | Bad: ffefffff`

**Responde:**

1. ¿En que módulo físico (slot) cres que reside o erro se o sistema ten 2 módulos de 8GB en Dual Channel?
2. ¿Cantos bits fallaron exactamente nesa lectura? (Convirte o valor *Good* e *Bad* a binario se é necesario).
3. ¿Que diferenza existe entre un erro detectado nunha pasada (Pass) e un erro que só aparece tras varias horas de test?

---
### 3. Informe a Completar e entregar na Aula virtual

**Nome do Alumno:** ___________________

**Data:** ___/__/____

**Hardware Testeado:** ________________________

#### Resultados de Testes:


**MemTest86+ Bootable:**
- Duración do test: _____ horas
- Erroress detectados: _____ (0 = OK)
- Tipo de memoria: _____ 
- Velocidade detectada: _____ MHz

* **Arquitectura do Procesador:** __________________________
* **Capacidade Total de RAM:** ___________________________
* **Velocidade (MT/s) e Latencia CAS:** ___________________
* **Configuración de Canles (Single/Dual/Quad):** __________
* **Rango de enderezos de memoria (Memory Range):** _________
* **Tamaño caché L1 e velocidade:** _________
* **Tamaño caché L2 e velocidade:** ________
* **Tamaño caché L3 e velocidade:** _________

#### Conclusións:

1. A memoria pasou tódolos tests?
2. Hai problemas de estabilidade?
3. Tes algunha recomendacións para optimización (XMP, timings)?
4. Require a memoria mantenimento ou reemplazo?

---
