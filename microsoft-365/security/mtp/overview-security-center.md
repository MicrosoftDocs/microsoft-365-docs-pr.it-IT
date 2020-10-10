---
title: Panoramica del Centro sicurezza Microsoft 365
description: Descrive la nuova Home per il monitoraggio e la gestione della sicurezza in tutte le identità, i dati, i dispositivi e le app di Microsoft.
keywords: sicurezza, malware, Microsoft 365, M365, Centro sicurezza, monitoraggio, report, identità, dati, dispositivi, app
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.openlocfilehash: 23f5fb935bb67efe8e08cb8be629aad242d856cb
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413437"
---
# <a name="overview-of-the-microsoft-365-security-center"></a>Panoramica del Centro sicurezza Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


La gestione della sicurezza dell'azienda per proteggersi da un paesaggio di minacce in continua evoluzione comporta molte sfide. Potrebbe essere necessario disporre di troppe soluzioni di sicurezza con diverse posizioni per configurare un numero elevato di controlli. È possibile lottare per sapere quali controlli sono i più efficaci e che introdurranno nuove sfide per la propria forza lavoro. Per i team di sicurezza può essere difficile trovare il giusto equilibrio tra sicurezza e produttività.

Immettere Microsoft 365 Security Center-la nuova Home page per il monitoraggio e la gestione della sicurezza in tutte le identità, i dati, i dispositivi, le app e l'infrastruttura di Microsoft. In questa sezione è possibile visualizzare facilmente l'integrità della sicurezza dell'organizzazione, agire per configurare dispositivi, utenti e app e ottenere avvisi per attività sospette. Microsoft 365 Security Center è progettato per aiutare gli amministratori della sicurezza e i team delle operazioni di sicurezza a gestire e proteggere la propria organizzazione.

I nuovi Microsoft 365 Security Center e [microsoft 365 Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) sono aree di lavoro specializzate progettate per soddisfare le esigenze dei team di sicurezza e conformità. Queste soluzioni sono integrate tra i servizi di Microsoft 365 e offrono informazioni utili per ridurre i rischi e salvaguardare la propria azienda digitale.

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4BmvV]

Visitare il Centro sicurezza Microsoft 365 all'indirizzo [https://security.microsoft.com](https://security.microsoft.com) . 

> [!NOTE]
> È necessario essere assegnati a un ruolo appropriato, ad esempio amministratore globale, amministratore della sicurezza, operatore di sicurezza o lettore di sicurezza in Azure Active Directory per accedere al centro sicurezza Microsoft 365.


## <a name="lets-take-a-closer-look"></a>Diamo un'occhiata più da vicino

La **Home** page Visualizza molte delle schede comuni necessarie ai team di sicurezza. La composizione delle schede e dei dati dipende dal ruolo dell'utente. Poiché Microsoft 365 Security Center utilizza il controllo di accesso basato sui ruoli, diversi ruoli vedranno le schede più significative per i loro processi giornalieri.  

Queste informazioni a colpo d'occhio consentono di tenere il passo con le attività più recenti nell'organizzazione. Il Centro sicurezza di Microsoft 365 riunisce segnali provenienti da origini diverse per presentare una visione olistica dell'ambiente Microsoft 365.

Il Centro sicurezza Microsoft 365 include:

* **Home** -visualizzazione a colpo d'occhio dell'integrità generale della sicurezza dell'organizzazione.
* **Operazioni** non consentite: vedere la storia più ampia di un attacco collegando i punti visualizzati sui singoli avvisi sulle entità. È possibile sapere esattamente dove è stato avviato un attacco, quali dispositivi sono interessati e quali sono le conseguenze della minaccia.
* **Avvisi** – avere una maggiore visibilità in tutti gli avvisi nell'ambiente Microsoft 365. Include avvisi di Microsoft cloud app Security, Office 365 ATP, Azure Active Directory, Azure ATP e Microsoft Defender ATP. Disponibile per i clienti E3 ed E5.  
* **Centro azioni** -ridurre il volume degli avvisi il team di sicurezza deve rispondere manualmente, consentendo al team di operazioni di sicurezza di concentrarsi su minacce più sofisticate e altre iniziative di alto valore.
* **Report** : consente di visualizzare i dettagli e le informazioni necessari per proteggere meglio gli utenti, i dispositivi, le app e altro ancora.
* **Secure Score**: consente di ottimizzare il livello di sicurezza complessivo con Microsoft Secure Score. In questa pagina viene fornito un riepilogo di tutte le caratteristiche e funzionalità di sicurezza che sono state abilitate e sono disponibili suggerimenti per migliorare le aree.
* **Caccia avanzata** – ricerca proattivamente di malware, file sospetti e attività nell'organizzazione Microsoft 365.
* **Classificazione**: consente di proteggere la perdita di dati aggiungendo etichette per classificare documenti, messaggi di posta elettronica, documenti, siti e altro. Quando viene applicata un'etichetta (automaticamente o dall'utente), il contenuto o il sito è protetto in base alle impostazioni selezionate. Ad esempio, è possibile creare le etichette per crittografare i file, aggiungere l'indicazione del contenuto e controllare l'accesso degli utenti a siti specifici.
* **Criteri**: consente di criteri per gestire i dispositivi, proteggere dalle minacce e ricevere avvisi su varie attività dell'organizzazione.
* **Permissions** -gestire gli utenti dell'organizzazione che dispongono dell'accesso alla visualizzazione del contenuto e all'esecuzione di attività nel centro sicurezza Microsoft 365. È inoltre possibile assegnare autorizzazioni di Microsoft 365 nel portale di Azure AD.

## <a name="learn-more"></a>Altre informazioni

Esaminare questi argomenti sul monitoraggio, la revisione e la risposta alle esigenze di sicurezza:

- Connettere i punti su avvisi tramite [eventi](incident-queue.md) non consentiti
- Correggere automaticamente le minacce mediante l' [analisi e la correzione automatizzate](mtp-autoir.md)
- Esaminare e migliorare la propria posizione di sicurezza in modo olistico con [Microsoft Secure Score](microsoft-secure-score.md)
- Visualizzare i [dispositivi](device-profile.md) nella rete
- [Segnalare](monitoring-and-reporting.md) lo stato di identità, dati, dispositivi, app e infrastruttura
- [Caccia proattivamente per minacce](advanced-hunting-overview.md) per tentativi di intrusione e attività di violazione che interessano la posta elettronica, i dati, i dispositivi e gli account
- [Comprendere le campagne e le tecniche di attacco più recenti](latest-attack-campaigns.md) con Threat Analytics

## <a name="see-also"></a>Vedere anche

- [Portali di sicurezza Microsoft](portals.md)
