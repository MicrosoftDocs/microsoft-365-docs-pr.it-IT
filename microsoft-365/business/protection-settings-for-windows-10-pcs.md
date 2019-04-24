---
title: Configurare le impostazioni di protezione dei dispositivi per i PC Windows 10
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
ms.assetid: bd66c26c-73a4-45a8-8642-3ea4ee7cd89d
description: Informazioni sull'impostazione predefinita e altre impostazioni disponibili in Microsoft 365 business per proteggere i dispositivi Windows 10.
ms.openlocfilehash: f9e890cde7a8290a9a8e81720d32a6a2889c312f
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285922"
---
# <a name="set-device-protection-settings-for-windows-10-pcs"></a>Configurare le impostazioni di protezione dei dispositivi per i PC Windows 10

## <a name="secure-windows-10-devices"></a>Proteggere i dispositivi Windows 10

Guardare un video che illustra come proteggere i dispositivi Windows 10 con Microsoft 365 Business:
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. Accedere all'interfaccia di [Amministrazione](https://go.microsoft.com/fwlink/p/?linkid=837890) con le credenziali di amministratore globale. 
    
2. Nella barra di spostamento sinistra fare clic su **criteri** \> **dispositivi** \> **Aggiungi**.
  
3. Nel riquadro **Aggiungi criterio** immettere un nome univoco per il criterio. 
    
4. In **Tipo di criterio** scegliere **Configurazione dei dispositivi di Windows 10**.
    
5. Expand **Secure Windows 10 Devices** \> configure the settings how you would like. See [Available settings](#available-settings) for more information. 
    
    È sempre possibile usare il collegamento **Ripristina impostazioni predefinite** per ripristinare l'impostazione predefinita. 
    
    ![Add policy pane with Windows 10 Device configuration selected](media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. In **Chi otterrà queste impostazioni?** specificare i destinatari. Se non si vuole usare il gruppo di sicurezza predefinito **Tutti gli utenti**, scegliere **Modifica**, cercare il gruppo di sicurezza che riceverà queste impostazioni \> **Seleziona**.
    
7. Infine, scegliere **Fatto** per salvare il criterio e assegnarlo ai dispositivi. 
    
## <a name="available-settings"></a>Impostazioni disponibili

Per impostazione predefinita, tutte le impostazioni sono **attivate**. Sono disponibili le impostazioni seguenti.
  
Per altre informazioni, vedere [Corrispondenza tra le caratteristiche di protezione in Microsoft 365 Business e le impostazioni di Intune](map-protection-features-to-intune-settings.md). 
  
|||
|:-----|:-----|
|Impostazione  <br/> |Descrizione  <br/> |
|Protegge i PC da virus e altre minacce tramite Windows Defender Antivirus  <br/> |Richiede l'attivazione di Windows Defender Antivirus per la protezione dei PC dai pericoli derivanti dalla connessione a Internet.  <br/> |
|Protegge i PC dalle minacce del Web in Microsoft Edge  <br/> |Attiva le impostazioni di Microsoft Edge che consentono di proteggere gli utenti da siti e download dannosi.  <br/> |
|Usa regole per ridurre la superficie di attacco dei dispositivi  <br/> |Quando è attivata, la riduzione della superficie di attacco consente di bloccare azioni e app generalmente usate dal malware per infettare i dispositivi. Questa impostazione è disponibile solo se Windows Defender Antivirus è attivato. Per altre informazioni, vedere [Ridurre le superfici di attacco con le regole di riduzione della superficie di attacco](https://go.microsoft.com/fwlink/?linkid=870417).  <br/> |
|Protegge le cartelle da minacce come il ransomware  <br/> |Questa impostazione usa l'accesso controllato alle cartelle per proteggere i dati aziendali dalle modifiche effettuate da app sospette o pericolose, come il ransomware. A questi tipi di app viene impedito di apportare modifiche nelle cartelle protette. Questa impostazione è disponibile solo se Windows Defender Antivirus è attivato. Per altre informazioni, vedere [Proteggere le cartelle importanti con l'accesso controllato alle cartelle](https://go.microsoft.com/fwlink/?linkid=870418).  <br/> |
|Impedisce l'accesso alla rete a contenuti potenzialmente pericolosi su Internet  <br/> |Usare questa impostazione per bloccare le connessioni in uscita degli utenti su percorsi Internet con reputazione bassa, che potrebbero ospitare tentativi di phishing, exploit o altri contenuti pericolosi. Questa impostazione è disponibile solo se Windows Defender Antivirus è attivato. Per altre informazioni, vedere [Proteggere la rete](https://go.microsoft.com/fwlink/?linkid=870419).  <br/> |
|Proteggi file e cartelle dei PC dall'accesso non autorizzato con BitLocker  <br/> |Bitlocker protegge i dati crittografando le unità disco rigido del computer e impedisce l'esposizione dei dati in caso di furto o smarrimento di un computer. Per altre informazioni, vedere [Domande frequenti su Bitlocker](https://go.microsoft.com/fwlink/?linkid=871000).  <br/> |
|Consenti agli utenti di scaricare app da Microsoft Store  <br/> |Consente agli utenti di scaricare e installare app da Microsoft Store. Le app possono essere di qualsiasi tipo, da giochi a strumenti per la produttività, quindi questa impostazione viene lasciata **attivata**, ma è possibile disattivarla per rafforzare la sicurezza.  <br/> |
|Consenti agli utenti di accedere a Cortana  <br/> |Cortana può risultare molto utile: è in grado di attivare o disattivare automaticamente le impostazioni, fornire indicazioni e assicurarsi che si sia puntuali agli appuntamenti, quindi questa impostazione è **attivata** per impostazione predefinita.<br/> |
|Consenti agli utenti di ricevere da Microsoft suggerimenti e pubblicità su Windows  <br/> |I suggerimenti su Windows possono essere utili e possono fornire informazioni sulle nuove funzionalità quando vengono rilasciate.  <br/> |
|Mantieni automaticamente aggiornati i dispositivi Windows 10  <br/> |Assicura che i dispositivi Windows 10 ricevano automaticamente gli aggiornamenti più recenti.  <br/> |
|Disattiva lo schermo del dispositivo quando rimane inattivo per questo periodo di tempo  <br/> |Assicura che i dati aziendali siano protetti in caso di inattività di un utente. È possibile che un utente lavori in un luogo pubblico, ad esempio un bar, e si allontani o si distragga per qualche minuto, esponendo il dispositivo agli sguardi altrui. Questa impostazione consente di controllare per quanto tempo l'utente può rimanere inattivo prima che lo schermo disattivato.  <br/> |
   
  

