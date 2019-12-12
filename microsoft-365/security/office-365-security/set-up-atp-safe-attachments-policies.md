---
title: Impostare i criteri per gli allegati sicuri ATP di Office 365
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: Definire i criteri per gli allegati sicuri per proteggere l'organizzazione da file dannosi nella posta elettronica.
ms.openlocfilehash: 65552e990eb5e12d2a624eea1e1bdbb74454b44f
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971424"
---
# <a name="set-up-office-365-atp-safe-attachments-policies"></a>Impostare i criteri per gli allegati sicuri ATP di Office 365

> [!IMPORTANT]
> Questo articolo è rivolto ai clienti aziendali di [Office 365 Advanced Threat Protection](office-365-atp.md). Se si è un utente di casa che cerca informazioni sugli allegati sicuri in Outlook, vedere [Advanced Outlook.com Security](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2).

Gli utenti inviano, ricevono e condividono regolarmente gli allegati, ad esempio documenti, presentazioni, fogli di calcolo e altro ancora. Non è sempre facile stabilire se un allegato è sicuro o dannoso solo guardando un messaggio di posta elettronica. E l'ultima cosa che si desidera è un allegato dannoso da superare, scatenando il caos per la propria organizzazione. Fortunatamente, [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) può essere di aiuto. È possibile configurare i criteri per gli [allegati sicuri di ATP](atp-safe-attachments.md) per garantire che l'organizzazione sia protetta dagli attacchi degli allegati di posta elettronica non sicuri. 
  
## <a name="what-to-do"></a>Procedura 
  
1. Esaminare i prerequisiti
    
2. Configurare un criterio per gli allegati sicuri ATP
    
3. Informazioni sulle opzioni dei criteri per gli allegati sicuri di ATP
    
## <a name="step-1-review-the-prerequisites"></a>Passaggio 1: esaminare i prerequisiti

- Assicurarsi che l'organizzazione disponga di [Office 365 Advanced Threat Protection](office-365-atp.md).
    
- Verificare di disporre delle autorizzazioni necessarie. Per definire (o modificare) i criteri ATP, è necessario essere assegnati a un ruolo appropriato. Alcuni esempi sono descritti nella tabella seguente: <br>

    |Ruolo  |Dove/come assegnato  |
    |---------|---------|
    |Amministratore globale di Office 365 |Per impostazione predefinita, la persona che si iscrive all'acquisto di Office 365 è un amministratore globale. Per ulteriori informazioni, vedere [informazioni sui ruoli di amministratore di Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) .         |
    |Amministratore della sicurezza |Interfaccia di amministrazione di Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)directory ()|
    |Gestione organizzazione di Exchange Online |Interfaccia di amministrazione di[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)Exchange () <br>oppure <br>  Cmdlet di PowerShell (vedere [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)) |
    
    Per ulteriori informazioni sui ruoli e sulle autorizzazioni, vedere [Permissions in the &amp; Office 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md).

- Informazioni [sulle opzioni dei criteri per gli allegati sicuri di ATP](#step-3-learn-about-atp-safe-attachments-policy-options) (in questo articolo). Alcune opzioni, ad esempio le opzioni monitor o Sostituisci, possono causare un ritardo minore della posta elettronica durante l'analisi degli allegati. Per evitare ritardi nei messaggi, è consigliabile utilizzare il [recapito dinamico e l'anteprima](dynamic-delivery-and-previewing.md).
    
- Consentono fino a 30 minuti affinché il criterio nuovo o aggiornato venga esteso a tutti i datacenter di Office 365.
    
## <a name="step-2-set-up-or-edit-an-atp-safe-attachments-policy"></a>Passaggio 2: configurare (o modificare) un criterio per gli allegati sicuri ATP
  
1. Accedere a [https://protection.office.com](https://protection.office.com) e accedere con l'account aziendale o dell'Istituto di istruzione. 
    
2. Nel centro &amp; sicurezza e conformità di Office 365, nel riquadro di spostamento a sinistra, in **gestione delle minacce**, scegliere **allegati sicuri**per i **criteri** \> .
    
3. Se si visualizza **attiva ATP per SharePoint, OneDrive e Microsoft teams**, è consigliabile selezionare questa opzione. Ciò consentirà la [protezione avanzata dalle minacce di office 365 per SharePoint, OneDrive e Microsoft teams](atp-for-spo-odb-and-teams.md) per l'ambiente Office 365. 
    
4. Scegliere **nuovo** (il pulsante nuovo assomiglia a un segno più ( **+**)) per iniziare a creare il criterio.
    
5. Specificare il nome, la descrizione e le impostazioni per il criterio.<br/><br/>**Esempio:** Per impostare un criterio denominato "No delays" che consente di inviare immediatamente tutti i messaggi e quindi di ricollegare gli allegati dopo la scansione, è possibile specificare le impostazioni seguenti: 
    
      - Nella casella **nome** digitare nessun ritardo.
    
      - Nella casella **Descrizione** Digitare una descrizione analoga, inviare immediatamente i messaggi e ricollegare gli allegati dopo l'analisi.
    
      - Nella sezione Response scegliere l'opzione per il **recapito dinamico** . [Ulteriori informazioni sul recapito dinamico e sulla visualizzazione in anteprima con gli allegati sicuri di ATP](dynamic-delivery-and-previewing.md).
    
      - Nella sezione **allegato di reindirizzamento** selezionare l'opzione per abilitare il reindirizzamento e digitare l'indirizzo di posta elettronica dell'amministratore globale di Office 365, dell'amministratore della sicurezza o dell'analista della sicurezza che indagherà sugli allegati dannosi. 
    
      - Nella sezione **applicato a** scegliere **il dominio del destinatario**e quindi selezionare il dominio. Scegliere **Aggiungi**e quindi fare clic su **OK**.
    
6. Fare clic su **Salva**.
    
Valutare la possibilità di configurare più criteri per gli allegati sicuri ATP per l'organizzazione. Questi criteri verranno applicati nell'ordine in cui sono elencati nella pagina **allegati sicuri di ATP** . Dopo la definizione o la modifica di un criterio, consentire almeno 30 minuti affinché le polizie abbiano effetto nei datacenter Microsoft. 
  
## <a name="step-3-learn-about-atp-safe-attachments-policy-options"></a>Passaggio 3: informazioni sulle opzioni dei criteri per gli allegati sicuri di ATP

Quando si configurano i criteri per gli allegati sicuri di ATP, è possibile scegliere tra molte opzioni, tra cui monitor, blocca, Sostituisci, il recapito dinamico e così via. Nel caso in cui si stia chiedendo cosa fanno queste opzioni, nella tabella seguente vengono riepilogati tutti gli effetti.
  
|**Opzione**|**Effetto**|**Utilizzare se si desidera eseguire le operazioni seguenti:**|
|:-----|:-----|:-----|
|**Disattivato** <br/> |Non esegue l'analisi degli allegati per il malware  <br/> Non ritarda il recapito del messaggio  <br/> |Disattivare l'analisi per mittenti interni, scanner, fax o smart host che invieranno solo allegati noti e validi  <br/> Impedire ritardi non necessari per il routing della posta interna  <br/> **Questa opzione non è consigliata per la maggior parte degli utenti. Consente di abilitare l'analisi degli allegati sicuri di ATP per un piccolo gruppo di mittenti interni.**           |
|**Monitor** <br/> |Recapita messaggi con allegati e quindi tiene traccia di cosa accade con malware rilevato  <br/> |Vedere dove il malware rilevato entra nell'organizzazione  <br/> |
|**Blocco** <br/> |Impedisce la proseguimento dei messaggi con allegati malware rilevati  <br/> Invia messaggi con malware rilevato per la [quarantena in Office 365 in](manage-quarantined-messages-and-files.md) cui un amministratore o un analista di sicurezza può rivedere e rilasciare (o eliminare) tali messaggi  <br/> Blocca automaticamente i messaggi e gli allegati futuri  <br/> |Salvaguardare l'organizzazione da attacchi ripetuti con gli stessi allegati di malware  <br/> |
|**Sostituisce** <br/> |Rimuove gli allegati di malware rilevati  <br/> Notifica ai destinatari che gli allegati sono stati rimossi  <br/> Invia messaggi con malware rilevato per la [quarantena in Office 365 in](manage-quarantined-messages-and-files.md) cui un amministratore o un analista di sicurezza può rivedere e rilasciare (o eliminare) tali messaggi  <br/> |Aumentare la visibilità ai destinatari che gli allegati sono stati rimossi a causa del malware rilevato  <br/> |
|**Recapito dinamico** <br/> |Recapita immediatamente i messaggi  <br/> Sostituisce gli allegati con un file segnaposto fino al completamento dell'analisi e quindi ricollega gli allegati se non è stato rilevato alcun malware  <br/> Include le funzionalità di anteprima degli allegati per la maggior parte dei file PDF e di Office durante l'analisi  <br/> Invia messaggi con malware rilevato per la quarantena, in cui un amministratore o un analista di sicurezza può rivedere e rilasciare (o eliminare) tali messaggi  <br/> [Informazioni sul recapito dinamico e sulla visualizzazione in anteprima con gli allegati sicuri di ATP](dynamic-delivery-and-previewing.md) <br/> |Evitare ritardi nei messaggi durante la protezione dei destinatari da file dannosi  <br/> Abilitazione dei destinatari all'anteprima degli allegati in modalità provvisoria durante la scansione  <br/> |
|**Attiva reindirizzamento** <br/> |Si applica quando si sceglie l'opzione Monitor, blocca o Sostituisci  <br/> Invia allegati a un indirizzo di posta elettronica specificato in cui gli amministratori di sicurezza o gli analisti possono esaminare  <br/> |Abilitare gli amministratori e gli analisti della sicurezza per la ricerca degli allegati sospetti  <br/> |
   
## <a name="next-steps"></a>Passaggi successivi

Una volta che i criteri per gli allegati sicuri di ATP sono sul posto, è possibile vedere in che modo ATP sta funzionando per l'organizzazione visualizzando i report. Per ulteriori informazioni, vedere le risorse seguenti:
- [Visualizzare i report per Office 365 Advanced Threat Protection](view-reports-for-atp.md)
- [Utilizzo di Esplora risorse nel &amp; Centro sicurezza e conformità](threat-explorer.md)

Rimanere in cima a nuove funzionalità che vengono a ATP. visitare la [Roadmap di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) e conoscere le [nuove funzionalità che vengono aggiunte a ATP](office-365-atp.md#new-features-in-office-365-atp).
 