
## Pasos seguidos

1. **Configuración de Nginx**: 
   - Se creó un archivo `nginx.conf` dentro del directorio `config` que define cómo Nginx debe balancear las solicitudes entre los dos servicios web.

2. **Servicios Web**:
   - Se crearon dos directorios, `web1` y `web2`, cada uno conteniendo un archivo `index.js` que define un servidor web simple en Node.js.
   - Cada directorio también contiene un `Dockerfile` que especifica cómo construir la imagen Docker para ese servicio web.

3. **Docker Compose**:
   - Se creó un archivo `docker-compose.yml` en el directorio principal que define tres servicios: `nginx`, `web1` y `web2`.
   - El servicio `nginx` utiliza la imagen oficial de Nginx y monta el archivo `nginx.conf` desde el directorio `config`.
   - Los servicios `web1` y `web2` se construyen a partir de los respectivos directorios y exponen el puerto 80.

4. **Ejecución**:
   - Se ejecutó el comando `docker compose up` para iniciar los contenedores.
   - Al acceder a `localhost:8088` en un navegador, el balanceador de carga Nginx muestra alternadamente los sitios web1 y web2.

## Uso

1. Asegúrate de tener Docker y Docker Compose instalados en tu máquina.
2. Navega al directorio `balanceador_ngix`.
3. Ejecuta `docker compose up`.
4. Abre un navegador y visita `localhost:8088` para ver el balanceo de carga en acción.

balanceador-docker-nginx-node/
│
├── config/
│ └── nginx.conf # Configuración de Nginx para el balanceo de carga
│
├── web1/
│ ├── Dockerfile # Dockerfile para construir la imagen del servicio web1
│ └── index.js # Código fuente del servicio web1
│
├── web2/
│ ├── Dockerfile # Dockerfile para construir la imagen del servicio web2
│ └── index.js # Código fuente del servicio web2
│
└── docker-compose.yml # Archivo de configuración de Docker Compose# balanceador-docker-nginx-node
