---
title: Autorizzazioni nel Centro Microsoft 365 conformità
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.service: O365-seccomp
audience: ITPro
ms.topic: article
localization_priority: Normal
description: Informazioni sulla gestione delle autorizzazioni nel Centro Microsoft 365 conformità.
ms.collection: M365-security-compliance
ms.openlocfilehash: 72575fce5f7d43354715c77016a8f444e539887f
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772485"
---
# <a name="permissions-in-the-microsoft-365-compliance-center"></a>Autorizzazioni nel Centro Microsoft 365 conformità

Il Microsoft 365 conformità è stato aggiornato di recente e ora supporta la gestione diretta delle autorizzazioni per gli utenti che eseguono attività di conformità in Microsoft 365. Questo aggiornamento significa che non sarà più necessario utilizzare il Centro sicurezza & Office 365 conformità per gestire le autorizzazioni per le soluzioni di conformità. Utilizzando la  nuova pagina Autorizzazioni nel Centro conformità di Microsoft 365, è possibile gestire le autorizzazioni per gli utenti per le attività di conformità in funzionalità come la gestione dei dispositivi, la prevenzione della perdita dei dati, eDiscovery, la gestione dei rischi insider, la conservazione e molti altri. Gli utenti possono eseguire solo le attività di conformità a cui si concede esplicitamente l'accesso.

Per visualizzare la scheda Autorizzazioni nel Centro conformità Microsoft 365, gli utenti devono essere  un amministratore globale o disporre  del ruolo Gestione ruoli (un ruolo viene assegnato solo al gruppo di ruoli Gestione organizzazione).  Il *ruolo Gestione ruoli* consente agli utenti di visualizzare, creare e modificare gruppi di ruoli.

![Pagina Autorizzazioni nel Centro Microsoft 365 conformità](../media/m365-compliance-center-permissions.png)

Le autorizzazioni nel Microsoft 365 conformità si basano sul modello di autorizzazioni RBAC (Role-Based Access Control). RBAC è lo stesso modello di autorizzazioni utilizzato dalla maggior parte dei servizi Microsoft 365, quindi se si ha familiarità con la struttura delle autorizzazioni in questi servizi, la concessione delle autorizzazioni nel Centro conformità di Microsoft 365 sarà familiare. È importante ricordare che le autorizzazioni gestite nel centro Microsoft 365 conformità non coprono la gestione di tutte le autorizzazioni necessarie in ogni singolo servizio. Sarà comunque necessario gestire determinate autorizzazioni specifiche del servizio nell'interfaccia di amministrazione per il servizio specifico. Ad esempio, se è necessario assegnare le autorizzazioni per l'archiviazione, il controllo e i criteri di conservazione, è necessario gestire queste autorizzazioni nell'interfaccia di amministrazione di Exchange.

## <a name="relationship-of-members-roles-and-role-groups"></a>Relazione tra membri, ruoli e gruppi di ruoli

Un ruolo concede le autorizzazioni per eseguire un set di attività. ad esempio, il ruolo Gestione casi consente agli utenti di utilizzare i casi di eDiscovery.

Un gruppo di ruoli è un set di ruoli che consentono agli utenti di eseguire le proprie attività nelle soluzioni di conformità nel centro Microsoft 365 conformità. Ad esempio, aggiungendo utenti al gruppo di ruoli *Insider Risk Management,* amministratori, analisti, investigatori e revisori designati vengono configurati per le autorizzazioni necessarie per la gestione dei rischi insider in un singolo gruppo. Il Microsoft 365 conformità include gruppi di ruoli predefiniti per attività e funzioni per ogni soluzione di conformità a cui sarà necessario assegnare gli utenti. In genere, è consigliabile aggiungere semplicemente singoli utenti come membri ai gruppi di ruoli di conformità predefiniti in base alle esigenze.

![Diagramma che mostra la relazione tra gruppi di ruoli e ruoli e membri](../media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)

## <a name="permissions-needed-to-use-features-in-the-microsoft-365-compliance-center"></a>Autorizzazioni necessarie per usare le funzionalità nel Centro Microsoft 365 conformità

Per visualizzare tutti i gruppi di ruoli predefiniti disponibili nel Centro conformità Microsoft 365 e i ruoli assegnati ai gruppi di ruoli per impostazione predefinita, vedere autorizzazioni nel Centro sicurezza [& conformità.](/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)

La gestione delle autorizzazioni nel Microsoft 365 conformità consente agli utenti di accedere solo alle funzionalità di conformità disponibili nel Centro Microsoft 365 conformità. Se si desidera concedere autorizzazioni ad altre funzionalità non presenti nel Centro conformità Microsoft 365, ad esempio le regole del flusso di posta di Exchange (note anche come regole di trasporto), è necessario utilizzare l'interfaccia di amministrazione di Exchange.

## <a name="azure-roles-in-the-microsoft-365-compliance-center"></a>Ruoli di Azure nel Centro Microsoft 365 conformità

I ruoli visualizzati nella sezione **Ruoli di Azure AD** della pagina Autorizzazioni del Centro Microsoft 365 conformità sono Azure Active Directory  >   ruoli.  Tali ruoli sono progettati per uniformarsi alle funzioni lavorative nel gruppo IT della propria organizzazione, semplificando quindi l'assegnazione di autorizzazioni necessarie per svolgere il lavoro. È possibile visualizzare gli utenti attualmente assegnati a ogni ruolo selezionando un ruolo di amministratore e visualizzando i dettagli del pannello dei ruoli. Per gestire i membri di un ruolo di Azure AD, selezionare Gestisci membri in Azure AD. Questa scelta reindirizza l'utente al portale di gestione di Azure.

|Ruolo|Descrizione|
|:---|:----------|
|**Amministratore globale**|Ha accesso a tutte le funzionalità amministrative presenti in ogni servizio di Microsoft 365. Solo gli amministratori globali possono assegnare altri ruoli di amministratore. Per altre informazioni, vedere [Amministratore globale / Amministratore aziendale](/azure/active-directory/roles/permissions-reference#global-administrator--company-administrator).|
|**Amministratore dati di conformità**|Tiene traccia dei dati dell'organizzazione su Microsoft 365, si assicura che siano protetti e ottiene informazioni dettagliate su eventuali problemi, in modo da attenuarne i rischi. Per ulteriori informazioni, vedere [Amministratore dati di conformità](/azure/active-directory/roles/permissions-reference#compliance-data-administrator).|
|**Amministratore di conformità**|Aiuta l'organizzazione a rimanere conforme ai requisiti normativi, gestire i casi di eDiscovery e mantenere i criteri di governance dei dati nelle posizioni, identità e app di Microsoft 365. Per ulteriori informazioni, vedere [Amministratore di conformità](/azure/active-directory/roles/permissions-reference#compliance-administrator).|
|**Operatore della sicurezza**|Può visualizzare, analizzare e rispondere alle minacce attive a utenti, dispositivi e contenuti di Microsoft 365. Per altre informazioni, vedere [Operatore della sicurezza](/azure/active-directory/roles/permissions-reference#security-operator).|
|**Ruolo con autorizzazioni di lettura per la sicurezza**|Può visualizzare, analizzare e rispondere alle minacce attive a utenti, dispositivi e contenuti di Microsoft 365 ma, a differenza del ruolo di Operatore della sicurezza, non ha le autorizzazioni necessarie per intervenire. Per altre informazioni, vedere [Ruolo con autorizzazioni di lettura per la sicurezza](/azure/active-directory/roles/permissions-reference#security-reader).|
|**Amministratore della sicurezza**|Può controllare la sicurezza complessiva dell'organizzazione gestendo i criteri di sicurezza, esaminando l'analisi e i report della sicurezza nei prodotti di Microsoft 365 e tenendosi informato sul panorama delle minacce. Per altre informazioni, vedere [Amministratore di sicurezza](/azure/active-directory/roles/permissions-reference#security-administrator).|
|**Ruolo con autorizzazioni di lettura globali**|La versione di sola lettura del ruolo **Amministratore globale**. Può visualizzare tutte le impostazioni e le informazioni amministrative in Microsoft 365. Per altre informazioni, vedere [Ruolo con autorizzazioni di lettura globali](/azure/active-directory/roles/permissions-reference#global-reader).|
|**Amministratore della simulazione di attacco**|Creare e gestire tutti gli aspetti della creazione della simulazione di attacco, dell'avvio/pianificazione di una simulazione e della revisione dei risultati della simulazione. Per ulteriori informazioni, vedere [Attack Simulation Administrator.](/azure/active-directory/roles/permissions-reference#attack-simulation-administrator)|
|**Autore payload di attacco**|Crea payload di attacco ma non avviali o pianificali. Per ulteriori informazioni, vedere [Autore payload di attacco.](/azure/active-directory/roles/permissions-reference#attack-payload-author)|
|

## <a name="add-users-to-a-compliance-role-group"></a>Aggiungere utenti a un gruppo di ruoli di conformità

Completare la procedura seguente per aggiungere utenti a un gruppo di ruoli di conformità:

1. Accedere all'area delle autorizzazioni del [Centro Microsoft 365 conformità](https://compliance.microsoft.com/permissions) usando le credenziali per un account amministratore nell'organizzazione Microsoft 365 aziendale.
2. Nel Centro Microsoft 365 conformità passare a **Autorizzazioni**. Selezionare il collegamento per visualizzare e gestire i ruoli di conformità in Microsoft 365.
3. Espandere la **sezione Centro conformità** e selezionare **Ruoli**.
4. Nella pagina **Ruoli centro conformità** selezionare un gruppo di ruoli di conformità a cui si desidera aggiungere utenti, quindi selezionare Modifica gruppo **di** ruoli nel riquadro dei dettagli.
5. Selezionare **Scegli membri** nel riquadro di spostamento sinistro, quindi selezionare **Modifica.**
6. Selezionare **Aggiungi** e quindi selezionare la casella di controllo per tutti gli utenti che si desidera aggiungere al gruppo di ruoli.
7. Selezionare **Aggiungi**, quindi **Fine**.
8. Selezionare **Salva** per aggiungere gli utenti al gruppo di ruoli. Selezionare **Chiudi** per completare la procedura.

## <a name="remove-users-from-a-compliance-role-group"></a>Rimuovere utenti da un gruppo di ruoli di conformità

Completare la procedura seguente per rimuovere gli utenti da un gruppo di ruoli di conformità:

1. Accedere all'area delle autorizzazioni del [Centro Microsoft 365 conformità](https://compliance.microsoft.com/permissions) usando le credenziali per un account amministratore nell'organizzazione Microsoft 365 aziendale.
2. Nel Centro Microsoft 365 conformità passare a **Autorizzazioni**. Selezionare il collegamento per visualizzare e gestire i ruoli di conformità in Microsoft 365.
3. Espandere la sezione Centro conformità e selezionare **Ruoli**.
4. Nella pagina **Ruoli centro** conformità selezionare un gruppo di ruoli di conformità da cui si desidera rimuovere gli utenti, quindi selezionare Modifica gruppo **di ruoli** nel riquadro dei dettagli.
5. Selezionare **Scegli membri** nel riquadro di spostamento sinistro, quindi selezionare **Modifica.**
6. Selezionare **Rimuovi** e quindi selezionare la casella di controllo per tutti gli utenti che si desidera rimuovere dal gruppo di ruoli.
7. Selezionare **Rimuovi** e quindi **Fare clic su Fine.**
8. Selezionare **Salva** per rimuovere gli utenti dal gruppo di ruoli. Selezionare **Chiudi** per completare la procedura.
