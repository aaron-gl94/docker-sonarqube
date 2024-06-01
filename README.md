
# Docker Hub
Antes de comenzar, recuerda consultar la imagen de SonarQube oficial: [https://hub.docker.com/_/sonarqube](https://hub.docker.com/_/sonarqube).

Aquí puedes consultar la versión que necesitas para acceder al github y obtener los archivos `Dockerfile` y `entrypoint.sh`.

## Configuración Docker - SonarQube
Dentro de este directorio continua con las siguientes instrucciones:
- Correr en terminal la siguiente línea:
~~~
docker build -t my-sonarqube .
docker run -d -p 8084:9000 sonarqube
~~~

## Configuración SonarQube
- Acceder a [http://localhost:8084](http://localhost:8084). Las credenciales por default son:
    - ***user:*** `admin`
    - ***password:*** `admin`

    **Nota:** En seguida SonarQube te pedirá actualizar la contraseña.

- Seleciona la opción de "Crear Análisis Local".

- Proveer Token:
    - Debes ingresar el nombre del proyecto: `[product-key]`
    - Después se pedirá generar un token, completa el campo el mismo ` [product-key]-token `, para fines prácticos y espera a que se genere tu token para login:
        - `prueba-angular-token: 10c3e8f0f7862938104f450b98041565d0e7fd59`

- Configuración de Análisis:
    - Selecciona la tecnología de building de tu proyecto;
        - `Maven, Gradle, .Net u otras (JS, TS, Go, Python, PHP, ...)`
    - Selecciona el sistema operativo con el cual trabajas:
        - `Linux, Windows o MacOS`
    - En seguida se desplegara un recuadro similar a esto:
    ~~~
    $ sonar-scanner \
    -Dsonar.projectKey=prueba-angular \
    -Dsonar.sources=. \
    -Dsonar.host.url=http://localhost:8084 \
    -Dsonar.login=10c3e8f0f7862938104f450b98041565d0e7fd59
    ~~~

    - Este script hay que ejecutarlo en la carpeta de nuestro proyecto.

