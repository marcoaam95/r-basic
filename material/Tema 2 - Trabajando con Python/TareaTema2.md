1. Escribe una secuencia de instrucciones que permitan leer un número real por pantalla y que muestre si el número es positivo o no.
    ```python
    # Tomamos 0 como positivo
    numero = float(input('Escribe número'))
    es_positivo = numero>=0
    texto = 'positivo' if es_positivo else 'negativo'

    print('El número es %s' % (texto))
    ```

2. Escribe una secuencia de instrucciones que permitan leer un número real por pantalla y que muestre si el número está en el rango entre -5 y 5

    ```python
    numero = float(input('Escribe número'))
    en_rango = lambda x: x > -5 and x < 5
    print(en_rango(numero))
    ```

3. Escribe una secuencia de instrucciones que permitan leer las coordenadas de un punto (x, y) e indique en cuál de los cuatro cuadrantes se encuentra dicho punto.

    ```python
    # Cuadrante 1: arriba derecha
    # Cuadrante 2: arriba izquierda
    # Cuadrante 3: abajo izquierda
    # Cuadrante 4: abajo derecha

    def cuadrante_punto(x, y):

        if x >= 0:
            return 'cuadrante1' if y>=0 else 'cuadrante4'   
        elif x < 0:
            return 'cuadrante2' if y>0 else 'cuadrante3'

    print(cuadrante_punto(0,0))
    print(cuadrante_punto(1,2))
    print(cuadrante_punto(1,0))
    print(cuadrante_punto(1,-1))
    print(cuadrante_punto(-1, 6))
    print(cuadrante_punto(-3, -7))
    ```

4. Escribe una secuencia de instrucciones que permitan leer dos números enteros y muestre el cociente de la división entera y el resto.
    ```python
    numero1 = int(input('Escriba el primer número entero: '))
    numero2 = int(input('Escriba el segundo número entero: '))
    cociente = numero1//numero2
    resto = numero1%numero2

    print("El cociente es %s y el resto es %s." % (cociente, resto))
    ```

5. Escribe una secuencia de instrucciones que permitan leer un número entero es cuadrado perfecto o no (piensa la mejor forma de hacerlo con lo que has aprendido hasta ahora)
    ```python
    numero = int(input('Número: '))

    # Establecemos rel_tol para que compare con la máximo precisión posible
    print(
        math.isclose(math.sqrt(numero)**2, numero, rel_tol=1e-16)
    )
    ```

6. Escribe una expresión que permita determinar si un número entero positivo puede corresponder a un año bisiesto o no. Se consideran años bisiestos aquellos cuyo número es divisible por cuatro excepto los años que son múltiplos de 100, a no ser que lo sean de 400 (por ejemplo el año 2000 fue bisiesto pero el 2100 no lo será).
    ```python
    numero = int(input('Número: '))

    if numero%400==0 or (numero%4==0 and numero%100!=0):
        print(' Es bisiesto')
    else:
        print('No es bisiesto')
    ```

7. Busca la imagen de un tablero de ajedrez en Google y fíjate en la nomenclatura de las casillas. Escribe una expresión lea una letra y un número de teclado correspondiente a una casilla de un tablero de ajedrez y nos indique si esta casilla es negra o blanca.
    ```python
    # En un tablero de ajedrez donde las letras son a,b,c,d,e,f,g,h y los números 1,2,3,4,5,6,7,8, si asignamos un número de posición (en orden natural, comenzando en 1) en una lista a cada una de las letras vemos que cuando la paridad (es par o impar) del número coincide con la paridad de la posición que ocupa la letra en la lista el cuadrado es negro. Entonces, para todas las combinaciones, cuando haya (par/par, impar/impar) el cuadrado es negro. Por ejemplo: la letra 'd' ocupa la cuarta posición, y si el usuario selecciona el número 5 tendremos que la posición de la letra 'd' es 4, que es par, cuya paridad no coincide con 5, que es impar.

    # Definimos las listas con los valores de los dos ejes del tablero
    letras = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h']
    numeros = [1,2,3,4,5,6,7,8]

    # Obtenemos lo datos del usuario
    letra = input('Introduce la letra de la casilla del tablero: ')
    numero = int(input('Introduce el número de la casilla del tablero: '))

    # Obtenemos el índice que ocupa la letra en la lista y sumamos 1 ya que en Python las listas comienzan en 0 y no en 1
    indice_letra = letras.index(letra) + 1

    # Si las paridades coinciden es negro, en caso contrario es blanco
    es_par = lambda x: 'par' if x%2==0 else 'impar'
    resultado_letra = es_par(indice_letra)
    resultado_numero = es_par(numero)

    if resultado_letra==resultado_numero:
        print('El cuadrado es negro')
    else:
        print('El cuadrado es blanco')
    ```