---
title: Mitigazioni per la gestione della continuità aziendale della società in Microsoft 365
author: chrfox
f1.keywords:
- NOCSH
ms.author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Alcuni esempi di mitigazioni per scenari di eventi imprevisti relativi ai servizi di Microsoft 365.
ms.openlocfilehash: e5313464a45be679eaee6c4d06ca000e63c1010c
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086634"
---
# <a name="service-incident-mitigation-strategies"></a>Strategie di mitigazione degli eventi imprevisti relativi ai servizi

In questo articolo sono illustrate alcune strategie e alcuni scenari per mitigare l'impatto di un evento imprevisto relativo ai servizi Microsoft 365 sul processo aziendale.

## <a name="service-incident-scenarios-and-potential-mitigations"></a>Scenari di eventi imprevisti relativi ai servizi e possibili mitigazioni

|Dipendenza di Microsoft 365|Possibili mitigazioni|
|---------|---------|
|Il sistema di gestione degli eventi imprevisti fa affidamento su Exchange Online per coinvolgere tecnici reperibili e responsabili degli eventi imprevisti.|Assicurarsi che il sistema di gestione degli eventi imprevisti supporti le comunicazioni multicanale, come la posta elettronica parallela, le telefonate e le notifiche tramite SMS, nonché gerarchie di chiamata ad albero in modo che il sistema possa contattare automaticamente il contatto di backup nel caso in cui il contatto principale non sia raggiungibile. Includere in ogni notifica anche metodi di contatto di backup, in modo da incorporare i metodi di comunicazione di backup per potervi fare più facilmente riferimento. Se il servizio di gestione degli eventi imprevisti non è disponibile, per casi di emergenza è possibile usare metodi di comunicazione alternativa, come Yammer.|
|Per archiviare i file a cui si accede tramite il client, si usa Microsoft Teams.|Teams archivia i file caricati nel client in una raccolta documenti di SharePoint Online. I file sono comunque accessibili tramite SharePoint Online. Addestrare gli utenti a usare i percorsi dei file in SharePoint Online.|
|Per le comunicazioni di carattere generale e per la valutazione della gestione degli eventi imprevisti si fa affidamento sulle conferenze telefoniche di Microsoft Teams.|Definire una soluzione per conferenze di backup con un provider di terze parti.|
|Come metodo di comunicazione secondario vengono usati i telefoni VoIP.|Implementare telefoni non VoIP in grado di effettuare chiamate PSTN, in particolare per i centri operativi di rete e di assistenza in caso di eventi imprevisti. Aggiungere i numeri di telefono cellulare dei dipendenti alla rubrica aziendale per consentire al personale interessato di essere contattato tramite cellulare.|
|Per l'archiviazione dei file e la produttività degli utenti si fa affidamento su OneDrive for Business. [File su richiesta](https://techcommunity.microsoft.com/t5/Microsoft-OneDrive-Blog/OneDrive-Files-On-Demand-For-The-Enterprise/ba-p/117234) è configurato in modo da liberare spazio nelle unità locali degli utenti.|La sincronizzazione di OneDrive fornisce criteri di gruppo che consentono agli amministratori di richiedere la sincronizzazione in locale di contenuti specifici o di liberare spazio se necessario. Per mitigare il rischio di inaccessibilità ai documenti, configurare questi criteri per la sincronizzazione in locale dei documenti critici. Insegnare agli utenti ad applicare manualmente l'impostazione "Conserva sempre su questo dispositivo" per i documenti chiave.|
|Per comunicare interruzioni dei servizi aziendali a clienti e fornitori, si usa Exchange Online.|Come strumento di comunicazione di massa alternativo è possibile usare social network pubblici di terze parti.
|L'architettura locale ibrida, come ADFS o l'autenticazione pass-through, non funziona causando interruzioni della capacità dell'utente di eseguire l'autenticazione ai servizi cloud.|Configurare la [Sincronizzazione hash password](https://docs.microsoft.com/azure/active-directory/authentication/concept-resilient-controls#deploy-password-hash-sync-even-if-you-are-federated-or-use-pass-through-authentication), in combinazione con i servizi di autenticazione ibrida, come meccanismo di autenticazione secondario basato sul cloud per evitare interruzioni di accesso durante l'interruzione. Per ulteriori informazioni sulla creazione di architetture resilienti e sui controlli di accesso, vedere [Creare una strategia resiliente per la gestione dei controlli di accesso con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/concept-resilient-controls).|  

## <a name="leveraging-mobile-app-access"></a>Sfruttare l'accesso alle app per dispositivi mobili

In seguito alla notevole diffusione dell'uso dei dispositivi mobili, sono disponibili nuovi strumenti per rimanere connessi, di conseguenza le applicazioni per dispositivi mobili di Microsoft 365 possono costituire un elemento chiave della strategia di resilienza. Dal momento che sono connessi ai servizi cloud tramite la rete cellulare, non dipendono dall'infrastruttura di rete dell'organizzazione.

È possibile usare Outlook come esempio. Gli utenti possono connettersi alle proprie cassette postali di Exchange Online tramite protocolli di rete diversi (HTTPS o MAPI) a seconda dell'app di posta elettronica in uso. Se si verifica un evento imprevisto relativo ai servizi che interessa uno dei protocolli usati dal client desktop, ad esempio MAPI, gli utenti possono comunque accedere alla propria cassetta postale tramite l'app Outlook Mobile o Outlook sul Web.
  
Se si decide di consentire agli utenti di connettersi ai servizi di Microsoft 365 tramite dispositivi mobili, è possibile usare Microsoft Intune per configurare e gestire in modo sicuro tali dispositivi. Dopo la registrazione degli account utente e dei dispositivi nella soluzione di gestione dei dispositivi mobili, assicurarsi che le app siano state scaricate e configurate.
