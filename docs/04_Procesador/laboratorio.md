# Laboratorio

### 1. Como identificalos os NÚCLEOS/CORES e o tipo no teu sistema operativo

Se xa tes o ordenador diante e queres comprobalo sen buscar en webs, tes tres xeitos profesionais:

#### A. O Administrador de Tarefas (Windows)
1.  Preme `Ctrl + Shift + Esc`.
2.  Vai á pestana **Rendemento** e fai clic en **CPU**.
3.  Abbaixo verás "Núcleos" e "Procesadores lóxicos".
    * *Exemplo Intel:* Se di "Núcleos: 14" e "Lóxicos: 20", sabes que hai mestura. (6P con 12 fíos + 8E con 8 fíos = 14 núcleos e 20 fíos).

#### B. Software Especializado (O máis fiable)

Descarga e executa **CPU-Z**. Na pestana principal ("CPU"), na esquina inferior dereita, verás un desglose exacto:
* En Intel poñerá algo como: `Selection: Socket #1 -> Cores: 8P + 8E`.
* En AMD poñerá o total de núcleos, pero nas versións novas detallará se son arquitecturas mixtas.



#### C. O terminal (Para técnicos de ASIR)

Podes usar o comando en PowerShell para ver como o SO identifica os núcleos:
```powershell
Get-WmiObject -Class Win32_Processor | Select-Object Name, NumberOfCores, NumberOfLogicalProcessors
```
