# SOLUCIÓNS - 2. Práctica 2: Diagnóstico de Subsistema de Memoria MemTest

## 1. Preparación (Notas técnicas)
* **Ventoy:** É a opción máis eficiente para un administrador de sistemas moderno. Funciona por emulación de ficheiro, o que permite ter múltiples ferramentas (Clonezilla, MemTest, ISOs de Windows/Linux) nun só disco.
* **dd:** É fundamental que o alumno entenda que `dd` (dataset definition) escribe a nivel de sectores, ignorando o sistema de ficheiros previo do pendrive.

## 2. Procedemento de Teste
* **Fase II (Algoritmos):**
    * **Test 5:** Busca problemas de "ruído" ou interferencias entre bits próximos.
    * **Test 7:** Estresa o controlador de memoria (IMC) movendo grandes bloques, útil para detectar inestabilidades por voltaxe ou temperatura.
    * **Test 13 (Row Hammer):** Estresa as celdas lendo repetidamente as filas adxacentes para ver se a carga eléctrica "salta" a unha celda veciña.

* **Fase III (Análise de Erro):**
    1. O erro está nos primeiros **420.5 MB**. Nun sistema con dous módulos de 8GB (16GB totais), as direccións baixas sempre corresponden ao **primeiro módulo físico (Slot 1)**.
    2. Fallou **1 bit**.
       * Good: `1111 1111 1111 1111 1111 1111 1111 1111`
       * Bad:  `1111 1111 1110 1111 1111 1111 1111 1111`
       * O bit na posición 20 (contando dende a dereita) cambiou de 1 a 0.
    3. Un erro inmediato adoita ser un **Hard Error** (celda danada fisicamente). Un erro tras horas adoita ser un **Soft Error** provocado por calor ou electromigración.

## 3. Cuestionario de Consolidación

1. **ECC:** No caso de memoria ECC, o MemTest informaría de "Corrected Errors". O sistema non fallaría, pero avisaría de que o módulo está empezando a degradarse.
2. **S.O. vs MemTest:** Porque o sistema operativo asigna direccións de memoria de xeito dinámico (Virtual Memory). O erro está nunha dirección física fixa, pero a aplicación que "cae" é a que o S.O. decide poñer nese enderezo nese momento.
3. **Hardware:** Se o erro desaparece ao cambiar de slot, a avaría está no **slot da placa base** (pins dobrados, sucidade ou pista cortada) ou nunha canle defectuosa do controlador de memoria integrado na **CPU**.

