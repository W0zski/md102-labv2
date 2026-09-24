# Projekt 2 – BitLocker och Windows LAPS med Microsoft Intune

## Sammanfattning

I det här projektet konfigurerade jag två centrala säkerhetsfunktioner för Windows 11 via Microsoft Intune: **BitLocker** för diskkryptering och **Windows LAPS** för säker hantering av lokala administratörslösenord.

Projektet omfattade policykonfiguration, grupp- och filtertilldelning, deployment monitoring samt verifiering både centralt i Intune och lokalt på endpointen.

## Mål

- Kräva BitLocker-kryptering på Windows 11.
- Konfigurera TPM-, startup- och recovery-inställningar.
- Rikta konfigurationen till Windows 11-enheter med ett Intune assignment filter.
- Konfigurera Windows LAPS med backup till Microsoft Entra ID.
- Skapa och hantera ett lokalt administratörskonto automatiskt.
- Verifiera att BitLocker var aktiverat.
- Verifiera att LAPS-lösenordet hade säkerhetskopierats och roterades.

## Windows LAPS

### Konfiguration

Windows LAPS konfigurerades med backup av det lokala administratörslösenordet till **Microsoft Entra ID**.

Jag använde **Automatic Account Management** för att skapa och hantera ett nytt lokalt administratörskonto:

```text
Account name: WLapsAdmin
Password age: 30 days
Password length: 14
Backup directory: Microsoft Entra ID
```

Kontot hanteras automatiskt av Windows LAPS och lösenordet roteras enligt policyn.

### Verifiering

I Intune verifierade jag att `WLapsAdmin` hade ett lagrat lösenord samt registrerade datum för senaste och nästa lösenordsrotation. Själva lösenordet visas inte i portfolion.

## BitLocker

### Grundkonfiguration

BitLocker-policyn konfigurerades för att kräva device encryption på Windows-klienten.

### Operating System Drive

Jag konfigurerade inställningar för operativsystemsenheten, bland annat:

- TPM/startup-beteende
- startup authentication
- PIN-relaterade inställningar
- recovery-konfiguration

### Recovery

Recovery-inställningarna användes för att styra hur BitLocker recovery-information hanteras i den testade konfigurationen.

## Assignment och Windows 11-filter

Både BitLocker- och LAPS-konfigurationerna tilldelades till gruppen **Windows Devices**.

Ett Intune assignment filter användes för att rikta konfigurationerna mot Windows 11:

```text
(device.operatingSystemVersion -ge 10.0.22000)
```

Det visar hur en bred enhetsgrupp kan kombineras med ett dynamiskt filter för mer precis targeting.

## Deployment monitoring

I Intune följde jag policyernas status efter deployment:

- BitLocker: **2 Succeeded, 0 Error, 0 Conflict**
- LAPS: **Succeeded utan Error eller Conflict** i den verifierade deploymenten

## Endpoint-verifiering

På Windows-klienten verifierades att:

```text
C: BitLocker på
```

Det gav ett lokalt bevis på att krypteringen faktiskt var aktiv och inte bara att policyn hade skapats i portalen.

## Skärmbilder och bevis

Den samlade bilden nedan visar LAPS-konfigurationen, BitLocker-inställningar, deployment-status, Windows 11-filtret, lokal BitLocker-verifiering och LAPS-verifiering i Intune.

[Öppna bilden i full storlek](./images/evidence.webp)

![Projekt 2 – BitLocker och Windows LAPS, samlad dokumentation](./images/evidence.webp)

## Resultat

Projektet visar hur Intune kan användas för att centralt styra både diskkryptering och lokala administratörskonton. Konfigurationerna tilldelades selektivt till Windows 11-enheter, följdes upp i Intune och verifierades på endpointen.

## Kompetenser som demonstreras

- BitLocker management via Microsoft Intune
- TPM- och startup-konfiguration
- BitLocker recovery settings
- Windows LAPS
- Automatic Account Management
- Microsoft Entra ID password backup
- Password rotation
- Intune assignment filters
- Policy assignment och monitoring
- Endpoint-verifiering
- Grundläggande felsökning av Intune/LAPS

[← Tillbaka till portfolioöversikten](../README.md)
