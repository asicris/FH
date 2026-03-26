# Laboratorio: Medición e Diagnóstico de Fontes de Alimentación

**Obxectivo:** Aprender a medir e verificar as voltaxes dunha fonte de alimentación (PSU) para garantir que funciona dentro das especificacións ATX, usando técnicas seguras e ferramentas axecuadas.

---

## 1. Ferramentas Necesarias

### Material de Medición

| Ferramenta | Descrición | Uso |
|---|---|---|
| **Multímetro Dixital** | Dispositivo para medir tensión, corrente e resistencia | Medir voltaxes en pins individuais do conector ATX |
| **Power Supply Tester** | Dispositivo con pantalla LCD que mostra voltaxes | Comprobar rápidamente os 4 raís principais (3.3V, 5V, 12V, -12V) |
| **Pinza de Crocodilo / Cables de Prueba** | Accesorios para conectar o multímetro | Acceder aos pins sen soltar o conector |
| **Conector ATX Mocho (Dummy Load)** | Conector cos pins saíntes | Permitir que a fonte inicie sen estar enchufada ao PC |

### Material de Seguridade

| Item | Descrición | Por que é necesario |
|---|---|---|
| **Guantes Antiestática** | Guantes de tela condutor | Evitar descargas electrostáticas que dañen componentes |
| **Pulseira Antiestática** | Banda que se conecta a terra | Manter a carga electrónica corporal a 0V |
| **Tapete Antiestático** | Superficie condutora | Lugar seguro para deixar compoñentes |
| **Óculos de Seguridade** | Protección ocular | Evitar proxeccións de partículas ou chispas |

---

## 2. Protocolo de Seguridade Estrito

### ⚠️ ADVERTENCIA CRÍTICA

**A electricidade pode ser MORTAL.** Segue atentamente todos os pasos de seguridade.

### Pre-Medición: Preparación

1. **Desconecta a fonte da rede eléctrica (220V).**
   - Separa o cable de corrente da toma de parede.
   - Asegúrate de que a fonte está completamente apagada (botón OFF, se o ten).

2. **Espera 5 minutos.**
   - As fontes modernas teñen capacitores que almacenan enerxía.
   - Isto permite que despois da desconexión aínda haxa carga residual.

3. **Ponte a pulseira antiestática.**
   - Colócate a pulseira no pulso.
   - Conecta o cable á toma de terra ou ao tapete antiestático.

4. **Ponte os guantes antiestática.**

5. **Coloca a fonte nun lugar ben iluminado e estable.**
   - Non a poñas en vertical, colócaa horizontal para acceder mellor aos pins.

### Durante a Medición

6. **NON TOQUES NADA máis que o necesario.**
   - Non toque os circuítos internos.
   - Non introduzas metálicos dentro da fonte.

7. **Non apliques enerxía eléctrica directa nunca.**
   - Non conectes a fonte á rede até que estea completamente montada de novo.

8. **Mide as voltaxes desa forma:**
   - Conecta o conector ATX ou o Cable EPS ao **Power Supply Tester** ou ao **multímetro**.
   - O Power Supply Tester proporciona una **carga mínima artificial (dummy load)** para que a fonte se encienda.
   - **Se usas só o multímetro:** Algunas fontes modernas non se encienden sen carga, polo que é mellor usar o Power Supply Tester.

9. **Se necesitas usar a fonte enchufada:**
   - Enchufa **SOLO** o **Power Supply Tester** ao conector ATX.
   - **NUNCA** enchufes directamente a fonte á placa base sen ter tido antecedentes de que funciona correctamente.

### Post-Medición: Remontaxe

10. **Desconecta de novo a fonte da rede.**
11. **Espera 5 minutos máis**
12. **Quita o Power Supply Tester ou o multímetro.**
13. **Se necesitas reinstalar a fonte no PC:**
    - Conecta todos os cables correctamente.
    - Asegúrate de que non hai cables folgos.
    - Verifica que os conectores están inseridos ata o fondo.
    - Só entón conecta a rede eléctrica.

---

## 3. Pasos Prácticos para Medir Voltaxes

### Método A: Usando Power Supply Tester (Recomendado)

#### Paso 1: Preparación

1. Coloca a fonte horizontal.
2. Localiza o conector ATX 24-pins.
3. Enchúfaa o **Power Supply Tester** ao conector ATX.

#### Paso 2: Encendido

4. Enchufa a fonte á rede eléctrica (220V).
5. Activa o **botón de encendido** da fonte (se a ten, adoita ser un botón físico ou un interruptor).
6. O **Power Supply Tester** mostrará na pantalla LCD os valores de:
   - **+3.3V**
   - **+5V**
   - **+12V**
   - **-12V** (dependendo do modelo)

#### Paso 3: Lectura de Resultados

7. Anota os valores que se mostran na pantalla.
8. Compáraos coa táboa de tolerancias (sección 4).

#### Paso 4: Desconexión

9. Apaga a fonte.
10. Desconecta o Power Supply Tester.
11. Desenchufa a fonte da rede eléctrica.

---

### Método B: Usando Multímetro (Máis Preciso pero Máis Complexo)

#### Paso 1: Preparación do Multímetro

1. Coloca o **multímetro en modo de medición de tensión DC (voltios)** → Busca o símbolo "⎓=" ou "DCV".
2. Selecciona o rango de **20V** (ou superior se dispoible).

#### Paso 2: Identificación de Pins

Localiza os pins do conector ATX 24-pins segundo esta táboa:

| Voltaxe | Cores de Cable | Pins |
|---|---|---|
| **+3.3V** | Naranja | 1, 2, 12, 13 |
| **+5V** | Vermello | 4, 6, 21, 22, 23 |
| **+12V** | Amarelo | 10, 11 |
| **GND (Masa)** | Negro | 3, 5, 7, 15, 17, 18, 19, 24 |
| **+5V SB** | Violeta | 9 |
| **-12V** | Azul | 14 |

#### Paso 3: Medición de Voltaxes

**Para medir a tensión entre dous puntos:**

3. Conecta a **sonda NEGRA (-)** do multímetro a un **pin GND (negro)** (por exemplo, pin 3, 5, 7, 15, 17, 18, 19 ou 24).
4. Conecta a **sonda ROJA (+)** do multímetro ao pin que desexas medir.

**Exemplo: Medir o raíl de +5V**
- Ponte a sonda negra en un pin negro (GND).
- Ponte a sonda roja en un pin vermello (pin 4, 6, 21, 22 ou 23).
- Le o valor no display do multímetro.

#### Paso 4: Toma de Medidas

5. **Mide todos estes raís:**
   - **+3.3V** (naranja): Espérase 3.3V ± 10% = entre **2.97V e 3.63V**
   - **+5V** (vermello): Espérase 5V ± 5% = entre **4.75V e 5.25V**
   - **+12V** (amarelo): Espérase 12V ± 5% = entre **11.4V e 12.6V**
   - **-12V** (azul): Espérase -12V ± 10% = entre **-10.8V e -13.2V**
   - **+5V Standby** (violeta, pin 9): Espérase 5V ± 5% = entre **4.75V e 5.25V**

6. **Anota todos os valores** nunha táboa.

#### Paso 5: Conclusión

7. Desconecta o multímetro.
8. Desenchufa a fonte con seguridade.

---

## 4. Táboa de Tolerancias Aceptables (Estándar ATX)

A seguinte táboa indica os rangos **aceptables** para cada raíl segundo o estándar ATX:

| Raíl | Voltaxe Nominal | Tolerancia | Rango Aceptable | Estado |
|---|---|---|---|---|
| **+3.3V** | 3.3V | ±10% | 2.97V — 3.63V | ✅ Aceptable |
| **+5V** | 5.0V | ±5% | 4.75V — 5.25V | ✅ Aceptable |
| **+12V** | 12.0V | ±5% | 11.4V — 12.6V | ✅ Aceptable |
| **-12V** | -12.0V | ±10% | -10.8V — -13.2V | ✅ Aceptable |
| **+5V SB** | 5.0V | ±5% | 4.75V — 5.25V | ✅ Aceptable |
| **PWRGOOD** | 0V ou 5V | — | Debe pasar a 5V en <100ms | ✅ Aceptable |

### Interpretación de Resultados

#### Resultado Verde (✅) - Fonte en Perfecto Estado
- Todos os raíles están **dentro do rango aceptable**.
- A fonte está **sirvível para o PC**.

#### Resultado Amarelo (⚠️) - Fonte Degradada
- Un ou dous raíles están **fóra do rango pero cercanos** (ex: 5.3V cando o máximo é 5.25V).
- A fonte **pode ser problemática** con carga máxima.
- **Recomendación:** Sústituíla, porque os componentes sensibles poderían dañarse.

#### Resultado Rojo (❌) - Fonte Defectuosa
- Un ou máis raíles están **moi fóra do rango** (ex: 3.8V cando o máximo é 3.63V).
- A fonte **debe ser substituída de inmediato**.
- **Risco de dañar a placa base, CPU e GPU**.

---

## 5. Actividade Práctica Proposta

## PRÁCTICA TALLER: Medición FONTE PSU co Power Suply Tester

**Materiais Necesarios:**

- Fonte de alimentación a testar
- Power Supply Tester
- Pulseira antiestática

**Protocolo:**

1. Coloca a fonte horizontal.
2. Localiza o conector ATX 24-pins.
3. Enchúfaa o **Power Supply Tester** ao conector ATX.
4. Enchufa a fonte á rede eléctrica (220V).
5. Activa o **botón de encendido** da fonte (se a ten, adoita ser un botón físico ou un interruptor).
6. **Completa a seguinte táboa:**

| Raíl | Voltaxe Medida | Rango Aceptable | Estado |
|---|---|---|---|
| +3.3V |  |  |  |
| +5V |  |  |  |
| +12V |  |  |  |
| -12V |  |  |  |
| +5V SB |  |  |  |

4. **Conclusión:**

- A fonte é **ACEPTABLE / DEFECTUOSA / DEGRADADA** (marca a opción).

``` Indica a cor
 
 ```

- **Xustificación:** Indica que raíles fallaron e en cánto se desvían.

```




  ```

5. **Fotografía -- ENTREGA**
   - Toma unha foto do Power Supply Tester con os valores mostrados e do folio cos resultados e SÚBEOS EN **PDF Á AULA VIRTUAL**

## PRÁCTICA TALLER : Medición FONTE PSU co MULTÍMETRO

**Materiais Necesarios:**

- Fonte de alimentación a testar
- Power Supply Tester OU Multímetro
- Pulseira antiestática

**Protocolo:**
1. Coloca o **multímetro en modo de medición de tensión DC (voltios)** → Busca o símbolo "⎓=" ou "DCV".
2. Selecciona o rango de **20V** (ou superior se dispoible).
3. **Mide todas as voltaxes**.

**RANGOS TOLERABLES**

A seguinte táboa indica os rangos **aceptables** para cada raíl segundo o estándar ATX:

| Raíl | Voltaxe Nominal | Tolerancia | Rango Aceptable | Estado |
|---|---|---|---|---|
| **+3.3V** | 3.3V | ±10% | 2.97V — 3.63V | ✅ Aceptable |
| **+5V** | 5.0V | ±5% | 4.75V — 5.25V | ✅ Aceptable |
| **+12V** | 12.0V | ±5% | 11.4V — 12.6V | ✅ Aceptable |
| **-12V** | -12.0V | ±10% | -10.8V — -13.2V | ✅ Aceptable |
| **+5V SB** | 5.0V | ±5% | 4.75V — 5.25V | ✅ Aceptable |
| **PWRGOOD** | 0V ou 5V | — | Debe pasar a 5V en <100ms | ✅ Aceptable |

4.**Completa a seguinte táboa:**

### 📋 Checklist de Diagnose: Conector ATX 24-Pins

### 📋 Checklist de Diagnose: Conector ATX 24-Pins (Só raís de voltaxe)

| Pin | Cor Típica | V Esperado | V Real (Medido) | Validez (±5%) | **VÁLIDO??** (✔️/❌) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **1** | Laranxa | **+3.3V** | | 3.14V - 3.47V | |
| **2** | Laranxa | **+3.3V** | | 3.14V - 3.47V | |
| **4** | Vermello | **+5V** | | 4.75V - 5.25V | |
| **6** | Vermello | **+5V** | | 4.75V - 5.25V | |
| **8** | Gris | **PWR_OK** | | 2.40V - 5.25V | |
| **9** | Violeta | **+5V SB** | | 4.75V - 5.25V | |
| **10** | Amarelo | **+12V** | | 11.40V - 12.60V | |
| **11** | Amarelo | **+12V** | | 11.40V - 12.60V | |
| **12** | Laranxa | **+3.3V** | | 3.14V - 3.47V | |
| **13** | Laranxa | **+3.3V** | | 3.14V - 3.47V | |
| **14** | Azul | **-12V** | | -10.80V - -13.20V | |
| **16** | Verde | **PS_ON#** | | 0V (Low) | |
| **20** | NC / Branco | **-5V** | | N/A (Opcional) | |
| **21** | Vermello | **+5V** | | 4.75V - 5.25V | |
| **22** | Vermello | **+5V** | | 4.75V - 5.25V | |
| **23** | Vermello | **+5V** | | 4.75V - 5.25V | |


4. **Conclusión:**

- A fonte é **ACEPTABLE / DEFECTUOSA / DEGRADADA** (marca a opción).

``` Indica a cor
 
```

- **Xustificación:** Indica que raíles fallaron e en cánto se desvían.

```



```

5. **Fotografía/Entrega**: foto ao folio e súbea a aula virtual en PDF.

---

## 6. Vídeos de Referencia

- **Como testar unha fonte cun Power Supply Tester:** [https://www.youtube.com/watch?v=F81j0KGX4FA](https://www.youtube.com/watch?v=F81j0KGX4FA)
- **Como medir voltaxes con multímetro:** [https://www.youtube.com/watch?v=nv8yor7fK-I](https://www.youtube.com/watch?v=nv8yor7fK-I)

---

## 7. Troubleshooting: Problemas Comúns

| Problema | Causa Probable | Solución |
|---|---|---|
| A fonte non se enciende | Non ten carga, necesita un dummy load | Usa o Power Supply Tester en lugar do multímetro |
| O multímetro mostra 0V en todos os raíles | Mala conexión das sondas | Verifica que a sonda negra está ben conectada a GND |
| Os valores oscilan moito | Mala conexión ou fonte de interferencia | Seca ben os contactos e retira cables electromagnéticos (móbiles) |
| Un raíl mostra voltaxe oposta (ex: -5V en lugar de +5V) | As sondas están invertidas | Cambia a sonda roja á negra e ao revés |
| A fonte emite chispas ou fumo | **PERIGO CRÍTICO** | Apagaa inmediatamente, **non a toqués máis**, destrúea ou lévaa a un centro de reciclaxe |

