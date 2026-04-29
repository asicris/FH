# Exercicios microprocesadores

## Exercicio 1: Análise Comparativa de Microprocesadores (Arquitectura Intel Core Ultra)

**Obxectivo:** Identificar as diferenzas técnicas e de rendemento entre dous modelos da mesma xeración para comprender a relación entre o custo e as capacidades do hardware.

**Instrucións:**

1. Busca as especificacións técnicas oficiais (Intel ARK) ou en tendas especializadas para os modelos **Intel Core Ultra 5 225** e **Intel Core Ultra 9 285K**.
2. Completa a táboa seguinte cos datos correspondentes.
3. Responde ás preguntas de análise que figuran ao final.

## Táboa Comparativa

| Característica | Core Ultra 5 225 | Core Ultra 9 285K |
| :--- | :--- | :--- |
| **Núcleos Totais (P-Cores + E-Cores)** | | |
| **Frecuencia Turbo Máxima** | | |
| **Capacidade de Overclocking** | | |
| **Uso Ideal / Perfil de Usuario** | | |
| **Prezo Aproximado (PVP)** | | |

## Preguntas de Análise

1. **Eficiencia vs Potencia:** Explica por que o Core Ultra 9 ten 16 núcleos de eficiencia (E-Cores) mentres que o Ultra 5 só ten 4. En que tipo de tarefas de ASIR notaríamos máis esta diferenza?
2. **O factor "K":** Que significa a letra "K" no modelo 285K? Que compoñente adicional do PC debemos escoller con máis coidado se montamos este procesador en comparación co 225?
3. **Relación custo-rendemento:** O prezo do Ultra 9 é máis do triplo que o do Ultra 5. Cres que para un posto de traballo de administración de sistemas básico (ofimática e SSH) paga a pena o investimento? Xustifica a resposta.

### Exercicio 2: "O Consultor de Sistemas" (Presuposto e Selección)

**Obxectivo:** Aprender a equilibrar o custo do procesador co resto dos compoñentes e as necesidades do cliente.

**Enunciado:**
Unha pequena academia de deseño gráfico necesita renovar 3 postos de traballo. Teñen un orzamento de **450€ por cada torre** (sen monitor). O software principal que usan é Adobe Photoshop e Illustrator.
Tes que escoller entre estas dúas configuracións e xustificar cal é mellor para o cliente:

* **Opción A:** Procesador **Intel Core Ultra 9 285K** (580€) + Placa base básica + 8GB RAM.
* **Opción B:** Procesador **AMD Ryzen 5 7600** (200€) + Placa base media + 32GB RAM + Disco SSD NVMe.

**Preguntas para o alumno:**
1.  É viable a Opción A? Por que?
2.  Por que para deseño gráfico é mellor a Opción B a pesares de ter un procesador máis "frouxo"?
3.  Que sufixo ten o procesador de AMD e que significa a nivel de gráficos integrados?

### Exercicio 3: "Investigación Forense no Terminal" (Linux/Windows)

**Obxectivo:** Familiarizarse coas ferramentas de diagnóstico do Sistema Operativo.

**Enunciado:**
Accede a un equipo con **Ubuntu Linux** (pode ser unha máquina virtual) e executa os comandos necesarios para cubrir a seguinte ficha técnica do procesador real que estás a usar:

1.  **Modelo exacto:** (Comando: `lscpu "`)
2.  **Arquitectura:** (¿É x86_64 ou ARM?)
3.  **Banderas (Flags):** Busca se o teu procesador soporta **VT-x** ou **AMD-V** (necesario para virtualizar). (Comando: `grep -E 'vmx|svm' /proc/cpuinfo`)
4.  **Velocidade en tempo real:** Executa o comando `watch -n 1 "grep MHz /proc/cpuinfo"` e abre varias pestanas no navegador. Que observas que lle pasa á frecuencia dos núcleos?

---

### Exercicio 4: "Interpretación de Sufixos e Sockets" (Matching)

**Obxectivo:** Memorizar a nomenclatura técnica para evitar erros de compra/montaxe.

**Enunciado:**
Une cada procesador coa súa característica de montaxe ou uso principal:

| Procesador | Característica / Sufixo / Socket |
| :--- | :--- |
| 1. Intel Core i7-14700**F** | A. Soldado á placa (BGA), portátil ultra-fino. |
| 2. AMD Ryzen 7 8840**U** | B. Requírese tarxeta gráfica dedicada obrigatoriamente. |
| 3. Intel Core Ultra 7 **155H** | C. Socket AM5, deseño de chiplets. |
| 4. AMD Ryzen 9 **7950X** | D. Alto rendemento en portátil, moito consumo. |

---

# 📝 Solucións

---

## Solución Exercicio 1: Análise Comparativa de Microprocesadores (Arquitectura Intel Core Ultra)

A continuación amósanse os datos correctos que o alumno debería cubrir:

### Táboa de Datos Solucionada

| Característica | Core Ultra 5 225 | Core Ultra 9 285K |
| :--- | :--- | :--- |
| **Núcleos Totais** | 10 (6P + 4E) | 24 (8P + 16E) |
| **Frecuencia Turbo** | 4.9 GHz | 5.7 GHz |
| **Overclocking** | Non (Multiplicador Bloqueado) | Si (Multiplicador Desbloqueado) |
| **Uso Ideal** | Ofimática avanzada, Gaming 1080p, Postos de usuario estándar. | Virtualización masiva, Render 3D, IA avanzada, Servidores locais de proba. |
| **Prezo** | ~174 € | ~580 € |

### Respostas Sugeridas ás Preguntas

1. **Eficiencia vs Potencia:** O Ultra 9 ten máis E-Cores para xestionar cargas de traballo multitarefa masivas (como renderizado ou compilación de software) sen saturar os núcleos principais. En ASIR, notaríase ao executar **múltiplas máquinas virtuais simultaneamente**.
2. **O factor "K":** A "K" significa que o multiplicador está desbloqueado para facer overclocking. Debemos escoller con moito coidado o **sistema de refrixeración** (disipador ou líquida), xa que o seu TDP e a calor xerada son moito máis altos.
3. **Relación custo-rendemento:** **Non paga a pena.** Para tarefas de administración básica (terminal, navegador, documentos), a potencia extra do Ultra 9 quedaría desaproveitada. O Ultra 5 ofrece un rendemento máis que suficiente por unha fracción do custo.

---



### Solución Exercicio 2:

1.  **Non é viable.** Só o procesador xa supera o orzamento total por torre (580€ > 450€).
2.  **Polo equilibrio de compoñentes.** Para deseño é vital ter moita RAM (32GB) e un disco rápido. Un Ultra 9 cunha placa barata e pouca RAM daría peor rendemento real e sería moito máis caro.
3.  O Ryzen 5 7600 non ten sufixo "G", pero os Ryzen 7000/9000 xa traen gráficos básicos integrados, suficientes para deseño 2D.

### Solución Exercicio 4:

* **1 - B:** O sufixo "F" en Intel indica ausencia de iGPU.
* **2 - A:** O sufixo "U" indica baixo consumo, típico de ultraportátiles soldados.
* **3 - D:** O sufixo "H" indica alto rendemento (High Performance) en portátiles.
* **4 - C:** A serie 7000/9000 de AMD usa o socket AM5 e arquitectura de chiplets.

