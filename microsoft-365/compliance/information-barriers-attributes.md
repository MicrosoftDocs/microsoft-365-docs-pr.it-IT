---
title: Attributi per i criteri di barriera delle informazioni
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: Utilizzare questo articolo come riferimento per i vari attributi che è possibile utilizzare nei criteri di barriera delle informazioni.
ms.openlocfilehash: 4198728d412062edced6238604b2b891da22aeac
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083738"
---
# <a name="attributes-for-information-barrier-policies"></a>Attributi per i criteri di barriera delle informazioni

Alcuni attributi in Azure Active Directory possono essere utilizzati per segmentare gli utenti. Una volta definiti i segmenti, tali segmenti possono essere utilizzati come filtri per i criteri di barriera delle informazioni. Ad esempio, è possibile utilizzare **Department** per definire segmenti di utenti per reparto all'interno dell'organizzazione (presupponendo che nessun singolo dipendente funzioni contemporaneamente per due reparti). 

In questo articolo viene descritto come utilizzare gli attributi con barriere informative e viene fornito un elenco degli attributi che è possibile utilizzare. Per ulteriori informazioni sulle barriere informative, vedere le risorse seguenti:
- [Barriere informative](information-barriers.md)
- [Definire i criteri per le barriere informative in Microsoft Teams](information-barriers-policies.md)
- [Modificare (o rimuovere) i criteri di barriera delle informazioni](information-barriers-edit-segments-policies.md.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a>Come utilizzare gli attributi nei criteri di barriere informative

Gli attributi elencati in questo articolo possono essere utilizzati per definire o modificare segmenti di utenti. I segmenti definiti fungono da parametri (denominati valori di *UserGroupFilter* ) nei [criteri di barriera delle informazioni](information-barriers-policies.md).

1. Determinare l'attributo che si desidera utilizzare per definire i segmenti. Vedere la sezione di [riferimento](#reference) in questo articolo.

2. Verificare che per gli account utente siano stati inseriti i valori per gli attributi selezionati nel passaggio 1. Visualizzare i dettagli dell'account utente e, se necessario, modificare gli account utente per includere i valori degli attributi. 

    - Per modificare più account o utilizzare PowerShell per modificare un singolo account, vedere [Configure user account properties with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell).

    - Per modificare un singolo account, vedere [aggiungere o aggiornare le informazioni sul profilo di un utente utilizzando Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).

3. [Definire i segmenti tramite PowerShell](information-barriers-policies.md#define-segments-using-powershell), analogamente agli esempi seguenti:

    |Esempio  |Cmdlet  |
    |---------|---------|
    |Definire un segmento denominato segment1 con l'attributo Department     | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"`        |
    |Definire un segmento denominato Segmenta utilizzando l'attributo member (si supponga che questo attributo contenga nomi di gruppo, ad esempio "BlueGroup").     | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"`        |
    |Definire un segmento denominato DayTraders tramite ExtensionAttribute1 (si supponga che questo attributo contenga titoli di lavoro, ad esempio "DayTrader").|`New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

    > [!TIP]
    > Quando si definiscono i segmenti, utilizzare lo stesso attributo per tutti i segmenti. Ad esempio, se si definiscono alcuni segmenti utilizzando *Department*, definire tutti i segmenti che utilizzano *Department*. Non definire alcuni segmenti con *Department* e altri utenti che utilizzano *member*. Verificare che i segmenti non siano sovrapposti. ogni utente deve essere assegnato a un solo segmento. 

## <a name="reference"></a>Riferimenti

Nella tabella seguente sono elencati gli attributi che è possibile utilizzare con le barriere informative.

|Nome della proprietà di Azure Active Directory<br/>(Nome visualizzato LDAP)  |Nome della proprietà di Exchange  |
|---------|---------|
|Co       | Co        |
|Company     |Company         |
|Reparto     |Reparto         |
|ExtensionAttribute1 |CustomAttribute1  |
|ExtensionAttribute2 |CustomAttribute2  |
|ExtensionAttribute3 |CustomAttribute3  |
|ExtensionAttribute4 |CustomAttribute4  |
|ExtensionAttribute5 |CustomAttribute5  |
|ExtensionAttribute6 |CustomAttribute6  |
|ExtensionAttribute7 |CustomAttribute7  |
|ExtensionAttribute8 |CustomAttribute8  |
|ExtensionAttribute9 |CustomAttribute9  |
|ExtensionAttribute10 |CustomAttribute10  |
|ExtensionAttribute11 |CustomAttribute11  |
|ExtensionAttribute12 |CustomAttribute12  |
|ExtensionAttribute13 |CustomAttribute13  |
|ExtensionAttribute14 |CustomAttribute14  |
|ExtensionAttribute15 |CustomAttribute15  |
|MSExchExtensionCustomAttribute1 |ExtensionCustomAttribute1 |
|MSExchExtensionCustomAttribute2 |ExtensionCustomAttribute2 |
|MSExchExtensionCustomAttribute3 |ExtensionCustomAttribute3 |
|MSExchExtensionCustomAttribute4 |ExtensionCustomAttribute4 |
|MSExchExtensionCustomAttribute5 |ExtensionCustomAttribute5 |
|MailNickname |Alias |
|PhysicalDeliveryOfficeName |Office |
|PostalCode |PostalCode |
|ProxyAddresses |EmailAddresses |
|StreetAddress |StreetAddress |
|TargetAddress |ExternalEmailAddress |
|UsageLocation |UsageLocation |
|UserPrincipalName  |UserPrincipalName  |
|Posta   |WindowsEmailAddress    |
|Descrizione    |Descrizione    |
|MemberOf   |MemberOfGroup  |

## <a name="related-topics"></a>Argomenti correlati

[Definire i criteri per le barriere informative in Microsoft Teams](information-barriers-policies.md)

[Risoluzione dei problemi di barriere informative](information-barriers-troubleshooting.md)

[Barriere informative](information-barriers.md)



