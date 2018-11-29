---
title: Configurare le impostazioni di protezione dei dispositivi per i PC Windows 10
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: bd66c26c-73a4-45a8-8642-3ea4ee7cd89d
description: Informazioni sulle altre impostazioni disponibili in Microsoft 365 Business per proteggere i dispositivi Windows 10 e valori predefiniti.
ms.openlocfilehash: ebfe5f59e544b67e5a4f2ecd990031e9221ff8e5
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868275"
---
# <a name="set-device-protection-settings-for-windows-10-pcs"></a>Configurare le impostazioni di protezione dei dispositivi per i PC Windows 10

## <a name="secure-windows-10-devices"></a>Proteggere i dispositivi Windows 10

Guardare un video che illustra come proteggere i dispositivi Windows 10 con Microsoft 365 Business:
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. Accedere a [Microsoft 365 Business](https://portal.office.com) con le credenziali di amministratore globale. 
    
2. nell'interfaccia di amministrazione scegliere **Aggiungi criterio** nella scheda **Criteri dispositivi**.
    
    ![Device policies card in the admin center.](media/27c12b61-d112-4348-b557-4f3e46204797.png)
  
3. Nel riquadro **Aggiungi criterio** immettere un nome univoco per il criterio. 
    
4. In **Tipo di criterio** scegliere **Configurazione dei dispositivi di Windows 10**.
    
5. Espandere **Proteggere Windows 10 dispositivi** \> configurare le impostazioni come desiderato. Per ulteriori informazioni, vedere [impostazioni disponibili](protection-settings-for-windows-10-pcs.md#bkmk_availablesettings) . 
    
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
|Proteggi i PC da virus e altre minacce tramite Windows Defender Antivirus  <br/> |Richiede l'attivazione di Windows Defender Antivirus per la protezione dei PC dai pericoli derivanti dalla connessione a Internet.  <br/> |
|Proteggi i PC dalle minacce del Web in Microsoft Edge  <br/> |Attiva le impostazioni di Microsoft Edge che consentono di proteggere gli utenti da siti e download dannosi.  <br/> |
|Usa regole per ridurre la superficie di attacco dei dispositivi  <br/> |Quando è attivata, la riduzione della superficie di attacco consente di bloccare azioni e app generalmente usate dal malware per infettare i dispositivi. Questa impostazione è disponibile solo se Windows Defender Antivirus è attivato. Per altre informazioni, vedere [Ridurre le superfici di attacco con le regole di riduzione della superficie di attacco](https://go.microsoft.com/fwlink/?linkid=870417).  <br/> |
|Protegge le cartelle da minacce come il ransomware  <br/> |Questa impostazione usa l'accesso controllato alle cartelle per proteggere i dati aziendali dalle modifiche effettuate da app sospette o pericolose, come il ransomware. A questi tipi di app viene impedito di apportare modifiche nelle cartelle protette. Questa impostazione è disponibile solo se Windows Defender Antivirus è attivato. Per altre informazioni, vedere [Proteggere le cartelle importanti con l'accesso controllato alle cartelle](https://go.microsoft.com/fwlink/?linkid=870418).  <br/> |
|Impedisce l'accesso alla rete a contenuti potenzialmente pericolosi su Internet  <br/> |Usare questa impostazione per bloccare le connessioni in uscita degli utenti su percorsi Internet con reputazione bassa, che potrebbero ospitare tentativi di phishing, exploit o altri contenuti pericolosi. Questa impostazione è disponibile solo se Windows Defender Antivirus è attivato. Per altre informazioni, vedere [Proteggere la rete](https://go.microsoft.com/fwlink/?linkid=870419).  <br/> |
|Proteggi file e cartelle dei PC dall'accesso non autorizzato con BitLocker  <br/> |Bitlocker protegge i dati crittografando le unità disco rigido del computer e impedisce l'esposizione dei dati in caso di furto o smarrimento di un computer. Per altre informazioni, vedere [Domande frequenti su Bitlocker](https://go.microsoft.com/fwlink/?linkid=871000).  <br/> |
|Consenti agli utenti di scaricare app da Microsoft Store  <br/> |Consente agli utenti di scaricare e installare app da Microsoft Store. Le app possono essere di qualsiasi tipo, da giochi a strumenti per la produttività, quindi questa impostazione viene lasciata **attivata**, ma è possibile disattivarla per rafforzare la sicurezza.  <br/> |
|Consenti agli utenti di accedere a Cortana  <br/> |Cortana può risultare molto utile: è in grado di attivare o disattivare automaticamente le impostazioni, fornire indicazioni e assicurarsi che si sia puntuali agli appuntamenti, quindi questa impostazione è **attivata** per impostazione predefinita.<br/> |
|Consenti agli utenti di ricevere da Microsoft suggerimenti e pubblicità su Windows  <br/> |I suggerimenti su Windows possono essere utili e possono fornire informazioni sulle nuove funzionalità quando vengono rilasciate.  <br/> |
|Mantieni automaticamente aggiornati i dispositivi Windows 10  <br/> |Assicura che i dispositivi Windows 10 ricevano automaticamente gli aggiornamenti più recenti.  <br/> |
|Disattiva lo schermo del dispositivo quando rimane inattivo per questo periodo di tempo  <br/> |Assicura che i dati aziendali siano protetti in caso di inattività di un utente. È possibile che un utente lavori in un luogo pubblico, ad esempio un bar, e si allontani o si distragga per qualche minuto, esponendo il dispositivo agli sguardi altrui. Questa impostazione consente di controllare per quanto tempo l'utente può rimanere inattivo prima che lo schermo venga disattivato.  <br/> |
   
  

