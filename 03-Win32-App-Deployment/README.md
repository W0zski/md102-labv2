# Projekt 3 – Win32 Application Deployment med Microsoft Intune

## Sammanfattning

I det här projektet paketerade och distribuerade jag 7-Zip som en Win32-applikation via Microsoft Intune. Installationsfilen konverterades till `.intunewin`, laddades upp till Intune och konfigurerades med silent install/uninstall, requirements, detection rule och required assignment.

## Mål

Målet var att genomföra hela livscykeln för en klassisk Win32-app i Intune: från paketering av installationsfilen till automatisk distribution och verifierad installation på en Windows 11-endpoint.

## Paketering

Installationsfilen `7z2603-x64.exe` paketerades med Microsoft Win32 Content Prep Tool.

![Intunewin package](./images/01-intunewin-package-created.png)

Resultatet blev en `.intunewin`-fil som kunde laddas upp till Intune.

## Appkonfiguration i Intune

![App information and program](./images/02-app-information-program.png)

```text
Install command:
7z2603-x64.exe /S

Uninstall command:
"C:\Program Files\7-Zip\Uninstall.exe" /S

Install behavior:
System
```

## Requirements, detection och assignment

![Requirements detection assignment](./images/03-requirements-detection-assignment.png)

- Architecture: x64
- Minimum OS: Windows 10 1607 eller senare
- Detection: `C:\Program Files\7-Zip`
- Assignment: Required till `Windows Devices` med `Windows 11 filter`

## Deployment-resultat

![App overview installed](./images/04-app-overview-installed.png)

## Device install status

![Device install status](./images/05-device-install-status.png)

CI3 rapporterar appversion `26.03` med status **Installed**.

## Verifiering på endpointen

![7-Zip installed on endpoint](./images/06-endpoint-7zip-installed.png)

## Resultat

Projektet visar ett komplett Win32-flöde: paketering, upload, silent installation, kravkontroll, detection, grupp-/filtertilldelning, deployment monitoring och lokal verifiering.

## Kompetenser som demonstreras

- Microsoft Win32 Content Prep Tool
- `.intunewin` packaging
- Win32 app management i Intune
- Silent install och uninstall
- x64/OS requirements
- Detection rules
- Required assignments
- Intune assignment filters
- Device install status
- Endpoint-verifiering
