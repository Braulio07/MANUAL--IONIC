# Herramientas esenciales

# consultar dark mode o ligth mode
https://ionicframework.com/docs/native/theme-detection

# Paletas de colores
https://ionicframework.com/docs/theming/color-generator


# Font Awesome en ionic
(1)
npm i @fortawesome/angular-fontawesome
npm i @fortawesome/fontawesome-svg-core
npm i @fortawesome/free-solid-svg-icons
npm i @fortawesome/free-regular-svg-icons
npm i @fortawesome/free-brands-svg-icons


(2) importarlo en nuestro App.Module princiar y en el import:
import { FontAwesomeModule, FaIconLibrary } from '@fortawesome/angular-fontawesome';
import { fas } from '@fortawesome/free-solid-svg-icons'
import { far } from '@fortawesome/free-regular-svg-icons'
import { fab } from '@fortawesome/free-brands-svg-icons'

@NgModule({
	declarations: [AppComponent],
	entryComponents: [],
	imports: [BrowserModule, IonicModule.forRoot(), AppRoutingModule, FontAwesomeModule],
 
 
(3)
export class AppModule {
  constructor(library: FaIconLibrary) { 
		library.addIconPacks(fas, fab, far);
	}
}


(4) importarlo en el modulo de nuestra page
import { FontAwesomeModule } from '@fortawesome/angular-fontawesome'

@NgModule({
  imports: [
    FontAwesomeModule,
    
   
 (5) y finalmente usarlo en nuestro html
   <fa-icon icon="home"></fa-icon>
    
    




# Importar AJAX
npm install jquery  
npm install @types/jquery

import * as $ from "jquery";


# Libreria para descargar fichero Txt
npm install file-saver --save
bower install file-saver




# Install cocoapods, para poder elumar ios
brew install cocoapods

# Intalar npx primera vez:
npm install -g npx


# PLUGIN PARA COMPARTIR REDES SOCIALES

//OFICIAL IONIC. (recomendado)
npm install cordova-plugin-x-socialsharing
npm install @ionic-native/social-sharing
ionic cap sync
enlace de uso ionic:   https://ionicframework.com/docs/native/social-sharing
enlace de uso terceros:   https://itelisoft.com/social-sharing-ionic-3/


npm install @ionic-native/social-sharing@4
npm install cordova-plugin-x-socialsharing


# Correccion error sqlite app 
npm install --save @ionic-native/core

# cuando se descargan proyectos de git
npm install

# Corregir Error con libreria y Dependencias
npm install --save @ionic-native/core

# Agregar libreria Firebase (notificaciones Push)
npm add @angular/fire
npm install firebase@latest

# Para obtener el token de mi dispositivo
npm install cordova-plugin-fcm-with-dependecy-updated
npm install @ionic-native/fcm
ionic cap sync


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

# Corregir problema npm de node primera vez,    Y CARPETA RESOURCES:
(PRIMERO)  sudo chown -R $USER /usr/local/lib/node_modules
1-   mkdir ~/.npm-global                    (Make a directory for global installations)
2-   npm config set prefix '~/.npm-global'  (Configure npm to use the new directory path:)
3-   export PATH=~/.npm-global/bin:$PATH    (Open or create a ~/.profile file and add this line:)
4-   sudo chown -R $USER ~/.npm-global   





#                     # CREAR ICONO Y SPLASH
# Agregar los carpeta resources/ en la raiz del proyecto y sus iconos respectivos:
npm i -g cordova-res    (1ra vez)
npm i native-run        (1ra vez)
npm i -g cordova-res    (1ra vez)
npm i cordova-res@latest --save (1ra vez)
ionic cordova resources ios --force
-----------------------LO MISMO DIRECTO -----------
 mkdir ~/.npm-global                  
npm config set prefix '~/.npm-global'  
export PATH=~/.npm-global/bin:$PATH
sudo chown -R $USER ~/.npm-global   
npm i -g cordova-res   
npm i native-run    
npm i -g cordova-res    
npm i cordova-res@latest --save 
ionic cordova resources ios --force
-----------------------FIN LO MISMO DIRECTO -----------

----RECOMENDADO (CREAR LOS IOCONOS)
npm install -g cordova-res
cordova-res -android --skip-config --copy
cordova-res -ios --skip-config --copy


#1- BLUETOOTH
npm install cordova-plugin-bluetooth-serial
npm install @ionic-native/bluetooth-serial
ionic cap sync

#2- BLE
npm install cordova-plugin-ble-central
npm install @ionic-native/ble
ionic cap sync

# FONT BLUETOOTH SERIAL
  // \x1b\x21\x30  texto Grande
  // \x1b\x21\x20  texto Mediano 
  // \x1b\x45\x01  bold
  // \x1b\x21\x00  normal
  // \x1b\x61\x01  center



# __________________ AGREGAR PERMISO DE INTERNET ________________________________________________________________________ 
# IMPORTANTE
# 1 (Agregar permiso en Android 8 en adelante:)
(agregar en todos los (3) AndroidManifest.xm que aparecen esta linea en dentro de Aplication:
<application 
  android:usesCleartextTraffic="true">
    
    
# 2 CORREGIR EL capacitor.config.json de esta forma sin el serve :)
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

# UPDATE Identity a un numero especifico. SQLite 
  public updateSequence(){
    return new Promise((resolve, rejects) => {
      let sql = "UPDATE sqlite_sequence  SET  seq = 105  WHERE name = 'noPedidoUnico';";
      this.db.executeSql(sql).then((data) => {
        resolve(data);
      }, (error) => {
        rejects(error);
      });
    });
  }

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


