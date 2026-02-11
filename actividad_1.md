# ACTIVIDAD1

# Ejercicio 1
En la Figura 2 se muestran los diferentes estados que se pueden representar usando una palabra binaria de 3 bits. Responde la pregunta de la imagen: ¿Cuántos estados diferentes se pueden representar usando N bits?
![ejercicio ](https://confusion-snapper-025.notion.site/image/https%3A%2F%2Fprod-files-secure.s3.us-west-2.amazonaws.com%2F86ff57e3-0a96-46be-a958-59ebefbb5e94%2F311a38c2-f518-4c1d-962a-eb10a024bba2%2FUntitled.png?table=block&id=22be8161-b2a1-80a6-bbb1-d412e9237e60&spaceId=86ff57e3-0a96-46be-a958-59ebefbb5e94&width=1520&userId=&cache=v2)

Respuesta: se pueden representar 2^N estados diferentes.

## Convierte el número decimal 22 a binario.
22/2=11, residuo 0

11/2=5, residuo 1

5/2=2, residuo 1

2/2=1, residuo 0

1/2=0, residuo 1

## ¿Cuál es el resultado en decimal del número binario 10110?  
1*2^4 + 0*2^3 + 1*2^2 + 1*2^1 + 0*2^0 = 22  
Por tanto, el número binario 10110 equivale al decimal 22.

## ¿Qué número binario representa el carácter 'C' en ASCII?
En ASCII, la letra C tiene el valor decimal: 67  
Convertido a binario: 01000011  

## Convierte el número flotante 5.75 a binario (explica los pasos).
Se separa en parte entera y decimal:

Parte entera (5)  
5 en binario es: 101  

Parte decimal (0.75)  
0.75 en binario es: .11

## ¿Cuántos bytes se necesitan para almacenar la palabra “Hola” en ASCII?

En ASCII, cada carácter ocupa 1 byte.  
La palabra “Hola” tiene 4 caracteres:  
H – o – l – a  
4 caracteres × 1 byte = 4 bytes

## ¿Cuántos bits hay en 5 KB?  
1 KB = 1024 bytes
1 byte = 8 bits

Entonces:

5 KB = 5 × 1024 = 5120 bytes
5120 × 8 = 40 960 bits

Respuesta: 40 960 bits.

## Convierte el número decimal 255 a hexadecimal.
Dividimos entre 16: 255/16 = 15 resto 15  
En hexadecimal: 15 = F

Entonces: 255 = FF

## ¿Cuál es el valor hexadecimal de la secuencia binaria 11010110?
Se agrupa el binario en bloques de 4 bits: 1101 0110

Ahora cada grupo a hexadecimal:  
1101 = D  
0110 = 6

# Ejercicios Finales de Repaso

## Explica, en tus propias palabras, por qué es necesario que las computadoras representen los datos en binario.
Pues pienso que es necesario que los ordenadores representen los datos en binario ya que usan electricidad y con un voltaje alto de corriente se puede encender el circuito, es decir con el "1"; y con poco voltaje se apaga el circuito es decir con el "0".

## Convierte el número binario 10011011 a decimal y a hexadecimal.
1*128 + 0*64 + 0*32 + 1*16 + 1*8 + 0*4 + 1*2 + 1*1 = 155 (En decimal)

Agrupamos 1001 1011
1*8 + 0*4 + 0*2 + 1*1 = 9
1*8 + 0*4 + 1*2 + 1*1 = 11=B
9B (Hexadecimal)

## Investiga y describe cómo se representa una imagen en formato PNG en el disco.
Todo PNG empieza con 8 bytes fijos que identifican el formato:  
89 50 4E 47 0D 0A 1A 0A

### Estructura por bloques (chunks)

Después de la firma, el archivo se divide en bloques llamados chunks.
Cada chunk contiene:

Longitud (cuántos bytes tiene)

Tipo (4 letras, por ejemplo IHDR)

Datos

CRC (verificación de errores)

Los principales son:

#### IHDR — Cabecera

Guarda información básica:

ancho y alto en píxeles

profundidad de color

tipo de color (RGB, escala de grises, con alfa, etc.)

método de compresión

#### IDAT — Datos de la imagen

Aquí está la imagen real:

Los valores de los píxeles (colores)

Comprimidos con DEFLATE para ocupar menos espacio

Puede haber varios bloques IDAT.

#### IEND — Fin del archivo

Marca que ya no hay más datos.

### Cómo se representan los colores

Cada píxel se guarda con números binarios que indican su color, por ejemplo:

RGB → rojo, verde y azul

RGBA → incluye transparencia (canal alfa)

Un píxel rojo puro puede ser: 255 0 0  

## Analiza la siguiente situación: ¿Qué sucede si intentas almacenar un número mayor al que puede representar un byte (por ejemplo, 300)? ¿Cómo lo maneja Python?
Un byte = 8 bits, así que puede representar:

Sin signo: 0 a 255

Con signo: −128 a 127 (en complemento a dos)

El número 300 es mayor que 255, así que: no cabe en un byte.

En sistemas de bajo nivel (como C con tipos fijos), esto puede causar:

- overflow (desbordamiento)

- Se pierde información

- El valor “se envuelve” o se produce un error, según el lenguaje.

#### Ejemplo conceptual:
300 mod 256 = 44 → eso es lo que quedaría en 1 byte sin signo.

### ¿Cómo lo maneja Python?

En Python, los enteros (int) no están limitados a 1 byte.

Python usa enteros de precisión arbitraria, es decir:

- Automáticamente usa más bytes en memoria.

- No ocurre overflow normal al hacer x = 300.