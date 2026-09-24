# Projekt 2 – BitLocker och Windows LAPS med Microsoft Intune

## Sammanfattning

I det här projektet konfigurerade jag BitLocker och Windows LAPS via Microsoft Intune för Windows 11-enheter. Målet var att centralisera diskkryptering och lokal administratörshantering, tilldela konfigurationerna med grupp och filter samt verifiera att de fungerade på endpointen.

## Mål

- Kräva BitLocker-kryptering på Windows 11.
- Konfigurera TPM/startup- och recovery-inställningar.
- Distribuera policyn till rätt enheter.
- Konfigurera Windows LAPS med backup till Microsoft Entra ID.
- Skapa och hantera ett lokalt administratörskonto automatiskt.
- Verifiera BitLocker och LAPS på klienten och i Intune.

## Windows LAPS-konfiguration

![LAPS configuration](./images/01-laps-configuration.png)

## BitLocker – grundinställningar

![BitLocker base settings](./images/02-bitlocker-base-settings.png)

## BitLocker – OS drive / TPM

![BitLocker OS drive settings](./images/03-bitlocker-os-drive-settings.png)

## BitLocker – recovery

![BitLocker recovery settings](./images/04-bitlocker-recovery-settings.png)

## Deployment-status för BitLocker

![BitLocker deployment status](./images/05-bitlocker-deployment-status.png)

## Deployment-status för LAPS

![LAPS deployment status](./images/06-laps-deployment-status.png)

## Windows 11 assignment filter

![Windows 11 assignment filter](./images/07-windows-11-assignment-filter.png)

```text
(device.operatingSystemVersion -ge 10.0.22000)
```

## Fixed och removable drives

![Fixed and removable drive defaults](./images/08-fixed-removable-drive-defaults.png)

## Verifiering – BitLocker

![BitLocker enabled on endpoint](./images/09-bitlocker-enabled-endpoint.png)

## Verifiering – Windows LAPS

![LAPS password verification](./images/10-laps-password-verification.png)

## Resultat

Projektet visar central säkerhetskonfiguration med BitLocker och Windows LAPS, riktad deployment med assignment filter samt lokal och central verifiering.

## Kompetenser som demonstreras

- BitLocker management via Intune
- TPM/startup policy
- Recovery configuration
- Windows LAPS
- Automatic Account Management
- Microsoft Entra ID password backup
- Password rotation
- Assignment filters
- Policy deployment monitoring
- Endpoint-verifiering
