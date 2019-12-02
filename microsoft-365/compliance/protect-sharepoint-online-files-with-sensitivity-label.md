---
title: Proteggere i file di SharePoint Online con un'etichetta di riservatezza
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/27/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
ms.custom:
- Ent_Solutions
ms.assetid: 5b9c8e41-25d2-436d-89bb-9aecb9ec2b80
description: 'Riepilogo: Applicare la protezione delle informazioni di Azure per proteggere i file in un sito del team di SharePoint Online di livello estremamente riservato.'
ms.openlocfilehash: b5251d393249e9023f6f437cb3df6c074ebdf436
ms.sourcegitcommit: bf30a2314376f0b7d577741b97df017969737d11
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/27/2019
ms.locfileid: "39638061"
---
# <a name="protect-sharepoint-online-files-with-a-sensitivity-label"></a>Proteggere i file di SharePoint Online con un'etichetta di riservatezza

Seguire la procedura descritta in questo articolo per configurare un'etichetta di riservatezza di Office 365 per fornire la crittografia e le autorizzazioni per i file. Questi file possono essere aggiunti a una raccolta di SharePoint configurata per la protezione di livello estremamente riservato. In alternativa, è possibile aprire un file direttamente dal sito e applicare l'etichetta. La protezione tramite crittografia e autorizzazioni è veicolata da un file quando viene scaricato dal sito. 

La procedura fa parte di una soluzione più ampia per configurare la protezione estremamente riservata per i siti di SharePoint e i file al loro interno. Per ulteriori informazioni, vedere [Siti e file di Secure SharePoint Online](https://docs.microsoft.com/microsoft-365/compliance/deploy-sharepoint-online-sites-for-three-tiers-of-protection). 

L'uso delle etichette di riservatezza per i file in SharePoint Online non è consigliato per tutti i clienti, ma è disponibile come opzione per i clienti che hanno l'esigenza di questo livello di protezione per un sottoinsieme di file.

Alcune note importanti su questa soluzione:
- Quando si applica la crittografia ai file archiviati in Office 365, il servizio non è in grado di elaborare il contenuto di questi file. La creazione condivisa, eDiscovery, la ricerca, Delve e altre funzionalità di collaborazione non funzionano. I criteri di prevenzione della perdita dei dati (DLP) funzionano solo con i metadati, incluse le etichette di Office 365, ma non con il contenuto dei file, ad esempio i numeri di carta di credito all'interno dei file.

- Questa soluzione prevede che un utente selezioni un'etichetta che applica la protezione. Se è necessaria la crittografia automatica e la possibilità che SharePoint indicizzi e controlli i file, è consigliabile usare Information Rights Management (IRM) in SharePoint Online. Quando si configura una raccolta di SharePoint per IRM, i file vengono crittografati automaticamente quando vengono scaricati per la modifica.  SharePoint IRM ha alcune limitazioni che potrebbero influire sulla decisione. Per altre informazioni, vedere [Configurare Information Rights Management (IRM) nell'interfaccia di amministrazione di SharePoint](https://support.office.com/article/Set-up-Information-Rights-Management-IRM-in-SharePoint-admin-center-239CE6EB-4E81-42DB-BF86-A01362FED65C).

## <a name="admin-setup"></a>Configurazione degli amministratori

Per implementare questo ulteriore livello di sicurezza per i file in un determinato sito del team di SharePoint Online, è necessario configurare un'etichetta di riservatezza personalizzata che sia l'etichetta specifica o una sottoetichetta dell'etichetta generale per i dati altamente regolamentati. Solo i membri del gruppo di Office 365 per il sito del team di SharePoint Online vedranno l'etichetta o la sottoetichetta personalizzata nell'elenco di etichette.

- Usare un'etichetta di riservatezza quando è necessario un numero limitato di etichette sia per l'uso globale che per i singoli team privati.

- Usare una sottoetichetta di riservatezza se si ha un numero elevato di etichette o se si vogliono organizzare le etichette per i team estremamente riservati sotto l'etichetta per i dati altamente regolamentati.

Seguire [queste istruzioni ](encryption-sensitivity-labels.md) per configurare un'etichetta separata o una sottoetichetta con le impostazioni seguenti:

- Il nome dell'etichetta o della sottoetichetta contiene il nome del team
- La crittografia è abilitata
- Il gruppo di Office 365 per il sito del team dispone delle autorizzazioni per la creazione condivisa

Una volta creata, pubblicare la nuova etichetta o sottoetichetta per gli utenti, che potranno quindi applicarla ai file in locale prima di caricarli nel team o dopo che il file sarà archiviato nel team.
 
Gli utenti possono selezionare l'etichetta di riservatezza dall'opzione **Riservatezza** nella scheda **Home** sulla barra multifunzione di Microsoft Word, Excel e PowerPoint.
  
> [!NOTE]
> Se sono presenti più siti del team di SharePoint Online altamente riservati, è consigliabile creare più etichette di riservatezza. 
  
## <a name="adding-permissions-for-external-users"></a>Aggiunta delle autorizzazioni per gli utenti esterni
Esistono due modi per concedere agli utenti esterni l'accesso ai file protetti con un'etichetta di riservatezza. In entrambi i casi gli utenti esterni devono avere un account di Azure AD. Se gli utenti esterni non sono membri di un'organizzazione che usa Azure AD, possono ottenere un account di Azure AD come utente singolo da questa pagina di iscrizione: [https://aka.ms/aip-signup](https://aka.ms/aip-signup).

 - Aggiungere utenti esterni al gruppo di Office 365 per il sito del team. È necessario per prima cosa aggiungere l'account come utente B2B nella propria directory. Il [caching dell'appartenenza a gruppi da parte di Azure Rights Management](https://docs.microsoft.com/azure/information-protection/plan-design/prepare#group-membership-caching-by-azure-information-protection) può richiedere un paio d'ore.  
 - Aggiungere account utente esterni direttamente alla configurazione dell'etichetta. È possibile aggiungere tutti gli utenti di un'organizzazione (ad esempio, Fabrikam.com), un gruppo di Office 365 (ad esempio, il gruppo contabilità di un'organizzazione) oppure un utente. Ad esempio, è possibile aggiungere un team esterno di autorità normative alle autorizzazioni dell'etichetta di riservatezza.

## <a name="see-also"></a>Vedere anche

[Protezione di file e siti di SharePoint Online](https://docs.microsoft.com/microsoft-365/compliance/deploy-sharepoint-online-sites-for-three-tiers-of-protection)
  
[Guida sulla sicurezza Microsoft per organizzazioni che si occupano della campagna politica, no profit e altre organizzazioni Agile](/security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[Adozione del cloud e soluzioni ibride](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
