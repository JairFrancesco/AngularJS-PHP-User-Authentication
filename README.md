# AngularJS-PHP-User-Authentication
AngularJS/PHP User Authentication

En este repositorio vamos a ver cómo podemos crear un sistema de autenticación utilizando Json Web Token (JWT), el cliente lo haremos con angularjs y el servidor con php, pero es simple implementarlo con nodejs, laravel, ruby o python.
Siguiendo el siguiente tutorial.
https://www.uno-de-piera.com/autenticacion-con-jwt-php-y-angularjs/


Entonces tendremos lo siguiente:

1.- Un formulario de login para iniciar sesión.
2.- Una vez haga login si las credenciales son correctas crearemos un token con JWT y le daremos 5 minutos de vida.
3.- El token lo devolveremos al cliente (angularjs) y utilizando el módulo angular-jwt podremos decodificar su payload.
4.- Una vez en el cliente y utilizando el módulo angular-storage guardaremos en localStorage el token proporcionado por el servidor para enviarlo en futuras peticiones.
5.- A través del provider jwtInterceptorProvider haremos que de forma automática nuestro token sea envíado en cada petición a través de los headers con un nombre y un prefijo para así capturarlo en el servidor, esto lo podremos hacer de forma dinámica cómo veremos más adelante.
6.- Gracias al método run y al evento $routeChangeStart podremos comprobar si nuestro token ha expirado, y si es así mandaremos al usuario fuera de la aplicación.
7.- Una vez el usuario esté dentro de la aplicación tendremos un botón para hacer una petición al servidor, recoger allí el token, comprobar si el usuario existe y si es así devolver un JSON con una tabla de películas que creareamos.
