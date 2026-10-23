# Laboratorio 4: Diseño y construcción de una incubadora neonatal a escala

**Universidad Militar Nueva Granada**  
**Programa:** Ingeniería Biomédica  
**Asignatura:** Instrumentación Biomédica y Biosensores  
**Práctica:** Diseño y construcción de una incubadora neonatal a escala

---

## Integrantes

- María Angélica Vargas Saldaña — 5600820
- Samuel Esteban Fonseca Luna — 5600808
- Laura Daniela Triana Molano — 5600828
---

# Resumen y palabras clave

El presente laboratorio tiene como propósito diseñar y construir un modelo a escala de una incubadora neonatal mediante la aplicación de conceptos de instrumentación biomédica, electrónica y sistemas de control. El desarrollo comprende la implementación de un sistema de monitoreo y regulación de temperatura, con un intervalo objetivo de 36 °C a 37,5 °C, y un sistema de medición de peso mediante un sensor de fuerza.

El prototipo construido integra una estructura transparente, un termistor, un bombillo de 120 W como fuente de calor, un ventilador para favorecer la circulación del aire y circuitos conectados a un Arduino. Además, se utilizaron indicadores LED para señalar el estado de la temperatura. Durante las pruebas, se observó que la temperatura interior alcanzaba aproximadamente los 37 °C. En la medición de peso se obtuvo una lectura de 1.976 g al utilizar una masa de referencia de 2.000 g.

La práctica permite analizar el funcionamiento de los sistemas de sensado y control, reconocer las limitaciones de un prototipo académico y establecer los aspectos que deben evaluarse antes de considerar un sistema de esta naturaleza para una aplicación clínica.

**Palabras clave:** incubadora neonatal, instrumentación biomédica, control de temperatura, sistema de lazo cerrado, termistor, sensor de fuerza, Arduino, medición de peso.

> **Advertencia:** este prototipo es exclusivamente académico. No está validado para uso clínico y no debe utilizarse con recién nacidos ni pacientes.

---

# 1. Introducción

La incubadora neonatal es un dispositivo médico diseñado para proporcionar un ambiente controlado que contribuya a mantener condiciones térmicas adecuadas para los recién nacidos, especialmente aquellos prematuros que presentan dificultades para regular su temperatura corporal.

La regulación de la temperatura es fundamental porque los neonatos pueden perder calor con mayor facilidad debido a la inmadurez de sus mecanismos fisiológicos. Por esta razón, las incubadoras utilizan sistemas de calentamiento, sensores, mecanismos de circulación del aire y controles que permiten supervisar las condiciones del ambiente interior.

En el campo de la ingeniería biomédica, estos equipos representan una aplicación importante de la instrumentación electrónica, debido a que integran sensores, circuitos de acondicionamiento, sistemas de control y mecanismos de seguridad.

En esta práctica se construyó un modelo de incubadora neonatal a escala. El prototipo utiliza un termistor para detectar cambios de temperatura, un bombillo de 120 W como fuente de calor y un ventilador que favorece la distribución del aire dentro de la estructura. Los circuitos están conectados a un Arduino y se utilizan indicadores LED para señalar el estado de la temperatura.

También se desarrolló una prueba de medición de peso mediante un sensor de fuerza, comparando la lectura del sistema con una masa de referencia conocida.

Finalmente, se analizan los resultados observados, las limitaciones del montaje, los costos de construcción y las diferencias entre el prototipo académico y los equipos comerciales.

# 2. Objetivos

## 2.1. Objetivo general

Diseñar y construir una incubadora neonatal a escala que permita estudiar la regulación de la temperatura interior y la medición de peso mediante la integración de sensores y circuitos electrónicos.

## 2.2. Objetivos específicos

- Identificar los componentes principales de una incubadora neonatal y describir sus funciones.
- Diseñar y simular un sistema de control de temperatura en lazo cerrado.
- Diseñar y simular un sistema de medición de peso mediante un sensor de fuerza.
- Implementar un sistema de calentamiento mediante un bombillo de 120 W y un ventilador que favorezca la circulación del aire.
- Incorporar indicadores LED para identificar el estado de la temperatura.
- Evaluar el comportamiento térmico del prototipo mediante las observaciones y mediciones disponibles.
- Comparar la lectura del sensor de fuerza con una masa de referencia conocida.
- Estimar los costos de construcción y establecer una comparación con soluciones comerciales.
- Documentar el procedimiento, los resultados y las limitaciones del proyecto en GitHub.

# 3. Marco teórico

## 3.1. Incubadora neonatal

Una incubadora neonatal es un equipo médico que proporciona un ambiente controlado para contribuir a la estabilidad térmica del recién nacido. Su estructura generalmente incorpora una cubierta transparente, sistemas de control ambiental, sensores, mecanismos de calentamiento y alarmas.

El diseño de una incubadora requiere considerar la regulación de la temperatura, la circulación del aire, la seguridad eléctrica y la supervisión de las condiciones interiores.

## 3.2. Termorregulación neonatal

La termorregulación es el proceso mediante el cual el organismo mantiene su temperatura corporal dentro de límites fisiológicos adecuados.

Los recién nacidos, particularmente los prematuros, pueden presentar dificultades para regular su temperatura debido a la inmadurez de sus mecanismos fisiológicos.

Por esta razón, las incubadoras buscan reducir las pérdidas de calor y proporcionar condiciones ambientales controladas.

Para esta práctica, la guía establece un intervalo de funcionamiento del prototipo entre **36 °C y 37,5 °C**.

Este intervalo corresponde al objetivo del montaje académico y no constituye, por sí solo, una prescripción clínica para todos los recién nacidos.

## 3.3. Transferencia de calor por convección

La convección es un mecanismo de transferencia térmica que ocurre mediante el movimiento de un fluido, como el aire.

En el prototipo, el bombillo de 120 W proporciona la fuente de calor y el ventilador favorece el movimiento del aire dentro de la caja.

La combinación de estos elementos busca distribuir el calor en el espacio interior. Sin embargo, para comprobar la uniformidad de la temperatura sería necesario medirla en diferentes posiciones de la cámara.

## 3.4. Termistor

Un termistor es un componente electrónico cuya resistencia eléctrica cambia en función de la temperatura.

Existen dos tipos principales:

- **NTC:** su resistencia disminuye cuando aumenta la temperatura.
- **PTC:** su resistencia aumenta cuando aumenta la temperatura.

En el prototipo se utilizó un termistor para detectar los cambios térmicos del interior de la incubadora.

La variación de resistencia se convierte, mediante el circuito correspondiente, en una señal que permite supervisar la temperatura y determinar el estado indicado por los LED.

## 3.5. Sistema de control de temperatura en lazo cerrado

Un sistema de control en lazo cerrado utiliza la medición de una variable para ajustar la acción de control según la diferencia entre el valor deseado y el valor medido.

En el prototipo, el termistor permite detectar los cambios de temperatura y los circuitos conectados al Arduino participan en el funcionamiento del sistema de control e indicación.

Los tres LED permiten representar los estados previstos:

- **LED rojo:** temperatura inferior al intervalo establecido.
- **LED verde:** temperatura dentro del intervalo establecido.
- **LED rojo:** temperatura superior al intervalo establecido.

## 3.6. Medición de peso mediante un sensor de fuerza

Un sensor de fuerza puede producir cambios eléctricos en respuesta a una carga aplicada.

Para estimar el peso, la señal del sensor debe acondicionarse y relacionarse con masas conocidas mediante un procedimiento de calibración.

La diferencia entre la lectura del sistema y la masa de referencia permite calcular el error de medición.


## 3.7. Partes principales de una incubadora neonatal

| Componente | Función |
|---|---|
| Cubierta transparente | Permite observar el interior y contribuye a limitar el intercambio de aire con el entorno. |
| Estructura o cámara | Contiene el espacio interior del prototipo. |
| Termistor | Detecta cambios de temperatura. |
| Circuito de control | Procesa la señal del sensor y participa en la regulación térmica. |
| Arduino | Plataforma electrónica utilizada para conectar y controlar los circuitos del montaje. |
| Bombillo de 120 W | Proporciona calor al sistema experimental. |
| Ventilador | Favorece la circulación del aire. |
| Indicadores LED | Señalan el estado de temperatura definido por el circuito. |
| Sensor de fuerza | Permite estimar el peso a partir de una carga aplicada. |
| Pantalla o indicador de peso | Permite presentar el valor medido, cuando está conectado e implementado. |
| Fuente de alimentación y protecciones | Suministran energía y contribuyen a reducir los riesgos eléctricos. |

La tabla presenta las funciones generales de los componentes. La presencia y función exactas de cada elemento deben contrastarse con el montaje construido.

# 4. Parte A: Diseño y simulación

## 4.1. Identificación de las partes de una incubadora neonatal

Durante la práctica se identificaron los componentes principales asociados a la estructura, el calentamiento, la circulación del aire, el sensado de temperatura y la medición de peso.

La cubierta transparente permite observar el interior. El termistor se utiliza para detectar cambios térmicos, mientras que el bombillo de 120 W actúa como fuente de calor. El ventilador favorece la circulación del aire y los LED proporcionan una indicación visual del estado de temperatura.

Por otra parte, el sistema de medición de peso utiliza un sensor de fuerza para obtener una lectura que pueda compararse con una masa conocida.

## 4.2. Diseño del circuito de control de temperatura

El objetivo del circuito es supervisar y regular la temperatura del interior del prototipo, tomando como referencia el intervalo de 36 °C a 37,5 °C establecido en la guía.

El sistema construido utiliza un termistor, circuitos electrónicos conectados a un Arduino, un bombillo de 120 W como fuente de calor, un ventilador y tres indicadores LED.

### Funcionamiento general

1. El termistor responde a los cambios de temperatura.
2. El circuito permite obtener una señal relacionada con la temperatura interior.
3. La electrónica conectada al Arduino participa en la supervisión y el control del sistema.
4. El bombillo proporciona calor al interior de la estructura.
5. El ventilador favorece la circulación del aire.
6. Los LED indican el estado térmico establecido por el circuito.



### Resultado experimental

Durante una prueba, se utilizó una masa de referencia de 2.000 g y el sistema mostró una lectura de 1.976 g.

| Parámetro | Valor |
|---|---:|
| Masa de referencia | 2.000 g |
| Lectura del sistema | 1.976 g |
| Error absoluto | 24 g |
| Error porcentual calculado | 1.2 % |


# 5. Parte B: Construcción del prototipo

## 5.1. Montaje experimental

El prototipo se construyó utilizando una caja plástica transparente, componentes electrónicos y un módulo externo para las conexiones.

El montaje incorpora un termistor para la detección de temperatura, un bombillo de 120 W como fuente de calor y un ventilador para favorecer la circulación del aire. Los circuitos se conectaron a un Arduino y se utilizaron indicadores LED para representar el estado térmico del sistema.

La fotografía siguiente documenta el montaje experimental realizado durante la práctica.

![Montaje experimental de la incubadora neonatal a escala](https://github.com/user-attachments/assets/4d715a2e-c951-4c74-8ec3-5810dec4c700)

*Figura 1. Montaje experimental del prototipo de incubadora neonatal a escala.*

La fotografía permite observar la estructura y la disposición general del montaje. No demuestra por sí sola la estabilidad de la temperatura ni la precisión de la medición de peso.

## 5.2. Sistema de calentamiento y circulación del aire

El calentamiento se realizó mediante un bombillo de 120 W. El ventilador se utilizó para favorecer la circulación del aire dentro de la caja y contribuir a distribuir el calor.

El termistor permite detectar los cambios de temperatura y los circuitos conectados al Arduino participan en la supervisión del estado térmico.

El sistema busca aproximarse al intervalo de funcionamiento establecido en la guía, de 36 °C a 37,5 °C.

Debido a que no se dispone de un registro continuo de temperatura ni de mediciones en diferentes puntos de la cámara, no es posible establecer cuantitativamente la uniformidad térmica del prototipo.

**Precaución de seguridad:** un bombillo de 120 W puede generar superficies calientes y riesgos eléctricos. El montaje debe permanecer supervisado, con conexiones aisladas y protecciones apropiadas. No debe utilizarse con personas ni animales.

## 5.3. Procedimiento experimental

El procedimiento documentado a partir de la información disponible comprende las siguientes actividades:

1. Construir la estructura del prototipo utilizando una caja plástica transparente.
2. Instalar los elementos electrónicos necesarios para el monitoreo de temperatura y la medición de peso.
3. Incorporar el termistor al sistema de detección de temperatura.
4. Instalar el bombillo de 120 W como fuente de calor.
5. Incorporar el ventilador para favorecer la circulación del aire.
6. Conectar los circuitos electrónicos al Arduino.
7. Incorporar los LED utilizados para indicar el estado térmico.
8. Poner en funcionamiento el sistema y observar su respuesta térmica.
9. Registrar la temperatura alcanzada y el comportamiento de los indicadores.
10. Realizar una prueba de medición de peso utilizando una masa de referencia conocida.
11. Comparar la lectura del sensor con la masa de referencia.
12. Calcular el error de medición y analizar las limitaciones observadas.

## 5.4. Resultados del control de temperatura

Durante las pruebas, el grupo observó que la temperatura interior variaba durante el funcionamiento y alcanzaba aproximadamente los 37 °C.

También se observó que los LED indicaban el estado de temperatura del sistema.

| Parámetro | Resultado observado |
|---|---|
| Sensor de temperatura | Termistor |
| Plataforma electrónica | Arduino |
| Fuente de calor | Bombillo de 120 W |
| Circulación del aire | Ventilador |
| Temperatura alcanzada | Aproximadamente 37 °C |
| Indicadores visuales | Tres LED para señalar el estado de temperatura |
| Tiempo de estabilización | No registrado |
| Temperatura ambiente | No registrada |
| Registro continuo de temperatura | No disponible |

La temperatura aproximada de 37 °C se encuentra dentro del intervalo de referencia de 36 °C a 37,5 °C.


## 5.5. Resultados de la medición de masa

Durante las pruebas experimentales se utilizó una masa de referencia de 2000 g. El sistema registró una masa medida de 1976 g, lo que corresponde a un error porcentual del 1,2 %.

La diferencia entre la masa de referencia y la masa medida fue de 24 g. Este resultado indica que el sistema presentó un error porcentual del 1,2 % durante esta prueba.


## 5.6. Código y funcionamiento del Arduino

El prototipo utilizó circuitos conectados a un Arduino. Sin embargo, no se dispone del código fuente original.

Por esta razón, no es posible documentar de manera verificable las librerías, los pines, la lógica de programación ni las instrucciones utilizadas durante la prueba.

Para completar esta sección se recomienda recuperar el programa original o reconstruirlo después de identificar las conexiones reales.

Si se desarrolla un programa nuevo, debe identificarse como una nueva implementación y no como el código utilizado originalmente durante la práctica.

# 6. Costos del sistema desarrollado

## 6.1. Costo de los componentes

El prototipo de incubadora neonatal a escala se construyó utilizando una estructura plástica y componentes electrónicos para el monitoreo de temperatura y la medición de peso.

Los siguientes valores corresponden a los precios registrados inicialmente por el grupo y deben verificarse antes de establecer el costo definitivo del proyecto.

| Material o componente | Costo estimado (COP) |
|---|---:|
| Caja plástica | $50.000 |
| Ventilador de 12 V | $9.000 |
| Relé | $30.000 |
| Pantalla OLED | $25.000 |
| Bombillo | $2.000 |
| Termistor | $4.500 |
| Roseta para bombillo | $4.000 |
| Sensor FSR | $28.000 |
| **Subtotal de los componentes registrados** | **$152.500** |

El subtotal se obtiene mediante la suma de los ocho valores registrados:

$50.000 + $9.000 + $30.000 + $25.000 + $2.000 + $4.500 + $4.000 + $28.000 = $152.500 COP.

El montaje utilizó un bombillo de 120 W como fuente de calor. El precio registrado para este componente debe verificarse para confirmar que corresponde al elemento utilizado.

El subtotal tampoco permite confirmar si se incluyeron el Arduino, la fuente de alimentación, los cables, las protecciones eléctricas y todos los demás materiales del montaje.

Por tanto, el valor de $152.500 COP corresponde únicamente a los componentes registrados y no necesariamente al costo total de construcción.

# 7. Comparación con incubadoras neonatales comerciales

Para evaluar económicamente el prototipo, se comparó su costo preliminar con los precios publicados para tres modelos de incubadoras neonatales comercializados en Colombia.

Los precios se consultaron en las páginas de proveedores y deben considerarse referencias comerciales, no cotizaciones definitivas.

## 7.1. Modelos y precios consultados

| Modelo | Proveedor | Precio publicado (COP) | Observaciones |
|---|---|---:|---|
| Incubadora neonatal YP-920 | HeEquiposMédicos | $15.000.000 | El proveedor solicita confirmar el tiempo de entrega. |
| Incubadora neonatal COMEN B3 | IMEDS Colombia | $30.710.000 | Precio publicado sin IVA. |
| Incubadora neonatal YP2000 | Instrumentalia | $53.391.350 | Precio publicado con impuestos incluidos. |

**Fuentes comerciales:**

- YP-920: https://www.heequiposmedicos.com/product-page/incubadora-yp-920
- COMEN B3: https://www.imedscolombia.com/tienda-on-line-1/incubadoras/
- YP2000: https://instrumentalia.com.co/medicina/61297-incubadora-yp2000.html

Los precios corresponden a los publicados por cada proveedor en sus respectivas páginas.

## 7.2. Comparación técnica y económica

| Característica | Prototipo académico | YP-920 | COMEN B3 | YP2000 |
|---|---|---|---|---|
| Precio de referencia | $152.500 COP de subtotal registrado | $15.000.000 COP | $30.710.000 COP, sin IVA | $53.391.350 COP, con impuestos |
| Estructura | Caja plástica transparente | Incubadora neonatal cerrada | Incubadora neonatal cerrada | Incubadora neonatal cerrada |
| Control de temperatura | Termistor y circuitos conectados a Arduino | Control electrónico mediante microcomputador, según proveedor | Sistema de control de temperatura, según proveedor | Modos de control de temperatura del aire y del bebé, según ficha comercial |
| Fuente de calor | Bombillo de 120 W | Sistema propio del equipo | Sistema de calentamiento del equipo | Sistema propio del equipo |
| Circulación del aire | Ventilador | Sistema integrado de circulación | Diseño de conductos para distribuir el aire | Sistema de circulación de aire de doble cabina |
| Indicadores | Tres LED | Sistema de alarmas y control | Pantalla interactiva | Pantalla LCD y alarmas |
| Medición de peso | Sensor de fuerza | Debe verificarse en la configuración ofertada | Balanza opcional, según proveedor | Capacidad de pesaje indicada de 100 a 8.000 g |
| Validación clínica | No validado para uso clínico | Equipo comercial; verificar documentación aplicable | Equipo comercial; verificar documentación aplicable | Equipo comercial; verificar documentación aplicable |

**Fuentes de las características:**

- YP-920: https://www.heequiposmedicos.com/product-page/incubadora-yp-920
- COMEN B3: https://www.imedscolombia.com/tienda-on-line-1/incubadoras/
- YP2000: https://instrumentalia.com.co/medicina/61297-incubadora-yp2000.html

Las características se resumen a partir de la información comercial publicada. La configuración exacta puede variar y debe confirmarse mediante las fichas técnicas y las cotizaciones de los proveedores.

## 7.3. Análisis económico

El subtotal preliminar del prototipo es de $152.500 COP, mientras que los precios publicados para las incubadoras comerciales consultadas son de $15.000.000 COP, $30.710.000 COP antes de IVA y $53.391.350 COP con impuestos incluidos, respectivamente.

Esta diferencia refleja que el prototipo es un modelo académico de bajo costo, mientras que las incubadoras comerciales están diseñadas para aplicaciones clínicas y pueden incorporar sistemas de control, alarmas, monitorización, mecanismos de seguridad y otras prestaciones que no se han implementado ni validado en el proyecto.

La comparación económica es orientativa: el subtotal del prototipo no representa necesariamente su costo total, y los precios comerciales no se encuentran expresados bajo las mismas condiciones tributarias.

Por tanto, no es correcto concluir que el prototipo puede sustituir a una incubadora comercial únicamente por su menor costo o por alcanzar una temperatura cercana a 37 °C.

# 8. Análisis de resultados

## 8.1. Control de temperatura

Durante las pruebas del prototipo, el grupo observó que la temperatura variaba durante el funcionamiento y alcanzaba aproximadamente los 37 °C.

El sistema utilizó un termistor para detectar cambios de temperatura, un bombillo de 120 W como fuente de calor, un ventilador para favorecer la circulación del aire y circuitos conectados a un Arduino. Los indicadores LED permitían identificar el estado de temperatura definido por el circuito.

La temperatura observada se encuentra dentro del intervalo de referencia de 36 °C a 37,5 °C establecido para la práctica. Sin embargo, al no contar con un registro de temperatura frente al tiempo, no es posible determinar cuantitativamente la estabilidad del sistema ni confirmar cuánto tiempo permaneció dentro del intervalo.

Para evaluar su funcionamiento de manera más completa, se requieren mediciones periódicas, registro de la temperatura ambiente y observación del comportamiento de los indicadores durante el ensayo.

## 8.2. Error en la medición de peso

El grupo reportó una lectura de 1.900 g durante una prueba relacionada con una masa de 2 kg y señaló un error aproximado del 1,2 %.

Para documentar correctamente el resultado, es necesario distinguir el porcentaje reportado por el grupo del cálculo que se obtiene al considerar los 2.000 g como masa de referencia.

Si la masa de referencia es de 2.000 g y la lectura del sistema es de 1.900 g, el error absoluto es:

\[
E_{\mathrm{abs}}=|1900-2000|=100\text{ g}
\]

El error porcentual correspondiente es:

\[
E_{\%}=\frac{|1900-2000|}{2000}\times100=5\%
\]

Por consiguiente, esos dos valores corresponden a un error del 5 %.

El grupo también reportó un error aproximado del 1,2 %. Este valor puede incluirse como resultado de una calibración o medición diferente si existe un registro experimental que lo respalde. No debe presentarse como el resultado matemático de la lectura de 1.900 g frente a una referencia de 2.000 g.

Para determinar el error de manera verificable, se recomienda repetir la prueba con masas de referencia conocidas, registrar las lecturas obtenidas y calcular el error absoluto y porcentual para cada medición.

## 8.3. Limitaciones del proyecto

Las principales limitaciones documentales y experimentales son:

- No se dispone del código fuente original del Arduino.
- No se cuenta con los diagramas eléctricos originales.
- No se dispone de una serie de mediciones de temperatura frente al tiempo.
- Se requiere verificar el resultado del error del 1,2 % y su relación con la lectura registrada.
- Es necesario completar la calibración del sensor de fuerza con varias masas conocidas.
- Los costos del prototipo deben verificarse y consolidarse.
- Los precios comerciales deben confirmarse con los proveedores.
- El prototipo no está validado para uso clínico.

Estas limitaciones deben considerarse al interpretar los resultados y al comparar el proyecto con equipos comerciales.

# 9. Preguntas para la discusión

## Pregunta 1. ¿Qué otras variables, además de la temperatura y el peso, son críticas en el monitoreo neonatal?

Además de la temperatura y el peso, existen otras variables importantes para el monitoreo neonatal.

La frecuencia cardíaca permite evaluar el funcionamiento del sistema cardiovascular, mientras que la frecuencia respiratoria aporta información sobre el patrón respiratorio. La saturación de oxígeno permite evaluar la oxigenación de la sangre.

La humedad relativa también es importante en el control del microambiente, ya que influye en las pérdidas de agua y calor a través de la piel, especialmente en los recién nacidos prematuros.

Dependiendo de las necesidades clínicas, también pueden ser relevantes la presión arterial y otros indicadores fisiológicos.

El monitoreo de estas variables permite identificar cambios en el estado del paciente y facilita la intervención del personal de salud. El prototipo desarrollado no mide todas estas variables.

## Pregunta 2. ¿Qué haría falta para convertir el sistema desarrollado en una incubadora neonatal real?

Para convertir el prototipo en una incubadora neonatal apta para uso clínico sería necesario realizar un proceso de diseño, validación y evaluación de riesgos mucho más amplio.

Entre los aspectos que se deberían desarrollar se encuentran:

- Sensores de temperatura adecuados y calibrados.
- Un sistema de control térmico con precisión y estabilidad verificadas.
- Protección independiente frente a sobretemperatura.
- Alarmas ante fallas del sensor, pérdida de alimentación o condiciones anormales.
- Distribución uniforme del aire y evaluación de la temperatura en distintos puntos.
- Control de humedad cuando corresponda.
- Sistemas de alimentación eléctrica y protecciones apropiadas.
- Validación de la medición de peso, si se incorpora esta función.
- Pruebas de seguridad eléctrica y mecánica.
- Gestión de riesgos y documentación técnica.
- Evaluación de los requisitos regulatorios aplicables a los dispositivos médicos en Colombia.

También sería necesario verificar el cumplimiento de las normas técnicas aplicables y los requisitos establecidos por las autoridades competentes.

Por tanto, el prototipo construido debe considerarse un modelo académico y no un equipo apto para la atención de recién nacidos.

## Pregunta 3. ¿Qué semejanzas hay entre una incubadora neonatal y una servo-cuna?

Ambos dispositivos se utilizan para apoyar el control térmico del recién nacido.

La incubadora neonatal suele contar con una cubierta que permite crear un microambiente más cerrado y controlado. Por su parte, la servo-cuna o cuna de calor radiante suele tener una estructura abierta y proporciona calor mediante una fuente situada sobre el paciente.

La estructura abierta de la servo-cuna facilita el acceso directo para procedimientos médicos y cuidados asistenciales, mientras que la incubadora permite controlar un ambiente interior más cerrado.

Ambos equipos requieren una supervisión adecuada de la temperatura y mecanismos de seguridad acordes con su aplicación clínica.

# 10. Conclusiones

Se construyó un prototipo académico de incubadora neonatal a escala que integra una estructura transparente, un termistor, un bombillo de 120 W, un ventilador, circuitos conectados a un Arduino y tres indicadores LED para señalar el estado de temperatura.

Durante las pruebas, la temperatura interior alcanzó aproximadamente 37 °C, valor que se encuentra dentro del intervalo objetivo de 36 °C a 37,5 °C establecido en la guía. Sin embargo, al no contar con registros de temperatura frente al tiempo, no es posible determinar cuantitativamente la estabilidad del sistema ni confirmar cuánto tiempo permaneció dentro del intervalo.

En la prueba de medición de peso, una masa de referencia de 2.000 g produjo una lectura de 1.976 g. La diferencia de 24 g corresponde a un error porcentual del 1.2 %. Este resultado evidencia la necesidad de realizar una calibración con varias masas conocidas y repetir las mediciones para evaluar el comportamiento del sensor.

La práctica permitió aplicar conceptos de instrumentación biomédica, sensado, calentamiento, circulación del aire y control electrónico. También permitió identificar las limitaciones de un prototipo académico frente a un equipo médico comercial.

Para completar la evaluación del proyecto se requiere recuperar o reconstruir los diagramas eléctricos, documentar el funcionamiento del Arduino, obtener mediciones experimentales adicionales y verificar el costo total de los componentes.

Finalmente, el prototipo no está validado para uso clínico y no debe utilizarse con recién nacidos ni pacientes.

# 11. Bibliografía

1. Tran, C. G. K., Gibson, A., Wong, D., Tilahun, D., Selock, N., Good, T., et al. (2014). Designing a low-cost multifunctional infant incubator. *Journal of Laboratory Automation, 19*(3), 332–337. https://doi.org/10.1177/2211068214530391

2. Restrepo-Pérez, L., Durango-Londoño, N., Gómez-Suárez, N. E., González-Ramírez, F., & Rivera-Bonilla, N. (2007). Prototipo de incubadora neonatal. *Revista Ingeniería Biomédica, 1*(1), 55–59. http://www.scielo.org.co/pdf/rinbi/v1n1/v1n1a12.pdf

3. van Leeuwen, M., Frauenfelder, O., Oude-Reimer, M., Camba, F., Ceccatelli, M., Hankes-Drielsma, I., et al. (2018). *European Standards of Care for Newborn Health: Temperature management in newborn infants*. European Foundation for the Care of Newborn Infants.

4. Knobel-Dail, R. B. (2014). Role of effective thermoregulation in premature neonates. *Research and Reports in Neonatology, 4*, 147–156. https://doi.org/10.2147/RRN.S52377

5. Latif, A., Widodo, H. A., Atmoko, R. A., Phong, T. N., & Helmy, E. T. (2021). Temperature and humidity controlling system for baby incubator. *Journal of Robotics and Control, 2*(3), 190–193. **Verificar los datos bibliográficos antes de la entrega.**

6. Mittal, H., Mathew, L., & Gupta, A. (2015). Design and development of an infant incubator for controlling multiple parameters. **Verificar los datos completos de publicación.**

7. Subramanian, M., Sheela, T., Srividya, K., & Arulselvam, D. (2019). Security and health monitoring system of the baby in incubator. **Verificar los datos completos de publicación.**

8. Universidad Militar Nueva Granada. (2025). *Guía de preparación de práctica de laboratorio: Diseño y construcción de una incubadora neonatal a escala*. Laboratorio de Instrumentación Biomédica y Biosensores.

---
