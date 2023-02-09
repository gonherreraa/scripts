# Actividad 6.1

#### Ejercicio 1- Recibir un número entero por teclado y decir si es positivo.
```bash
#!/bin/bash

read num

if [ ${num} > 0 ]
then              
        echo "Es positivo"
fi
````
### Ejercicio 2- Recibir un número entero por teclado y decir si es negativo.
```bash
#!/bin/bash
read num

if [ $num -lt 0 ] 
then
        echo  "Es negativo"
fi
````
### Ejercicio 3- Recibir un número entero por teclado y decir si es igual a cero.
```bash
#!/bin/bash

read num

if [ $num -eq 0 ] 
then
        echo "Igual a 0"
fi

````
### Ejercicio 4- Recibir un numero entero por teclado y decir si es positivo, negativo o cero.
```bash
#!/bin/bash

read num

if [ $num -eq 0 ]
then 
        echo "Es igual a 0"
elif [ $num -gt 0 ]
then
        echo "Es positivo"
else
        echo "Es negativo"
fi
````

### Ejercicio 5- Comprobar si el número de parámetros introducido es igual a 3, en el caso de que sea otro número mostrará un mensaje de error por pantalla.
```bash
#!/bin/bash

if [ $# -eq 3 ]
then
        echo "Hay 3 parametros"
else
        echo "error"
fi

````

### Ejercicio 6- Recibir dos números por parámetros y lo suma. En caso de que el número de parámetros sea incorrecto mostrará un mensaje de error.
```bash
#!/bin/bash

if [ $# -eq 2 ]
then
        total=$((${1}+${2}))
        echo "La suma es: $total"
else
        echo "error"
fi
````
### Ejercicio 7- Recibir 3 parámetros. En el caso de que reciba un número diferente mostrará un mensaje de error. Los dos primeros serán dos números y el tercero será uno de los siguientes símbolos “+” “-“ “x” “/”, dependiendo del tercer parámetro introducido realizara la correspondiente operación. El en caso de que se introduzca un símbolo diferente, presentará un mensaje indicando cuales son las opciones correctas
```bash
#!/bin/bash

if [ $# -eq 3 ]; then
        if [[ ${1} =~ ^[0-9]+$ && ${2} =~ ^[0-9]+$ ]]; then

        case "$3" in
                '*')
                        total=$(($1 * $2))
                        echo "el resultado es: $total"
                        ;;
                '+')
                        total=$(($1 + $2))
                        echo "el resultado es: $total"
                        ;;
                '-')
                        total=$(($1 - $2))
                        echo "el resultado es: $total"
                        ;;
                '/')
                        total=$(($1 / $2))
                        echo "el resultado es: $total"
                        ;;
        esac
        else 
                echo "Los parametros no son numeros"
        fi
else
        "numero de parametros incorrecto"
fi 
````
### Ejercicio 8- Recibir la ruta de un fichero e indicar si existe
```bash
#!/bin/bash

echo "Intruduce una ruta"
read ruta

if [ -e $ruta ]; then
        echo "La ruta $ruta existe"
else
        echo "No existe"
fi

````

### Ejercicio 9- Recibir la ruta de un fichero e indicar si es un directorio o un fichero.
```bash
#!/bin/bash

echo "Introduce una ruta"
read ruta

if [ -e $ruta ]; then
        if [ -d $ruta ]; then
                echo "Es un directorio"
        else
                echo "Es un fichero"
        fi
else
        echo "La ruta no existe"
fi
````

### Ejercicio 10- Recibir la ruta de un fichero e indicar los permisos que tiene (escritura, lectura, ejecución)
```bash
#!/bin/bash

echo "Introduce el nombre de un fichero"
read nom

if [ -e $nom ]; then
       if [ -r $nom ]; then
               echo "Tiene permisos de lectura"
        fi
        if [ -w $nom ]; then
                echo "Tiene permisos de escritura"
        fi
        if [ -x $nom ]; then
                echo "Tiene permisos de ejecucion"
        fi
else 
        echo "No existe"
fi
````
### Ejercicio 11- Imprimir por pantalla 50 veces la palabra hola.
```bash
#!/bin/bash

for (( i=1; i <= 50; i++ ))
do
        echo "hola"
done
````

### Ejercicio 12- Leer una palabra por teclado y mostrarla por consola. Debe realizar esta operación 10 veces.
```bash
#!/bin/bash

for ((i=1; i<= 10; i++))
do
        echo "introduce una palabra"
        read pal
        echo "la palabra es: $pal"
done

````

### Ejercicio 13- Recibir un número por parámetro. El programa imprimirá la palabra “hola” el número de veces indicado por parámetro.
```bash
#!/bin/bash

for (( i=0; i<=${1}; i++))
do
        echo "hola"
done
````

### Ejercicio 14- Se debe pasar un número n por parámetro. El programa imprimirá los números del 0 al n por pantalla.
```bash
#!/bin/bash

for (( i=0; i<=${1};i++ ))
do
        echo "$i"
done
````

### Ejercicio 15- Recibir un número n por parámetro. El programa tendrá que sumar todos los números entre 1 y n. Posteriormente mostrará el resultado de la suma por pantalla
```bash
#!/bin/bash

total=0

for (( i=0; i<=${1};i++ ))
do
        total=$(( $total + $i ))

done
        echo "el total es: ${total}"
````
### Ejercicio 16- Recibir dos números por parámetro. El programa deberá hacer que el primer parámetro tome el valor del segundo parámetro y el segundo parámetro tome el valor del primero. Por ejemplo si se introduce el 2 y el 9, en un principio $1 es 1 y $2 es 9. Tras la ejecución del programa $1 valdrá 9 y $2 1.
```bash
#!/bin/bash

num1=$1
num2=$2

echo "valor del parametro 1 es: $num1"
echo "valor del parametro 2 es: $num2"
N=$num1

num1=$num2
num2=$N

echo "Ahora el parametro 1 es: $num1"
echo "Ahora el parametro 2 es: $num2"
````
### Ejercicio 17- Programa que lea palabras hasta que se escriba “:q”
```bash
#!/bin/bash

echo "Introduce una palabra"
read n

while [ $n != ':q' ] 
do
        read n
done
````

### Ejercicio 18- Programa que lea palabras y las guarde en un fichero, hasta que se escriba “:q”
```bash
#!/bin/bash

echo "escribe una palabra"
read n

while [ $n != ':q' ]
do
        read n
        echo $n >> ejercicio18.txt
done
        cat ejercicio18.txt
````    

### Ejercicio 19- Programa que lea palabras y las guarde en un fichero de forma ordenada, hasta que se escriba “:q”
```bash
#!/bin/bash

echo "escribe una palabra"
read n

while [ $n != ':q' ]
do
        read n 
        echo $n >> ejercicio19.txt
        sort -o ejercicio19.txt ejercicio19.txt
done
        cat ejercicio19.txt
````
### Ejercicio 20- Realiza un programa que solicite un número y compruebe si se encuentre en un archivo llamado números.txt
```bash
#!/bin/bash

echo "introduce un numero"
read num

for i in `cat numeros.txt`
do
        if [ $i -eq $num ]; then
                echo "el numero $i si se encuentra en el fichero"
                exit 0; 
        fi
done
        echo "el numero $num no se encuentra en el fichero"
````
