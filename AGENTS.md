# Guía para agentes: apuntes de Cálculo Multivariable

## Propósito y alcance

Este repositorio contiene apuntes en español de Cálculo Multivariable. El
resultado debe ser un material autocontenido, matemáticamente correcto y útil
para estudiantes con conocimientos sólidos de álgebra y Cálculo de una
variable.

Antes de modificar un tema, se debe leer su archivo principal y los ejercicios
adyacentes para conservar la notación, el orden pedagógico y el nivel de detalle
del tema.

## Estructura del repositorio

- `main.tex` es el documento raíz. Declara la clase, los paquetes, las cajas
  `mydefinition`, `mytheorem` y `mynote`, y reúne los temas con `\include`.
- `unidad1/`, `unidad2/` y `unidad3/` agrupan los temas de cada unidad. `extra/`
  contiene material complementario.
- Cada tema se escribe en un archivo `.tex` propio y normalmente inicia con
  `\section{...}`. Sus apartados usan `\subsection{...}` y, cuando hace falta,
  `\subsubsection{...}`.
- Los ejercicios de un tema viven en una carpeta temática, normalmente
  `unidadN/ejercicios/<tema>/` o `extra/ejercicios/<tema>/`. La sección final
  `\subsection{Ejercicios}` los enumera mediante `\input{ruta/exN.tex}`.
- No se modifican archivos generados (`main.pdf`, `.aux`, `.log`, `.toc`,
  `.out`, `.fls`, `.fdb_latexmk` ni `.synctex.gz`).

## Redacción

- Todo el contenido nuevo o reescrito se redacta en español y en tercera
  persona. Se prefieren construcciones como «se tiene», «se define», «el campo
  satisface» y «la figura muestra»; se evitan la primera persona y las órdenes
  dirigidas al lector, como «calculemos», «veamos» o «observa».
- La prosa debe ser precisa, directa y sobria. Los adjetivos se usan únicamente
  cuando aportan una distinción matemática necesaria; se evita intensificarlos
  o acumularlos.
- No se usan negritas ni cursivas como recurso de énfasis en el texto nuevo.
  Los nombres de secciones, los títulos de las cajas y la notación matemática
  ya proporcionan jerarquía visual. No se añaden `\textbf{}`, `\textit{}` ni
  `\emph{}` para resaltar prosa.
- Cada concepto se presenta, cuando corresponda, con definición, interpretación
  o motivación breve, ejemplo desarrollado y ejercicios. Las afirmaciones deben
  indicar sus hipótesis y el dominio pertinente.
- Se conserva la terminología y la notación ya empleadas en el tema. Por
  ejemplo, los campos vectoriales se escriben con `\mathbf{F}` y vectores con
  componentes entre `\langle\,\rangle` cuando ese sea el estilo local.

## Matemáticas y LaTeX

- Se usan las cajas existentes para definiciones, teoremas y notas:
  `\begin{mydefinition}{Título}`, `\begin{mytheorem}{Título}` y
  `\begin{mynote}{Título}`. No se duplican sus definiciones en archivos de
  tema.
- Las expresiones importantes van en entornos de visualización `\[ ... \]` o
  `equation` cuando requieran etiqueta. Las ecuaciones se alinean con `align*`
  cuando haya varios pasos; no se abusa de `$$ ... $$`.
- Se muestran los pasos que justifican un cálculo no inmediato, sin convertir
  operaciones rutinarias en una lista excesiva de igualdades.
- Las demostraciones deben ser completas al nivel de los apuntes: se declaran
  hipótesis, se usa una cadena de razonamiento verificable y se señala la
  conclusión. No se invocan resultados fuera del temario sin enunciarlos o
  justificarlos.
- Las figuras se hacen con los paquetes ya disponibles, especialmente TikZ y
  PGFPlots. Cada figura debe aclarar una idea matemática; se incluyen ejes,
  etiquetas y dominio cuando sean necesarios para interpretarla.
- Si se incorpora un tema nuevo, se añade su `\include{...}` a `main.tex` en la
  posición pedagógica apropiada. Si se añade un ejercicio, también se añade su
  `\input{...}` a la lista del tema, respetando el orden numérico.

## Ejercicios

- Cada ejercicio se guarda en un archivo independiente llamado exactamente
  `ex1.tex`, `ex2.tex`, `ex3.tex`, etc. El siguiente número se determina a
  partir del mayor `exN.tex` existente en la carpeta temática; no se renumeran
  archivos ya referenciados.
- Un archivo de ejercicio contiene sólo el enunciado y, si aporta comprensión,
  una figura local de TikZ. El contenedor del tema proporciona el `\item` y la
  numeración de la lista.
- Los ejercicios se ordenan de menor a mayor dificultad. La secuencia habitual
  comienza con reconocimiento, evaluación o aplicación directa; continúa con
  cálculos que combinan técnicas; y termina con interpretación, generalización
  o demostración.
- Los ejercicios de demostración son habituales, en especial hacia el final de
  cada serie. Deben poder resolverse usando únicamente los contenidos ya
  presentados en los apuntes, álgebra sólida y Cálculo de una variable. No deben
  depender de teoría posterior, trucos no motivados ni herramientas externas.
- Los enunciados son directos y no desglosan el procedimiento de resolución en
  instrucciones extensas. Una pista breve puede incluirse solo cuando sea
  necesaria para orientar un ejercicio que, de otro modo, quedaría fuera del
  alcance de los contenidos presentados.
- Los incisos deben ser independientes cuando sea posible. Si son consecutivos,
  el enunciado debe hacer explícita la dependencia y guiar hacia la conclusión
  sin resolverla.

## Verificación

- Antes de terminar, se revisan rutas de `\include` y `\input`, llaves y
  entornos, consistencia de la notación, acentos y redacción en tercera persona.
- Tras cambios de contenido, se compila el documento raíz desde la raíz del
  repositorio con `latexmk -pdf main.tex` cuando la herramienta esté disponible.
  Se corrigen los errores introducidos y se revisan las advertencias relevantes,
  en particular referencias o archivos incluidos que no existan.
- Se preservan las modificaciones ajenas ya presentes en el árbol de trabajo.
