# Manejo de Comandos y Expresiones Lógicas en Linux

En la Shell de Linux, los **comandos** son las instrucciones que el usuario escribe para interactuar con el sistema operativo.  
Con ellos podemos realizar acciones como crear archivos, listar directorios, mover datos o gestionar procesos.

El **manejo de comandos** incluye no solo ejecutarlos, sino también **combinarlos**, **controlar su ejecución** y **tomar decisiones** según si se ejecutaron correctamente o no.

---

## ¿Qué son las expresiones lógicas en la Shell?

En Linux, cada comando devuelve un **código de salida** que indica si su ejecución fue correcta o no.  
Este valor se utiliza para formar **expresiones lógicas** dentro de la terminal o en scripts.

- **0 → Verdadero (éxito)**  
- **Distinto de 0 → Falso (error)**  

Podemos comprobar el código de salida del último comando con:

```bash
echo $?
```

Por ejemplo:

```bash
ls
echo $?
```

Si `ls` se ejecutó correctamente, mostrará `0`.
Si hubo un error (por ejemplo, un directorio inexistente), mostrará otro número distinto.

## Operadores lógicos en la Shell

Los **operadores lógicos** permiten **encadenar comandos** y decidir si se ejecutan según el resultado lógico (éxito o error) del anterior.

### Operador AND (`&&`)

Ejecuta el segundo comando **solo si el primero fue exitoso**.

Sintaxis:

```bash
comando1 && comando2
```

- **comando1** → se ejecuta primero.

- **comando2** → solo se ejecuta si el primero devuelve 0.

**Ejemplo**:

```bash
mkdir proyectos && cd proyectos
```

**Explicación**:

Si `mkdir proyectos` se ejecuta correctamente, entonces se ejecuta `cd proyectos`.

Si falla, el segundo comando no se ejecuta.

### Operador OR (`||`)

Ejecuta el segundo comando `solo si el primero falla`.

**Sintaxis**:

```bash
comando1 || comando2
```

**Ejemplo**:

```bash
comando1 || comando2
```

**Explicación**:

`cd` falla porque la carpeta no existe.

Entonces, se ejecuta el segundo comando `echo`.

### Combinación de `&&` y `||`

Podemos combinar ambos operadores para crear `expresiones condicionales más completas`.

**Ejemplo**:

```bash
mkdir test && echo "Carpeta creada" || echo "Error al crear carpeta"
```

**Cómo funciona**:

1. Si `mkdir test` funciona → ejecuta `echo "Carpeta creada"`.

Si falla → ejecuta echo `"Error al crear carpeta"`.

  - Consejo: para evitar confusiones, es recomendable agrupar con paréntesis:

```bash
(mkdir test && echo "Carpeta creada") || echo "Error al crear carpeta"
```

### Operador NOT (`!`)

El operador `!` invierte el resultado lógico de un comando.

**Sintaxis**:

```bash
! comando
```

**Ejemplo**:

```bash
! ls archivo_inexistente
```

**Explicación**:

`ls archivo_inexistente` falla (salida ≠ 0).

Con `!` se invierte el resultado y pasa a considerarse verdadero.

---

**Ejemplo practico**:

```bash
cd /home/usuario && ls || echo "No se pudo entrar al directorio"
```

**Paso a paso**:

1. Intenta entrar al directorio `/home/usuario`.

2. Si lo logra (`&&`) → ejecuta `ls`.

3. Si falla (`||`) → muestra el mensaje `"No se pudo entrar al directorio"`.


## Tip extra

Los operadores lógicos son muy útiles cuando querés automatizar tareas o escribir **scripts inteligentes**, porque te permiten controlar el flujo de ejecución sin usar estructuras más complejas como `if`.

**Ejemplo típico**:

```bash
mkdir demo && cd demo && touch notas.txt && ls -l
(mkdir proyecto && cd proyecto && touch README.md && echo "OK") || echo "Fallo"
```
