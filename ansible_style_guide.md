# Ansbile Styleguide

## Variables

Usaremos el estilo "snake case":

- Mal:
``` Nombre-Variable 
    NombreVariable
    nombreVariable
    nombrevariable```

- Bien:
``` nombre_variable ```

## Escritura de los playbooks

Como cabecera se usarán tres guiones.
Se usarán dos espacios como indentación. No se permitirá el uso de _hard tabs_.
Los bloques se separarán con un salto de línea.
El separador llave-valor (:) estarán pegados a la llave y se dejará un espacio para el valor.
Como booleano usaremos *True* o *False*, en vez de "yes" o "no"
Usaremos comillas simples para los strings
Variables de entorno en Mayusculas

- Mal:
```
- name: Configurar nginx
	hosts : www
	become: "yes"
	roles :
  		- nginx
- name: Configurar mariadb
	hosts : mariadb
	become: "yes"
	roles :
		- mariadb
```

- Bien:
```
---
- name: 'Configurar nginx'
  hosts: 'www'
  become: True
  roles:
  - nginx

- name: 'Configurar mariadb'
  hosts: 'mariadb'
  become: True
  roles:
  - mariadb
```

## Multilíneas

Se usará el símbolo > para indicar el inicio de una multilínea. Se indentará con un nivel más.

- Mal:
```
- string: |
  Esto es una
  prueba de
  multilínea
´´´

- Bien:
´´´
- string: >
  Esto es una
  prueba de
  multilínea
´´´
