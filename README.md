# Herramientas esenciales

# Iniciar con capacitor
1 - ionic start  nombreProyecto --capacitor
2 - ionic build 
3 - npx cap add android (ios)
4 - npx cap open android 
5 - ionic cap sync 

# Agregar los carpeta resources/ en la raiz del proyecto y sus iconos respectivos:
cordova-res -android --skip-config --copy
cordova-res -ios --skip-config --copy


# IMPORTANTE
# Agregar permiso en Android 8 en adelante:
(agregar en todos los (3) AndroidManifest.xm que aparecen esta linea en dentro de Aplication:
<application
    android:usesCleartextTraffic="true">
    
    
# instalar libreria de sweet dialogos
npm install --save sweetalert2


# Capacitor funciona mejor con estos plugin
1- npm install cordova-sqlite-storage
2- npm install @ionic-native/sqlite
3- ionic cap sync










# Extras: MySQL
# Obtener ultimo id
select MAX(codigo)+1 As codigo FROM TABLA


# Insertar con parámetros personalizado
SELECT MAX(codigo)+1 into @varcodigo FROM TABLA;
INSERT INTO TABLA2 ('campo1', 'campo2', 'campo3') VALUES (NULL, 'nombre14' , CONCAT('user_b01_',@varcodigo))




