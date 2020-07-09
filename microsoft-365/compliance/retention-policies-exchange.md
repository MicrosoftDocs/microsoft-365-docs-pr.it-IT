---
title: Informazioni sulla conservazione per Exchange
f1.keywords:
- NOCSH
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
description: Informazioni sul comportamento di conservazione applicabile specificamente alle cartelle di posta elettronica di Exchange e alle cartelle pubbliche di Exchange.
ms.openlocfilehash: 57f0bf7737522b0435b076fee46edd1736efd856
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/08/2020
ms.locfileid: "45080093"
---
# <a name="learn-about-retention-policies-for-exchange"></a>Informazioni sui criteri di conservazione per Exchange

Questo articolo integra [Informazioni sui criteri di conservazione](retention-policies.md) con informazioni specifiche per Exchange.

## <a name="how-a-retention-policy-works-with-exchange"></a>Funzionamento dei criteri di conservazione in Exchange

Per quanto riguarda la posta dell’utente, il calendario e altri elementi della cassetta postale, i criteri di conservazione vengono applicati a livello di cassetta postale.

Nel caso delle cartelle pubbliche, i criteri di conservazione vengono applicati a tutte le cartelle pubbliche e non a livello di cartella o cassetta postale.

Quando si configurano i criteri di conservazione per tali posizioni, sono inclusi gli elementi di posta elettronica seguenti: i messaggi di posta elettronica con allegati, incluse le bozze, le attività, gli elementi del calendario quando hanno una data di fine e le note. I contatti, le attività e gli elementi del calendario che non hanno una data di fine sono esclusi. Altri elementi archiviati in una cassetta postale, ad esempio i messaggi salvati di Skype e di Teams, sono inclusi con i propri criteri di conservazione distinti.

Le cassette postali e le cartella pubbliche utilizzano la cartella [Elementi ripristinabili](https://docs.microsoft.com/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder) per conservare gli elementi. Solo gli utenti a cui sono state assegnate autorizzazioni di eDiscovery possono visualizzare il contenuto di una cartella Elementi ripristinabili di un altro utente.
  
Quando un utente elimina un messaggio da una cartella (fatta eccezione per la cartella Posta eliminata), per impostazione predefinita il messaggio viene trasferito nella cartella Posta eliminata. Quando un utente elimina un elemento dalla cartella Posta eliminata, il messaggio viene spostato nella cartella Elementi ripristinabili. Tuttavia, un utente può eliminare temporaneamente un elemento (MAIUSC+CANC) di qualsiasi cartella. Con questa operazione la cartella Posta eliminata viene ignorata e l'elemento viene inserito direttamente nella cartella Elementi ripristinabili.
  
Quando si applica un criterio di conservazione a un percorso di Exchange, un processo timer valuta periodicamente gli elementi nella cartella Elementi ripristinabili. Se un elemento non corrisponde alle regole specificate in almeno un criterio di conservazione, viene eliminato definitivamente dalla cartella Elementi ripristinabili.

L’esecuzione del processo timer può richiedere fino a 7 giorni, e il percorso di Exchange deve contenere almeno 10 MB.
  
Quando un utente prova a modificare le proprietà di un elemento della cassetta postale, ad esempio, l'oggetto, il corpo, gli allegati, i mittenti, i destinatari o la data di invio o di ricezione di un messaggio, una copia dell'elemento originale viene salvata nella cartella Elementi ripristinabili prima che la modifica diventi effettiva. Questo si verifica per ogni modifica successiva. Alla fine del periodo di conservazione, le copie nella cartella Elementi ripristinabili vengono eliminate definitivamente.

Dopo l'assegnazione di un criterio di conservazione a una cassetta postale o a una cartella pubblica, i percorsi del contenuto variano in base al fatto che il criterio di conservazione preveda di conservare ed eliminare, solo conservare o solo eliminare.

Se l'impostazione di conservazione è Conserva ed elimina:

![Diagramma del flusso di conservazione nella posta elettronica e nelle cartelle pubbliche](../media/88f174cc-bbf4-4305-93d7-0515f496c8f9.png)

1. **Se l'elemento viene modificato o eliminato definitivamente** dall'utente, con MAIUSC+CANC o eliminandolo da Posta eliminata, durante il periodo di conservazione: l'elemento viene spostato o copiato, in caso di modifica, nella cartella Elementi ripristinabili. Lì, a intervalli regolari viene eseguito un processo timer che identifica i messaggi il cui periodo di conservazione è scaduto. Questi elementi vengono eliminati definitivamente entro 14 giorni dalla data di fine del periodo di conservazione. 14 giorni è l'impostazione predefinita, ma può essere configurato un valore fino a 30 giorni.

2. **Se l'elemento non viene modificato o eliminato** durante il periodo di conservazione: lo stesso processo viene eseguito periodicamente in tutte le cartelle della cassetta postale e identifica i messaggi il cui periodo di conservazione è scaduto. Questi elementi vengono eliminati definitivamente entro 14 giorni dalla data di fine del periodo di conservazione. 14 giorni è l'impostazione predefinita, ma può essere configurato un valore fino a 30 giorni. 

Quando l'impostazione di conservazione è Conserva solo o Elimina solo, i percorsi del contenuto sono varianti di Conserva ed elimina:

### <a name="content-paths-for-retain-only-retention-settings"></a>Percorsi di contenuto per l'impostazione di conservazione Conserva solo

1. **Se l'elemento viene modificato o eliminato** durante il periodo di conservazione: una copia dell'elemento originale viene creata nella cartella Elementi ripristinabili e conservata fino al termine del periodo di conservazione, quindi la copia nella cartella Elementi ripristinabili viene eliminata definitivamente entro 14 giorni dalla scadenza dell'elemento. 

2. **Se l’elemento non viene modificato o eliminato** durante il periodo di conservazione: non succede niente prima o dopo il periodo di conservazione. L’elemento rimane nella posizione originale.

### <a name="content-paths-for-delete-only-retention-settings"></a>Percorsi di contenuto per l'impostazione di conservazione Elimina solo

1. **Se l’elemento non viene eliminato** durante il periodo configurato: alla fine del periodo configurato nel criterio di conservazione, l’elemento viene spostato nella cartella Elementi ripristinabili. 

2. **Se l'elemento viene eliminato** durante il periodo configurato: l'elemento viene immediatamente spostato nella cartella Elementi ripristinabili. Se un utente elimina l’elemento da questa posizione o svuota la cartella Elementi ripristinabili, l’elemento viene eliminato definitivamente. In caso contrario, l'elemento viene eliminato definitivamente dopo un periodo di 14 giorni nella cartella Elementi ripristinabili. 

## <a name="excluding-specific-types-of-exchange-items-from-a-retention-policy"></a>Esclusione di specifici tipi di elementi di Exchange dai criteri di conservazione

È possibile usare PowerShell per escludere specifici tipi di elementi di Exchange dai criteri di conservazione quando le impostazioni dei criteri sono Conserva solo. Ad esempio, è possibile escludere i messaggi vocali, le conversazioni di messaggistica istantanea e altri contenuti di Skype for Business Online nelle cassette postali. Si possono anche escludere elementi del calendario, note e attività. Questa funzionalità è disponibile solo tramite PowerShell, non è disponibile quando si crea un criterio di conservazione usando la procedura guidata nel Centro conformità Microsoft 365.
  
Per escludere i tipi selezionati per gli elementi di Exchange in un criterio di conservazione, usare il parametro `ExcludedItemClasses` con i cmdlet [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule) e [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule).

Per usare i cmdlet dei criteri di conservazione, è prima necessario [connettersi a PowerShell in Centro sicurezza e conformità](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps).

## <a name="when-a-user-leaves-the-organization"></a>Quando un utente abbandona l’organizzazione 

Se un utente abbandona l’organizzazione e la relativa cassetta postale è inclusa nei criteri di conservazione, quest’ultima diventerà inattiva quando viene eliminato l'account di Microsoft 365 dell'utente. I contenuti di una cassetta postale inattiva sono comunque soggetti ai criteri di conservazione applicati alla cassetta postale prima della disattivazione e sono disponibili per la ricerca eDiscovery. Per altre informazioni, vedere [Cassette postali inattive in Exchange Online](inactive-mailboxes-in-office-365.md). 

## <a name="how-to-configure-a-retention-policy-for-exchange"></a>Come configurare un criterio di conservazione per Exchange

Seguire le istruzioni per [Creare e configurare i criteri di conservazione](create-retention-policies.md), e nella pagina **Scegli percorsi** della procedura guidata, selezionare una delle opzioni seguenti:

- **Applica il criterio solo al contenuto dei messaggi di posta elettronica di Exchange, alle cartelle pubbliche, ai gruppi di Office 365 e ai documenti di OneDrive e di SharePoint**

- **Voglio scegliere posizioni specifiche** > **Posta elettronica di Exchange**, **Cartelle pubbliche di Exchange**, e **Gruppi di Office 365**.

Anche se un gruppo di Microsoft 365 ha una cassetta postale di Exchange, un criterio di conservazione che include l'intero percorso **Posta elettronica di Exchange** non includerà il contenuto nelle cassette postali del gruppo di Microsoft 365. Per conservare i contenuti delle cassette postali, selezionare la posizione dei **Gruppi di Office 365**.
