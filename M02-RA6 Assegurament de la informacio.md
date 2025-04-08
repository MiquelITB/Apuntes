# Apuntes UF3 - Gestió de BD

### Introducción

*   Las bases de datos son fundamentales para las organizaciones, requiriendo una planificación cuidadosa en cuanto a seguridad de la información.
*   La información debe ser **confidencial**, **íntegra** y **disponible**.
*   La protección legal de los datos, especialmente los de carácter personal, es crucial debido a su valor y las amenazas existentes.
*   Se deben implementar soluciones para amenazas intencionadas o accidentales, incluyendo copias de seguridad y procedimientos de recuperación.
*   La transferencia de datos entre diferentes bases de datos y ubicaciones es un aspecto importante en la gestión de bases de datos.

### Seguridad de la Información

*   La información es un activo valioso en la sociedad actual, y su seguridad es primordial.
*   Es esencial garantizar el derecho a la privacidad y la protección de los datos personales.
*   Los principios clave de la seguridad de la información son **confidencialidad**, **integridad** y **disponibilidad**.
*   La **confidencialidad** asegura que solo las personas autorizadas puedan acceder a los datos.
*   La **integridad** garantiza que los datos no han sido alterados y mantienen su coherencia.
*   La **disponibilidad** asegura que los datos y servicios estén accesibles cuando se necesiten.

### Normativa Legal Vigente

*   La protección de datos personales requiere una normativa legal específica debido a los avances en las tecnologías de la información.
*   La **Constitución de 1978** establece el marco legal para la protección de la intimidad y los derechos personales.
*   La **LORTAD** (Ley Orgánica 5/92) fue la primera ley que reguló específicamente el tratamiento automatizado de datos personales.
*   La **Directiva europea 95/46 CE** regula la protección de las personas físicas en el tratamiento de datos personales dentro de la Unión Europea.
*   La **Llei d’accés electrònic dels ciutadans als serveis públics (LAECSP)** obliga a las administraciones públicas a hacer accesibles sus servicios por medios electrónicos.
*   La **Llei 29/2009** modifica el régimen legal de la competencia desleal y de la publicidad para proteger a los consumidores del acoso publicitario.
*   La **Llei de protecció de dades de caràcter personal** (LOPD) establece los derechos y principios para la protección de datos personales.

### Agència de Protecció de Dades

*   La **Agència de Protecció de Dades** se creó para velar por el cumplimiento de las leyes orgánicas relacionadas con la protección de datos.
*   Sus funciones incluyen ofrecer ayuda a las organizaciones, ejercer la potestad sancionadora, emitir autorizaciones, requerir medidas de corrección y proteger los derechos de las personas afectadas.
*   El **Registre General de Protecció de Dades** es un órgano de la Agència encargado de controlar la publicidad de la existencia de ficheros y la gestión de datos de carácter personal.

### Amenazas a la Seguridad

*   Las amenazas a la seguridad de las bases de datos pueden ser accidentales o intencionadas.
*   Las **amenazas accidentales** incluyen errores humanos, fallos del sistema, falta de copias de seguridad y contraseñas no seguras.
*   Las **amenazas intencionadas** son más peligrosas e incluyen el acceso no autorizado, el malware y los ataques a la infraestructura.

### Salvaguarda, Recuperación y Transferencia

*   Es fundamental proteger las bases de datos para evitar la pérdida de información.
*   La **salvaguarda** implica la creación de copias de seguridad y la implementación de medidas de protección.
*   La **recuperación** es el proceso de restaurar la base de datos a partir de una copia de seguridad.
*   La **transferencia de datos** es necesaria para la comunicación entre diferentes bases de datos y ubicaciones.
*   Existen diversas utilidades para importar y exportar datos entre sistemas.

# Apuntes Tipos de Amenazas Informáticas

## 1. Virus Informático

*   **Definición:** Programa que se copia automáticamente y altera el funcionamiento normal de la computadora sin permiso del usuario.
*   **Funcionamiento:** Se ejecuta un programa infectado, el virus se aloja en la RAM y toma el control de servicios del sistema operativo, infectando otros archivos ejecutables.
*   **Daños:**
    *   Pérdida de productividad.
    *   Cortes en los sistemas de información.
    *   Daños a los datos.
    *   Consumo de recursos.
*   **Formas de contagio:**
    *   Red (gusanos).
    *   Ejecución de archivos infectados (e-mails, descargas).
*   **Formas de combatirlos:**
    *   Antivirus (avast!, nod32, kaspersky, bitdefender, etc.).

## 2. Gusanos (Worms)

*   **Definición:** Virus que se duplica a sí mismo, utilizando las partes automáticas del sistema operativo.
*   **Diferencia con virus:** No altera archivos de programas, reside en la memoria y se duplica.
*   **Daños:**
    *   Consumo de recursos del sistema.
    *   Lentitud en las tareas ordinarias.
    *   Consumo de ancho de banda en la red.
*   **Formas de combatirlos:**
    *   Antivirus actualizados.

## 3. Spywares (Programas espías)

*   **Definición:** Aplicaciones que recopilan información sobre una persona u organización sin su conocimiento.
*   **Función:** Recopilar información del usuario y distribuirla a terceros.
*   **Daños:**
    *   Robo de información.
    *   Páginas emergentes (pueden descargar virus).
    *   Consumo de ancho de banda.
    *   Apagado del computador sin aviso.
*   **Formas de combatirlos:**
    *   Anti-spyware (spyware-serch & destroy, spyware doctor, SUPERAntispyware, etc.).

## 4. Caballos de Troya (Troyanos)

*   **Definición:** Programa malicioso que se aloja en computadoras y permite el acceso a usuarios externos para robar información o controlar la máquina remotamente.
*   **Diferencia con virus:** No es un virus en sí, su finalidad es acceder y controlar la máquina sin ser advertido.
*   **Funcionamiento:** Se instala dentro de una aplicación o archivo de apariencia inocente.
*   **Daños:**
    *   Infectar archivos.
    *   Subir y bajar archivos infecciosos.
    *   Puerta de enlace para virus.
    *   Control remoto del computador.
    *   Alteraciones en el hardware.
    *   Robo de información (como spyware).
    *   Auto-ejecutar virus.
    *   Reiniciar o apagar el equipo.
*   **Formas de combatirlos:**
    *   Antivirus actualizados.
    *   Borrado manual del registro (regedit).
    *   Evitar programas P2P.

## 5. Hacker

*   **Definición:** Informático capacitado que entra en una computadora sin autorización para robar información o causar daño.
*   **Daños:**
    *   Dependen de las intenciones del hacker, pueden ser desde leves hasta irreparables.
    *   Destrucción total del computador.
*   **Formas de combatirlos:**
    *   No entrar a páginas de dudosa procedencia.
    *   No revelar datos por medios no confiables.
    *   Contratar a otro hacker (de confianza).

# Derechos de Protección de Datos

Este documento describe los derechos que tienen las personas en relación con la protección de sus datos personales. Estos derechos están diseñados para garantizar que las personas tengan control sobre cómo se recopila, utiliza y comparte su información personal.

## Derechos Principales

* **Derecho de acceso**: El derecho a obtener confirmación de si se están tratando datos personales que le conciernen y, en tal caso, derecho de acceso a los datos personales.
* **Derecho de rectificación**: El derecho a obtener sin dilación indebida del responsable del tratamiento la rectificación de los datos personales inexactos que le conciernan.
* **Derecho de supresión (derecho al olvido)**: El derecho a obtener sin dilación indebida del responsable del tratamiento la supresión de los datos personales que le conciernan.
* **Derecho a la limitación del tratamiento**: El derecho a obtener del responsable del tratamiento la limitación del tratamiento de los datos cuando se cumpla alguna de las condiciones establecidas en el Reglamento General de Protección de Datos (RGPD).
* **Derecho a la portabilidad de los datos**: El derecho a recibir los datos personales que le incumban, que haya facilitado a un responsable del tratamiento, en un formato estructurado, de uso común y lectura mecánica, y a transmitirlos a otro responsable del tratamiento sin que lo impida el responsable al que se los haya facilitado.
* **Derecho de oposición**: El derecho a oponerse en cualquier momento, por motivos relacionados con su situación particular, a que datos personales que le conciernan sean objeto de un tratamiento basado en el interés legítimo del responsable o de un tercero, incluida la elaboración de perfiles.
* **Derecho a no ser objeto de decisiones individuales automatizadas, incluida la elaboración de perfiles**: El derecho a no ser objeto de una decisión basada únicamente en el tratamiento automatizado, incluida la elaboración de perfiles, que produzca efectos jurídicos en él o le afecte significativamente de modo similar.

## Ejercicio de los Derechos

* Los interesados pueden ejercer sus derechos dirigiéndose al responsable del tratamiento.
* La solicitud puede realizarse por diversos medios, incluyendo formularios electrónicos y correo postal.
* El responsable del tratamiento está obligado a responder a las solicitudes en un plazo máximo de un mes, que puede prorrogarse en determinados casos.

## Información Adicional

* El documento también proporciona información sobre la Agencia Española de Protección de Datos (AEPD), que es la autoridad de control en España en materia de protección de datos.
* Se incluyen enlaces a recursos útiles, como formularios para el ejercicio de derechos y guías informativas.

