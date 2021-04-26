# Spring Boot

En este documento se muestra lo básico para empezar a usar Spring Boot en Java.

## Fuentes de información

* https://www.baeldung.com/spring-request-param

## Instalación de XAMPP

https://www.apachefriends.org/download.html

Para revisar que funciona, ir a localhost:80 en su navegador.

## Creación de una plantilla de Spring

https://start.spring.io

Siempre inicia con estas dependencias en el pom.xml:

```
<dependencies>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-web</artifactId>
    </dependency>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-test</artifactId>
        <scope>test</scope>
    </dependency>
 </dependencies>
```

## Dependencias más usadas

* Spring Boot DevTools: Casi siempre se usa, mejora el rendimiento.

* Spring Web: También se debe usar.

* MySQL Driver: Para trabajar con MySQL.

* Spring Data Reactive MongoDB: Para trabajar con MongoDB.

* 

## Gitignore por defecto

```
HELP.md
target/
!.mvn/wrapper/maven-wrapper.jar
!**/src/main/**/target/
!**/src/test/**/target/

### STS ###
.apt_generated
.classpath
.factorypath
.project
.settings
.springBeans
.sts4-cache

### IntelliJ IDEA ###
.idea
*.iws
*.iml
*.ipr

### NetBeans ###
/nbproject/private/
/nbbuild/
/dist/
/nbdist/
/.nb-gradle/
build/
!**/src/main/**/build/
!**/src/test/**/build/

### VS Code ###
.vscode/
```

## Archivo principal por defecto

```
package com.example.demo;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class DemoApplication {

    public static void main(String[] args) {
        SpringApplication.run(DemoApplication.class, args);
    }

}

```

## Ejemplo de hola mundo

Los strings que se retornan deben tratarse como HTML, no como Java.

```
package com.example.demo;

import org.springframework.web.bind.annotation.*;

@RestController
@RequestMapping(value = "/api")
public class HolaMundoController {

    @GetMapping(value = "/holamundo")
    public String desplegarHolaMundo() {
        return "Hola mundo";
    }

}
```

Ejemplo de uso:
http://localhost:8080/api/holamundo

## Ejemplo con un parámetro

```
package com.example.demo;

import org.springframework.web.bind.annotation.*;

@RestController
@RequestMapping(value = "/api")
public class CuadradoController {

    @GetMapping(value = "/cuadrado")
    public String desplegarId(@RequestParam int x) {
        return "Cuadrado: " + Math.pow(x, 2);
    }

}
```

Ejemplo de uso:
http://localhost:8080/api/cuadrado
http://localhost:8080/api/cuadrado?x=15

## Ejemplo con múltiples parámetros

```
package com.example.demo;

import org.springframework.web.bind.annotation.*;

@RestController
@RequestMapping(value = "/api")
public class IdController {

    @GetMapping(value = "/id")
    public String desplegarId(@RequestParam int id, @RequestParam String nombre) {
        // Nota importante: HTML no reconoce \n, pero <br> si
        return "Nombre: " + nombre + "<br>ID: " + id;
    }

}
```

Ejemplo de uso:
http://localhost:8080/api/id?nombre=Juan&id=1234
http://localhost:8080/api/id?id=1234&nombre=Juan

## Ejemplo con parámetros opcionales

```
package com.example.demo;

import org.springframework.web.bind.annotation.*;

@RestController
@RequestMapping(value = "/api")
public class NombreController {

    @GetMapping(value = "/nombre")
    public String desplegarNombre(@RequestParam(required = false) String nombre) {
        return "Nombre: " + nombre;
    }

}
```

Ejemplo de uso:
http://localhost:8080/api/id?nombre=Felipe
http://localhost:8080/api/id

## Ejemplo con valores por defecto

```
package com.example.demo;

import org.springframework.web.bind.annotation.*;

@RestController
@RequestMapping(value = "/api")
public class TestController {

    @GetMapping(value = "/test")
    public String desplegarNombre(@RequestParam(defaultValue = "Test") String nombre) {
        return "Nombre: " + nombre;
    }

}
```

Ejemplo de uso:
http://localhost:8080/api/test?nombre=Francisca
http://localhost:8080/api/test

## Ejemplo usando mapas

```
package com.example.demo;

import org.springframework.web.bind.annotation.*;

import java.util.Map;

@RestController
@RequestMapping(value = "/api")
public class MapController {

    @GetMapping(value = "/map")
    public String desplegarParametros(@RequestParam Map<String, String> parametros) {
        // Después se puede trabajar con ellos usando sus claves
        return "Parámetros ingresados: " + parametros.entrySet();
    }

}
```

Ejemplo de uso:
http://localhost:8080/api/map/?pi=3.14&e=2.71&phi=1.61

## Ejemplo de parámetros con valores múltiples

```
package com.example.demo;

import org.springframework.web.bind.annotation.*;

import java.util.List;

@RestController
@RequestMapping(value = "/api")
public class SumaController {

    @GetMapping(value = "/suma")
    public String desplegarSuma(@RequestParam List<Integer> numeros) {
        int suma = 0;

        for (int n : numeros) {
            suma += n;
        }

        return "Números ingresados: " + numeros.toString() + "<br>Suma: " + suma;
    }

}
```

Ejemplo de uso:
http://localhost:8080/api/suma?numeros=10,20,30,45
http://localhost:8080/api/suma?numeros=10&numeros=20&numeros=30&numeros=45