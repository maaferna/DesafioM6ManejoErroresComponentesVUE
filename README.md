# Sistema de Gestión de Citas Médicas

Este proyecto es un sencillo sistema de gestión de citas médicas desarrollado con Vue.js y Bootstrap. Permite a los usuarios registrar citas médicas ingresando el nombre del paciente, fecha, hora, gravedad y el motivo de la consulta. El nivel de gravedad cambia el color de fondo de cada tarjeta para representar visualmente la urgencia de la cita (baja, media o alta).

## Funcionalidades

Formulario dinámico: El formulario tiene validación que asegura que todos los campos estén completos antes de habilitar el botón "Agregar".
Tarjetas dinámicas: Una vez que se agrega una cita, se muestra en una tarjeta con la información del paciente. Las tarjetas están codificadas por colores según la gravedad de la cita.

Funcionalidad de eliminación: Cada tarjeta de cita tiene un botón para eliminarla.

Diseño responsivo: El proyecto utiliza Bootstrap para hacer que el diseño sea responsivo. Las tarjetas están organizadas en filas con espacio entre ellas, y el formulario está alineado correctamente utilizando el sistema de grillas de Bootstrap.

## Tecnologías Utilizadas

Vue.js: Para crear la interfaz de usuario dinámica.

Bootstrap: Para el estilo y la capacidad de respuesta.

HTML5 y CSS3: Para el marcado básico y estilos adicionales.


## Primeros pasos

Prerrequisitos

Asegúrate de tener lo siguiente instalado en tu sistema:

Node.js: Asegúrate de tener Node.js instalado, ya que lo necesitarás para gestionar los paquetes a través de npm.

Vue CLI: Si no tienes Vue CLI instalado, puedes instalarlo ejecutando:

bash'''
npm install -g @vue/cli

'''

Instalación
Clona el repositorio:
git clone git@github.com:maaferna/DesafioM6ManejoErroresComponentesVUE.git


Navega a la carpeta del proyecto:

cd DesafioM6ManejoErroresComponentesVUE

Instala las dependencias: En el directorio raíz del proyecto, ejecuta:

npm install

Ejecutar el proyecto
Una vez instaladas todas las dependencias, puedes iniciar el servidor de desarrollo.

npm run dev


Esto lanzará un servidor de desarrollo local. De forma predeterminada, la aplicación se ejecutará en http://localhost:8080/ en tu navegador.

Estructura del Proyecto
Aquí tienes un resumen de la estructura del proyecto:

├── public/               # Archivos estáticos
│   └── index.html        # Archivo principal HTML
├── src/
│   ├── assets/           # Imágenes, CSS, etc.
│   ├── components/       # Componentes de Vue
│   │   ├── AppointmentCard.vue
│   │   └── AppointmentForm.vue
│   ├── App.vue           # Componente principal
│   └── main.js           # Punto de entrada del proyecto
├── .gitignore            # Archivos a ignorar en Git
├── package.json          # Metadatos del proyecto y dependencias
└── README.md             # Este archivo


## Uso

Completa los campos Paciente, Fecha, Hora, Gravedad y Motivo en el formulario.

Los labels del formulario se volverán de color rojo si el campo correspondiente está vacío y volverán a negro una vez que se complete.

Haz clic en Agregar para añadir la cita. El formulario se restablecerá y una nueva tarjeta aparecerá debajo del formulario mostrando la información de la cita.

Haz clic en Eliminar en cualquier tarjeta para eliminar la cita correspondiente.
Problemas Conocidos

Asegúrate de que todos los campos del formulario estén completados antes de enviarlo.

En caso de que los elementos se superpongan, es posible que necesites ajustar el sistema de grillas de Bootstrap para adaptarse a diferentes tamaños de pantalla.


## Licencia
Este proyecto es de código abierto y se puede usar bajo la licencia MIT.