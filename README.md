# ci-cd-skils

## Ejecución del proyecto: devsecops-web-scaffolding-poc

descargué el proyecto y tuve problemas para iniciarlo, resolví de la siguiente forma:

- ejecutando 'npm install' me daba problemas de permisos
- agregué 'sudo' al comando de 'npm' para ejecutarlo
- activé self service para poder ejercutarlo
- tuve probelmas con la carpeta 'cache' así que googleando agregué estas lineas de codigo al 'package.json'

```javascript
  "eslintConfig": {
    "cache": true,
    "cacheLocation": "path/to/your/cache",
```

se agregó la carpeta `node_modules` ejecutando la app en localhost, procedí luego a probar el comando `npm build` y generó la carpeta `build` con la app compilada y por ultimo ejecuté `npm rest` probando el script de `App.test.js`