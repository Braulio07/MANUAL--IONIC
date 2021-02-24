# Herramientas esenciales
# Corregir problema npm de node primera vez:
sudo chown -R $USER /usr/local/lib/node_modules
1-   mkdir ~/.npm-global                    (Make a directory for global installations)
2-   npm config set prefix '~/.npm-global'  (Configure npm to use the new directory path:)
3-   export PATH=~/.npm-global/bin:$PATH    (Open or create a ~/.profile file and add this line:)
4-   sudo chown -R $USER ~/.npm-global   

# Intalar npx primera vez:
npm install -g npx

# cuando se descargan proyectos de git
npm install

# Ionic start
ionic start
ionic start --list
ionic start myApp
ionic start myApp blank
ionic start myApp tabs --cordova
ionic start myApp tabs --capacitor
ionic start myApp super --type=ionic-angular
ionic start myApp blank --type=ionic1
ionic start cordovaApp tabs --cordova
ionic start "My App" blank
ionic start "Conference App" https://github.com/ionic-team/ionic-conference-app



# Iniciar con capacitor
1 - ionic start  nombreProyecto --capacitor
2 - ionic build 
3 - npx cap add android (ios)
4 - npx cap open android 
5 - ionic cap sync 

# Integrar capacitor a proyecto existente:
1 npm install @capacitor/core @capacitor/cli
2 npx cap init
3 ionic build 
4 npx cap add android
5 ionic cap sync
6 npx cap open android


# Emular App en tiempo real Android
ionic capacitor run android -l --host=YOUR_IP_ADDRESS

# Emular App en tiempo real IOS
ionic capacitor run ios -l --external



# Agregar Animate-CSS con npm
 npm install animate.css --save
 
# Libreria comparar dias entre dos fechas: 
npm install --save moment

# Agregar los carpeta resources/ en la raiz del proyecto y sus iconos respectivos:
cordova-res -android --skip-config --copy
cordova-res -ios --skip-config --copy

# __________________ AGREGAR PERMISO DE INTERNET ________________________________________________________________________ 
# IMPORTANTE
# 1 (Agregar permiso en Android 8 en adelante:)
(agregar en todos los (3) AndroidManifest.xm que aparecen esta linea en dentro de Aplication:
<application
    android:usesCleartextTraffic="true">
    
    
 # 2  (CORREGIR EL capacitor.config.json de esta forma sin el serve:)
# ____________________mal____________________________________________ 
 antes......:
 {
  "appId": "com.sisBoa.com",
  "appName": "SisBOA",
  "bundledWebRuntime": false,
  "npmClient": "npm",
  "webDir": "www",
  "plugins": {
    "SplashScreen": {
      "launchShowDuration": 0
    }
  },
  "cordova": {},
  "server": {
    "url": "http://localhost:8100",
    "cleartext": true
  }
}
# __________________bien______________________________________________
despues......:
 {
  "appId": "com.sisBoa.com",
  "appName": "SisBOA",
  "bundledWebRuntime": false,
  "npmClient": "npm",
  "webDir": "www",
  "cordova": {
    "preferences": {
      "ScrollEnabled": "false",
      "android-minSdkVersion": "19",
      "BackupWebStorage": "none",
      "SplashMaintainAspectRatio": "true",
      "FadeSplashScreenDuration": "0",
      "SplashShowOnlyFirstTime": "false",
      "SplashScreen": "none",
      "SplashScreenDelay": "0"
    }
  }
}
# __________________________________________________________________________________________      
    
# Cambiar iconos ionc
<ion-icon color="primary" slot="start" [src]="c.icon"></ion-icon>

# instalar libreria de sweet dialogos
npm install --save sweetalert2

# (SQLIte) Capacitor funciona mejor con estos plugin
1- npm install cordova-sqlite-storage
2- npm install @ionic-native/sqlite
3- ionic cap sync








# **************************************** ...EXTRAS... *********************************************************************************************
# MySQL

--de los mejores qerry: para crear consultas de 3 tablas agrupadas:
https://www.lawebdelprogramador.com/foros/SQL/1349320-QUERY-SUM-VALOR-DE-REGISTRO-DE-OTRA-TABLA.html

# Sum colunma
SELECT SUM(Quantity) AS TotalItems FROM OrderDetails;

# Resetear un IDENTITY a un valor espeficio: (se debe colocar justo el numero por donde vaya: si va por el 1,2,3. se debe colocar el (3)
ALTER TABLE tbl_sample AUTO_INCREMENT = 1

# Obtener ultimo id
select MAX(codigo)+1 As codigo FROM TABLA

# Insertar con parámetros personalizado
SELECT MAX(codigo)+1 into @varcodigo FROM TABLA;
INSERT INTO TABLA2 ('campo1', 'campo2', 'campo3') VALUES (NULL, 'nombre14' , CONCAT('user_b01_',@varcodigo))

# Update Tabla1.total = sum(columna) from Tabla2
$comando = "UPDATE TABLA_1 o INNER JOIN ( SELECT campo_id, SUM(subTotal) 'sumu'
FROM TABLA_2  GROUP BY campo_id) i ON o.campo_id = i.campo_id SET o.totalPrincipal = i.sumu";


