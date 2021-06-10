---
title: Attributi per i criteri delle barriere informative
description: Questo articolo è un riferimento per gli attributi Azure Active Directory account utente che è possibile utilizzare per definire i segmenti di barriera delle informazioni.
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ee410bf455e770087da7999ad2019c17419a8e00
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919732"
---
# <a name="attributes-for-information-barrier-policies"></a>Attributi per i criteri delle barriere informative

Alcuni attributi in Azure Active Directory possono essere usati per segmentare gli utenti. Dopo aver definito i segmenti, questi segmenti possono essere usati come filtri per i criteri di barriera delle informazioni. Ad esempio, è possibile utilizzare **Department** per definire segmenti di utenti per reparto all'interno dell'organizzazione (presupponendo che nessun singolo dipendente lavori contemporaneamente per due reparti).

In questo articolo viene descritto come utilizzare gli attributi con le barriere di informazioni e viene fornito un elenco di attributi che è possibile utilizzare. Per ulteriori informazioni sugli ostacoli alle informazioni, vedere le risorse seguenti:

- [Barriere informative](information-barriers.md)
- [Definire i criteri per le barriere in Microsoft Teams](information-barriers-policies.md)
- [Modificare (o rimuovere) i criteri delle barriere informative](information-barriers-edit-segments-policies.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a>Come usare gli attributi nei criteri di barriera delle informazioni

Gli attributi elencati in questo articolo possono essere utilizzati per definire o modificare segmenti di utenti. I segmenti definiti fungono da parametri (denominati *valori UserGroupFilter)* nei [criteri di barriera delle informazioni.](information-barriers-policies.md)

1. Determinare l'attributo che si desidera utilizzare per definire i segmenti. Vedere la [sezione Riferimenti](#reference) in questo articolo.

2. Assicurati che agli account utente siano stati inseriti valori per gli attributi selezionati nel passaggio 1. Visualizzare i dettagli dell'account utente e, se necessario, modificare gli account utente in modo da includere i valori degli attributi. 

    - Per modificare più account (o usare PowerShell per modificare un singolo account), vedere [Configure user account properties with Office 365 PowerShell](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md).

    - Per modificare un singolo account, vedere [Add or update a user's profile information using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).

3. [Definire i segmenti utilizzando PowerShell](information-barriers-policies.md#define-segments-using-powershell), in modo analogo agli esempi seguenti:

    |**Esempio**|**Cmdlet**|
    |:----------|:---------|
    | Definire un segmento denominato Segment1 utilizzando l'attributo Department | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"` |
    | Definire un segmento denominato SegmentA utilizzando l'attributo MemberOf (si supponga che questo attributo contenga nomi di gruppo, ad esempio "BlueGroup") | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"` |
    | Definire un segmento denominato DayTraders usando ExtensionAttribute1 (si supponga che questo attributo contenga titoli di lavoro, ad esempio "DayTrader") | `New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

    > [!TIP]
    > Quando definisci i segmenti, usa lo stesso attributo per tutti i segmenti. Ad esempio, se si definiscono alcuni segmenti utilizzando *Department*, definire tutti i segmenti utilizzando *Department*. Non definire alcuni segmenti usando Department e *altri* *usando MemberOf*. Assicurati che i segmenti non si sovrappongano; ogni utente deve essere assegnato esattamente a un segmento.

## <a name="reference"></a>Riferimenti

Nella tabella seguente sono elencati gli attributi che è possibile utilizzare con le barriere di informazioni.

|**Azure Active Directory proprietà <br/> (nome visualizzato LDAP)**|**Exchange proprietà**|
|:---------------------------------------------------------------|:-------------------------|
| Co | Co |
| Company | Company |
| Reparto | Reparto |
| ExtensionAttribute1 | CustomAttribute1 |
| ExtensionAttribute2 | CustomAttribute2 |
| ExtensionAttribute3 | CustomAttribute3 |
| ExtensionAttribute4 | CustomAttribute4 |
| ExtensionAttribute5 | CustomAttribute5 |
| ExtensionAttribute6 | CustomAttribute6 |
| ExtensionAttribute7 | CustomAttribute7 |
| ExtensionAttribute8 | CustomAttribute8 |
| ExtensionAttribute9 | CustomAttribute9 |
| ExtensionAttribute10 | CustomAttribute10 |
| ExtensionAttribute11 | CustomAttribute11 |
| ExtensionAttribute12 | CustomAttribute12 |
| ExtensionAttribute13 | CustomAttribute13 |
| ExtensionAttribute14 | CustomAttribute14 |
| ExtensionAttribute15 | CustomAttribute15 |
| MSExchExtensionCustomAttribute1 | ExtensionCustomAttribute1 |
| MSExchExtensionCustomAttribute2 | ExtensionCustomAttribute2 |
| MSExchExtensionCustomAttribute3 | ExtensionCustomAttribute3 |
| MSExchExtensionCustomAttribute4 | ExtensionCustomAttribute4 |
| MSExchExtensionCustomAttribute5 | ExtensionCustomAttribute5 |
| MailNickname | Alias |
| PhysicalDeliveryOfficeName | Office |
| PostalCode | PostalCode |
| ProxyAddresses | EmailAddresses |
| StreetAddress | StreetAddress |
| TargetAddress | ExternalEmailAddress |
| UsageLocation | UsageLocation |
| UserPrincipalName | UserPrincipalName |
| Posta | WindowsEmailAddress |
| Descrizione | Descrizione |
| MemberOf | MemberOfGroup |

## <a name="resources"></a>Risorse

- [Definire i criteri per le barriere in Microsoft Teams](information-barriers-policies.md)
- [Risoluzione dei problemi relativi alle barriere informative](information-barriers-troubleshooting.md)
- [Barriere informative](information-barriers.md)