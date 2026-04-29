# Prácticas de Diagnóstico de hardware base (Memoria e discos)


## Material Necesario:
* PC con sospeita de fallo ou para mantemento.
* USB Booteable con **Ultimate Boot CD (UBCD)**.
* Cronómetro.

---

### Fase 1: Validación da Integridade de Datos (0:00 - 0:15)
**Obxectivo:** Confirmar que o bus de datos e a RAM non corrompen a información.

1.  Arranca o equipo dende o USB e selecciona **Memory** > **MemTest86+**.
2.  Deixa que se execute o **Test 5**. Vas a (1) Test Selection e escolemos **test número 5**(son os máis críticos para detectar fallos de direccionamento e patróns de bits).
3.  **Criterio de éxito:** Se nunha pasada completa (aprox. 12-15 min en sistemas modernos) non hai enderezos en vermello, abortamos e pechamos. Se hai erros, a práctica remata aquí: hai que illar o módulo defectuoso.

### Fase 2: Análise de S.M.A.R.T. e Superficie (0:15 - 0:35)
**Obxectivo:** Verificar a saúde física do soporte de almacenamento mediante comandos directos ao firmware.

1.  Executa a lectura dos atributos S.M.A.R.T. ben desde o programa do fabricante, ou desde a ferramenta DISCOS de Linux, ou con kdiskmark (linux)

### Fase 3: Estrés Térmico e Lóxico da CPU (0:35 - 0:45)

**Obxectivo:** Forzar os estados de voltaxe e a disipación de calor.

1.  Reinicia e vai a **CPU** > **CPUStress**.
2.  Configura unha proba de carga sintética (**Mersenne Prime test** ou similar incluído), escolle a opción **Blend** (O ideal sería deixalo 1 ou 2 horas, pero imos deixalo 5 min), logo cancela con **Ctrl+C** 
3.  Lanza o test de temperatura **#sensors** toma nota das temperaturas.
4.  Monitoriza (se a placa o permite vía BIOS ou utilidade interna) a temperatura. 

Se o sistema se apaga instantaneamente, tes un problema de **pasta térmica seca** ou fallos nos **condensadores do VRM**.

### Fase 4: Documentación e Informe Técnico (0:45 - 0:50)

**Obxectivo:** Formalizar o diagnóstico.

1.  Redacta un breve informe incorporando pantallazos de resultado de cada proba e nun folio, de forma clara:

    * **Status RAM:** (Pass/Fail + número de erros).
    * **Status Disco:** (Atributos críticos e tempo de acceso).
    * **Status Térmico:** (Estabilidade baixo carga).

---

### Notas:

* **Por que esta orde?** Nunca estreses unha CPU (Fase 3) ou escribas nun disco (Fase 2) se a RAM (Fase 1) non é estable, xa que poderías corromper o firmware ou os datos do cliente durante as propias probas.

