
# 📑 Ficha de Campo: Seguridade e Continuidade (CPD Hospital)

### 1. Sistema de Enerxía Ininterrompida (SAI/UPS)
*   **Autonomía:** ¿Canto tempo poden soster os SAIs a carga crítica do CPD antes de que se esgoten as baterías?
    *   *Tempo estimado:* ____________ minutos.
*   **Configuración:** ¿Existe redundancia nos SAIs? (Ex: **N+1**, onde se falla un SAI, outro asume a carga).
    *   [ ] SI [ ] NON
*   **Grupo Electróxeno:** ¿Hai un xerador externo de combustión? ¿Canto tarda en arrincar e conmutar desde que falla a rede eléctrica?
    *   *Resposta:* _________________________________________________

### 2. Capa Lóxica e Alta Dispoñibilidade (HA)
*   **Virtualización:** ¿Que Hipervisor utilizan para xestionar o clúster? (Ex: VMware, Proxmox, Hyper-V).
    *   *Resposta:* _________________________________________________
*   **HA Real:** Se desconectamos un servidor físico agora mesmo, ¿as máquinas virtuais migran ou reinician noutro nodo automaticamente?
    *   [ ] SI, automaticamente. [ ] Requiere intervención manual. [ ] Non hai HA.
*   **Sistemas Operativos:** ¿Que SO predomina nos servidores (Windows Server / Linux)?
    *   *Resposta:* _________________________________________________

### 3. Seguridade Física e Ambiental
*   **Extinción de Incendios:** ¿Que axente extintor utilizan? (Busca botellas de gas, non debe haber auga).
    *   [ ] Gas (Novec, Inergen, etc.) [ ] Outros: ____________________
*   **Control de Acceso:** ¿Que medidas de seguridade hai para entrar na sala? (Teclado, tarxeta biométrica, dobre porta).
    *   *Observación:* _________________________________________________
*   **Climatización:** ¿A que temperatura se mantén a sala e como se detectan fugas de auga ou humidade?
    *   *Temperatura actual:* __________ ºC.

### 4. Pilas de Discos e Backup
*   **Almacenamento Exterior:** ¿Os datos residen nunha cabina (SAN) ou nos propios servidores?
    *   *Tipo:* ______________________________________________________
*   **Copia de Seguridade (Inmutabilidade):** ¿Existe algunha copia de seguridade fóra de liña (offline) ou fóra do hospital para protexer contra Ransomware?
    *   *Resposta:* _________________________________________________

### 5. Conectividade e Fabric (Rede de Datos)

Nesta sección debemos diferenciar entre a rede de **servizo** (usuarios conectándose ao servidor) e a rede de **almacenamento** (servidores escribindo na pila de discos).

*   **Rede de Almacenamento (Storage):** ¿Como se conectan os servidores ás cabinas de discos/SAN?
    *   [ ] **Fibre Channel (FC):** (Fibra óptica dedicada, normalmente cables laranxas ou acuáticos con conectores LC). ¿A que velocidade? (Ex: 8Gb, 16Gb, 32Gb).
    *   [ ] **iSCSI / NFS:** (Rede Ethernet dedicada).
*   **Rede de Datos (Ethernet):** ¿Que cables conectan os servidores aos switches de rede?
    *   **Cobre (RJ45):** Identifica a categoría marcada no cable (Ex: **Cat6, Cat6a ou Cat7**).
    *   **Fibra/SFP+:** ¿Vedes transceptores ópticos inseridos nos switches?
*   **Velocidade do Backbone:** ¿Cal é a velocidade das ligazóns troncais (tronco principal)?
    *   (Ex: 10 Gbps, 40 Gbps ou 100 Gbps).

### Curiosidades: 
* Como fan para almacenar probas que ocupan moito espazo? Onde almacenan? Fano por períodos de tempo?