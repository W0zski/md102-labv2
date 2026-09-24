# Projekt 1 – Windows Autopilot med Microsoft Intune

## Sammanfattning

I det här projektet byggde och verifierade jag ett komplett användardrivet Windows Autopilot-flöde i en egen Microsoft 365-testmiljö. En Windows 11-enhet registrerades med hardware hash, fick en distributionsprofil, genomförde OOBE med organisationsinloggning och blev automatiskt ansluten till Microsoft Entra ID och hanterad av Microsoft Intune.

## Mål

- Registrera en Windows 11-enhet i Windows Autopilot.
- Tilldela en **User-driven** Autopilot-profil.
- Använda **Microsoft Entra join**.
- Styra provisioneringen med **Enrollment Status Page (ESP)**.
- Genomföra organisationsstyrd OOBE.
- Registrera Windows Hello for Business.
- Verifiera deploymenten både i Intune och lokalt på klienten.

## Genomförande

### 1. Hardware hash och Autopilot-registrering

Jag samlade in enhetens hardware hash och registrerade enheten i Windows Autopilot. Därefter kopplades enheten till rätt deployment-profil.

### 2. Autopilot-profil

Jag skapade en användardriven Autopilot-profil för Windows och tilldelade den till rätt enhetsgrupp. Profilen konfigurerades för Microsoft Entra join och standardanvändare.

### 3. Enrollment Status Page

Enrollment Status Page användes för att hålla kvar användaren i provisioneringsflödet tills nödvändiga appar och profiler hade bearbetats. Det gav kontroll över enhetens setup innan användaren fick tillgång till skrivbordet.

### 4. OOBE

Efter återställning till OOBE hämtade enheten organisationens Autopilot-konfiguration. Användaren möttes av organisationsstyrd inloggning i stället för ett vanligt privat Windows-flöde.

### 5. Provisionering och Windows Update

Under device setup-fasen applicerade Intune tilldelade konfigurationer och Windows Update kördes som en del av provisioneringen.

### 6. Windows Hello for Business

Efter organisationsinloggningen registrerades Windows Hello for Business för användaren.

## Verifiering

Efter deploymenten verifierade jag resultatet på flera nivåer:

- Autopilot deployment report visade lyckad deployment.
- Enheten visades som hanterad i Microsoft Intune.
- Enheten var företagsägd och compliant i testmiljön.
- Lokal kontroll med `dsregcmd /status` bekräftade att enheten var Microsoft Entra joined.

## Skärmbilder och bevis

Bilden nedan sammanställer de viktigaste stegen: Autopilot-profil, ESP, registrerad enhet, OOBE, device setup, Windows Update, Windows Hello, deployment report, Intune-status och lokal `dsregcmd`-verifiering.

[Öppna bilden i full storlek](./images/evidence.webp)

![Projekt 1 – Windows Autopilot, samlad dokumentation](./images/evidence.webp)

## Resultat

Projektet resulterade i en Windows 11-enhet som provisionerades genom Windows Autopilot, anslöts till Microsoft Entra ID och hanterades automatiskt av Intune. Jag verifierade både den centrala Intune-statusen och den lokala enhetsidentiteten.

## Kompetenser som demonstreras

- Windows Autopilot
- Hardware hash-registrering
- Microsoft Intune
- Microsoft Entra ID
- User-driven deployment
- Microsoft Entra join
- Enrollment Status Page
- Windows OOBE
- Windows Hello for Business
- Device enrollment och management
- Deployment monitoring
- Lokal verifiering med `dsregcmd`

[← Tillbaka till portfolioöversikten](../README.md)
