---
title: Creare e pubblicare etichette di riservatezza
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Istruzioni per creare, configurare e pubblicare etichette di riservatezza per classificare e proteggere i documenti e i messaggi di posta elettronica dell'organizzazione.
ms.openlocfilehash: edcfcf5a4f4891e4e1159c4c42327e59ceb35449
ms.sourcegitcommit: a122fd1fce523171529c7f610bb7faf09d30a8bb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/18/2020
ms.locfileid: "41238403"
---
# <a name="create-and-configure-sensitivity-labels-and-their-policies"></a>Creare e configurare etichette di riservatezza e i relativi criteri

Per creare e pubblicare le [etichette di riservatezza](sensitivity-labels.md), passare all'interfaccia di amministrazione per l'applicazione di etichette, ad esempio il [Centro conformità Microsoft 365](https://compliance.microsoft.com/). È anche possibile usare il Centro sicurezza Microsoft 365 o il Centro sicurezza e conformità di Office 365.

Prima di tutto, creare e configurare le etichette di riservatezza che si vogliono rendere disponibili nelle app di Office e per i servizi. Quindi, creare uno o più criteri di etichetta contenenti le etichette e le impostazioni dei criteri configurate. È il criterio di etichetta che pubblica le etichette e le impostazioni per gli utenti e i percorsi scelti.

## <a name="create-and-configure-sensitivity-labels"></a>Creare e configurare etichette di riservatezza

1. Nell'interfaccia di amministrazione per l’applicazione di etichette passare alle etichette di riservatezza:
    
    - Centro conformità Microsoft 365: 
        - **Soluzioni** > **Information Protection (anteprima)**
        
        Se questa opzione non è immediatamente visibile, selezionare prima **Mostra tutto**. 
    
    - Centro sicurezza Microsoft 365: 
        - **Classificazione** > **Etichette di riservatezza**
    
    - Centro sicurezza e conformità di Office 365:
        - **Classificazione** > **Etichette di riservatezza**

2. Nella scheda **Etichette** selezionare **+ Crea un'etichetta** per avviare la procedura guidata **Nuova etichetta di riservatezza**.

3. Seguire le indicazioni per le impostazioni dell'etichetta.
    
    Per altre informazioni sulle impostazioni delle etichette, vedere [Operazioni eseguibili dalle etichette di riservatezza](sensitivity-labels.md#what-sensitivity-labels-can-do) nelle informazioni di panoramica.

4. Ripetere questi passaggi per creare altre etichette. Se invece si vuole creare un'etichetta secondaria, selezionare prima di tutto l'etichetta padre, poi **...** per **Altre azioni**, quindi selezionare **Aggiungi etichetta secondaria**.

5. Una volta create tutte le etichette desiderate, rivedere l'ordine e, se necessario, spostarle verso l'alto o verso il basso. Per modificare l'ordine di un'etichetta selezionare **...** per **Altre azioni**, quindi selezionare **Sposta su** o **Sposta giù**. Per altre informazioni, vedere [Priorità dell'etichetta (l'ordine è importante)](sensitivity-labels.md#label-priority-order-matters) nelle informazioni di panoramica.

Per modificare un'etichetta esistente, selezionarla e quindi scegliere **Modifica etichetta**. Verrà avviata la procedura guidata **Modifica etichetta di riservatezza**, che consente di modificare tutte le impostazioni dell'etichetta descritte al passaggio 3. Se l'etichetta è già pubblicata con un criterio di etichetta, non sono necessarie altre operazioni, ma è possibile che la replica delle modifiche in utenti e percorsi richieda fino a 24 ore.

Finché non verranno pubblicate, le etichette non saranno disponibili per la selezione nelle app o per i servizi. Per pubblicare le etichette è necessario aggiungerle a un criterio di etichetta.

### <a name="additional-label-settings-with-office-365-security--compliance-center-powershell"></a>Impostazioni aggiuntive per le etichette con PowerShell per Centro sicurezza e conformità di Office 365

Con il cmdlet [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) di [PowerShell per Centro sicurezza e conformità di Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps) sono disponibili altre impostazioni delle etichette.

Ad esempio, usare il parametro *LocaleSettings* per specificare lingue diverse per i nomi e le descrizioni comando delle etichette. 

Con questo cmdlet è anche possibile specificare [impostazioni avanzate](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) per il client di etichettatura unificata di Azure Information Protection. Queste impostazioni avanzate includono l'impostazione di un colore per le etichette e l'applicazione di una proprietà personalizzata quando si applica un'etichetta. Per l'elenco completo, vedere [Impostazioni avanzate disponibili per i criteri delle etichette](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies). 

## <a name="publish-sensitivity-labels-by-creating-a-label-policy"></a>Pubblicare etichette di riservatezza creando un criterio di etichetta

1. Nell'interfaccia di amministrazione per l’applicazione di etichette passare a **Classificazione** > **Etichette di riservatezza**.

2. Selezionare la scheda **Criteri delle etichette**.

3. Selezionare **Pubblica etichette** per avviare la procedura guidata **Crea criterio**.

4. Selezionare **Scegliere le etichette di riservatezza da pubblicare**. Selezionare le etichette che si vogliono rendere disponibili nelle app e per i servizi e quindi selezionare **Aggiungi**.

5. Rivedere le etichette selezionate e selezionare **Modifica** se si vogliono apportare modifiche. Altrimenti selezionare **Avanti**.

6. Seguire le istruzioni visualizzate per configurare le impostazioni del criterio.
    
    Per altre informazioni sulle impostazioni, vedere [Operazioni eseguibili dai criteri di etichetta](sensitivity-labels.md#what-label-policies-can-do) nelle informazioni di panoramica.

7. Ripetere questi passaggi se sono necessarie impostazioni dei criteri diverse per utenti o posizioni diverse. Ad esempio, possono occorrere altre etichette per un gruppo di utenti o un'etichetta predefinita diversa per un subset di utenti.

8. Se si creano più criteri di etichetta che potrebbero comportare un conflitto per un utente o una posizione, rivedere l'ordine dei criteri e, se necessario, spostarli verso l'alto o verso il basso. Per modificare l'ordine di un criterio di etichetta selezionare **...** per **Altre azioni**, quindi selezionare **Sposta su** o **Sposta giù**. Per altre informazioni, vedere [Priorità dei criteri di etichetta (l'ordine è importante)](sensitivity-labels.md#label-policy-priority-order-matters) nelle informazioni di panoramica.

Completando la procedura guidata, il criterio di etichetta viene pubblicato automaticamente. Per apportare modifiche a un criterio pubblicato, basta modificarlo. Non è necessario selezionare una specifica azione di pubblicazione o ripubblicazione.

Per modificare un criterio di etichetta, selezionarlo e quindi scegliere **Modifica criterio**. Verrà avviata la procedura guidata **Crea criterio**, che consente di modificare le etichette incluse e le impostazioni dell'etichetta. Una volta completata la procedura guidata, le modifiche vengono replicate automaticamente alle posizioni e agli utenti selezionati. La replica può richiedere fino a 24 ore.

### <a name="additional-label-policy-settings-with-office-365-security--compliance-center-powershell"></a>Impostazioni aggiuntive per i criteri delle etichette con PowerShell per Centro sicurezza e conformità di Office 365

Con il cmdlet [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) di [PowerShell per Centro sicurezza e conformità di Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps) sono disponibili altre impostazioni per i criteri delle etichette.

Con questo cmdlet è possibile specificare [impostazioni avanzate](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) per il client di etichettatura unificata di Azure Information Protection. Queste impostazioni avanzate includono l'impostazione di un'etichetta predefinita diversa per Outlook e l'implementazione di messaggi popup in Outlook che avvertono, giustificano o bloccano l'invio di messaggi di posta elettronica. Per l'elenco completo, vedere [Impostazioni avanzate disponibili per le etichette](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels). 

Si può usare questo cmdlet anche per aggiungere e rimuovere etichette da un criterio di etichetta.


## <a name="next-steps"></a>Passaggi successivi

Per configurare e usare le etichette di riservatezza per scenari specifici, vedere gli articoli seguenti:

- [Limitare l'accesso al contenuto utilizzando la crittografia nelle etichette di riservatezza](encryption-sensitivity-labels.md)

- [Applicare automaticamente un'etichetta di riservatezza al contenuto](apply-sensitivity-label-automatically.md)

- [Usare etichette di riservatezza con team, gruppi e siti](sensitivity-labels-teams-groups-sites.md)

- [Abilitare le etichette di riservatezza per i file di Office in SharePoint e OneDrive](sensitivity-labels-sharepoint-onedrive-files.md)

Per monitorare il modo in cui vengono usate le etichette, vedere [Visualizzare l'utilizzo delle etichette con Analisi delle etichette](label-analytics.md).