# Projekt 1 – Windows Autopilot med Microsoft Intune

## Sammanfattning

I det här projektet konfigurerade jag en Windows 11-enhet med Windows Autopilot och Microsoft Intune. Målet var att genomföra hela provisioneringsflödet från registrerad hårdvara till en fullt hanterad och Microsoft Entra-joined klient.

## Mål

- Registrera enheten i Windows Autopilot.
- Tilldela en användardriven Autopilot-profil.
- Styra OOBE och Enrollment Status Page.
- Genomföra Microsoft Entra Join.
- Verifiera att enheten blev Intune-managed.
- Kontrollera join-status lokalt med `dsregcmd /status`.

## Autopilot-profil

![Autopilot profile](./images/01-autopilot-profile.png)

## Enrollment Status Page

![Enrollment Status Page](./images/02-enrollment-status-page.png)

## Enhetsregistrering

![Autopilot device registration](./images/03-autopilot-device-registration.png)

## OOBE och organisationsinloggning

![OOBE organization sign-in](./images/04-oobe-organization-signin.png)

## Device setup

![OOBE device setup](./images/05-oobe-device-setup.png)

## Uppdatering under provisionering

![Windows update during provisioning](./images/06-windows-update-during-provisioning.png)

## Windows Hello for Business

![Windows Hello for Business](./images/07-windows-hello-for-business.png)

## Deployment-resultat

![Autopilot deployment report](./images/08-autopilot-deployment-report.png)

## Verifiering i Intune

![Intune managed device](./images/09-intune-managed-device.png)

## Lokal verifiering

![dsregcmd verification](./images/10-dsregcmd-verification.png)

## Resultat

Projektet visar ett komplett Autopilot-flöde från registrering och profil till OOBE, Entra Join, Intune management och lokal verifiering.

## Kompetenser som demonstreras

- Windows Autopilot
- Microsoft Intune
- Microsoft Entra ID
- User-driven deployment
- Enrollment Status Page
- OOBE
- Windows Hello for Business
- Device enrollment och management
- Lokal felsökning/verifiering med `dsregcmd`
