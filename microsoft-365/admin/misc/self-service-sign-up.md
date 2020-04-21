---
title: Uso dell'iscrizione self-service nell'organizzazione
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 4f8712ff-9346-4c6c-bb63-a21ad7a62cbd
description: Informazioni sull'iscrizione a Microsoft 365 self-service e sui programmi self-service disponibili, ad esempio Microsoft Power Apps, Microsoft Flow e Dynamics 365 per i servizi finanziari.
ms.custom: okr_SMB
ms.openlocfilehash: d20609d48c71795205940546bef752c236ae3e81
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627801"
---
# <a name="using-self-service-sign-up-in-your-organization"></a>Uso dell'iscrizione self-service nell'organizzazione

È possibile ascoltare i propri commenti e rendere più facile per gli utenti dell'organizzazione iscriversi ai servizi online di Microsoft. Questo nuovo processo viene definito "iscrizione self-service" in quanto gli utenti possono effettuare l'iscrizione per usare i servizi pagati tramite l'abbonamento oppure usare i servizi gratuiti senza che sia necessario eseguire operazioni a loro nome.
  
## <a name="how-self-service-sign-up-works"></a>Funzionamento dell'iscrizione self-service

L'esempio seguente descrive come funziona l'iscrizione self-service per un istituto di istruzione. Lo stesso processo funziona per qualsiasi organizzazione con programmi self-service abilitati nel proprio tenant.
  
1. Gli studenti e i membri della facoltà hanno indirizzi di posta elettronica dell'istituto di istruzione, che indicano che sono associati all'istituto. L'indirizzo di posta elettronica jakob@uw.edu può ad esempio indicare uno studente dell'Università di Washington.

2. Studenti e docenti accedere al [sito Web](https://go.microsoft.com/fwlink/p/?LinkId=536628)e utilizzare il proprio indirizzo di posta elettronica per iscriversi ai servizi offerti dall'organizzazione, ad esempio Microsoft 365 Apps for Enterprise. Possono anche iscriversi ad altri servizi gratuiti offerti.

3. Convalidare il proprio indirizzo di posta elettronica e quindi iniziare a utilizzare Microsoft 365, Power BI o altri servizi subito.

4. Come amministratore dell'azienda, è possibile visualizzare gli utenti che hanno effettuato l'iscrizione a un abbonamento visualizzando la pagina **prodotti & Services** nell'interfaccia di amministrazione. In questo modo è possibile vedere quando ci sono licenze nuove o non riconosciute per i servizi nel tenant. Per controllare se gli utenti possono iscriversi per le sottoscrizioni in modalità self-service, utilizzare il cmdlet [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0) di PowerShell con il parametro **AllowAdHocSubscriptions** . Per ulteriori informazioni, vedere [come si controllano le impostazioni self-service?](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/self-service-purchase-faq?view=o365-worldwide)

## <a name="available-self-service-programs"></a>Programmi self-service disponibili

Di seguito sono elencati i programmi self-service attualmente disponibili. Questo elenco verrà aggiornato man mano che vengono aggiunti nuovi programmi.
  
|||||
|:-----|:-----|:-----|:-----|
|**Programma** <br/> |**Descrizione** <br/> |**Altre informazioni** <br/> |****Sito Web per l'iscrizione self-service**** <br/> |
|Office 365 a1 * * * * <br/> |Qualsiasi studente o insegnante può usare un indirizzo di posta elettronica scolastico per iscriversi gratuitamente a Office 365 e ottenere le app di Office per il Web, 1 TB di spazio di archiviazione cloud di OneDrive e SharePoint Online per i siti di classe, team e di progetto.  <br/> |[Domande frequenti tecniche su Office 365 Education](https://go.microsoft.com/fwlink/p/?LinkId=536625) <br/> |[Office 365 Education](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Office 365 a1 Plus** <br/> |Gli studenti e gli insegnanti idonei possono iscriversi a Office 365 a1 Plus, che include tutto quello menzionato sopra oltre a Microsoft 365 Apps for Enterprise. Microsoft 365 Apps for Enterprise è un software per la produttività, tra cui Word, PowerPoint, Excel, Outlook, OneNote, Publisher, Access e Skype for business, installato nel computer desktop o laptop.  <br/> |[Domande frequenti tecniche su Office 365 Education](https://go.microsoft.com/fwlink/p/?LinkId=536625) <br/> |[Office 365 Education](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Power BI** <br/> |Power BI consente agli utenti di visualizzare i dati, condividere le individuazioni e collaborare in modi nuovi e intuitivi. <br/> Se l'organizzazione sottoscrive già la sottoscrizione, è possibile visualizzare le licenze per "Power BI Pro single user trial", che offre agli utenti un accesso gratuito limitato alle funzionalità avanzate.  <br/> |[Power BI nell'organizzazione](https://go.microsoft.com/fwlink/p/?LinkId=536626) <br/> |[Microsoft Power BI](https://go.microsoft.com/fwlink/p/?LinkId=536629) <br/> |
|**Rights Management Services (RMS)** <br/> |RMS per singoli utenti è un abbonamento gratuito self-service per gli utenti di un'organizzazione a cui sono stati inviati file dal contenuto riservato protetti da Azure Rights Management (Azure RMS), ma il cui reparto IT non ha implementato Azure Rights Management (Azure RMS) o Active Directory Rights Management Services (AD RMS).  <br/> |[RMS per utenti singoli e Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=536627) <br/> |[Portale di Microsoft Rights Management](https://portal.azure.com/) per verificare se è possibile aprire un determinato documento protetto da diritti.  <br/> |
|**Microsoft Power Apps** <br/> |In PowerApps è possibile gestire i dati dell'organizzazione eseguendo un'app creata personalmente o creata e condivisa da qualcun altro. Le app vengono eseguite su dispositivi mobili come i telefoni oppure in un browser aprendo Dynamics 365. È possibile creare un'infinita varietà di app senza che sia necessario conoscere un linguaggio di programmazione, come C#.  <br/> |[Iscrizione self-service a PowerApps](https://go.microsoft.com/fwlink/p/?linkid=841461) <br/> |[Microsoft Power Apps](https://go.microsoft.com/fwlink/p/?linkid=841462) <br/> |
|**Dynamics 365 for Financials** <br/> |È una soluzione completa per la gestione aziendale e finanziaria pensata per le piccole e medie imprese. Con Dynamics 365 for Financials i processi di ordinazione, vendita, fatturazione e reporting sono più facili che mai.  <br/> |[Microsoft Dynamics 365 for Financials](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |[Microsoft Dynamics 365 for Financials](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |
|**Microsoft Dynamics 365 for Operations** <br/> |Questa soluzione aumenta l'efficienza sul lavoro. Gli strumenti ERP completi disponibili in Dynamics 365 for Operations forniscono scalabilità globale e intelligenza digitale per aiutare le aziende a crescere con i propri ritmi.  <br/> |[Microsoft Dynamics 365 for Operations](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |[Microsoft Dynamics 365 for Operations](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |
|**Microsoft AppSource** <br/> |Microsoft AppSource è una destinazione per le app SaaS aziendali sviluppate sulla piattaforma cloud Microsoft. AppSource offre centinaia di app, componenti aggiuntivi e pacchetti di contenuto che ampliano le funzionalità di prodotti Microsoft come Azure, Dynamics 365, Office 365 e Power BI.  <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |
|**Incentivi per i partner Microsoft** <br/> |Microsoft Partner Network offre tre tipi di adesione. Ogni tipo offre un set di vantaggi che aiutano l'azienda a crescere. Man mano che si raggiungono gli obiettivi prefissati, è possibile partecipare al programma al livello che soddisfa le specifiche esigenze per accedere ad altri vantaggi e sviluppare il rapporto con Microsoft e con altri partner della rete.  <br/> |[Incentivi per i partner Microsoft](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |[Incentivi per i partner Microsoft](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |
|**Microsoft Business Center** <br/> |Microsoft Business Center è il portale per i clienti che hanno effettuato acquisti tramite il contratto di prodotti e servizi Microsoft (MPSA). <br/> |[Guida introduttiva: Registrarsi per il Microsoft Business Center](https://go.microsoft.com/fwlink/p/?linkid=841479) <br/> |[Microsoft Business Center](https://go.microsoft.com/fwlink/p/?linkid=841470) <br/> |
|**Centro servizi per contratti multilicenza Microsoft** <br/> |Il centro servizi per contratti multilicenza di Microsoft Visualizza le licenze acquistate in Enterprise, Select, Education (Campus o School), Open Value, Open License e ISV Royalty agreements.  <br/> |[Formazione e risorse di VLSC](https://www.microsoft.com/en-us/Licensing/existing-customer/vlsc-training-and-resources.aspx) <br/> |[Centro servizi per contratti multilicenza](https://www.microsoft.com/Licensing/servicecenter/default.aspx) <br/> |
|**Minecraft Education Edition** <br/> |Usando Minecraft come piattaforma di apprendimento, i docenti possono motivare e stimolare ogni studente a raggiungere obiettivi più alti e accendere la passione per lo studio. È possibile iscriversi a una community di docenti e imparare a usare Minecraft per sbloccare le potenzialità degli studenti.  <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841480) <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841471) <br/> |
|**Microsoft Stream** <br/> |È possibile caricare e condividere video nell'intera organizzazione per migliorare la comunicazione, la partecipazione e l'apprendimento.  <br/> |[Sign up &amp; Day 0 experience](https://go.microsoft.com/fwlink/p/?linkid=841472) <br/> |[Microsoft Stream](https://go.microsoft.com/fwlink/p/?linkid=841473) <br/> |
|**Automatizzare la potenza** <br/> |Power automatizzate è un prodotto che consente di configurare i flussi di lavoro automatizzati tra le app e i servizi preferiti per sincronizzare i file, ottenere notifiche, raccogliere dati e altro ancora.  <br/> |[Iscriviti e accedi per il servizio automatizzato di alimentazione](https://docs.microsoft.com/power-automate/sign-up-sign-in) <br/> |[Automatizzare la potenza](https://go.microsoft.com/fwlink/p/?linkid=841465) <br/> |
|**Agenti virtuali di alimentazione** <br/> |Power Virtual Agents consente ai team di creare facilmente bot potenti utilizzando un'interfaccia grafica senza codice guidata e senza il bisogno di scienziati o sviluppatori di dati. Power Virtual Agents affronta molti dei principali problemi relativi alla creazione di bot nell'industria odierna. Elimina il divario tra gli esperti del soggetto e i team di sviluppo che costruiscono i bot e la lunga latenza tra i team che riconoscono un problema e aggiornano il bot per risolverlo.  <br/> |[Informazioni su licenze e accessi](https://go.microsoft.com/fwlink/?linkid=2113708) <br/> |[Iscriversi a Power Virtual Agents](https://aka.ms/TryPVA) <br/> |