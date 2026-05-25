# 1. PORTADA

**Proyecto:** AppCiencias2  
**Documento:** Manual de Usuario  
**Autores:** Equipo del proyecto (completar con nombres oficiales)  
**Universidad:** (completar)  
**Carrera:** Ingeniería de Sistemas / Computación (completar denominación oficial)  
**Curso:** Ciencias de la Computación II (completar sección)  
**Fecha:** 25 de mayo de 2026

---

# 2. INTRODUCCIÓN

AppCiencias2 es una aplicación educativa de escritorio desarrollada en **Java + JavaFX** para apoyar el aprendizaje práctico de estructuras de datos y algoritmos. Su enfoque es visual e interactivo: el estudiante construye estructuras, ejecuta algoritmos y observa resultados en tablas, paneles y áreas gráficas.

## 2.1 Propósito del sistema
- Facilitar la comprensión de búsquedas internas y externas.
- Permitir prácticas de hashing, índices y expansión dinámica.
- Visualizar grafos, operaciones, métricas y caminos mínimos.
- Simular árboles (simples, generadores y digitales), además de codificación Huffman.

## 2.2 Objetivo educativo
La herramienta está orientada a clases, laboratorios y autoaprendizaje en cursos de estructuras de datos, organización de archivos y teoría de grafos.

## 2.3 Tecnologías base
- Java 21
- JavaFX 21.0.2
- Maven (plugin JavaFX)

[INSERTAR IMAGEN: pantalla principal]

---

# 3. ACCESO Y EJECUCIÓN

## 3.1 Requisitos mínimos

| Componente | Requisito |
|---|---|
| JDK | 21 |
| Maven | 3.9+ |
| JavaFX | 21.0.2 |
| RAM recomendada | 4 GB o superior |
| Resolución recomendada | 1280x800 o superior |

## 3.2 Apertura del proyecto
1. Abrir terminal en la carpeta `AppCiencias2`.
2. Verificar Java y Maven.

```bash
java -version
mvn -version
```

## 3.3 Ejecución de la aplicación
Comandos detectados compatibles con el proyecto:

```bash
mvn clean compile
mvn javafx:run
```

Opcional para empaquetar:

```bash
mvn clean package
```

## 3.4 Inicio de la aplicación
Al iniciar:
1. Se carga `layout.fxml` como contenedor principal.
2. Se muestra `inicio.fxml` como pantalla inicial.
3. El menú lateral se abre desde el icono de menú.

---

# 4. INTERFAZ GENERAL

## 4.1 Estructura visual global
- **Barra superior:** botón de menú y opción “Ir atrás”.
- **Menú lateral desplegable:** acceso jerárquico a módulos.
- **Área central de contenido:** panel dinámico donde cambia cada vista.
- **Paneles internos por módulo:** formularios, tablas, área de dibujo y salida textual.

## 4.2 Navegación del usuario
- El usuario abre menú lateral y selecciona módulo/submódulo.
- Cada selección reemplaza el panel central.
- El botón **Ir atrás** recupera paneles previos.

## 4.3 Controles JavaFX frecuentes
- `TextField` para parámetros (N, clave, pesos, vértices, bloques).
- `ChoiceBox` / `ComboBox` para variantes de algoritmo u operación.
- `TableView` para estructuras tabulares y resultados.
- `Pane` / `ScrollPane` para visualización gráfica.
- `TextArea` para explicación de pasos y resultados.

[INSERTAR IMAGEN: interfaz principal]  
[INSERTAR IMAGEN: menú lateral]  
[INSERTAR IMAGEN: área de visualización]

---

# 5. GUÍA GENERAL DE MÓDULOS

## 5.1 Menú principal

| Ruta de navegación | Propósito |
|---|---|
| Inicio → Búsquedas | Búsquedas internas y externas |
| Inicio → Grafos | Operaciones, algoritmos, árboles y métricas |

## 5.2 Búsquedas internas
Incluye:
- Búsqueda lineal
- Búsqueda binaria
- Función hash (interna)
- Búsqueda por árboles: Árbol digital, Tries por residuos, Residuos múltiples, Huffman

Uso general: crear estructura, insertar/buscar/eliminar, limpiar, guardar y recuperar.

[INSERTAR IMAGEN: búsquedas internas]

## 5.3 Búsquedas externas
Incluye:
- Búsquedas dinámicas: expansión total y parcial
- Función hash externa
- Índices: primario, secundario, agrupamiento, multinivel

Uso general: configurar tamaño lógico/físico, simular accesos y evaluar estructura de almacenamiento.

[INSERTAR IMAGEN: búsquedas externas]

## 5.4 Grafos
Incluye:
- Operaciones entre grafos
- Árboles (simple, generador, distancia entre árboles)
- Algoritmos de grafos (función ordinal, caminos mínimos)
- Representación y métricas (matrices, distancias)
- Teoría de coloración

[INSERTAR IMAGEN: módulo grafos]

---

# 6. EXPLICACIÓN DETALLADA DE ALGORITMOS Y VISTAS

## 6.1 Búsqueda lineal
**Función:** busca una clave recorriendo secuencialmente la estructura.  
**Entradas:** tamaño N, dígitos de clave, clave a insertar/buscar/eliminar.  
**Botones típicos:** Crear, Insertar, Buscar, Eliminar, Limpiar, Guardar, Recuperar.  
**Visualización:** tabla posición-clave y mensaje de resultado.

**Pasos de uso:**
1. Definir N y dígitos.
2. Crear estructura.
3. Insertar claves.
4. Buscar una clave.
5. Revisar resultado en etiqueta/tabla.

[INSERTAR IMAGEN: búsqueda lineal]

## 6.2 Búsqueda binaria
**Función:** búsqueda sobre estructura ordenada.  
**Uso:** inserción ordenada y búsqueda binaria de clave.  
**Resultados:** posición encontrada o mensaje de no encontrado; soporte de eliminación y persistencia.

[INSERTAR IMAGEN: búsqueda binaria]

## 6.3 Función hash interna
**Función:** dispersión de claves con gestión de colisiones.  
**Entradas:** N, dígitos, divisor hash, tipo de función hash, estrategia de colisión.  
**Botones:** Crear, Insertar, Buscar, Eliminar, Arreglar colisiones, Guardar, Recuperar, Limpiar.  
**Visualización:** tabla con posición, clave y colisiones.

[INSERTAR IMAGEN: hash interno]

## 6.4 Hash externo
**Función:** simulación de hashing sobre bloques externos.  
**Entradas:** tamaño total, tamaño de bloque, dígitos, divisor/base.  
**Visualización:** bloque, posición, hash, clave, colisiones.  
**Opciones:** resolver colisiones, guardar/cargar estructura externa.

[INSERTAR IMAGEN: hash externo]

## 6.5 Expansión total
**Función:** ajuste dinámico de estructura hash mediante expansión/reducción.  
**Controles:** Expandir, Reducir, DO (densidad de ocupación), pendientes, guardar/cargar.  
**Resultado:** reacomodo de claves en tabla.

[INSERTAR IMAGEN: expansión total]

## 6.6 Expansión parcial
**Función:** expansión dinámica localizada por cubetas/bloques.  
**Controles:** similares a expansión total con operaciones manuales de crecimiento y reducción.

[INSERTAR IMAGEN: expansión parcial]

## 6.7 Índice primario
**Función:** modelar bloques de datos y bloques índice primario.  
**Entradas:** r, B, R, Ri.  
**Salida:** bfr, b, bi, accesos estimados y panel de bloques.  
**Opciones:** crear, limpiar, guardar, recuperar.

[INSERTAR IMAGEN: índice primario]

## 6.8 Índice secundario
**Función:** estimación y visualización de accesos con índice secundario.  
**Salida:** métricas de bloques/entradas y explicación textual.

[INSERTAR IMAGEN: índice secundario]

## 6.9 Índice multinivel
**Función:** simulación de niveles de índices y accesos acumulados.  
**Salida:** nivel 1, nivel 2, nivel 3, accesos y representación por paneles.

[INSERTAR IMAGEN: índice multinivel]

## 6.10 Árbol simple
**Función:** construir árbol con raíz, relaciones padre-hijo y edición básica.  
**Botones:** Crear raíz, Agregar relación, Eliminar relación, Crear árbol, Limpiar, Guardar, Cargar.  
**Visualización:** panel del árbol + área de información.

[INSERTAR IMAGEN: árbol simple]

## 6.11 Árbol generador (Kruskal mínimo/máximo)
**Función:** generar árbol generador mínimo o máximo desde un grafo ponderado.  
**Entradas:** lista de vértices y aristas ponderadas.  
**Botones:** Mostrar grafo original, Generar mínimo, Generar máximo, Guardar, Cargar, Limpiar.

[INSERTAR IMAGEN: árbol generador]

## 6.12 Distancia entre árboles
**Función:** comparar dos árboles y calcular su distancia estructural.  
**Entradas:** vértices/aristas de árbol 1 y árbol 2.  
**Salida:** paneles de cada árbol, panel de resultado y texto comparativo.

[INSERTAR IMAGEN: distancia entre árboles]

## 6.13 Árbol digital
**Función:** codificación/organización por caracteres con búsqueda de letra.  
**Entradas:** mensaje y letra a consultar.  
**Salida:** tabla de letra, posición y código binario; visual del árbol.

[INSERTAR IMAGEN: árbol digital]

## 6.14 Tries por residuos
**Función:** construir trie a partir de mensaje y rutas binarias.  
**Controles:** Procesar, Buscar, Limpiar búsqueda, Reiniciar.  
**Salida:** tabla de códigos y panel del trie.

[INSERTAR IMAGEN: tries por residuos]

## 6.15 Residuos múltiples
**Función:** árbol de residuos parametrizado por bits por nivel (`m`).  
**Entradas:** slider de `m`, mensaje.  
**Salida:** tabla de letra/alfabeto/binario y visual del árbol.

[INSERTAR IMAGEN: residuos múltiples]

## 6.16 Huffman
**Función:** compresión por frecuencias y generación de códigos Huffman.  
**Entradas:** mensaje.  
**Botón:** Generar Árbol.  
**Salida:** tabla (letra, frecuencia, código) y visual del árbol en `ScrollPane`.

[INSERTAR IMAGEN: árbol de huffman]

## 6.17 Representación de grafos y matrices
**Función:** crear grafo (dirigido/no dirigido) y obtener:
- matriz de adyacencia,
- matriz de incidencia,
- adyacencia entre aristas.

**Controles:** generar vértices, clic para aristas, eliminar arista, guardar/cargar, limpiar.

[INSERTAR IMAGEN: matrices de grafos]

## 6.18 Distancia y métricas en grafos
**Función:** calcular distancias, radio y excentricidad en grafo ponderado.  
**Salida:** resultados en `TextArea` y visual del grafo.

[INSERTAR IMAGEN: distancia y métricas]

## 6.19 Función ordinal
**Función:** ejecución de análisis ordinal en grafo.  
**Controles:** generar vértices, crear aristas por clic, ejecutar función, guardar/cargar.

[INSERTAR IMAGEN: función ordinal]

## 6.20 Caminos mínimos (Dijkstra / Bellman / Floyd)
**Función:** cálculo de rutas mínimas según algoritmo seleccionado.  
**Entradas:** vértices, aristas con peso, algoritmo en combo.  
**Botones:** Ejecutar algoritmo, guardar/cargar, eliminar arista, limpiar.  
**Salida:** trazas y resultado en `TextArea`.

[INSERTAR IMAGEN: caminos mínimos]

## 6.21 Operaciones entre grafos
**Función:** operar G1 y G2 (según opción seleccionada en combo) y visualizar resultado en G3.  
**Controles:** Ver G1, Ver G2, Ver resultado de operación, Guardar, Cargar, Limpiar.

[INSERTAR IMAGEN: operaciones entre grafos]

## 6.22 Teoría de coloración
**Función:** análisis de operaciones/categorías de coloración y propiedades relacionadas.  
**Controles:** combo de elemento, combo de operación, ejecución y persistencia.

[INSERTAR IMAGEN: teoría de coloración]

---

# 7. SECCIÓN COMPLETA DE GRAFOS

## 7.1 Creación de vértices y aristas
1. Ingresar cantidad/listado de vértices.
2. Presionar **Generar vértices** o **Ver G1 / Ver G2**.
3. Crear aristas mediante clic en origen y destino.
4. En módulos ponderados, asignar peso a la arista.

## 7.2 Grafo dirigido / no dirigido
En representación de grafos, activar/desactivar **Grafo dirigido** para cambiar reglas de conexión y matrices.

## 7.3 Selección, movimiento y eliminación
- Selección por clic en nodos/aristas.
- Eliminación mediante botón **Eliminar arista**.
- Movimiento visual disponible en paneles interactivos (según controlador de cada vista).

## 7.4 Matrices
- **Matriz de adyacencia**
- **Matriz de incidencia**
- **Matriz de adyacencia de aristas**

Resultados mostrados en área textual/matriz.

## 7.5 Floyd, Dijkstra y Bellman
1. Generar grafo ponderado.
2. Elegir algoritmo en combo.
3. Ejecutar.
4. Revisar detalle de distancias/caminos en resultado.

## 7.6 MST (árbol generador)
- Cargar grafo con pesos.
- Ejecutar mínimo o máximo.
- Visualizar árbol obtenido y detalle.

## 7.7 Operaciones entre grafos
- Construir G1 y G2.
- Elegir operación.
- Visualizar resultado en panel G3.

## 7.8 Importar/exportar
Las vistas de grafos incluyen botones **Guardar** y **Cargar** para persistir estados.

[INSERTAR IMAGEN: editor de grafos]  
[INSERTAR IMAGEN: Floyd]  
[INSERTAR IMAGEN: MST]  
[INSERTAR IMAGEN: matrices]  
[INSERTAR IMAGEN: operaciones entre grafos]

---

# 8. TUTORIALES PASO A PASO

## 8.1 Tutorial: búsqueda lineal
1. Definir tamaño de estructura.
2. Crear estructura.
3. Insertar claves.
4. Ejecutar búsqueda de clave.
5. Ver resultado visual.

## 8.2 Tutorial: árbol simple
1. Ingresar raíz y crearla.
2. Seleccionar padre y escribir hijo.
3. Agregar relación.
4. Dibujar árbol.
5. Guardar estructura si desea reutilizarla.

## 8.3 Tutorial: Huffman
1. Escribir mensaje.
2. Presionar **Generar Árbol**.
3. Revisar tabla de frecuencias/códigos.
4. Explorar árbol en panel desplazable.

## 8.4 Tutorial: hashing dinámico
1. Definir cubetas, registros y dígitos.
2. Crear estructura.
3. Insertar claves.
4. Observar DO y pendientes.
5. Expandir/reducir manualmente y evaluar comportamiento.

## 8.5 Tutorial: caminos mínimos
1. Definir cantidad de vértices.
2. Generar vértices.
3. Crear aristas con peso.
4. Seleccionar Dijkstra/Bellman/Floyd.
5. Ejecutar y analizar resultados.

## 8.6 Tutorial: matrices de grafos
1. Generar grafo dirigido o no dirigido.
2. Insertar aristas.
3. Ejecutar matriz de adyacencia/incidencia.
4. Comparar resultados en panel textual.

---

# 9. FUNCIONALIDADES GENERALES TRANSVERSALES

| Funcionalidad | Presencia en módulos |
|---|---|
| Crear estructura | Búsquedas, hash, índices, grafos, árboles |
| Insertar / Buscar / Eliminar | Búsquedas, hash, índices |
| Limpiar | Prácticamente todos los módulos |
| Guardar / Cargar | Hash, índices, grafos, árboles, caminos, métricas |
| Visualización gráfica | Grafos, árboles, Huffman, tries, residuos |
| Resultados textuales | Módulos con `TextArea`/`Label` de salida |
| Configuración por combos | Hash, operaciones, caminos mínimos, teoría de color |

> Nota: no se identificaron controles explícitos de deshacer/rehacer universales en las vistas revisadas.

---

# 10. SOLUCIÓN DE PROBLEMAS COMUNES

## 10.1 No carga un archivo guardado
- Verifique que fue generado por el mismo módulo.
- Confirme que el formato del archivo no fue modificado manualmente.
- Reintente con una estructura nueva y luego cargar nuevamente.

## 10.2 No aparece el grafo o árbol
- Asegúrese de haber presionado **Generar vértices** o acción equivalente.
- Verifique que el panel no esté vacío por limpiar reciente.
- Revise si faltan aristas o datos de entrada.

## 10.3 No deja insertar clave
- Compruebe que la estructura ya fue creada.
- Revise tamaño de dígitos y rango esperado.
- Evite claves vacías o formato no numérico cuando el módulo lo exige.

## 10.4 Error con pesos de arista
- Use valores válidos (numéricos).
- Evite dejar peso en blanco en módulos ponderados.
- Si hay resultado incoherente, limpie y reconstruya el grafo.

## 10.5 Estructura vacía o resultados “Listo.” sin cambios
- Verifique que ejecutó el botón principal del algoritmo (Buscar/Ejecutar/Generar).
- Confirme que existen datos previos en la tabla o panel.

## 10.6 Menú o navegación no responde como espera
- Cierre y abra nuevamente el menú lateral.
- Use **Ir atrás** para recuperar panel previo.
- Si persiste, reinicie la aplicación.

---

# 11. RECOMENDACIONES DE USO ACADÉMICO

1. Trabajar por módulos (internas → externas → grafos → árboles).
2. Registrar parámetros usados en cada práctica.
3. Guardar estructuras de prueba antes de limpiar.
4. Comparar resultados entre algoritmos sobre el mismo conjunto de datos.
5. Documentar observaciones de complejidad y comportamiento visual.

---

# 12. ANEXO: MAPA DE VISTAS FXML DEL SISTEMA

- Núcleo UI: `layout.fxml`, `menu.fxml`, `inicio.fxml`.
- Búsquedas: `busquedas.fxml`, `busquedasInternas.fxml`, `busquedasExternas.fxml`, `busquedaLineal.fxml`, `busquedaBinaria.fxml`, `busquedaHash.fxml`, `busquedaHashExterna.fxml`, `busquedaExpTotales.fxml`, `busquedaExpParciales.fxml`, `busquedaPorResiduos.fxml`, `tresResiduos.fxml`, `residuosMultiples.fxml`, `huffman.fxml`, `arbolDigital.fxml`.
- Índices: `indicesExternos.fxml`, `IndicePrimario.fxml`, `IndiceSecundario.fxml`, `IndiceMultinivel.fxml`, `busquedaIndicePrimario.fxml`.
- Grafos y métricas: `grafos.fxml`, `representacionGrafos.fxml`, `menuRepresentacionMetricas.fxml`, `distanciaVertices.fxml`, `funcionOrdinal.fxml`, `caminosMinimos.fxml`, `operaciones.fxml`, `teoriaColor.fxml`, `algoritmosGrafos.fxml`.
- Árboles: `arbolesMenu.fxml`, `arbolSimple.fxml`, `arbolGenerador.fxml`, `distanciaArboles.fxml`.

---

**Fin del Manual de Usuario**
