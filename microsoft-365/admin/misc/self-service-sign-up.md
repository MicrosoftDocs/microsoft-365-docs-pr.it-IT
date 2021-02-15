---
title: Uso dell'iscrizione self-service nell'organizzazione
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- okr_SMB
search.appverid:
- MET150
ms.assetid: 4f8712ff-9346-4c6c-bb63-a21ad7a62cbd
description: Informazioni sull'iscrizione self-service di Microsoft 365 e sui programmi self-service disponibili come Microsoft Power Apps, Microsoft Flow e Dynamics 365 for Finance.
ms.openlocfilehash: 21e41661141a817a1751c80608035d839d2e3952
ms.sourcegitcommit: 7355cc8871cde5fac6d7d6dcecc3e41e35601623
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2020
ms.locfileid: "48906574"
---
# <a name="using-self-service-sign-up-in-your-organization"></a>Uso dell'iscrizione self-service nell'organizzazione

L'iscrizione in modalità self-service consente agli utenti dell'organizzazione di iscriversi ai servizi online di Microsoft. Questo processo di iscrizione viene chiamato "iscrizione self-service", perché gli utenti possono iscriversi per usare i servizi pagati dall'abbonamento o utilizzare i servizi gratuiti, senza richiedere l'intervento dell'utente per conto dell'utente.
  
## <a name="how-self-service-sign-up-works"></a>Funzionamento dell'iscrizione self-service

L'esempio seguente descrive come funziona l'iscrizione self-service per un istituto di istruzione. Lo stesso processo funziona per qualsiasi organizzazione con programmi self-service abilitati nel proprio tenant.
  
1. Gli studenti e i membri della facoltà hanno indirizzi di posta elettronica dell'istituto di istruzione, che indicano che sono associati all'istituto. Ad esempio, l'indirizzo di posta jakob@uw.edu può indicare uno studente dell'Università di Washington.
2. Gli studenti e i docenti visitano il sito [Web](https://go.microsoft.com/fwlink/p/?LinkId=536628)e usano il loro indirizzo di posta elettronica per iscriversi ai servizi che l'organizzazione offre, ad esempio Microsoft 365 Apps for enterprise. Possono anche iscriversi ad altri servizi gratuiti offerti.
3. Convalidiamo il loro indirizzo e-mail e quindi possono iniziare subito a usare Microsoft 365, Power BI o altri servizi.
4. L'amministratore aziendale può vedere chi ha effettuato l'iscrizione a  un abbonamento selezionando l'abbonamento nella pagina Licenze nell'interfaccia di amministrazione di Microsoft 365. In questo modo è possibile vedere quando sono presenti licenze nuove o non riconoscite per i servizi nel tenant. Per controllare se gli utenti possono iscriversi per le sottoscrizioni self-service, utilizzare il cmdlet Di PowerShell [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0) con il parametro **AllowAdHocSubscriptions.** Per ulteriori informazioni, vedere [Come si controllano le impostazioni self-service?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="available-self-service-programs"></a>Programmi self-service disponibili

Di seguito sono elencati i programmi self-service attualmente disponibili. Questo elenco verrà aggiornato man mano che vengono aggiunti nuovi programmi.
  
| Programma <br/> | Descrizione <br/> | Info aggiuntive <br/> | Sito Web per l'iscrizione self-service <br/> |
|:-----|:-----|:-----|:-----|
|Office 365 A1**** <br/> |Qualsiasi studente o insegnante può usare un indirizzo di posta elettronica dell'istituto di istruzione per iscriversi gratuitamente a Office 365 e ottenere le app di Office per il Web, 1 TB di spazio di archiviazione cloud di OneDrive e SharePoint Online per i siti di classe, team e progetto.  <br/> |[Domande frequenti tecniche su Office 365 Education](https://go.microsoft.com/fwlink/p/?LinkId=536625) <br/> |[Office 365 Education](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Office 365 A1 Plus** <br/> |Gli studenti e gli insegnanti idonei possono iscriversi a Office 365 A1 Plus, che include tutto ciò di cui sopra più Microsoft 365 Apps for enterprise. Microsoft 365 Apps for enterprise è un software di produttività, tra cui Word, PowerPoint, Excel, Outlook, OneNote, Publisher, Access e Skype for Business, installato nel computer desktop o portatile.  <br/> |[Domande frequenti tecniche su Office 365 Education](https://go.microsoft.com/fwlink/p/?LinkId=536625) <br/> |[Office 365 Education](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Power BI** <br/> |Power BI consente agli utenti di visualizzare i dati, condividere individuazioni e collaborare in nuovi modi intuitivi. <br/> Se l'organizzazione si sottoscrive già, è possibile visualizzare anche le licenze per "Power BI Pro Individual User Trial", che offrono agli utenti un accesso limitato e gratuito alle funzionalità avanzate.  <br/> |[Power BI nell'organizzazione](https://go.microsoft.com/fwlink/p/?LinkId=536626) <br/> |[Microsoft Power BI](https://go.microsoft.com/fwlink/p/?LinkId=536629) <br/> |
|**Rights Management Services (RMS)** <br/> |RMS per singoli utenti è un abbonamento gratuito self-service per gli utenti di un'organizzazione a cui sono stati inviati file dal contenuto riservato protetti da Azure Rights Management (Azure RMS), ma il cui reparto IT non ha implementato Azure Rights Management (Azure RMS) o Active Directory Rights Management Services (AD RMS).  <br/> |[RMS per utenti singoli e Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=536627) <br/> |[Portale di Microsoft Rights Management](https://portal.azure.com/) per verificare se è possibile aprire un determinato documento protetto da diritti.  <br/> |
|**Microsoft Power Apps** <br/> |In PowerApps è possibile gestire i dati dell'organizzazione eseguendo un'app creata personalmente o creata e condivisa da qualcun altro. Le app vengono eseguite su dispositivi mobili come i telefoni oppure in un browser aprendo Dynamics 365. È possibile creare un'infinita varietà di app senza che sia necessario conoscere un linguaggio di programmazione, come C#.  <br/> |[Iscrizione self-service a PowerApps](https://go.microsoft.com/fwlink/p/?linkid=841461) <br/> |[Microsoft Power Apps](https://go.microsoft.com/fwlink/p/?linkid=841462) <br/> |
|**Dynamics 365 for Financials** <br/> |È una soluzione completa per la gestione aziendale e finanziaria pensata per le piccole e medie imprese. Con Dynamics 365 for Financials i processi di ordinazione, vendita, fatturazione e reporting sono più facili che mai.  <br/> |[Microsoft Dynamics 365 for Financials](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |[Microsoft Dynamics 365 for Financials](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |
|**Microsoft Dynamics 365 for Operations** <br/> |Questa soluzione aumenta l'efficienza sul lavoro. Gli strumenti ERP completi disponibili in Dynamics 365 for Operations forniscono scalabilità globale e intelligenza digitale per aiutare le aziende a crescere con i propri ritmi.  <br/> |[Microsoft Dynamics 365 for Operations](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |[Microsoft Dynamics 365 for Operations](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |
|**Microsoft AppSource** <br/> |Microsoft AppSource è una destinazione per le app SaaS aziendali sviluppate sulla piattaforma cloud Microsoft. AppSource offre centinaia di app, componenti aggiuntivi e pacchetti di contenuto che estendono le funzionalità di prodotti Microsoft come Azure, Dynamics 365, Office 365 e Power BI.  <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |
|**Incentivi per i partner Microsoft** <br/> |Microsoft Partner Network offre tre tipi di adesione. Ogni tipo offre un set di vantaggi che aiutano l'azienda a crescere. Man mano che si raggiungono gli obiettivi prefissati, è possibile partecipare al programma al livello che soddisfa le specifiche esigenze per accedere ad altri vantaggi e sviluppare il rapporto con Microsoft e con altri partner della rete.  <br/> |[Incentivi per i partner Microsoft](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |[Incentivi per i partner Microsoft](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |
|**Microsoft Business Center** <br/> |Microsoft Business Center è il portale per i clienti che hanno effettuato acquisti tramite il Contratto di prodotti e servizi Microsoft (MPSA). <br/> |[Guida introduttiva: Registrarsi per il Microsoft Business Center](https://go.microsoft.com/fwlink/p/?linkid=841479) <br/> |[Microsoft Business Center](https://go.microsoft.com/fwlink/p/?linkid=841470) <br/> |
|**Centro servizi per contratti multilicenza Microsoft** <br/> |Il Centro servizi per contratti multilicenza Microsoft visualizza le licenze acquistate in base ai contratti Enterprise, Select, Education (Campus o School), Open Value, Open License e ISV Royalty.  <br/> |[Risorse e formazione VLSC](https://www.microsoft.com/en-us/Licensing/existing-customer/vlsc-training-and-resources.aspx) <br/> |[Centro servizi per contratti multilicenza](https://www.microsoft.com/Licensing/servicecenter/default.aspx) <br/> |
|**Minecraft Education Edition** <br/> |Usando Minecraft come piattaforma di apprendimento, i docenti possono motivare e stimolare ogni studente a raggiungere obiettivi più alti e accendere la passione per lo studio. È possibile iscriversi a una community di docenti e imparare a usare Minecraft per sbloccare le potenzialità degli studenti.  <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841480) <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841471) <br/> |
|**Microsoft Stream** <br/> |È possibile caricare e condividere video nell'intera organizzazione per migliorare la comunicazione, la partecipazione e l'apprendimento.  <br/> |[Sign up &amp; Day 0 experience](https://go.microsoft.com/fwlink/p/?linkid=841472) <br/> |[Microsoft Stream](https://go.microsoft.com/fwlink/p/?linkid=841473) <br/> |
|**Power Automate** <br/> |Power Automate è un prodotto che consente di configurare flussi di lavoro automatizzati tra le app e i servizi preferiti per sincronizzare i file, ricevere notifiche, raccogliere dati e altro ancora.  <br/> |[Iscriversi e accedere a Power Automate](https://docs.microsoft.com/power-automate/sign-up-sign-in) <br/> |[Power Automate](https://go.microsoft.com/fwlink/p/?linkid=841465) <br/> |
|**Power Virtual Agents** <br/> |Gli agenti virtuali di Power consentono ai team di creare facilmente potenti bot con un'interfaccia grafica senza codice senza bisogno di sviluppatori o esperti di dati. Power Virtual Agents risolve molti dei principali problemi relativi alla creazione di bot nel settore oggi. Elimina il divario tra gli esperti in materia e i team di sviluppo che compilano i bot e la lunga latenza tra i team che riconoscono un problema e aggiornano il bot per risolvere il problema.  <br/> |[Dettagli su licenze e accesso](https://go.microsoft.com/fwlink/?linkid=2113708) <br/> |[Iscriversi agli agenti virtuali di Power](https://aka.ms/TryPVA) <br/> |
|**Azure AD B2B** <br/> |La collaborazione business-to-business (B2B) di Azure Active Directory (Azure AD) consente di invitare utenti esterni (o "utenti guest") a usare i servizi di Azure AD a pagamento. Alcune funzionalità sono gratuite, ma per tutte le funzionalità di Azure AD a pagamento, è possibile invitare fino a cinque utenti guest per ogni licenza di edizione di Azure AD di cui si è proprietari per un dipendente o un utente non guest nel tenant. <br/> |[Iscrizione self-service per la collaborazione B2B di Azure AD](https://docs.microsoft.com/azure/active-directory/b2b/self-service-portal) <br/> |[Guida alle licenze per la collaborazione B2B di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) <br/> |
