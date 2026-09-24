# Projekt 3 – Win32 Application Deployment med Microsoft Intune

## Sammanfattning

I det här projektet paketerade och distribuerade jag **7-Zip 26.03 (x64)** som en Win32-applikation med Microsoft Intune. Projektet omfattade hela flödet från en vanlig `.exe`-installer till en automatiskt distribuerad och verifierad applikation på en Windows 11-endpoint.

## Mål

- Paketera en klassisk Windows-applikation till `.intunewin`.
- Konfigurera silent installation och avinstallation.
- Sätta arkitektur- och OS-krav.
- Skapa en detection rule.
- Distribuera appen som **Required**.
- Använda samma Windows 11-filter som i övriga projekt.
- Verifiera installationen både i Intune och på klienten.

## 1. Paketering

Installationsfilen:

```text
7z2603-x64.exe
```

paketerades med **Microsoft Win32 Content Prep Tool** till:

```text
7z2603-x64.intunewin
```

Den färdiga `.intunewin`-filen användes som app package file i Intune.

## 2. App information och program

Applikationen skapades i Intune som:

```text
Name: 7-Zip 26.03 (x64)
Publisher: Igor Pavlov
Version: 26.03
Install behavior: System
```

### Install command

```cmd
7z2603-x64.exe /S
```

### Uninstall command

```cmd
"C:\Program Files\7-Zip\Uninstall.exe" /S
```

Parametern `/S` används för silent installation/avinstallation så att deploymenten inte kräver att slutanvändaren klickar igenom en installationsguide.

## 3. Requirements

Applikationen begränsades till:

- **Architecture:** x64
- **Minimum OS:** Windows 10 1607 eller senare

Det säkerställer att x64-installern endast erbjuds till kompatibla Windows-enheter.

## 4. Detection rule

Jag skapade en manuell file-based detection rule som kontrollerar att 7-Zip finns installerat under:

```text
C:\Program Files\7-Zip
```

Detection rules används av Intune för att avgöra om installationen faktiskt lyckades och om appen redan finns på enheten.

## 5. Assignment

Appen tilldelades som **Required** till:

```text
Group: Windows Devices
Filter mode: Include
Filter: Windows 11 filter
```

Det innebär att Intune automatiskt installerar appen på enheter som matchar tilldelningen, utan att användaren behöver installera den manuellt från Company Portal.

## 6. Deployment monitoring

Efter deployment visade appens Overview:

```text
Installed: 1
Not installed: 0
Failed: 0
Install pending: 0
Not applicable: 0
```

Under **Device install status** rapporterade klienten `CI3`:

```text
App version: 26.03
Status: Installed
```

## 7. Verifiering på endpointen

På Windows 11-klienten verifierades slutresultatet lokalt genom att **7-Zip File Manager** fanns installerad och tillgänglig i Start-menyn.

Det bekräftar hela kedjan:

```text
EXE
  ↓
IntuneWinAppUtil
  ↓
.INTUNEWIN
  ↓
Microsoft Intune
  ↓
Required assignment
  ↓
Silent installation
  ↓
Detection rule
  ↓
Installed / verifierad på endpoint
```

## Skärmbilder och bevis

Den samlade bilden nedan visar paketeringen, appkonfigurationen, requirements, detection rule, assignment, Intune-status och lokal verifiering på CI3.

[Öppna bilden i full storlek](./images/evidence.webp)

![Projekt 3 – Win32 Application Deployment, samlad dokumentation](./images/evidence.webp)

## Resultat

Projektet resulterade i en fungerande Win32-deployment där 7-Zip paketerades, distribuerades automatiskt, identifierades med en detection rule och rapporterades som installerad i Intune. Installationens resultat verifierades även direkt på klienten.

## Kompetenser som demonstreras

- Microsoft Win32 Content Prep Tool
- `.intunewin` packaging
- Win32 app management i Microsoft Intune
- Silent install och uninstall
- System-context deployment
- Architecture och OS requirements
- Detection rules
- Required assignments
- Intune assignment filters
- Device install monitoring
- Endpoint-verifiering

[← Tillbaka till portfolioöversikten](../README.md)
