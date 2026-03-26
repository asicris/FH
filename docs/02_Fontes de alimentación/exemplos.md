# Exemplos do Tema 02: Fontes de Alimentación

## Diagrama de bloques dunha fonte conmutada (SMPS)

A continuación móstrase o fluxo lóxico da corrente e os sinais de control nunha fonte ATX moderna:

```mermaid
graph LR
    subgraph Entrada[Etapa Primaria - Alta Voltaxe]
        AC[Entrada 230V AC] --> Filtro[Filtro EMI/Transitorios]
        Filtro --> Rect[Rectificador e Filtro]
        Rect --> Conm[Conmutadores/Transistores]
    end

    subgraph illamento[Illamento Galvánico]
        Conm --- Trans[Transformador de Alta Frecuencia]
    end

    subgraph Saida[Etapa Secundaria - Baixa Voltaxe]
        Trans --> RectOut[Rectificación e Filtrado DC]
        RectOut --> Reg[Regulación e Control PWM]
    end

    subgraph Control[Xestión de Sinais]
        Reg --> PG[Sinal Power_Good +5V]
        PS_ON[Sinal PS_ON - Pin 16] -.-> Reg
    end

    Reg --> V12[Raíl +12V]
    Reg --> V5[Raíl +5V]
    Reg --> V3[Raíl +3.3V]

    style Entrada fill:#fdd,stroke:#333
    style Saida fill:#dfd,stroke:#333
    style Control fill:#ddf,stroke:#333
```