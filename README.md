# Microsoft Intune / MD-102 – Teknisk portfolio

**Erik Fors**

Praktisk portfolio med Microsoft Intune, Microsoft Entra ID och Windows 11. Projekten är genomförda i en egen Microsoft 365-testmiljö och visar hela arbetsflöden – från konfiguration och tilldelning till deployment, felsökning och verifiering på endpointen.

## Projekt

| Projekt | Område | Praktiskt resultat |
|---|---|---|
| [01 – Windows Autopilot](./01-Windows-Autopilot/) | Provisionering | Windows 11-enhet registrerad i Autopilot, provisionerad via OOBE, Entra-joined och verifierad som Intune-managed |
| [02 – BitLocker & Windows LAPS](./02-BitLocker-LAPS/) | Endpoint security | BitLocker aktiverat på klienten och Windows LAPS konfigurerat med Entra-backup och lösenordsrotation |
| [03 – Win32 App Deployment](./03-Win32-App-Deployment/) | Applikationshantering | 7-Zip paketerad som .intunewin, distribuerad som Required och verifierad som Installed på endpointen |

## Tekniker och områden

- Microsoft Intune
- Microsoft Entra ID
- Windows Autopilot
- Windows 11 device enrollment
- Enrollment Status Page
- BitLocker
- Windows LAPS
- Intune assignment filters
- Win32 app packaging och deployment
- Detection rules
- Deployment monitoring
- Endpoint-verifiering och felsökning

## Miljö

- Microsoft 365 testtenant
- Microsoft Intune
- Microsoft Entra ID
- Windows 11
- Hyper-V virtuella klienter

## Arbetssätt

Varje projekt dokumenterar:

1. **Mål** – vad lösningen skulle uppnå.
2. **Konfiguration** – vilka inställningar och policies som användes.
3. **Deployment** – hur lösningen tilldelades och distribuerades.
4. **Verifiering** – hur resultatet kontrollerades i Intune och/eller lokalt på klienten.
5. **Resultat** – vad som faktiskt fungerade i testmiljön.

Skärmbilderna är inkluderade som tekniskt bevis på genomförda steg och resultat.

## Nästa områden

Portfolion byggs vidare med fler MD-102-relaterade projekt, bland annat:

- Compliance policies och Conditional Access
- Microsoft Defender / Endpoint Security
- PowerShell och Remediations
- Windows Update / Autopatch

> Miljön används endast för labb och utbildning. Konton, enhetsnamn och identifierare som syns i dokumentationen tillhör testmiljön.
