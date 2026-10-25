# Mi Metropolitano – Prototipo web de gestión de recargas

El Metropolitano es uno de los principales servicios de transporte público de Lima y es utilizado a diario por pasajeros con distintas necesidades de viaje. El seguimiento de las recargas puede resultar confuso cuando una operación aún requiere activación presencial antes de que el importe se refleje en el saldo disponible. Por ello, es útil contar con una vista clara del saldo y del estado de cada movimiento.

Mi Metropolitano es un prototipo web dirigido a pasajeros habituales y ocasionales que desean organizar la información de una tarjeta de demostración en un solo lugar. La aplicación permite consultar el saldo simulado, registrar recargas sin realizar pagos y revisar el historial para distinguir las operaciones activadas de las que siguen pendientes.

La propuesta también permite simular la activación de recargas pendientes y muestra una alerta cuando el saldo disponible es menor a S/ 5.00. De este modo, el prototipo ilustra cómo una interfaz sencilla puede facilitar el seguimiento de las operaciones, sin sustituir los canales oficiales del servicio.

## Tecnologías utilizadas

- **HTML5** estructura la interfaz y sus controles accesibles.
- **CSS3** define el diseño adaptable, las animaciones y los temas claro y oscuro según las preferencias del dispositivo.
- **JavaScript** administra las interacciones, las validaciones y los estados simulados de la tarjeta y sus recargas.
- **`localStorage`** conserva localmente el número de tarjeta de demostración, el saldo y el historial entre visitas.
- **GitHub Pages** publica la aplicación estática directamente desde el repositorio mediante un workflow de GitHub Actions, sin etapa de compilación.

## Funcionalidades principales

- Consulta de una tarjeta virtual de demostración, edición de su número y visualización separada del saldo disponible y del monto pendiente de activación.
- Alerta visual cuando el saldo disponible es inferior a S/ 5.00.
- Simulación de recargas con montos rápidos de S/ 5, S/ 10 y S/ 20 o con un monto personalizado, con validación de un límite diario simulado de S/ 200.
- Confirmación antes de registrar una recarga y aviso de éxito. Las recargas quedan pendientes y no aumentan el saldo disponible hasta la activación simulada.
- Simulación de activación de las recargas pendientes, que actualiza el saldo y el estado de los movimientos.
- Historial con fecha, hora, monto y estado, con un filtro para mostrar todas las recargas o solo las pendientes.
- Persistencia local de los datos y adaptación a pantallas estrechas y a los temas claro y oscuro.

## Ejecución local

Clona el repositorio y abre `index.html` directamente en un navegador. No necesitas instalar dependencias ni iniciar un servidor.

```powershell
git clone https://github.com/KarenAriZ/karen-arias-cainamari-examen-final.git
cd karen-arias-cainamari-examen-final
Start-Process .\index.html
```

También puedes descargar el repositorio como archivo ZIP, extraerlo y abrir `index.html`.

## Demostración en línea

La aplicación está publicada en [GitHub Pages](https://karenariz.github.io/karen-arias-cainamari-examen-final/).

## Alcance y limitaciones

Este proyecto tiene fines exclusivamente académicos y no está afiliado a la Autoridad de Transporte Urbano para Lima y Callao (ATU). No se conecta con bancos, medios de pago, tarjetas reales ni sistemas oficiales del Metropolitano. El número de tarjeta, el saldo, las recargas y sus activaciones son simulados y se guardan únicamente en el almacenamiento local del navegador.
