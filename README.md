# PropuestaCongreso
Esta aplicación está diseñada para verificar la integridad de documentos mediante la comparación de hashes SHA-256 de los archivos con hashes almacenados en un archivo Excel. 

# Verificación de Integridad de Documentos PDF

Este programa de Python verifica la integridad de archivos PDF comparándolos con hashes almacenados en un archivo Excel. Es útil en contextos donde la autenticidad y la integridad de los documentos son cruciales, como en los ámbitos legal, financiero, educativo, y de investigación.

## Características de la Aplicación

- **Interfaz Intuitiva:** Utiliza `tkinter` para ofrecer una interfaz gráfica sencilla donde los usuarios pueden seleccionar fácilmente la carpeta con los archivos PDF y el archivo Excel con los hashes originales.
- **Cálculo de Hashes:** Usa `hashlib` y `PyPDF2` para calcular el hash SHA-256 de los contenidos de cada PDF, asegurando una verificación precisa.
- **Comparación Automática:** Compara automáticamente los hashes calculados con los almacenados en el archivo Excel, clasificando los documentos en válidos e inválidos.
- **Resultados Visuales:** Muestra los resultados de la verificación en una ventana clara y fácil de entender, indicando visualmente los documentos válidos y proporcionando enlaces interactivos para los documentos inválidos.

## Importancia de la Verificación de Documentos

1. **Seguridad y Confianza:**
   - Asegura que la información contenida en los documentos es auténtica y confiable.
   - Previene el fraude y la manipulación de documentos.

2. **Cumplimiento Legal:**
   - Asegura el cumplimiento de normativas legales que requieren la integridad de los documentos.
   - Protege contra litigios legales.

3. **Integridad de Datos:**
   - En instituciones educativas y de investigación, garantiza que los trabajos sean originales y no plagiados.
   - En el sector financiero, mantiene la integridad de reportes y transacciones.

4. **Eficiencia Operativa:**
   - Automatiza la verificación de documentos, ahorrando tiempo y recursos.
   - Reduce el riesgo de errores humanos.

## Componentes y Funcionalidades

### Importación de Módulos

- `os`, `shutil`: Manejo de archivos y directorios.
- `tkinter`: Crear interfaces gráficas de usuario (GUI).
- `hashlib`: Calcular hashes.
- `openpyxl`: Trabajar con archivos Excel.
- `PyPDF2`: Leer y extraer texto de archivos PDF.

### Función `calcular_hash_pdf`

- Calcula el hash SHA-256 del contenido de un archivo PDF.
- Usa `PdfReader` de `PyPDF2` para leer el PDF y extraer el texto de cada página.
- Codifica el texto extraído en UTF-8 y actualiza el objeto `hasher`.
- Retorna el hash calculado en formato de bytes.

### Función `abrir_archivo`

- Abre un archivo especificado usando la función `startfile` de `os`.

### Función `cargar_carpeta_y_verificar`

- Crea una ventana oculta de `tkinter` para seleccionar la carpeta con archivos PDF y el archivo Excel con hashes.
- Lee el archivo Excel usando `openpyxl` y accede a su primera hoja.
- Itera sobre los archivos PDF en la carpeta seleccionada, calcula su hash y verifica si coincide con alguno de los hashes en el archivo Excel.
- Clasifica los archivos en válidos e inválidos.
- Muestra los resultados en una nueva ventana con una lista de archivos válidos (en verde) y archivos inválidos (en rojo). Al hacer clic en un archivo inválido, se abre el archivo para revisión.

### Función `mostrar_ventana_bienvenida`

- Crea una ventana de bienvenida donde el usuario puede iniciar el proceso de verificación.
- Incluye un botón para seleccionar la carpeta y el archivo Excel.
- Define una función para cerrar la ventana de bienvenida.

### Ejecución Principal

- Llama a `mostrar_ventana_bienvenida` para iniciar el programa mostrando la ventana de bienvenida.

## Uso del Programa

1. **Inicio del Programa:**
   - Se muestra una ventana de bienvenida con un mensaje y un botón para seleccionar la carpeta y el archivo Excel.

2. **Selección de Archivos:**
   - Al hacer clic en el botón, se abre un diálogo para seleccionar la carpeta con los archivos PDF.
   - Luego, se abre otro diálogo para seleccionar el archivo Excel con los hashes.

3. **Cálculo y Verificación de Hashes:**
   - El programa lee el archivo Excel y extrae los hashes.
   - Para cada archivo PDF en la carpeta, calcula el hash y lo compara con los hashes del archivo Excel.
   - Clasifica los archivos en válidos o inválidos según si el hash coincide o no.

4. **Visualización de Resultados:**
   - Muestra una ventana con los resultados de la verificación.
   - Los archivos válidos se listan en verde, los inválidos en rojo.
   - Al hacer clic en un archivo inválido, se abre el archivo para revisión.

5. **Cierre del Programa:**
   - El programa se cierra cuando el usuario cierra la ventana de resultados.

Este código es útil para verificar la integridad de documentos PDF asegurando que no hayan sido alterados, comparando los hashes calculados de los archivos con los hashes originales almacenados en un archivo Excel.
