# React Native

### 1. Actualizar React Native y dependencias:
Asegúrate de tener la última versión de React Native y sus dependencias instaladas. Puedes usar el siguiente comando para actualizar tu proyecto:

```
npx react-native upgrade
```

### 2. Limpiar la caché:
Si estás experimentando problemas extraños después de una actualización o cambio, limpiar la caché puede ayudar. Utiliza los siguientes comandos:

```
watchman watch-del-all
rm -rf node_modules
rm -rf /tmp/haste-map-react-native-packager-*
npm cache clean --force
npm install
```

### 3. Instalar pods para iOS:
Si estás desarrollando una aplicación para iOS, asegúrate de instalar los pods:

```
cd ios && pod install && cd ..
```

### 4. Eliminar archivos de "metro-cache":
Metro es el paquete de JavaScript que utiliza React Native. A veces, la caché de Metro puede causar problemas. Elimina los archivos "metro-cache":

```
rm -rf $TMPDIR/metro-*
```

### 5. Actualizar Xcode y Android Studio:
Asegúrate de tener la última versión de Xcode (para iOS) y Android Studio (para Android) instalada en tu sistema. Mantener actualizados estos IDEs suele resolver problemas de compatibilidad.

### 6. Reiniciar el servidor de Metro:
En ocasiones, el servidor de Metro puede colgarse o no actualizarse correctamente. Reiniciarlo puede ayudar:

```
npx react-native start --reset-cache
```

### 7. Usar Rosetta para emuladores Android en Mac M1:
Si estás utilizando una Mac con chip M1 y experimentas problemas con los emuladores de Android, intenta ejecutarlos a través de Rosetta:

```
arch -x86_64 /path/to/android-studio/sdk/emulator/emulator -avd <EMULATOR_NAME>
```

### 8. Cambiar el uso de Flipper en iOS:
Si tienes problemas con Flipper en iOS en una Mac con chip M1, cambia temporalmente el uso de Flipper para evitar conflictos:
En AppDelegate.m, comenta o elimina las líneas que importan y usan Flipper:

```
#if defined(FB_SONARKIT_ENABLED) && !defined(DEBUG)
  // #import <FlipperKit/FlipperKit.h>
  // #import <FlipperKitLayoutPlugin/FlipperKitLayoutPlugin.h>
  // #import <FlipperKitUserDefaultsPlugin/FKUserDefaultsPlugin.h>
#endif
```

### 9. Actualizar CocoaPods:
Si estás experimentando problemas con CocoaPods en iOS, asegúrate de tener la última versión instalada:

```
sudo gem install cocoapods
```

### 10. Verificar cambios de API:
A veces, las actualizaciones de React Native introducen cambios en la API. Asegúrate de consultar las notas de la versión y actualizar tu código en consecuencia.
