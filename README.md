# LINK Control

Repositorio privado del código Android de LINK Control (antes AppControl), compañero de NOVORA-LINK.

Estado de fuente sincronizado el 19 de octubre de 2026: **1.4.113 / código 113**, paquete `com.novora.appcontrol`, Android 11/API 30 o posterior, Release ARM64.

## Código y compilación

El proyecto está en `src/NOVORA.Android/NLProjectAndroid.csproj`. `src/NOVORA` contiene únicamente contratos, utilidades y recursos enlazados necesarios para Android y sus pruebas; no es una copia del escritorio completo.

Requiere .NET 10 y la carga de trabajo Android. Verificar el código sin generar una nueva APK:

```powershell
dotnet workload restore src/NOVORA.Android/NLProjectAndroid.csproj
dotnet build src/NOVORA.Android/NLProjectAndroid.csproj -c Release -r android-arm64 -t:Compile -p:AndroidBuildApplicationPackage=false
./scripts/Test-NOVORA-CI.ps1 -Configuration Release
```

CI compila y ejecuta pruebas de contrato; no instala, firma ni publica APK, ni valida sesiones físicas USB/LAN. No se versionan bin/obj ni claves de firma. El desarrollo canónico continúa en NOVORA-LINK.

## Política de distribución

Conservar cada APK publicada desde 1.4.110 como release independiente `v<versionName>`, con APK firmada, `NLAndroidRelease.json` y SHA256SUMS. No reemplazar activos históricos ni reconstruirlos desde fuentes posteriores. La APK original 1.4.110 continúa pendiente de localizar. La publicación registrada de 1.4.111 se conserva; subir fuente 1.4.113 no publica su APK.

Toda APK nueva requiere N+1, firma compatible y comprobación de manifiesto/hash/certificado. Nunca publicar keystores, contraseñas o tokens. El canal privado requiere autorización individual; el actualizador Android permanece como propuesta y no se incorpora por subir este código.
