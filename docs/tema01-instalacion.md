# Tema 01: Instalacion con Docker

| | |
|---|---|
| **Fecha de inicio** | 09/11/2026 |
| **Fecha de fin** | 16/11/2026 |
| **Tiempo dedicado** | 1 horas |
| **Rama de Git** | `tema01` |

---

## 1. 🎯 Objetivo del tema

Instalación del proyecto con Docker y cración del proyecto Laravel
---

## 2. 🛠️ Desarrollo paso a paso

<!-- Un apartado por cada paso importante. Para cada uno:
     - Qué haces y POR QUÉ.
     - El comando o el código, en un bloque de código (nunca como captura).
     - Una captura solo si aporta algo visual (navegador, resultado, estructura...). -->

### 2.1 Creacion de vistas

se van a crear 3 vistas llamadas: home, about y contact

### 2.2 Definición de rutas
Se modifica el fichero *routes/web.php* de la ssiguiente forma:

```php
 Route::view('/', 'home')->name('home');
 Route::view('/about', 'about')->name('about');
 Route::view('/contact', 'contact')->name('contact');

```

---

## 3. 📋 Resumen de comandos utilizados

| Comando | Para qué sirve |
|---------|----------------|
| ` | ... |
| `composer ...` | ... |
| `docker-composer ...` | ... |

---

## 4. 🐞 Problemas encontrados y soluciones

<!-- Documenta TODOS los problemas, aunque te parezcan tontos.
     Copia el error como texto, no como captura.
     Si no has tenido ningún problema, documenta al menos algo que hayas tenido que investigar. -->

### Problema 1: Comprobacion del funcionamiento de laravel despues de su instalación 

**Qué estaba haciendo:** Comprovar el correcto funcionamiento de laravel una vez creado el proyecto básico

**Error:**

```
Problema de servicios
```

**Causa:** Posible problema de servicios

**Solución:**

Ejecutamos en una terminar los siguientes commandos

```bash

docker exec -it proyecto-php-1 bash
	php artisan key:generate
	chmod -R 775 storage bootstrap/cache
	chown -R www-data:www-data storage bootstrap/cache
```
Posteriormente será necesario añadir en fichero .em la siguiente configuración

```bash
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=test
DB_USERNAME=alumno
DB_PASSWORD=alumno
SESSION_DRIVER=file

```


**Fuente:** chat GPT



## 5. ✅ Resultado final

<!-- Captura(s) de la aplicación funcionando al terminar el tema. -->

Vista "about.blade.php"
![Descripción de la captura](img/temaXX/01-descripcion.png)

Visya "home.balde.php"
![Descripción de la captura](img/temaXX/01-descripcion.png)
Visya "contact.balde.php"
![Descripción de la captura](img/temaXX/01-descripcion.png)

---

## 6. 💭 Conclusiones

- **Qué he aprendido:** ...
- **Qué me ha costado más:** ...
- **Qué haría diferente / dudas pendientes:** ...
