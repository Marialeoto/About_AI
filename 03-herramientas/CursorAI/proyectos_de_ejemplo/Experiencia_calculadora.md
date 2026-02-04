# Mi Viaje Aprendiendo Cursor AI: De la Configuración a la Acción 🚀

Este artículo documenta mi proceso de aprendizaje con **Cursor AI**, el editor de código basado en inteligencia artificial que está transformando la manera en que construimos software. Aquí resumo los pasos que seguí, los desafíos técnicos que enfrenté y cómo los solucioné con mi primer proyecto sencillo.

---

## 1. Entendiendo el "Cerebro" de Cursor
Al abrir por primera vez la interfaz de **Cursor Settings**, comprendí que no es solo un editor visual, sino un centro de control de modelos de lenguaje (LLMs).

### Configuraciones clave aprendidas:
* **Modelos:** Aprendí que puedo elegir entre diferentes "mentes" como `Claude 3.5 Sonnet` (ideal por su razonamiento lógico) o `GPT-4o`.
* **Indexación:** Para que la IA no "alucine", es vital dejar que el editor indexe los archivos locales. Esto le da contexto real sobre lo que estoy construyendo.
* **Reglas Personalizadas:** Descubrí que puedo dar instrucciones persistentes (como "háblame siempre en español") en la sección de *Rules & Commands*.

---

## 2. Mi Primer Proyecto: Calculadora de Propinas 💡
Para poner a prueba la herramienta, decidí crear una aplicación web desde cero.

### El Flujo de Trabajo:
1.  **Generación con `Ctrl + K`:** En un archivo vacío llamado `calculadora_propina.html`, usé un lenguaje natural para pedir una calculadora moderna con diseño *dark mode*. 
2.  **Resultado:** En menos de 30 segundos, la IA generó la estructura HTML, los estilos CSS y la lógica de JavaScript.
3.  **Refinamiento con el Chat (`Ctrl + L`):** Solicité añadir la funcionalidad de "dividir cuenta entre personas" referenciando el archivo mediante el símbolo `@`.

---

## 3. Desafíos Técnicos: El Conflicto con Git 🛠️
No todo fue "soplar y hacer botellas". Me enfrenté a un problema común: **mi archivo local no aparecía en GitHub.**

### El Problema:
Aunque el archivo existía en mi computadora, GitHub mostraba la carpeta como un **"submódulo" (una carpeta gris con una flecha blanca)** que no permitía ver el contenido. Esto ocurre cuando se crea accidentalmente un repositorio Git dentro de otro, el cuál cree por error al correr el comando **git init** posicionada desde ese directorio.

### La Solución (Paso a paso):
Para solucionar esto y que otros puedan aprender de mi error, realicé los siguientes pasos en la terminal de Cursor:

1.  **Eliminar el rastro oculto:** Borré la carpeta `.git` interna que causaba el conflicto:
    ```powershell
    Remove-Item -Recurse -Force .git
    ```
2.  **Limpiar la memoria de Git:** Forcé a Git a olvidar esa carpeta "fantasma":
    ```bash
    git rm -rf --cached ruta/de/tu/carpeta
    ```
3.  **Sincronización:** Añadí los archivos correctamente y subí los cambios:
    ```bash
    git add .
    git commit -m "Fix: Carpeta convertida a directorio normal"
    git push origin main
    ```

---

## 4. Conclusiones y Tips de Aprendizaje
Después de esta sesión intensiva, mis recomendaciones para quien empiece con Cursor AI son:

* **No te desesperes si la IA tarda:** Si la generación se queda trabada, usa `Ctrl + Shift + P` y elige `Developer: Reload Window`.
* **Domina la `@`:** Es la herramienta más potente para dar contexto.
* **Lee el código:** La IA es una asistente, no el jefe. Siempre revisa lo que genera antes de darle a "Accept".

---
*Documentado con ❤️ usando Cursor AI.*