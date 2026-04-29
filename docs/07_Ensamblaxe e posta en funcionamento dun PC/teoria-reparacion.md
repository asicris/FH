# 🛠️ GUÍA DE REPARACIÓN DE PCs (ASIR – Fundamentos de Hardware)

Ante calquera erro no PC ou portátil, **moi importante**

1. **Ir do simple ao complexo**
2. **Cambiar só unha cousa cada vez**
3. **Documentar probas**
4. **Aislar o compoñente defectuoso**

---

## 🎯 ESQUEMA RÁPIDO 

* Non acende → alimentación / fonte / placa
* Acende sen imaxe → RAM / GPU / BIOS
* Apágase → temperatura / fonte
* Non carga SO → disco / boot
* Vai lento → RAM / disco / temperatura

## 🔌 1. O EQUIPO NON ACENDE (non fai nada)

👉 *Síntoma:* Non hai luces, nin ventiladores, nin pitidos.

### ✔️ Comprobacións básicas

1. **Alimentación externa**

   * Cable de corrente ben conectado
   * Regleta/SAI funcionando
   * Probar outro enchufe

2. **Fonte de alimentación (PSU)**

   * Interruptor traseiro en ON
   * Comprobar con tester ou “ponteo” (clip entre verde e negro en ATX)
   * Ver se xira o ventilador

3. **Botón de acendido**

   * Revisar conexión do **POWER SW** na placa base
   * Probar arrancar ponteando os pinos cun desaparafusador

4. **Placa base**

   * Hai LEDs acendidos?
   * Revisar curtocircuítos (separadores mal colocados)

---

## ⚡ 2. ACENDE PERO NON ARRANCA (pantalla negra)

👉 *Síntoma:* Os ventiladores xiran pero non hai imaxe

### ✔️ Pasos

1. **Monitor**

   * Acendido e cable correcto (HDMI/DP/VGA)
   * Probar outro monitor/cable

2. **Memoria RAM**

   * Sacar e volver colocar
   * Probar módulo por módulo
   * Cambiar de slot

3. **Tarxeta gráfica**

   * Revisar alimentación PCIe
   * Probar sen gráfica (se hai integrada)

4. **Pitidos (BIOS)**

   * Escoitar códigos de erro
   * Consultar fabricante (AMI, Award, etc.)

---

## 🔄 3. ACENDE E APÁGASE SO

👉 *Síntoma:* Arrinca uns segundos e apágase

### ✔️ Posibles causas

1. **Sobrequentamento**

   * Disipador mal colocado
   * Pasta térmica seca ou mal aplicada

2. **Fonte defectuosa**

   * Non entrega potencia estable

3. **Curtocircuíto**

   * Parafuso solto
   * Placa tocando a caixa

---

## 🖥️ 4. ARRANCA PERO NON CARGA O SISTEMA

👉 *Síntoma:* BIOS OK pero non entra a Windows/Linux

### ✔️ Revisar

1. **Disco duro / SSD**

   * Detectado na BIOS
   * Estado SMART

2. **Orde de arranque**

   * Boot priority correcta

3. **Sistema operativo**

   * Reparar con USB (Windows ou Linux live)

---

## 🐢 5. EQUIPO MOI LENTO

👉 *Síntoma:* Funciona pero con baixo rendemento

### ✔️ Diagnóstico

1. **RAM insuficiente**
2. **Disco duro lento (HDD vs SSD)**
3. **Procesos en segundo plano**
4. **Temperaturas altas (throttling)**

---

## ❄️ 6. PROBLEMAS DE TEMPERATURA

👉 *Síntoma:* Ruído, apagados, baixo rendemento

### ✔️ Solución

* Limpar po (ventiladores, disipador)
* Cambiar pasta térmica
* Mellorar fluxo de aire

---

## 🔊 7. PITIDOS E ERROS DE BIOS

👉 *Importante para diagnóstico rápido*

Exemplo:

* 1 pitido curto → OK
* Pitidos longos repetidos → RAM
* Pitidos curtos continuos → fonte ou placa

---

## 🧪 8. FERRAMENTAS BÁSICAS DE DIAGNÓSTICO

* Multímetro (fonte) tester de fontes.
* USB booteable (Linux / Windows)
* Software:

  * Memtest86 (RAM)
  * CrystalDiskInfo (Windows), GSmartControl(Linux e SystemRescue), smartmoontools (discos)
  * HWMonitor (windows), lm-sensors(linux) (temperaturas)
ISOS: SystemRescue e Ultimate Boot CD (test de hw e monitorización)

Nas **BIOS MODERNAS**:

- SmartTools (discos) incorporado na BIOS
- Hw Monitor
- PC Health Status
---
