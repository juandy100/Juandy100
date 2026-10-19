# guia c#





# array

```csharp

    int[] numeros = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
    Console.WriteLine(numeros[9]);
    Console.ReadLine();

```

# que 

 Es la declaración e inicialización de un arreglo (array). Un arreglo es una estructura de datos de tamaño fijo que almacena varios elementos del mismo tipo en posiciones contiguas de memoria.


# como funciona 

1. int[]: Define un arreglo (array) de tipo entero. Los corchetes [] le indican al compilador que la variable guardará una colección ordenada de elementos del mismo tipo (int).

3. numeros: Es el nombre que le asignas a la variable del arreglo.

4. = { 1, 2, ... }: Utiliza la sintaxis de inicializador de colección para asignar de inmediato 10 elementos al arreglo. Esto crea automáticamente un arreglo de tamaño 10 en memoria.

# que aparecera en la consola y como funciona

Console.WriteLine(): Es un método que envía datos a la consola de comandos para imprimirlos y coloca un salto de línea al final.

numeros[9]: Es el acceso por índice. Los arreglos en C# empiezan a contar desde el índice 0. Por ende:

numeros[0] $\rightarrow$ 1
numeros[1] $\rightarrow$ 2


# lista

```csharp

    List<int> numeroos = new List<int> { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
    Console.WriteLine(numeroos[7]);
 
```

# que es 

Es la declaración, inicialización e impresión de una lista dinámica (List<T>). A diferencia de un arreglo (array) que tiene un tamaño fijo, una lista es una estructura de datos flexible que puede crecer o reducirse dinámicamente agregando o quitando elementos durante la ejecución del programa.

# como funciona

1. List<int>: Especifica el tipo de estructura. List<T> es una clase genérica del espacio de nombres System.Collections.Generic. El <int> dentro de los corchetes angulares indica que la lista guardará únicamente números enteros.



3. numeroos: Es el nombre o identificador que se le asigna a la variable.

4. = new List<int> { ... }: Usa el operador new para instanciar (crear) el objeto en memoria y utiliza un inicializador de colección para agregar los 10 valores iniciales.

5. numeroos[7]: Es el acceso por índice. Las listas en C# también utilizan base cero, por lo que el conteo empieza en 0:

# que apare cera en la consola

1. Al ejecutar las dos líneas de código, la consola imprimirá únicamente el número guardado en la posición 7


# DICIONARIO

```csharp

    var jugadores = new Dictionary<int, (int puntos, string pasiva1)>
    {
    [1] = (10, "Juan"),
    [2] = (20, "Pedro"),
    [3] = (30, "Maria"),
    [4] = (40, "Luis")
    };
```
# que es 

Es la declaración e inicialización de un Diccionario (Dictionary<K, V>) que utiliza Tuplas con nombre (ValueTuple) como sus valores. Un diccionario es una estructura de datos que almacena elementos en parejas de Clave-Valor (Key-Value), donde cada clave es única y permite buscar o acceder a su valor asociado de forma muy rápida.

# como funciona

1. var: Le indica al compilador de C# que deduzca automáticamente el tipo de dato de la variable según los datos que se le están asignando a la derecha.



3. Dictionary<int, (int puntos, string pasiva1)>:
-   Clave (Key): Es de tipo int (en este caso representa los identificadores o IDs: 1, 2, 3, 4).

-   Valor (Value): Es una Tupla (int puntos, string pasiva1), lo que permite agrupar dos datos distintos (un entero para puntos y un texto para el nombre/pasiva) dentro de un solo valor con nombres de campos personalizados.

4. new Dictionary<...> { ... }: Instancia el diccionario en memoria.

5. Sintaxis de índice [1] = (10, "Juan"): Utiliza el inicializador de índices de C# para asociar la clave entre corchetes con su correspondiente tupla de valor:
-   Clave 1 $\rightarrow$ Contiene la tupla (puntos: 10, pasiva1: "Juan")

-   Clave 2 $\rightarrow$ Contiene la tupla (puntos: 20, pasiva1: "Pedro") ...

# que apare cera en la consola

1. Este fragmento solo crea y llena la estructura de datos en la memoria del programa. Para imprimir algún valor en la consola, se necesitaría un comando como Console.WriteLine(jugadores[1].pasiva1); (que imprimiría Juan).

#  desestructuración de una Tupla

```csharp

    var (puntos, nombre) = jugadores[3];
    Console.WriteLine($"Jugador ID 3: {nombre} - Puntos: {puntos}");
    Console.ReadLine();
      
```
    
# que es 

Es la desestructuración de una Tupla obtenida desde un Diccionario, seguida de la impresión formateada del resultado y una pausa de ejecución. Toma la tupla almacenada en la clave 3 del diccionario jugadores de la lección anterior, extrae sus dos valores en variables independientes e imprime sus contenidos mediante interpolación de cadenas.

# como funciona

1. var (puntos, nombre) = jugadores[3];:
-   jugadores[3]: Busca la clave 3 en el diccionario y devuelve la tupla correspondiente: (30, "Maria").

-   var (puntos, nombre): Utiliza el patrón de desestructuración (deconstruction) de C#. Desempaqueta automáticamente la tupla dividiéndola en dos variables nuevas:
-   - puntos recibe el primer valor (30).
-   - nombre recibe el segundo valor ("Maria").



3. Console.WriteLine($"Jugador ID 3: {nombre}Puntos: {puntos}");:

-   El símbolo $ activa la interpolación de cadenas en C#, lo que permite incrustar variables directamente dentro del texto rodeadas por llaves { }.
-   Sustituye {nombre} por "Maria" y {puntos} por 30.

4. Console.ReadLine();:
-   Detiene la ejecución del programa a la espera de que el usuario presione la tecla Enter, evitando que la consola se cierre de golpe.


# que apare cera en la consola

Al ejecutar estas líneas, la consola mostrará la frase combinada e interpolada y mantendrá el cursor parpadeando debajo a la espera de un Enter:

Jugador ID 3: MariaPuntos: 30

# ecuaciones con float

```csharp

    double suma = numeroos.Sum();
    suma = 0;



    float PI = 3.1416f;
    float radio = 5.0f;
    float bases = 10.0f;  
    float haltura = 8.0f;


    float perimetroBase = 2 * bases + 2 * haltura; Console.WriteLine($"resultado del perimetro de la base es: {perimetroBase}");
    float areaBase = bases * haltura; Console.WriteLine($"resultado del area de la base es: {areaBase}");
    float volumenBase = areaBase * haltura; Console.WriteLine($"resultado del volumen de la base es: {volumenBase}");



    float PIesfera = 3.1416f;
    float areaesfera = 50.656f;
    float diametroesfera = radio * radio;


    float areaEsfera = PIesfera * areaesfera * areaesfera; Console.WriteLine($"resultado del  area de la esfera es: {areaEsfera}");
    float diametroEsfera = 2 * areaesfera; Console.WriteLine($"resultado del diametro de la esfera es: {diametroEsfera}");

```

# que es 

Es un programa de cálculos matemáticos y geométricos simples mediante variables de punto flotante (float) e impresión de resultados. Declara variables numéricas con decimales, realiza varias operaciones aritméticas (multiplicaciones y sumas para perímetros, áreas y volúmenes) y muestra los valores calculados en la consola mediante interpolación de cadenas.

# como funciona

1. Declaración de variables float (float PI = 3.1416f;, etc.):
-   float: Tipo de dato numérico usado para representar números de punto flotante (con decimales) de precisión simple.

-   El sufijo f le indica al compilador de C# que la constante numérica debe tratarse como un float (de lo contrario, C# la interpretaría por defecto como un double). dividiéndola en dos 
variables nuevas:

3. Cálculos aritméticos en la base:

-   2 * bases + 2 * haltura: Calcula el perímetro ($2 \times 10.0 + 2 \times 8.0 = 20.0 + 16.0 = 36.0$).

-   bases * haltura: Calcula el área de la base ($10.0 \times 8.0 = 80.0$).

-   areaBase * haltura: Calcula el volumen ($80.0 \times 8.0 = 640.0$).

4. Cálculos aritméticos en la esfera:

-  radio * radio: Multiplica el radio por sí mismo ($5.0 \times 5.0 = 25.0$, aunque esta variable no se imprime).

-   PIesfera * areaesfera * areaesfera: Multiplica el valor de PI por la variable areaesfera dos veces ($3.1416 \times 50.656 \times 50.656 \approx 8050.37$).

-   2 * areaesfera: Multiplica el valor por dos ($2 \times 50.656 = 101.312$).

5. Console.WriteLine($"...");: Toma el texto interpolado con el resultado de cada cálculo y lo imprime línea por línea en la consola de comandos.


# que apare cera en la consola

Al ejecutar todo el bloque, la consola mostrará exactamente el siguiente texto con los resultados calculados:

1.   resultado del perimetro de la base es: 36
3.  resultado del area de la base es: 80
4.   resultado del volumen de la base es: 640
5.  resultado del  area de la esfera es: 8050.3706
6.   resultado del diametro de la esfera es: 101.312

# ecuaciones con double
```csharp

    double PIesfera3 = 3.1416;

    double areaesfera3 = 5.988;
    double diametroesfera3 = radio * radio;


    double areaEsfera3 = (float) PIesfera3 * (float) areaesfera3 * (float) areaesfera3; Console.WriteLine($"resultado del  area de la esfera es: {areaEsfera3}");
    double diametroEsfera3 = 2 * (float) areaesfera3; Console.WriteLine($"resultado del diametro de la esfera es: {diametroEsfera3}");



    PI = 3.14f;
    radio = 5.0f;
    bases = 10.0f;
    haltura = 8.0f;

    float volumenCilindro = PI * radio * radio * haltura; Console.WriteLine($"resultado del volumen del cilindro es: {volumenCilindro}");
    float areaCono = PI * radio * (radio + MathF.Sqrt(haltura * haltura + radio * radio)); Console.WriteLine($"resultado del area del cono es: {areaCono}");
        

```

# que es 

Es un conjunto de cálculos geométricos avanzados usando tipos de datos double y float, conversión explícita de tipos (Casting) y funciones matemáticas complejas (MathF.Sqrt). Realiza operaciones para calcular el área aproximada de una esfera, el volumen de un cilindro ($V = \pi \cdot r^2 \cdot h$) y el área total de un cono ($A = \pi \cdot r \cdot (r + \sqrt{h^2 + r^2})$).

# como funciona

1. Uso de double y Casting explícito (float):
-   double: Tipo de dato de punto flotante de doble precisión (64 bits), ideal para cálculos que requieren mayor exactitud que un float (32 bits).

-   (float)PIesfera3: Realiza un cast (conversión explícita) del valor double a float antes de operarlo.

3. Reasignación de variables existentes:

-   Las variables PI, radio, bases y haltura (declaradas previamente en tu programa) actualizan sus valores en memoria con la nueva precisión.

4. MathF.Sqrt(...):

-  Es un método de la biblioteca matemática de .NET que calcula la raíz cuadrada de un número flotante (float).

-   En el cálculo del área del cono, calcula la generatriz ($g = \sqrt{h^2 + r^2} = \sqrt{8.0^2 + 5.0^2} = \sqrt{64 + 25} = \sqrt{89} \approx 9.4339$).


5. Fórmulas aplicadas:

volumenCilindro: Multiplica $\pi \times r^2 \times h \rightarrow 3.14 \times 5.0 \times 5.0 \times 8.0 = 628.0$.

areaCono: Aplica $3.14 \times 5.0 \times (5.0 + 9.4339) \rightarrow 15.7 \times 14.4339 \approx 226.613$.


# que apare cera en la consola

Al ejecutar las líneas que contienen Console.WriteLine(), la consola imprimirá en pantalla los siguientes resultados:

1. resultado del  area de la esfera es: 112.63777085730408
3. resultado del diametro de la esfera es: 11.97599983215332
4. resultado del volumen del cilindro es: 628
5. resultado del area del cono es: 226.61314

# operacones basicas

```csharp

    Console.ReadLine();

    Console.WriteLine(1 + 10 );
    Console.WriteLine(10 - 1);
    Console.WriteLine(5 * 2);
    Console.WriteLine(10 / 2);
    Console.WriteLine(100 % 30);

    Console.ReadLine();

```

# que es 

Es un bloque de código que demuestra la ejecución de operadores aritméticos básicos en C# (suma, resta, multiplicación, división y módulo) combinados con métodos de lectura y escritura en consola.

# como funciona

1. Primer Console.ReadLine();:

-   Pausa el programa al inicio y espera a que el usuario presione Enter antes de realizar y mostrar los cálculos.

3. Operaciones aritméticas dentro de Console.WriteLine():

-   1 + 10 (Suma): Evalúa $1 + 10 = 11$.
-   10 - 1 (Resta): Evalúa $10 - 1 = 9$.
-   5 * 2 (Multiplicación): Evalúa $5 \times 2 = 10$.
-   10 / 2 (División entera): Divide $10 \div 2 = 5$.
-   100 % 30 (Operador Módulo / Residuo): Devuelve el residuo de dividir $100$ entre $30$. Como $30 \times 3 = 90$, el residuo que sobra para llegar a $100$ es 10.

4. Segundo Console.ReadLine();:

-   Vuelve a pausar la ejecución al final para evitar que la ventana de la consola se cierre de inmediato, permitiendo ver todos los resultados impresos.

# que apare cera en la consola

Al ejecutar el código, la consola esperará a que presiones Enter por primera vez. Una vez presionado, imprimirá los 5 resultados línea por línea y se pausará de nuevo:

1.  11
3.  9
4.  10
5.  5
6.  10
_

# operador logico or

```csharp

    Console.WriteLine(true || false);
    Console.WriteLine(true || true);
    Console.WriteLine(false || true);
    Console.WriteLine(false || false);

    Console.ReadLine();

```
# que es 

Es un programa que demuestra el comportamiento del operador lógico OR (O lógico, representado por ||) en la tabla de verdad booleana de C#. Realiza evaluaciones de condiciones lógicas duplicadas en dos bloques separados por pausas de consola.

# como funciona

1. Operador lógico OR (||):

-   El operador || evalúa dos expresiones booleanas (true o false).

-   Regla del OR: Retorna True si al menos uno de los operandos es true. Únicamente retorna False cuando ambos operandos son false.


3. Evaluación de las expresiones paso a paso:

-   true || false $\rightarrow$ True (el primero es verdadero).
-   true || true $\rightarrow$ True (ambos son verdaderos).
-   false || true $\rightarrow$ True (el segundo es verdadero).
-   false || false $\rightarrow$ False (ninguno es verdadero).

4. Pausas interactivas (Console.ReadLine();):

-   Detienen el programa en dos momentos clave para permitir al usuario leer los resultados antes de continuar o finalizar.

# que apare cera en la consola

Al ejecutar el código, se imprime el primer bloque de resultados booleanos y el programa se detiene esperando un Enter:

1.  True
3.  True
4.  True
5.  False

# operador: Operador Lógico AND

```csharp

    Console.WriteLine(true && false);
    Console.WriteLine(true && true);
    Console.WriteLine(false && true);
    Console.WriteLine(false && false);

    Console.ReadLine();

```
# que es 

Es un programa que demuestra la Tabla de Verdad del Operador Lógico AND (Y lógico, representado por &&). A diferencia del operador OR (||), el operador AND evalúa si múltiples condiciones se cumplen de manera simultánea.

# como funciona

1. Operador lógico AND (&&):

-   El operador && evalúa dos expresiones booleanas (true o false).

-   Regla del AND: Retorna True únicamente si ambos operandos son true. Si al menos uno de los operandos es false, el resultado completo será False.

3. Evaluación de las expresiones paso a paso:

-   true && false $\rightarrow$ False (el segundo es falso).
-   true && true $\rightarrow$ True (ambos son verdaderos).
-   false && true $\rightarrow$ False (el primero es falso).
-   false && false $\rightarrow$ False (ambos son falsos).

4. Console.ReadLine();:

-   Mantiene abierta la ventana de la consola esperando a que presiones la tecla Enter para finalizar la ejecución.

# que apare cera en la consola

Al ejecutar las líneas, la consola imprimirá en pantalla los siguientes resultados booleanos y se detendrá esperando un Enter:

1.  False
3.  True
4.  False
5.  False

#   operador: Estructura de Control Condiciona

```csharp

    bool autorizado = false;

    if (autorizado)
    {
    Console.WriteLine("no autorizado");
    }
    else
    {
    Console.WriteLine("Acceso permitido");
    }

    Console.ReadLine();

```
# que es 

Es un programa que utiliza una instrucción condicional if - else junto con una variable booleana (bool) para tomar decisiones en el flujo del código. Evalúa el estado de una condición para decidir qué bloque de instrucciones debe ejecutarse y cuál debe ignorarse.

# como funciona

1. bool autorizado = false;:

-   Declara una variable de tipo booleano llamada autorizado y le asigna el valor false.

3. if (autorizado):

-   Evalúa la condición dentro de los paréntesis. Como autorizado vale false, la condición del if no se cumple.

-   El programa ignora por completo el bloque dentro del if (no ejecuta Console.WriteLine("no autorizado");).


4. else:

-   Como la condición del if fue falsa, el control pasa automáticamente al bloque del else.

-   Executa la instrucción dentro de sus llaves: Console.WriteLine("Acceso permitido");.

5.  Console.ReadLine();:

-   Detiene el programa y mantiene visible el resultado en la ventana hasta que el usuario presione la tecla Enter.

# que apare cera en la consola

Como la variable autorizado es false, la consola entrará directamente a la rama else e imprimirá:

1.  Acceso permitido

# Estructura Condicional Múltiple if - else if - else y Operador de Igualdad ==

```csharp
     
    int entero8 = 10;

    if (entero8 == 99)
    {
    Console.WriteLine("El 99");
    }
    else if (entero8 == 100)
    {
    Console.WriteLine("El 100");
    }
    else
    {
    Console.WriteLine("El número no es 99 NI 100");
    }


    Console.ReadLine();

```  
# que es 

Es un programa que utiliza una estructura de control condicional encadenada (if - else if - else) para evaluar múltiples condiciones en secuencia. Permite comparar una variable numérica contra varios valores posibles y ejecutar un único bloque de código correspondiente a la primera condición que resulte verdadera, o una alternativa por defecto (else) si ninguna se cumple.

# como funciona

1. int entero8 = 10;:

-   Declara una variable entera llamada entero8 y le asigna el valor 10.

3. if (entero8 == 99):

-   Compara mediante el operador de igualdad (==) si 10 es igual a 99.

-   La condición es falsa, por lo que ignora el bloque Console.WriteLine("El 99"); y pasa a la siguiente evaluación.

4. else if (entero8 == 100):

-   Compara si 10 es igual a 100.

-   La condición vuelve a ser falsa, por lo que también ignora el bloque Console.WriteLine("El 100");.

5. else:

-   Como ninguna de las condiciones previas fue verdadera, el flujo entra obligatoriamente en el bloque de escape else.

-   Executa Console.WriteLine("El número no es 99 NI 100");.

6.  Console.ReadLine();:

-   Pausa la consola y espera a que presiones la tecla Enter antes de cerrar la ventana.

# que apare cera en la consola

Al evaluarse las tres opciones, la consola mostrará únicamente el mensaje de la rama else y esperará la interacción del usuario:

1.  El número no es 99 NI 100

# Nombre del tema / operador: Estructura de Selección Múltiple switch - case - break - default

```csharp

    string colores = "verde";

    switch (colores)
    {
    case "verde":
    Console.WriteLine("correcto");
    break;
    case "amarillo":
    Console.WriteLine("masomenos");
    break;
    case "rojo":
    Console.WriteLine("masomenos");
    break;


    default:
    Console.WriteLine("incorrecto");
    break;
    }

    Console.ReadLine();

```  
# que es 

Es un programa que utiliza la instrucción de selección de control switch. La estructura switch evalúa una variable (en este caso un texto de tipo string) y transfiere el control de la ejecución al bloque etiquetado con la palabra clave case que coincida con el valor exacto de la expresión.

# como funciona

1. string colores = "verde";:

-   Declara e inicializa la variable de tipo texto colores con el valor "verde".

3. switch (colores):

-   Compara el valor de la variable colores contra los casos (case) declarados dentro de sus llaves.

4. case "verde"::

-   Evalúa si colores coincide con el texto "verde".

-   Coincide: El programa entra a este caso y ejecuta la instrucción Console.WriteLine("correcto");.

5.  break;:

-   Rompe o interrumpe la ejecución de la estructura switch. Impide que el flujo de ejecución continúe evaluando los demás casos ("amarillo", "rojo") o la sección default.

6.  default::
-   Define la opción por defecto que se ejecutaría si la variable no coincidiera con ningún case previo (funciona similar al else). En este caso no llega a ejecutarse porque la coincidencia ocurrió con "verde".

7.  Console.ReadLine();:
-   Pausa la consola a la espera de que el usuario presione la tecla Enter.

# que apare cera en la consola

Como la variable colores coincide exactamente con el primer case, la consola imprimirá esa única palabra y se pausará:

1. correcto

# operador: Funciones

```csharp


    int sumatoria(int a, int b)
    {
    return a + b;
    }

    sumatoria(10, 20);


    int multiplicacion(int a, int b)
    {
    return a * b;
    }

    Console.WriteLine(multiplicacion(3, 200));

    Console.ReadLine();

    int division(int a, int b)
    {
    return a / b;
    }

    Console.WriteLine(division(10, 2));

    Console.ReadLine();

    int resta(int a, int b)
    {
    return a - b;
    }
    Console.WriteLine(resta(10, 2));

    Console.ReadLine();

    int modulo(int a, int b)
    {
    return a % b;
    }
    Console.WriteLine(modulo(10, 3));

```
# que es 

Es la declaración e invocación de Funciones Locales (Métodos). Una función es un bloque de código reutilizable que recibe datos de entrada (parámetros), realiza un cálculo o proceso y devuelve un valor de salida mediante la palabra clave return.

# como funciona

1. Declaración de Funciones (int sumatoria(int a, int b)):

-   int (al inicio): Especifica el tipo de dato que la función devolverá al finalizar.
-   sumatoria, multiplicacion, etc.: Es el nombre de la función.
-   (int a, int b): Define los parámetros o datos requeridos que la función necesita recibir para trabajar. 
-   return: Devuelve el resultado calculado al punto desde donde fue llamada la función.

3.  Evaluación bloque por bloque:

-   sumatoria(10, 20);: Se llama a la función, esta realiza $10 + 20 = 30$ y lo devuelve. No se imprime en consola porque no está envuelta dentro de un Console.WriteLine().

-   Console.WriteLine(division(10, 2));: Ejecuta $10 \div 2 = 5$ e imprime el resultado.
-   Console.ReadLine();: Pausa la consola y espera un Enter.
-   Console.WriteLine(resta(10, 2));: Ejecuta $10 - 2 = 8$ e imprime el resultado.
-   Console.ReadLine();: Pausa la consola y espera un Enter.
-   Console.WriteLine(modulo(10, 3));: Calcula el residuo de $10 \div 3$, dando 1, e imprime el resultado.  

# que apare cera en la consola

El programa mostrará los resultados de forma secuencial, avanzando cada vez que presiones la tecla Enter:

Paso 1: Tras llamar a la multiplicación, se muestra el resultado y la consola se detiene:

1.  600

# operador: Bucle (Lazo) while y Operador de Decremento (--)

```csharp

    Console.ReadLine();

    int entero10 = 10;
    int emergencia = 1;

    while (entero10 >= emergencia)
    {
    Console.WriteLine(entero10);
    entero10--;
    }

    Console.ReadLine();

```
# que es 

Es un programa que implementa un bucle o ciclo repetitivo while. Un bucle while evalúa una condición lógica booleana antes de cada iteración y ejecuta de forma continua el bloque de código contenido entre sus llaves mientras dicha condición se mantenga verdadera (true).

# como funciona

1. Es un programa que implementa un bucle o ciclo repetitivo while. Un bucle while evalúa una condición lógica booleana antes de cada iteración y ejecuta de forma continua el bloque de código contenido entre sus llaves mientras dicha condición se mantenga verdadera (true).

-   Pausa el programa al inicio y espera a que presiones Enter para arrancar el conteo.

3. Declaración de variables de control:

-   int entero10 = 10;: Variable contador inicializada en 10.
-   int emergencia = 1;: Variable límite inicializada en 1.

4. Estructura del bucle while (entero10 >= emergencia):

-   Evalúa la condición: ¿Es el valor de entero10 mayor o igual a emergencia (10 >= 1)?
-   Como la respuesta es true, entra al cuerpo del bucle y ejecuta dos acciones:
    -   1. Console.WriteLine(entero10);: Imprime el valor actual de la variable.
    -   3.  entero10--;: Aplica el operador de decremento, reduciendo en 1 el valor de la variable (10 pasa a ser 9).

-   Vuelve arriba a evaluar la condición nuevamente (9 >= 1, 8 >= 1, etc.).
-   El ciclo se repite disminuyendo la variable en cada vuelta hasta que entero10 llega a 0. En ese punto, 0 >= 1 resulta falso (false) y el bucle termina automáticamente.

5.  Segundo Console.ReadLine();:

-   Pausa la consola al finalizar la cuenta regresiva para mantener los números visibles hasta que vuelvas a presionar Enter.

# que apare cera en la consola

Tras presionar Enter la primera vez, el programa imprimirá una cuenta regresiva del 10 al 1 en líneas separadas y volverá a pausarse:

1.  1,3,4,5,6,7,8,9,10 

# operador: Bucle for, Operador de Incremento (++) y Concatenación de Cadenas

```csharp

    {
    {
    for (int i = 1; i <= 10; i++)
    {
    Console.WriteLine("Número: " + i);
    }
    }
    }
      
```

# que es 

Es un programa que utiliza el bucle o ciclo de repetición for. La estructura for es una de las instrucciones de iteración más comunes en programación; se utiliza cuando se conoce de antemano la cantidad exacta de veces que se desea repetir un conjunto de instrucciones.

# como funciona

1. Estructura del Bucle for (int i = 1; i <= 10; i++):
Consta de tres partes fundamentales dentro de sus paréntesis, separadas por puntos y comas (;):

-   Inicialización (int i = 1): Se ejecuta una sola vez al comenzar el bucle. Crea la variable de control i (contador) con un valor inicial de 1.
-   Condición de permanencia (i <= 10): Se evalúa antes de cada vuelta. Mientras i sea menor o igual a 10, el bucle seguirá ejecutándose.
-   Actualización / Incremento (i++): Se ejecuta al final de cada vuelta. Utiliza el operador de incremento para sumar 1 al valor actual de i en cada paso.

3. Console.WriteLine("Número: " + i);:

-   Utiliza el operador + para concatenar (unir) el texto fijo "Número: " con el valor numérico dinámico de i.
-   Imprime el mensaje resultante en la consola con un salto de línea al final.

4. Bloques entre llaves extra { { ... } }:

-   Las llaves dobles adicionales crean ámbitos (scopes) de código internos opcionales. No afectan la ejecución del bucle for, pero delimitan el alcance visual del bloque.

# que apare cera en la consola

Al ejecutar el bucle, la variable i aumentará secuencialmente de 1 en 1 hasta llegar a 10, imprimiendo el mensaje en cada paso:

1.  Número: 1
3.  Número: 2
4.  Número: 3
5.  Número: 4
6.  Número: 5
7.  Número: 6
8.  Número: 7
9.  Número: 8
10. Número: 9
11. Número: 10



















```csharp
    }
    }
```

(cerrador)