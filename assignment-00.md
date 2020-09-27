# ASSIGNMENT 00: Procedimientos

En este _assignment_ te describimos los procedimientos para el
desarrollo de la docencia interactiva en la asignatura de Interfaces
Persona Máquina (IPM).


## Uso del sentido común

* Dentro de los objetivos de cada assignment está estipulado el tiempo
  necesario para su realización. Un período habitual son cuatro
  semanas.  También, cada assignment está dividido en cometidos
  (_tasks_). Si, por ejemplo, un assignment se divie en 6 tasks y
  dispones de 4 semanas, 6/4 = ... ¿ En serio necesitas que siga ?
  
* Todo el trabajo en cada uno de los assignments tiene que estar bajo
  un control de versiones. El control de versiones es una herramienta
  muy poderosa que aporta muchos beneficios en el desarrollo de
  software, y su uso es una norma común hoy en día en la industria del
  software. Úsalo y aprovéchate de sus ventajas.
  
* En general la evaluación continua es preferible a la evaluación
  única.  La evaluación continua, como su propio nombre indica, evalúa
  un trabajo realizado de forma continua.  Para que el trabajo
  relamente sea continuo, siguiendo al definición de la RAE, tiene que
  extenderse sin interrupción entre el primer día del cuatrimestre y
  el último día.
  
  La realización de dicho trabajo se puede apreciar en la observación
  de distintos indicadores, siendo los principales:

  - Commits en el repositorio de referencia de cada uno de los
    assignments.
  - Corrección de issues en el repostorio de referencia de cada uno de
    los assignments.
  - Participación en el foro de prácticas de la asignatura.
  - Participación en el desarrollo de las herramientas y recursos
    empleados en las prácticas de la asignatura.


## Trabajo en equipo

El trabajo en equipo es una habilidad clave para un/a graduado/a en
ingeniería informática. Todos los assignments se debe realizar en
grupos de dos personas. No intentes escaquearte y hacer el trabajo por
tu cuenta.

> N.B. Dada la situación especial de este curso (2020/2021) es
> previsible que tengas que usar más que nunca las herramientas de IT
> que te permitan trabajar online con tu compañera/o. No pasa nada, el
> dominio de esas herramientas y esa forma de trabajo también es una
> habilidad muy valiosa.


## Control de versiones

El control de versiones establecido para todos los assignments es
[git](https://git-scm.com/).

En teoría ya conoces el funcionamiento básico de un control de
versiones: confirmar una versión, ver el historial de versiones,
cambiar a una versión concreta, replicar un repositorio, ...  Además
del funcionamiento básico, para que puedas sacarle todo el rendimiento
y que te ayude en la realización de los assignments, también tienes
que conocer: manejo de etiquetas, trabajo con repositorios remotos,
y manejo de ramas (_branches_).

Existen multitud de recursos online para aprender el uso de las
funcionalidades de _git_ que acabamos de enumerar. Si no sabes por
donde empezar, prueba con este libro: [Git
Succinctly](https://www.syncfusion.com/ebooks/confirmation/git)


## Repositorios

Si has hecho caso a la sección anterior, ya sabrás que una
características muy interesante de _git_ es que usa un modelo de
repositorios distribuidos. Durante la realización de los assignments
no tienes ninguna restricción sobre el número de repositorios que vas
a usar, ni la localización de los mismos.

Sin embargo, el seguimiento y la valoración de tu trabajo se tiene que
realizar sobre un único repositorio. Este repositorio no lo eliges tú,
está especificado en la descripción de cada assignment. En general
será un repositorio accesible online a traves de un servicio de
gestión de repositorios como, por ejemplo, _GitHub_.

Este repositorio es el repositorio de referencia para las prácticas de
la asignatura, tienes acceso tanto tú como el profesor que valora tu
trabajo. El profesor valorará **única y exclusivamente** el contenido
de dicho repositorio.

> Recuerda: lo que no está en el repositorio de referencia, no existe
> para el profesor.

> Recuerda: un trabajo continuo se refleja en _commits_ y _push_
> continuos.


## Notificaciones del repositorio

Para que el profesor reciba una notificación cada vez que haces un push,
debes configurar tu repositorio de Github.

En la interface del repositorio en: Setting > Notifications > Address,
debes introducir el email del profesor que va a evaluar tu práctica.


## Servicio de repositorios: issues

Los servicios de gestión de repositorios (_Github_, _GitLab_,
_Bitbucket_, etc) además del propio hosting de los repositorios, nos
ofrecen otros servicios relacionados: feature request, bug tracking,
wikis, continuous integration/development, ...

De todos estos servicios vamos a usar el bug/issue tracking. El bug
tracking también es una herramienta habitual en el desarrollo de
software. Aunque a estas alturas de la carrera, no te estoy contando
nada que no sepas.

El profesor que realiza el seguimiento y valoración de tu trabajo
usará este servicio, creando un _issue_ por cada defecto que tengas
que corregir en la práctica.

> Recuerda: cuanto antes hagas un push al repositorio de referencia,
> antes podrá el profesor indicarte las correcciones necesarias, si es
> el caso.


## Uso de ramas

El uso de ramas (_branches_) es habitual en el desarrollo de
sw. Durante el desarrollo de los assignments también te puedes
beneficiar de su uso. En concreto, el escenario más probable en que te
podrán ser de utilidad, es en el caso que tengas issues abiertos.

Por ejemplo, en el siguiente escenario, has terminado de desarrollar
el primer cometido (_task_) del assignment. Las `O` representan las
versiones (_commits_) que contiene el respositorio y `task_1` es la
etiqueta asocida al último commit del cometido: `task_1`. Los commmits
posteriores se corresponden con el trabajo en el siguiente cometido:
`task_2`.


```
 O -- O -- O -- O -- O
           |
           \_ task_1

```

Si en este momento el profesor abre un _issue_ para la `task_1`,
tienes que hacer las correcciones oportunas. Pero esas correcciones
deberían estar incorporadas a la `task_1` sin mezclarse con el trabajo
de la `task_2` y, en este caso, una única rama de desarrollo no
permite esto.

El uso de varias ramas de desarrollo te puede facilitar el trabajo,
por ejemplo:

* Puedes crear una rama a partir de la última versión de la `task_1` y
  corregir el issue.
  
  ```
            /- O -- O -- O branch fix issue
            | 
  O -- O -- O -- O -- O
           |
           \_ task_1

  ```
  
  Una vez corregido el issue puedes cambiar la etiqueta e incorporar los cambios
  a la rama de desarrollo donde estás trabajando en la `task_2`.

  
  ```
                         /- task_1
                         |
            /- O -- O -- O branch fix issue
            |            |
  O -- O -- O            X -- O -- O

  ```
  O bien:

  ```
                         /- task_1
                         |
            /-- O -- O -- O branch fix issue
            |              \
  O -- O -- O -- O -- O -- X

  ```

* También, en previsión de que pueda ocurrir esta situación, en el
  momento de terminar la `task_1`, puedes continuar el desarrollo de la
  `task_2` en una nueva rama.
  
  ```
            /- O -- O -- O branch task 2
            |
  O -- O -- O
            |
            \_ task_1

  ```
  
  Si tienes que realizar correcciones sobre la task 1, una vez realizadas, puedes
  hacer un `merge` hacia la rama de la task 2 para incorporar las correcciones.
  
  ```
            /- O -- O -- O -- X           branch task 2
            |    _____________|
            |    |
  O -- O -- O -- O
                 |
                 \_ task_1

  ```

* etc.

Como puedes ver hemos planteado unas posibilidades, pero no son las
únicas. Sea cual sea la opción que escojas, lo importante en que, una
vez terminada una `task_n`, puedas continuar trabajando en la siguiente
sin que ello te impida realizar más tarde correcciones sobre la `task_n`
sin incluir el trabajo de la `task_n+1`.


## Penalizaciones

La valoración de las prácticas se basa tanto en la calidad del trabajo
realizado, como en la capacidad para realizarlo en el plazo
establecido. Esto significa que, en caso de no cumplir los plazos, la
valoración final se verá penalizada. El criterio es el siguiente:

  * **Sobresaliente**. Las prácticas que se valoren con un
    sobresaliente, es decir una nota numérica en el intervalo [9,10],
    tiene que haber sido entregadas dentro del plazo.
  
  * **Notable**. Una práctica se puede valorar con un notable, nota
    numérica en el intervalo [7,9), aunque tenga un retraso en la
    entrega no superior a una semana.
  
  * **Aprobado**. Una práctica se puede valorar con un aprobado, nota
    numérica en el intervalo [5,7), independientemente del retraso en
    la entrega.
  
  
A mayores de la penalización por entrega fuera de plazo, existe otra
penalización más estricta por no realizar el trabajo en equipo. Si la
práctica ha sido realizada por una única persona la nota númerica
tendrá  que estar en el intervalo [0,6).
