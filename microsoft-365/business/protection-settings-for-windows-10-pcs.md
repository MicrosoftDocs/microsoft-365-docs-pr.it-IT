---
title: Modificare o creare le impostazioni di protezione dei dispositivi Windows 10 PC
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: bd66c26c-73a4-45a8-8642-3ea4ee7cd89d
description: Informazioni sulle impostazioni disponibili in Microsoft 365 per le aziende per proteggere Windows 10 dispositivi.
ms.openlocfilehash: acfb27b2e4592d4ed1e446a63c9495ae07d916de
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578228"
---
# <a name="edit-or-create-device-protection-settings-for-windows-10-pcs"></a>Modificare o creare le impostazioni di protezione dei dispositivi Windows 10 PC

Questo articolo si applica a Microsoft 365 Business Premium.

Dopo aver configurato le impostazioni di protezione Windows predefinite nella pagina Installazione, è possibile aggiungerne di nuove che si applicano a tutti gli utenti o a un set di utenti. Puoi anche modificare uno qualsiasi di quelli che hai creato.

## <a name="create-protection-settings-for-windows-10-devices"></a>Creare impostazioni di protezione per Windows 10 dispositivi

Guarda un video su come proteggere Windows 10 dispositivi con Microsoft 365 Business Premium:
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>. 
2. Nel riquadro di spostamento sinistro scegliere **Criteri** \> **dispositivi** \> **Aggiungi**.
3. Nel riquadro **Aggiungi criterio** immettere un nome univoco per il criterio. 
4. In **Tipo di criterio** scegliere **Configurazione dei dispositivi di Windows 10**.
5. Expand **Secure Windows 10 Devices** \> configure the settings how you would like. Per ulteriori informazioni, vedere [Impostazioni disponibili.](#available-settings) 
    
    È sempre possibile usare il collegamento **Ripristina impostazioni predefinite** per ripristinare l'impostazione predefinita. 
    
    ![Add policy pane with Windows 10 Device configuration selected](../media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. In **Chi otterrà queste impostazioni?** specificare i destinatari. Se non si vuole usare il gruppo di sicurezza predefinito **Tutti gli utenti**, scegliere **Modifica**, cercare il gruppo di sicurezza che riceverà queste impostazioni \> **Seleziona**.
7. Infine, scegliere **Fatto** per salvare il criterio e assegnarlo ai dispositivi. 

## <a name="edit-windows-10-protection-settings"></a>Modificare Windows 10 di protezione
 
1. Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.     
2. Nel riquadro di spostamento sinistro scegliere **Criteri** \> **dispositivi.**
1. Scegli un criterio Windows dispositivo esistente e quindi **Modifica**.
1. Scegliere **Modifica** accanto a un'impostazione che si desidera modificare e quindi **Salva.**

## <a name="available-settings"></a>Impostazioni disponibili

Per impostazione predefinita, tutte le impostazioni sono **attivate**. Sono disponibili le impostazioni seguenti.
  
Per ulteriori informazioni, vedere [How do protection features in Microsoft 365 Premium map to Intune settings](map-protection-features-to-intune-settings.md). 
  
|||
|:-----|:-----|
|Impostazione  <br/> |Descrizione  <br/> |
|Protegge i PC da virus e altre minacce tramite Windows Defender Antivirus  <br/> |Richiede l'attivazione di Windows Defender Antivirus per la protezione dei PC dai pericoli derivanti dalla connessione a Internet.  <br/> |
|Protegge i PC dalle minacce del Web in Microsoft Edge  <br/> |Attiva le impostazioni di Microsoft Edge che consentono di proteggere gli utenti da siti e download dannosi.  <br/> |
|Usa regole per ridurre la superficie di attacco dei dispositivi  <br/> |Quando è attivata, la riduzione della superficie di attacco consente di bloccare azioni e app generalmente usate dal malware per infettare i dispositivi. Questa impostazione è disponibile solo se Windows Defender Antivirus è attivato. Per altre informazioni, vedere [Ridurre le superfici di attacco con le regole di riduzione della superficie di attacco](/windows/security/threat-protection/microsoft-defender-atp/exploit-protection).  <br/> |
|Protegge le cartelle da minacce come il ransomware  <br/> |Questa impostazione usa l'accesso controllato alle cartelle per proteggere i dati aziendali dalle modifiche effettuate da app sospette o pericolose, come il ransomware. A questi tipi di app viene impedito di apportare modifiche nelle cartelle protette. Questa impostazione è disponibile solo se Windows Defender Antivirus è attivato. Per [ulteriori informazioni, vedere Proteggere le cartelle con accesso](/mem/configmgr/protect/deploy-use/create-deploy-exploit-guard-policy#bkmk_CFA) controllato alle cartelle.  <br/> |
|Impedisce l'accesso alla rete a contenuti potenzialmente pericolosi su Internet  <br/> |Utilizzare questa impostazione per bloccare le connessioni degli utenti in uscita a posizioni Internet con reputazione bassa che potrebbero ospitare tentativi di phishing, exploit o altro contenuto dannoso. Questa impostazione è disponibile solo se Windows Defender Antivirus è impostato su **On.** Per ulteriori informazioni, vedere [Proteggere la rete.](/windows/security/threat-protection/windows-defender-antivirus/configure-real-time-protection-windows-defender-antivirus)  <br/> |
|Proteggi file e cartelle dei PC dall'accesso non autorizzato con BitLocker  <br/> |Bitlocker protegge i dati crittografando le unità disco rigido del computer e impedisce l'esposizione dei dati in caso di furto o smarrimento di un computer. Per altre informazioni, vedi Domande [frequenti su Bitlocker.](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions)  <br/> |
|Consenti agli utenti di scaricare app da Microsoft Store  <br/> |Consente agli utenti di scaricare e installare app da Microsoft Store. Le app possono essere di qualsiasi tipo, da giochi a strumenti per la produttività, quindi questa impostazione viene lasciata **attivata**, ma è possibile disattivarla per rafforzare la sicurezza.  <br/> |
|Consenti agli utenti di accedere a Cortana  <br/> |Cortana può essere molto utile! Cortana può attivare o disattivare automaticamente le impostazioni, fornire indicazioni stradali e assicurarsi  di essere in tempo per gli appuntamenti, quindi questa impostazione viene conservata per impostazione predefinita.  <br/> |
|Consenti agli utenti di ricevere da Microsoft suggerimenti e pubblicità su Windows  <br/> |I suggerimenti su Windows possono essere utili e possono fornire informazioni sulle nuove funzionalità quando vengono rilasciate.  <br/> |
|Mantieni automaticamente aggiornati i dispositivi Windows 10  <br/> |Assicura che i dispositivi Windows 10 ricevano automaticamente gli aggiornamenti più recenti.  <br/> |
|Disattiva lo schermo del dispositivo quando rimane inattivo per questo periodo di tempo  <br/> |Assicura che i dati aziendali siano protetti in caso di inattività di un utente. È possibile che un utente lavori in un luogo pubblico, ad esempio un bar, e si allontani o si distragga per qualche minuto, esponendo il dispositivo agli sguardi altrui. Questa impostazione consente di controllare per quanto tempo l'utente può rimanere inattivo prima che lo schermo disattivato.  <br/> |