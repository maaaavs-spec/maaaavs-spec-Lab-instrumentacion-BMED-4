# 
## Laboratorio_4_
# **Integrantes**
>
* María Angélica Vargas Saldaña 5600820
* Samuel Esteban Fonseca Luna 5600808
* Laura Daniela Triana Molano 560028


<h1 align="center"><i><b>Resumen y palabras claves</b></i></h1>
El presente laboratorio tiene como propósito diseñar y construir un modelo a escala de una incubadora neonatal mediante la aplicación de conceptos de instrumentación biomédica, electrónica y sistemas de control. El desarrollo comprende el diseño de un sistema de control de temperatura en lazo cerrado, capaz de mantener la temperatura interior entre 36 °C y 37,5 °C, y un sistema de medición de peso mediante un sensor de fuerza. Se busca integrar estos componentes en un prototipo que permita evaluar el control de temperatura, la medición del peso y las limitaciones del sistema frente a una incubadora neonatal comercial.

Palabras claves:Incubadora neonatal, instrumentación biomédica, control de temperatura, sistema de lazo cerrado, sensor de fuerza, fuente de alimentación, electrónica.

<h2 align="center">𝙞𝙣𝙩𝙧𝙤𝙙𝙪𝙘𝙘𝙞ó𝙣</h2>
La incubadora neonatal es un aparato de la medicina cuyo propósito esencial es crear un microambiente controlado que simula las circunstancias del útero materno, garantizando así que el recién nacido sobreviva y se desarrolle de manera óptima, sobre todo aquellos que nacen prematuramente. La norma internacional IEC 60601-2-19 regula su funcionamiento, la cual define los requerimientos de seguridad básica y rendimiento esencial para este tipo de dispositivos.


En este contexto, la práctica consiste en diseñar, simular y construir un modelo de incubadora neonatal a escala que integre el control de temperatura y la medición de peso. A través de su desarrollo, se busca evaluar el funcionamiento de los circuitos implementados e identificar las limitaciones que deben considerarse para diferenciar un prototipo académico de un dispositivo médico destinado al uso clínico.


<h2 align="center">𝙤𝙗𝙟𝙚𝙩𝙞𝙫𝙤𝙨</h2>

𝙊𝙗𝙟𝙚𝙩𝙞𝙫𝙤 𝙜𝙚𝙣𝙚𝙧𝙖𝙡: 
Diseñar una incubadora neonatal a escala que permita regular la temperatura interior y medir el peso mediante la integración de circuitos electrónicos para el control de temperatura y la medición de peso


𝙊𝙗𝙟𝙚𝙩𝙞𝙫𝙤𝙨 𝙀𝙨𝙥𝙚𝙘𝙞́𝙛𝙞𝙘𝙤𝙨:

 - Identificar los componentes principales de una incubadora neonatal y describir sus funciones.
 - Implementar un sistema de calentamiento mediante un bombillo y un ventilador que favorezca la distribución del calor en el interior de la incubadora.
 - Evaluar el funcionamiento de la incubadora a escala mediante pruebas de temperatura y medición de peso, y comparar sus características con las de equipos comerciales.

<h1 align="center"><i><b>Marco teorico</b></i></h1>

*1. Incubadora neonatal* Es un dispositivo médico diseñado para proporcionar a un recién nacido un ambiente controlado, manteniendo condiciones ambientales similares a las intrauterinas, esto con el fin de para ayudar y favorecer la supervivencia y correcto desarrollo del bebé, especialmente en neonatos prematuros, debido a que presentan una mayor dificultad para regular su temperatura corporal como consecuencia de la inmadurez de sus mecanismos de termorregulación.

*2. Termorregulación neonatal* La termorregulación es el proceso fisiológico mediante el organismo mantiene su temperatura corporal dentro de los limites adecuados, en el caso de los recién nacidos especialmente en los prematuros, este proceso puede ser menos eficiente debido a la inmadurez de sus mecanismos de regulación térmica y por las características de su piel.

Por esto mismo, las incubadoras proporcionan un ambiente que permite reducir las pérdidas de calor y mantener las condiciones térmicas controladas, normalmente establecida entre 36° y 37,5°, medidas que usamos para nuestra práctica.

*3. Transferencia de calor por convección* Este tipo de transferencia ocurre cuando la energía térmica se transfiere mediante el movimiento de un fluido, comúnmente el aire. En una incubadora se evidencia este mecanismo permitiendo distribuir de mejor manera el calor generado por el sistema dentro de la cámara. El prototipo utiliza un elemento resistivo el cual transforma la energía eléctrica en energía térmica y un ventilador que favorece el movimiento del aire.

*4. Termistor* Es un componente el cual tiene una resistencia eléctrica cuyo valor varía en función de la temperatura. Esta propiedad posibilita su uso para evaluar las condiciones térmicas dentro de la incubadora.
Los termistores se dividen en dos categorías principales: NTC y PTC. En los NTC, la resistencia baja al elevarse la temperatura; en cambio, en los PTC lo hace cuando se incrementa. A través de un circuito eléctrico, la fluctuación de resistencia tiene el potencial de convertirse en una señal eléctrica, lo cual posibilita detectar alteraciones en la temperatura. La señal adquirida se utiliza como una referencia para decidir si la temperatura al interior está dentro del rango establecido y si es necesario ajustar el calentamiento. 

*5. Regulación de la temperatura* Consiste en comparar el valor medio en el interior de la incubadora con un valor de referencia para determinar cuando debe aumentarse o reducirse el calentamiento. E l error de temperatura se puede expresar mediante la ecuación:
$e(t)=T_{\mathrm{ref}}-T_{\mathrm{medida}}(t)$
Donde $(T_{\mathrm{ref}})$ es la temperatura de referencia y $(T_{\mathrm{medida}}(t))$ corresponde a la temperatura registrada por el sensor.
Cuando la temperatura es inferior al nivel requerido, el circuito puede activar el elemento calefactor. Cuando alcanza el intervalo establecido, el circuito debe ajustar el aporte de calor para evitar un calentamiento excesivo. La estrategia específica depende del diseño electrónico utilizado.
En el prototipo, tres LED permiten identificar visualmente el estado de la temperatura: el verde indica que se encuentra dentro del intervalo especificado, mientras que los dos rojos indican una temperatura inferior o superior al rango de funcionamiento.
 
 


<h1 align="center"><i><b>𝐏𝐚𝐫𝐭𝐞 A 𝐝𝐞𝐥 𝐥𝐚𝐛𝐨𝐫𝐚𝐭𝐨𝐫𝐢𝐨</b></i></h1>
*Partes de la incubadora*
<img width="526" height="526" alt="image" src="https://github.com/user-attachments/assets/01cb03c3-7e7d-434d-bdd4-e799fa3538da" />

 *Circuito Lazo cerrado*
 *Circuito peso*
 
 
<h1 align="center"><i><b>𝐏𝐚𝐫𝐭𝐞 B 𝐝𝐞𝐥 𝐥𝐚𝐛𝐨𝐫𝐚𝐭𝐨𝐫𝐢𝐨</b></i></h1>
𝙈𝙤𝙣𝙩𝙖𝙟𝙚 𝙚𝙭𝙥𝙚𝙧𝙞𝙢𝙚𝙣𝙩𝙖𝙡

𝙀𝙭𝙥𝙡𝙞𝙘𝙖𝙘𝙞𝙤́𝙣 𝙙𝙚𝙡 𝙘𝙤𝙙𝙞𝙜𝙤
```
```
*Costo total deel sistema*

*Costo por partes*
| Material/Componente  | Costo estimado (COP) |
| -------------------- | -------------------- |
| Caja plastica        | 50,000               |
| Ventilator 12v       |  9.000               |
| Rele                 | 30.000.              |
| OLED                 | 25.000               |
| Bombillo.            | 2.000                |
| Termisor             |  4,500               |
|Rosaueta para bombillo| 4,000                |
|FSR                   | 28,000               |
*Comparación con incubadoras comerciales*

<h1 align="center"><i><b>𝐏𝐚𝐫𝐭𝐞 C 𝐝𝐞𝐥 𝐥𝐚𝐛𝐨𝐫𝐚𝐭𝐨𝐫𝐢𝐨</b></i></h1>
*Procedimiento*
*Discución*
Pregunta 1: ¿Qué otras variables (y por qué) además de las aquí 
mencionadas son críticas en el monitoreo neonatal? 
Además de la temperatura y el peso, existen otras variables importantes para el monitoreo neonatal, entre estas se encuentra la frecuencia cardíaca, la frecuencia respiratoria, la saturación de oxígeno en la sangre y la humedad relativa del ambiente. Donde la frecuencia cardíaca permite evaluar el funcionamiento del sistema cardiovascular, mientras que la frecuencia respiratoria ayuda a identificar alteraciones en la respiración, la saturación de oxígeno permite conocer si el organismo recibe una cantidad adecuada de oxígeno y por otra parte, la humedad relativa influye en las pérdidas de agua y calor a través de la piel, especialmente en los recién nacidos prematuros. El monitoreo de estas variables permite identificar cambios en el estado fisiológico del neonato y facilita la intervención oportuna del personal de salud cuando sea necesario.

• Pregunta 2: ¿Qué haría falta para convertir el sistema desarrollado en una 
incubadora neonatal real? 
sería necesario incorporar sistemas de medición y regulación de mayor precisión, mecanismos de seguridad y alarmas que detecten más condiciones anormales como los problemas en la alimentación electrica, además garantizar una distribución uniforme del aire y controlar variables ambientales adicionales como la humedad, y verificar el cumplimiento de las normas técnicas y los requisitos regulatorios aplicables a los dispositivos médicos especificamente en la normativa Colombiana para equipos biomédicos expedida por el INVIMA  (Instituto Nacional de Vigilancia de Medicamentos y Alimentos )

• Pregunta 3: ¿Qué semejanzas hay entre una incubadora neonatal y una 
servo-cuna?
A pesar de que ambos dispositivos medicos se usan para mantener la temperatura de los neonatos, se diferencian principalmente en su estructura y en la forma de proporcionar calor: la incubadora cuenta con una cubierta que crea un ambiente más cerrado y controlado que simula el útero materno, mientras que la servo-cuna o cuna de calor radiante suele ser una cama abierta que utiliza una fuente de calor radiante situada sobre el recién nacido. Por esta razón, la incubadora favorece el control del microambiente interior, mientras que la servo-cuna facilita el acceso directo al paciente para procedimientos médicos y cuidados asistenciales.

<img width="399" height="501" alt="image" src="https://github.com/user-attachments/assets/ed06ebe1-5c90-4c7c-9e08-397ec7b9e504" />

Imagen tomada de https://enfermeriabuenosaires.com

𝘾𝙤𝙣𝙘𝙡𝙪𝙨𝙞𝙤𝙣

𝘽𝙞𝙗𝙡𝙞𝙤𝙜𝙧𝙖𝙛𝙞𝙖

+Restrepo Pérez, L., Durango Londoño, N., Gómez Suárez, N., González Ramírez, F., & Rivera Bonilla, N. (2007). Prototipo de incubadora neonatal. Revista Ingeniería Biomédica, 1(1), 55-59.
+ Latif, A., Widodo, H. A., Atmoko, R. A., Phong, T. N., & Helmy, E. T. (2021). Temperature and humidity controlling system for baby incubator. Journal of Robotics and Control (JRC), 2(3), 190-193.
+ Mittal, H., Mathew, L., & Gupta, A. (2015). Design and development of an infant incubator for controlling multiple parameters. Int. J. Emerg. Trends Electr. Electron, 11(5), 2320-9569.
+ Subramanian, M., Sheela, T., Srividya, K., & Arulselvam, D. (2019). Security and health monitoring system of the baby in incubator. Int. J. Eng. Adv. Technol, 8(6), 3582-3585.
+ Client challenge. (s. f.-b). https://es.scribd.com/document/670874835/Clase-7-8-Incubadora-y-Servocunas
+ Castro, L. B., Parra, M. C., & Díaz, G. M. INCUBADORA NEONATAL. Biomedicina, 1, 1.
+ García Olivares, D. (2022). NeoEq: Desarrollo de una incubadora infantil de bajo costo para la estabilización neonatal en zonas remotas de Colombia.
+ Restrepo Pérez, L., Durango Londoño, N., Gómez Suárez, N., González Ramírez, F., & Rivera Bonilla, N. (2007). Prototipo de incubadora neonatal. Revista Ingeniería Biomédica, 1(1), 55-59.
+ Mojica, A., Vásquez, K., & Cerón, M. (2026). Diseño e Implementación de una Incubadora Neonatal Utilizando Tecnología ESP32 para Entornos de Recursos Limitados. Conducta científica, 9(1), 95-105.
