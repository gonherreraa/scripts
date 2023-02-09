# Actividad 6.1

#### Ejercicio 1
```bash
#!/bin/bash

read num

if [ ${num} > 0 ]
then              
        echo "Es positivo"
fi
````
### Ejercicio 2
```bash
#!/bin/bash
read num

if [ $num -lt 0 ] 
then
        echo  "Es negativo"
fi
````
### Ejercicio 3
```bash
#!/bin/bash

read num

if [ $num -eq 0 ] 
then
        echo "Igual a 0"
fi

````
### Ejercicio 4
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

### Ejercicio 5
```bash
#!/bin/bash

if [ $# -eq 3 ]
then
        echo "Hay 3 parametros"
else
        echo "error"
fi

````

### Ejercicio 6
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
### Ejercicio 7
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
### Ejercicio 8
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

### Ejercicio 9
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

### Ejercicio 10
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
### Ejercicio 11
```bash
#!/bin/bash

for (( i=1; i <= 50; i++ ))
do
        echo "hola"
done
````

### Ejercicio 12
```bash
#!/bin/bash

for ((i=1; i<= 10; i++))
do
        echo "introduce una palabra"
        read pal
        echo "la palabra es: $pal"
done

````

### Ejercicio 13
```bash
#!/bin/bash

for (( i=0; i<=${1}; i++))
do
        echo "hola"
done
````

### Ejercicio 14
```bash
#!/bin/bash

for (( i=0; i<=${1};i++ ))
do
        echo "$i"
done
````

### Ejercicio 15
```bash
#!/bin/bash

total=0

for (( i=0; i<=${1};i++ ))
do
        total=$(( $total + $i ))

done
        echo "el total es: ${total}"
````
### Ejercicio 16
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
### Ejercicio 17
```bash
#!/bin/bash

echo "Introduce una palabra"
read n

while [ $n != ':q' ] 
do
        read n
done
````

### Ejercicio 18
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

### Ejercicio 19
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
### Ejercicio 20
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
