---
title: Proteggere i PC e i Mac Windows 10 non gestiti
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
description: Proteggersi da tentativi di phishing e altri attacchi con Microsoft 365 per le campagne.
ms.openlocfilehash: 3e0c6a52209c56e75c6ff1210f26e6926e4d7d32
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527139"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a>Proteggere i PC e i Mac Windows 10 non gestiti

È possibile gestire Windows 10 PC e Mac eseguendo la registrazione in Microsoft Intune, che consente di verificare che siano integri e sicuri prima di accedere ai dati nell'ambiente in uso. Tuttavia, molte campagne e piccole aziende includono personale che porta i propri dispositivi (BYOD), che non verranno gestiti dall'organizzazione. Per questi PC e Mac non gestiti, utilizzare questo articolo per verificare che siano configurate le funzionalità di sicurezza minime. 

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a>Proteggere un computer che esegue Windows 10 o un Mac

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365, or a Mac, the Microsoft 365 protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
Se il PC o Mac Windows 10 non è gestito dall'organizzazione, assicurarsi di configurare queste funzionalità di sicurezza.

## <a name="windows-10"></a>[Windows 10](#tab/Windows10)
**Attivazione della crittografia del dispositivo**<p>

La crittografia del dispositivo è disponibile su una vasta gamma di dispositivi Windows e consente di proteggere i dati crittografati. Se si attiva la crittografia del dispositivo, solo gli utenti autorizzati saranno in grado di accedere al dispositivo e ai dati. Per istruzioni, vedere [abilitare la crittografia del dispositivo](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) .

 Se la crittografia del dispositivo non è disponibile nel dispositivo, è possibile abilitare invece la [crittografia BitLocker](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) standard. (BitLocker non è disponibile in Windows 10 Home Edition). 


**Protezione del dispositivo con sicurezza di Windows**<p>
Se si dispone di Windows 10, è possibile ottenere la protezione antivirus più recente con sicurezza di Windows. Quando si avvia Windows 10 per la prima volta, Windows Security è attivo e contribuisce attivamente alla protezione del PC tramite la ricerca di malware (software dannoso), virus e minacce alla sicurezza. La sicurezza di Windows utilizza la protezione in tempo reale per analizzare tutto quello che scarichi o Esegui nel PC.

Windows Update Scarica automaticamente gli aggiornamenti per la sicurezza di Windows per mantenere il PC sicuro e proteggerlo dalle minacce.

Se si dispone di una versione precedente di Windows e si utilizza Microsoft Security Essentials, è consigliabile passare alla sicurezza di Windows. Per ulteriori informazioni, vedere [la guida alla protezione del dispositivo con Windows Security](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security).

**Attivazione di Windows Firewall**<p>
È consigliabile eseguire sempre Windows Firewall anche se è stato attivato un altro firewall. La disattivazione di Windows Firewall potrebbe rendere il dispositivo (e la rete, se ne esiste uno) più vulnerabile all'accesso non autorizzato. Per istruzioni, vedere [attivazione o disattivazione di Windows Firewall](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off)

## <a name="mac"></a>[Mac](#tab/Mac)
**Utilizzo di FileVault per crittografare il disco Mac**<p>
La crittografia del disco protegge i dati quando i dispositivi vengono persi o rubati. La crittografia Full-Disk di FileVault consente di impedire l'accesso non autorizzato alle informazioni sul disco di avvio. Per istruzioni, vedere [utilizzare FileVault per crittografare il disco di avvio sul Mac](https://support.apple.com/HT204837) .

**Proteggi il tuo Mac da malware**<p>
Microsoft consiglia di installare e utilizzare un software antivirus affidabile sul Mac. Per un elenco delle opzioni, vedere l'articolo seguente: [Best Mac antivirus 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).

È inoltre possibile ridurre il rischio di malware utilizzando il software solo da origini affidabili. Le impostazioni delle preferenze di sicurezza & privacy consentono di specificare le fonti del software installate sul Mac. Per ulteriori informazioni, vedere [Protect your Mac from malware](https://support.apple.com/kb/PH25087).

**Attiva protezione firewall**<p>
Utilizzare le impostazioni del firewall per proteggere il Mac da contatti indesiderati avviati da altri computer quando si è connessi a Internet o a una rete. Senza questa protezione, il Mac potrebbe essere più vulnerabile all'accesso non autorizzato. Per istruzioni, vedere [informazioni sul firewall dell'applicazione](https://support.apple.com/HT201642) .
