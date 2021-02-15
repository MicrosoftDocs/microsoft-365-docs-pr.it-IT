---
title: Proteggere i PC Windows 10 e Mac non gestiti
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
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
description: Proteggere i dispositivi non gestiti o bring-your-own (BYOD) con Microsoft 365.
ms.openlocfilehash: 5c27b29b5bb4fb445655e671d8c654ad8e9abc6b
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044385"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a>Proteggere i PC Windows 10 e Mac non gestiti

Puoi gestire PC e Mac Windows 10 registrandoli in Microsoft Intune, che ti consente di assicurarti che siano integri e sicuri prima di accedere ai dati nel tuo ambiente. Tuttavia, molte campagne e piccole aziende includono personale che porta i propri dispositivi (BYOD), che non verrà gestito dall'organizzazione. Per questi PC e Mac non gestiti, usa questo articolo per assicurarti che le funzionalità di sicurezza minime siano configurate.

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a>Proteggere un computer che esegue Windows 10 o un Mac

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365, or a Mac, the Microsoft 365 protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
Se il PC Windows 10 o il Mac non è gestito dall'organizzazione, assicurati di configurare queste funzionalità di sicurezza.

## <a name="windows-10"></a>[Windows 10](#tab/Windows10)

**Attivare la crittografia del dispositivo**<p>

La crittografia dei dispositivi è disponibile su un'ampia gamma di dispositivi Windows e consente di proteggere i dati crittografando i dati. Se si attiva la crittografia del dispositivo, solo gli utenti autorizzati saranno in grado di accedere al dispositivo e ai dati. Per [istruzioni, vedi attivare la crittografia](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) del dispositivo.

 Se la crittografia del dispositivo non è disponibile nel dispositivo, puoi attivare la crittografia [BitLocker](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) standard. BitLocker non è disponibile in Windows 10 Home Edition. 

**Proteggere il dispositivo con sicurezza di Windows**<p>
Se si dispone di Windows 10, si otterrà la protezione antivirus più recente con Sicurezza di Windows. Quando si avvia Windows 10 per la prima volta, la sicurezza di Windows è attiva e contribuisce attivamente alla protezione del PC mediante la ricerca di malware (software dannoso), virus e minacce alla sicurezza. Sicurezza di Windows usa la protezione in tempo reale per analizzare tutti gli elementi scaricati o eseguiti nel PC.

Windows Update scarica automaticamente gli aggiornamenti per Sicurezza di Windows per proteggere il computer e difenderlo dalle minacce.

Se hai una versione precedente di Windows e stai usando Microsoft Security Essentials, è una buona idea passare a Sicurezza di Windows. Per altre informazioni, vedi [la guida alla protezione del dispositivo con Sicurezza di Windows.](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security)

**Attivare Windows Firewall**<p>
È consigliabile eseguire sempre Windows Firewall anche se è attivato un altro firewall. La disattivazione di Windows Firewall potrebbe rendere il dispositivo (e la rete, se ne hai uno) più vulnerabile all'accesso non autorizzato. Per [istruzioni, vedere Attivare o disattivare Windows Firewall](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off)

## <a name="mac"></a>[Mac](#tab/Mac)

**Usare FileVault per crittografare il disco Mac**<p>
La crittografia del disco protegge i dati quando i dispositivi vengono smarriti o rubati. La crittografia su disco completo di FileVault consente di impedire l'accesso non autorizzato alle informazioni sul disco di avvio. Per istruzioni, vedi usare [FileVault per crittografare il disco di avvio nel Mac.](https://support.apple.com/HT204837)

**Proteggere il mac da malware**<p>
Microsoft consiglia di installare e utilizzare software antivirus affidabile nel Mac. Vedi l'articolo seguente per un elenco di scelte: [Best Mac antivirus 2019. ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/)

È inoltre possibile ridurre il rischio di malware utilizzando software solo da fonti affidabili. Le impostazioni nelle preferenze & privacy consentono di specificare le origini del software installato nel Mac. Per altre informazioni, vedi [proteggere il Mac da malware.](https://support.apple.com/kb/PH25087)

**Attivare la protezione firewall**<p>
Usa le impostazioni del firewall per proteggere il Mac da contatti indesiderati avviati da altri computer quando sei connesso a Internet o a una rete. Senza questa protezione, il Mac potrebbe essere più vulnerabile ad accessi non autorizzati. Per [istruzioni, vedere il firewall](https://support.apple.com/HT201642) applicazioni.
