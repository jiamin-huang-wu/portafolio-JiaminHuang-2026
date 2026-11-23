# portafolio-JiaminHuang-2026
Bitácora personal Jiamin Huang Wu

Link figma: https://www.figma.com/design/w3IqzMvd3vXOxj6ED0D6jI/Jiamin-Huang-Wu?node-id=1-2&p=f&t=4nY8rjVMRzYt9IUD-0


Descripción: 
Creación de portafolio mediante figma y vscode para generar una página web, recopilando los proyectos realizados a lo largo de la trayectoria de mi carrera, rescatando 4 de los trabajos que considero destacables.

recursos:
Figma
Material entregado en clase
claude
vscode

Páginas de referencia:
https://share.google/3M4waMMZXycU20kXO  - Tomé de referencia e inspiración los colores pasteles, lo minimalista de la página y simpleza para lograr mostrar productos.

https://share.google/zPusJ8i05wNpwVmqI: Rescate los recursos visuales, el uso simple de las imágenes, muestra lo que interesa ver sin tanto preámbulo.

https://www.behance.net/gallery/224698099/Graphic-Design-Portfolio-2025?tracking_source=search_projects|portafolio+2025&l=6: Me interesa cómo utiliza hojas para disponer la información.

Proceso:
Se utilizó figma para crear el diseño de la página para tener una visualización de la página antes de programarla, primero se realizó un boceto y wireframes de baja fidelidad, luego a la de media modificando hasta llegar a la definitiva. 
           Se definieron la paleta de color, la tipografía y los botones de navegación.

Una vez listo el diseño de figma se trabajó en el código HTML con apoyo del material de clases y ayuda de la IA con cosas que me costaron y que no tenía conocimiento.
Con ayuda de claude pude crear el código CSS para que cuadren los espacios y disposición de las imágenes como los botones.

Correcciones:

Mejorar la redacción de la bitácora y extenderla para entender y explicar mejor el trabajo hecho.
Corregir botones que no funcionaban, ya que no permitía la interacción de hover a activo.
Seguir trabajando en figma y código.

Dificultades:
No me dejaba cambiar los modos de los botones, debía crear primero la forma y volverlo componente antes de darle forma y texto deseado.
Superposición de elementos en la portada: tuve problemas para crear el efecto de hojas apiladas y que cada una tuviera una pequeña inclinación 
consulta a claude:
¿Cómo puedo superponer tres rectángulos en CSS, manteniéndolos centrados y con diferentes rotaciones, para crear un efecto de hojas apiladas? Quiero que el elemento del frente quede por encima de los otros dos.
antes:
.portafolio-wrap .hoja {
  width: 230px;
  height: 100px;
  background: pink;
}


-después:

.portafolio-wrap .hoja {
  position:absolute;
  left:50%;
  top:40px;
  width:230px;
  height:100px;
  background:var(--rosa);
  border:1px solid #333;
}

.hoja.h1{
  transform:translateX(-50%) rotate(-6deg);
  background:#ffc7f1;
}

.hoja.h2{
  transform:translateX(-50%) rotate(4deg);
  background:#f4a9e6;
}

.hoja.h3{
  transform:translateX(-50%);
  background:var(--rosa);
  z-index:2;
}



Posicionar correctamente la tarjeta de presentación
Problema: Tuve dificultades para distribuir los elementos de la presentación, especialmente la ilustración y la tarjeta de texto. Quería que ambos elementos se superpusieron parcialmente, sin que la ilustración tapara la información.
Cómo lo resolví: Organicé los elementos utilizando posicionamiento absoluto y diferentes valores de z-index, lo que permitió controlar cuál elemento quedaba delante.
Consulta  claude:
¿Cómo puedo posicionar una imagen a la izquierda y una tarjeta de texto a la derecha, haciendo que ambas se superponen parcialmente? Necesito que la tarjeta quede por encima de los otros elementos y que el diseño tenga un fondo de color.

-Antes: 

.presentación {
  display:flex;
  align-items:center;
}


-Después:

.presentación{
  position:relative;
  height:210px;
  margin:20px 0 0;
}

.presentacion .fondo-rosa{
  position:absolute;
  left:0;
  bottom:0;
  width:70%;
  height:110px;
  background:var(--rosa);
}

.presentacion .personaje{
  position:absolute;
  left:30px;
  bottom:30px;
  width:90px;
  height:150px;
  z-index:2;
}

.presentación .tarjeta{
  position:absolute;
  right:20px;
  top:20px;
  width:62%;
  background:var(--rosa-claro);
  border-radius:12px;
  padding:14px 16px;
  z-index:3;
}



Problema para crear páginas individuales para cada proyecto 
- Problema: Al principio, tenía todos los proyectos dentro de una misma página y no sabía cómo hacer que cada botón «Más info» llevará a una sección independiente sin tener que crear varios archivos HTML.
- Cómo lo resolví: Utilicé identificadores (id) y enlaces internos (href) para conectar cada botón con su respectiva sección. También utilicé :target en CSS para mostrar únicamente el detalle seleccionado y ocultar la página principal.
- Consulta a claude:
¿Cómo puedo hacer que cada botón de «Más info» de mi portafolio abra una página de detalle diferente, pero manteniendo todo dentro del mismo archivo HTML? Me gustaría que al presionar volver se regrese a la página principal.


Antes:
HTML:
<a href="#">Más info</a>


CSS:
.detalle {
  display:block;
}
 
Después:
HTML:
<a class="btn-info" href="#mimus-tenca">
  Más info
</a>


<div class="detalle azul" id="mimus-tenca">
  <div class="hoja-det">
    <a class="volver" href="#inicio">
      ← volver
    </a>
    <h2>Réplica Mimus Tenca</h2>
  </div>
</div>




CSS:
.detalle{
  display:none;
}


.detalle:target{
  display:block;
}


body:has(.detalle:target) .home{
  display:none;
}


Aprendizaje:
Como crear correctamente un botón y que funcione correctamente
Como disponer elementos sobre posicionados en código CSS 
Aprender cómo superponer dos imágenes parcialmente también en código CSS.
Aprender a crear/redirigir a páginas individuales mediante un botón manteniendo todo en un mismo archivo HTML.
Durante el desarrollo de mi portafolio web me enfrenté a distintas dificultades relacionadas principalmente con la organización de los elementos, el posicionamiento de imágenes y textos, la creación de páginas de detalle y la mantención de una identidad visual coherente.
Algunas herramientas de CSS, como Flexbox, Position, Transform y las variables, fueron fundamentales para conseguir la distribución visual que estaba buscando.
Para resolver algunas de estas dificultades recurrí a consultas a Claude, principalmente para comprender cómo aplicar ciertas propiedades y encontrar soluciones a problemas específicos de código. A partir de sus respuestas fui probando, modificando y adaptando los fragmentos hasta conseguir el resultado que buscaba.
Este proceso me permitió comprender mejor la relación entre HTML y CSS, y aprender que la programación de una página web requiere probar distintas alternativas, corregir errores y ajustar constantemente los elementos hasta lograr una composición visual coherente con la propuesta inicial.



