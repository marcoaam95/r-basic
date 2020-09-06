1. Si hubiéramos empezado a contar segundos a partir de las 12 campanadas que marcan el inicio de 2018, ¿a qué hora de qué día de qué año llegaríamos a los 250 millones de segundos? ¡Cuidado con los años bisiestos!

    ```r
    segundos <- 2.5e8
    segundos_minuto <- 60
    segundos_hora <- segundos_minuto * 60
    segundos_dia <- segundos_hora * 24



    # Calculamos los días, horas y minutos.

    # Las unidades más pequeñas se calculan a partir de los restos de las unidades mayores.

    # NOTA: Las variables resto_xxx siempre se expresan en segundos.



    dias <- segundos%/%segundos_dia

    resto_dias <- segundos%%segundos_dia

    horas <- resto_dias %/% segundos_hora

    resto_horas <- resto_dias %% segundos_hora

    minutos <- resto_horas %/% segundos_minuto

    segundos <- resto_horas %% segundos_minuto

    # Mostramos la fecha

    print(sprintf("Días: %d, Horas: %d, Minutos: %d, Segundos: %d", dias, horas, minutos, segundos))


    # Si sumamos a la fecha 01/01/2018 00:00:00 obtenemos la fecha 02/12/2025 12:26:40
    ```

2. Cread una función que os resuelva una ecuación de primer grado (de la forma Ax+B=0). Es decir, vosotros tendréis que introducir como parámetros los coeficientes (en orden) y la función os tiene que devolver la solución. Por ejemplo, si la ecuación es 2x+4=0, vuestra función os tendría que devolver -2. Una vez creada la función, utilizadla para resolver las siguientes ecuaciones de primer grado:
    * 5x+3=0
    * 7x+4 = 18
    * x+1 = 1

    ```r
    ecuacion <- function(a, b){
    # Ax + B = 0 -> x = -B/A
    print(-b/a)
    }

    ecuacion(5, 3)

    ecuacion(7, -14)

    ecuacion(1, 0)
    ```

3.  a) Dad una expresión para calcular 3e-π y a continuación, dad el resultado que habéis obtenido con R redondeado a 3 cifras decimales.

    ```r
    print(3*exp(-pi), 3)
    ```

    b) Dad el módulo del número complejo (2+3i)^2/(5+8i) redondeado a 3 cifras decimales.
    ```r
    round(Mod((2+3i)^2/(5+8i)), 3)
    ```
