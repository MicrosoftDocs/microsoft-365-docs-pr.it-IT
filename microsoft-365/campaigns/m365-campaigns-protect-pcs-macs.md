---
title: Proteggere i PC Windows 10 e Mac non gestiti
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Proteggi i dispositivi non gestiti o bring-your-own (BYOD) con Microsoft 365.
ms.openlocfilehash: 40e94e2f961ab34827de4ce5e43e100af53a7340
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227500"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a>Proteggere i PC Windows 10 e Mac non gestiti

Puoi gestire Windows 10 PC e Mac registrandoli in Microsoft Intune, che ti consente di assicurarti che siano integri e sicuri prima di accedere ai dati nel tuo ambiente. Tuttavia, molte campagne e piccole aziende includono personale che porta i propri dispositivi (BYOD), che non verranno gestiti dall'organizzazione. Per questi PC e Mac non gestiti, usa questo articolo per assicurarti che le funzionalità di sicurezza minime siano configurate.

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a>Proteggere un computer che esegue Windows 10 o un Mac

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365, or a Mac, the Microsoft 365 protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
Se il Windows 10 PC o Mac non è gestito dall'organizzazione, assicurati di configurare queste funzionalità di sicurezza.

## <a name="windows-10"></a>[Windows 10](#tab/Windows10)

**Attivare la crittografia del dispositivo**<p>

La crittografia dei dispositivi è disponibile in un'ampia gamma di Windows e consente di proteggere i dati crittografando i dati. Se si attiva la crittografia del dispositivo, solo gli utenti autorizzati potranno accedere al dispositivo e ai dati. Per [istruzioni, vedi Attivare la crittografia](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) del dispositivo.

 Se la crittografia del dispositivo non è disponibile nel dispositivo, puoi attivare la crittografia [BitLocker](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) standard. BitLocker non è disponibile nell'Windows 10 Home edizione. 

**Proteggere il dispositivo con Sicurezza di Windows**<p>
Se si dispone Windows 10, si otterrà la protezione antivirus più recente con Sicurezza di Windows. Quando si avvia Windows 10 per la prima volta, Sicurezza di Windows è attivo e aiuta attivamente a proteggere il PC mediante la ricerca di malware (software dannoso), virus e minacce alla sicurezza. Sicurezza di Windows usa la protezione in tempo reale per analizzare tutto ciò che scari clici o esegui sul PC.

Windows Update scarica automaticamente gli aggiornamenti per Sicurezza di Windows per proteggere il computer e difenderlo dalle minacce.

Se si dispone di una versione precedente di Windows e si utilizza Microsoft Security Essentials, è buona idea passare a Sicurezza di Windows. Per altre informazioni, vedi [proteggere il dispositivo con Sicurezza di Windows](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security).

**Attivare Windows firewall**<p>
Dovresti sempre eseguire Windows Firewall anche se hai un altro firewall attivato. La disattivazione Windows firewall potrebbe rendere il dispositivo (e la rete, se ne hai uno) più vulnerabile agli accessi non autorizzati. Per [istruzioni, Windows attivare o disattivare](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) firewall.

## <a name="mac"></a>[Mac](#tab/Mac)

**Usare FileVault per crittografare il disco Mac**<p>
La crittografia del disco protegge i dati quando i dispositivi vengono persi o rubati. La crittografia su disco completo di FileVault consente di impedire l'accesso non autorizzato alle informazioni sul disco di avvio. Per [istruzioni, vedi usare FileVault per crittografare il disco di avvio sul Mac.](https://support.apple.com/HT204837)

**Proteggere il mac da malware**<p>
Microsoft consiglia di installare e usare software antivirus affidabile sul Mac. Vedi l'articolo seguente per un elenco di scelte: [Best Mac antivirus 2019](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).

È inoltre possibile ridurre il rischio di malware utilizzando software solo da fonti affidabili. Le impostazioni in Impostazioni & preferenze privacy consentono di specificare le origini del software installato nel Mac. Per altre informazioni, vedi [Proteggere il Mac da malware.](https://support.apple.com/kb/PH25087)

**Attivare la protezione firewall**<p>
Usa le impostazioni del firewall per proteggere il Mac da contatti indesiderati avviati da altri computer quando sei connesso a Internet o a una rete. Senza questa protezione, il Mac potrebbe essere più vulnerabile agli accessi non autorizzati. Per [istruzioni, vedere Firewall applicazioni.](https://support.apple.com/HT201642)
