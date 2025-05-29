# SKLauncher-fedora

Paso 1: Descargar SKLauncher 3.2.12
Ve a la página oficial y descarga manualmente:
bash# Crear directorio
mkdir ~/SKLauncher
cd ~/SKLauncher

# Abrir navegador para descargar manualmente
firefox https://skmedix.pl/downloads
O descarga directamente (si funciona):
bashwget -O SKlauncher-3.2.12.jar "https://skmedix.pl/downloads/launcher/latest"
Paso 2: Verificar descarga
bashls -la ~/SKLauncher/
Paso 3: Crear script de ejecución
bashnano ~/SKLauncher/run_sklauncher.sh
Contenido:
bash#!/bin/bash
export GDK_BACKEND=x11
export QT_QPA_PLATFORM=xcb
cd ~/SKLauncher
java -Djava.awt.headless=false -Dawt.toolkit=sun.awt.X11.XToolkit -jar SKlauncher-*.jar
Paso 4: Dar permisos y ejecutar
bashchmod +x ~/SKLauncher/run_sklauncher.sh
~/SKLauncher/run_sklauncher.sh
