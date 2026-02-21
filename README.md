# Cifrador César y Atbash

## Descripción General

Este proyecto consiste en el desarrollo de una herramienta web interactiva que implementa los algoritmos clásicos de cifrado César y Atbash utilizando aritmética modular sobre conjuntos de caracteres configurables.

La aplicación permite cifrar, descifrar y analizar mensajes empleando distintos espacios de caracteres basados en el estándar ASCII, incluyendo conjuntos personalizados definidos por el usuario.

El propósito del proyecto es comprender el funcionamiento matemático de los cifrados monoalfabéticos y demostrar sus vulnerabilidades frente a ataques de fuerza bruta y análisis de frecuencia, dentro del contexto de la materia Seguridad en Sistemas.

---

## Enlaces del Proyecto

🔹 Documentación (Google Doc):  
https://docs.google.com/document/d/1s8G7u3OESyaKuHT8GfsaTmfZac2ooU77XHZa4mRbFjo/edit?usp=sharing  

🔹 Repositorio Oficial:  
https://github.com/KenpachiRyu/cifrador-cesar-atbash.git  

🔹 Código Fuente Principal (index.html):  
https://github.com/KenpachiRyu/cifrador-cesar-atbash/blob/main/index.html  

🔹 Aplicación Web Desplegada (GitHub Pages):  
http://kenpachiryu.github.io/cifrador-cesar-atbash/

---

## Fundamento Matemático

### Cifrado César

El cifrado César se basa en un desplazamiento modular dentro de un conjunto de tamaño N.

Fórmula implementada:

nuevo = (indice + k) mod N

Donde:
- indice es la posición del carácter dentro del conjunto seleccionado.
- k es el módulo (desplazamiento).
- N es el tamaño del conjunto activo.

El sistema valida dinámicamente el rango del módulo bajo la condición:

1 ≤ k ≤ N − 1

Esto garantiza que el desplazamiento sea matemáticamente correcto y reversible.

Para descifrar, se aplica el desplazamiento inverso:

nuevo = (indice + (N − k)) mod N

---

### Cifrado Atbash

El cifrado Atbash es una transformación simétrica que invierte el orden del conjunto activo.

Fórmula implementada:

nuevo = (N − 1) − indice

Este método no utiliza módulo y su propiedad principal es la simetría: aplicar Atbash dos veces devuelve el texto original.

---

## Conjuntos de Caracteres

La aplicación permite seleccionar distintos espacios modulares:

- ASCII completo (caracteres 32–126).
- Solo letras (A–Z, a–z).
- Letras y números (A–Z, a–z, 0–9).
- Conjunto personalizado definido por el usuario.

En el conjunto personalizado:

- Se eliminan caracteres duplicados automáticamente.
- Se valida que N ≥ 2.
- El rango del módulo se ajusta dinámicamente al tamaño del conjunto.
- Se garantiza coherencia matemática en el desplazamiento modular.

Esto permite experimentar con distintos tamaños de espacio de claves y observar cómo cambia el comportamiento del cifrado.

---

## Detección Automática de Cifrado

El sistema incluye un módulo de detección que:

1. Ejecuta fuerza bruta sobre todos los desplazamientos posibles del cifrado César.
2. Evalúa cada resultado mediante una heurística basada en:
   - Frecuencia de letras comunes del español.
   - Presencia de vocales.
   - Aparición de palabras frecuentes.
   - Penalización por exceso de símbolos.

Además, se evalúa la transformación Atbash y se comparan puntuaciones, mostrando los resultados más probables.

Este enfoque se inspira en los principios del análisis de frecuencia descritos por Al-Kindi en el siglo IX.

---

## Seguridad y Limitaciones

Aunque el tamaño del conjunto puede variar, estos algoritmos no son seguros en el contexto moderno:

- El espacio de claves es reducido.
- La fuerza bruta es computacionalmente trivial.
- El análisis de frecuencia permite descifrar textos largos sin conocer la clave.
- Son cifrados monoalfabéticos vulnerables a ataques estadísticos.

Este proyecto tiene fines educativos y demostrativos dentro del estudio de la seguridad informática.

---

## Tecnologías Utilizadas

- HTML5  
- CSS3  
- JavaScript (Vanilla)  
- GitHub Pages para despliegue web  

---

## Información Académica

Nombre del estudiante: Héctor Oswaldo Villegas Pérez  
Materia: Seguridad en Sistemas  
Fecha: 20/02/2026  

---
