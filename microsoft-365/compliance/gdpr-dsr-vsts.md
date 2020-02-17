---
title: Richieste degli interessati per Azure DevOps nell'ambito del GDPR e del CCPA
keywords: Visual Studio Team Services, VSTS, documentazione Azure DevOps, privacy, GDPR, CCPA
localization_priority: Priority
audience: itpro
ms.prod: devops
ms.topic: article
ms.date: 06/11/2018
author: robmazz
f1.keywords:
- NOCSH
ms.author: robmazz
manager: laurawi
ms.collection:
- GDPR
- M365-security-compliance
ms.workload:
- multiple
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 4ae98f6e396bdca0f1f1a4d6d360cf062878ba73
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42073273"
---
# <a name="azure-devops-services-data-subject-requests-for-the-gdpr-and-ccpa"></a>Richieste degli interessati per Azure DevOps Services nell'ambito del GDPR e del CCPA

Il [Regolamento generale sulla protezione dei dati (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) dell'Unione europea garantisce alle persone, denominate come *interessati* nel regolamento, il diritto di gestire i dati personali raccolti da un *titolare del trattamento dei dati*. Il titolare del trattamento dei dati, o semplicemente *titolare*, è il datore di lavoro o un'altra organizzazione o agenzia. I dati personali sono descritti nel GDPR come dati che si riferiscono a una persona fisica identificata o identificabile. Il GDPR garantisce agli interessati diritti specifici sui propri dati personali. Tali diritti includono la possibilità di ottenere delle copie dei dati personali, richiedere di apportare delle modifiche ai dati, limitare il trattamento dei dati, eliminarli o riceverli in un formato elettronico affinché possano essere trasferiti a un altro titolare. Una richiesta formale di un interessati rivolta a un titolare in merito a un'operazione da effettuare sui propri dati personali è denominata *Richiesta DSR* (Data Subject Rights, Diritti dell'interessato) o DSR.

Analogamente, il California Consumer Privacy Act (CCPA) fornisce obblighi e diritti in materia di privacy per i consumatori della California, inclusi diritti simili ai diritti dell'interessato del GDPR, ad esempio il diritto di eliminare, ricevere e accedere alle informazioni personali (portabilità).  Nell'ambito dei diritti che i consumatori possono esercitare, il CCPA prevede inoltre l'obbligo per determinate divulgazioni, di protezioni contro la discriminazione e requisiti di consenso o rifiuto esplicito per alcuni trasferimenti di dati classificati come "vendite". In generale, la definizione di vendite include la condivisione di dati a titolo oneroso. Per altre informazioni sul CCPA, vedere il [California Consumer Privacy Act](offering-ccpa.md) e le [Domande frequenti sul California Consumer Privacy Act](ccpa-faq.md).

Per informazioni generali sul GDPR, consultare la [sezione riguardante il GDPR del Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted).

Questa guida illustra come utilizzare gli strumenti Microsoft per esportare o eliminare i dati personali raccolti durante una sessione autenticata (dopo aver effettuato l'accesso) di Azure DevOps Services (denominato in precedenza Visual Studio Team Services).

## <a name="additional-privacy-information"></a>Ulteriori informazioni sulla privacy

Gli articoli riguardanti l'[informativa sulla privacy di Microsoft](https://privacy.microsoft.com/privacystatement), le [Condizioni dei servizi online (OST)](https://www.microsoft.com/licensing/product-licensing/products.aspx) e gli [impegni di Microsoft per il GDPR](/legal/gdpr) descrivono le procedure di trattamento dei dati.

## <a name="personal-data-we-collect"></a>Dati personali raccolti da Microsoft

Microsoft raccoglie i dati dagli utenti per eseguire e migliorare Azure DevOps Services. Azure DevOps Services raccoglie due categorie di dati, i dati dei clienti e i log generati dal sistema. I dati dei clienti includono dati transazionali e interazionali identificabili dell'utente necessari ad Azure DevOps Services necessita per fornire il servizio. I log generati dal sistema includono i dati sull'utilizzo del servizio che vengono aggregati per ogni area e funzionalità del prodotto.

## <a name="delete-azure-devops-data"></a>Eliminare i dati di Azure DevOps

Il primo passaggio per eliminare i dati dei clienti Azure DevOps Services associati e per rendere anonimi i dati personali identificabili trovati nei log generati dal sistema è quello di chiudere l'account identificativo di Azure Active Directory (AAD) o l'account Microsoft (MSA). Azure DevOps Services è considerato un sistema di record con rigide regole di integrità, tracciabilità e controllo. Questi obblighi esistenti riguardano gli obblighi di cancellazione e conservazione per il GDPR. La chiusura dell'account identificativo non altera, rimuove o modifica elementi e record associati all'identità individuale nell'organizzazione di Azure DevOps Services. Microsoft assicura che, nel momento in cui viene eliminata un'intera organizzazione Azure DevOps Services, tutti i dati personali identificabili e i log generati dal sistema rilevati in tale organizzazione vengono rimossi dal sistema (dopo il periodo di eliminazione temporanea di 30 giorni dell'organizzazione Azure DevOps Services richiesto).

## <a name="export-azure-devops-data"></a>Esportare i dati di Azure DevOps

I titolari possono esportare i dati dei clienti e i log generati dal sistema raccolti dai loro interessati con uno dei due metodi, a seconda del provider di identità (MSA o AAD) utilizzato per accedere al servizio Azure DevOps.

- Gli utenti che hanno effettuato l'autenticazione con un account supportato da un tenant di Azure, ad esempio, un account AAD o un account del servizio gestito (MSA) associato a una sottoscrizione di Azure, possono seguire le istruzioni contenute in [Richieste degli interessati per Azure nell'ambito del GDPR](gdpr-dsr-azure.md).

- Gli utenti che eseguono l'autenticazione utilizzando un'identità MSA possono utilizzare il [sito per le richieste di privacy](https://www.microsoft.com/concern/privacyrequest-msa) per visualizzare i dati delle attività legati all'identità MSA su più servizi Microsoft. In tale scenario, l'utente è titolare per i propri dati personali.

## <a name="export-or-delete-issues"></a>Problemi relativi all'esportazione o all'eliminazione

Per le identità AAD, se si verificano problemi durante l'esportazione o l'eliminazione di dati dal portale di Azure, accedere al pannello **Guida e Supporto** del portale di Azure e inviare un nuovo ticket in **Gestione della sottoscrizione** > **Altre richieste di sicurezza e conformità** > **Pannello privacy e richieste GDPR**.

Per le identità MSA, se si verificano problemi durante l'esportazione dei dati dal sito per le richieste di privacy, accedere al [sito per le richieste di privacy](https://www.microsoft.com/concern/privacyrequest-msa) e inviare una richiesta di aiuto al team della privacy di Microsoft tramite il modulo Web di richiesta.

## <a name="learn-more"></a>Ulteriori informazioni

Microsoft si impegna a garantire che i dati di Azure DevOps Services rimangano protetti e privati, senza eccezioni. Per ulteriori informazioni su come Microsoft protegge i dati di Azure DevOps Services, consultare il white paper riguardante la [panoramica sulla protezione dei dati di Azure DevOps Services](/vsts/articles/team-services-security-whitepaper?view=vsts).

## <a name="see-also"></a>Vedere anche

- [Impegni di Microsoft relativi al GDPR con i clienti dei prodotti software aziendali generalmente disponibili](https://docs.microsoft.com/legal/gdpr)
- [Centro protezione Microsoft](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
- [Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)
- [Dashboard di privacy di Microsoft](https://account.microsoft.com/privacy)
- [Microsoft Privacy Response Center](https://aka.ms/userprivacysite)
- [Richieste degli interessati per Azure nell'ambito del GDPR](gdpr-dsr-azure.md)
