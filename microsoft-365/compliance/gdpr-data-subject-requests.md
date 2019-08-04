---
title: Richieste del soggetto dei dati per l'RGPD
description: ''
keywords: Microsoft 365, Microsoft 365 Education, Documentazione Microsoft 365, GDPR
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: GDPR
ms.openlocfilehash: dc4352ac14f42a227f1572b0c7f1442aa4dec838
ms.sourcegitcommit: c201f5cc13d501e5207ebad166e42f90260af0c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2019
ms.locfileid: "35078906"
---
# <a name="data-subject-requests-and-the-gdpr"></a>Richieste dell’interessato e GDPR

Il regolamento generale per la protezione dei dati (GDPR) introduce nuove regole per le organizzazioni che offrono beni e servizi alle persone che risiedono nell'Unione europea (UE) o che raccolgono e analizzano i dati dei residenti nell'UE in qualunque luogo si trovi l'utente o la sua azienda. Altri dettagli sono disponibili [nell'argomento Riepilogo sul GDPR](gdpr.md). <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWs1SI] 

Questo documento illustra come completare le richieste dell’interessato (DSR) secondo il GDPR usando i prodotti e i servizi Microsoft.

- [Office 365](gdpr-dsr-Office365.md)
- [Azure](gdpr-dsr-Azure.md)
- [Intune](gdpr-dsr-Intune.md)
- [Dynamics 365](gdpr-dsr-Dynamics365.md)
- [Famiglia di prodotti Visual Studio](gdpr-dsr-visual-studio-family.md)
- [Azure DevOps Services](gdpr-dsr-vsts.md)
- [Servizi professionali e supporto tecnico Microsoft](gdpr-dsr-prof-services.md)

## <a name="terminology"></a>Terminologia

Definizioni utili per i termini relativi al GDPR usati nel documento:

- *Titolare del trattamento dei dati (Titolare)*: una persona giuridica, un'autorità pubblica, un'agenzia o un altro organismo che, da solo o congiuntamente con altri, determina le finalità e le modalità di trattamento dei dati personali.  
- *Dati personali* e *soggetto interessato*: qualsiasi informazione relativa a una persona naturale identificata o identificabile (soggetto interessato); una persona naturale identificabile è una persona che può essere identificata, direttamente o indirettamente.  
- *Responsabile*: una persona fisica o giuridica, un'autorità pubblica o un altro ente che si occupa del trattamento dei dati personali per conto del titolare.  
- *Dati dei clienti*: dati prodotti e archiviati nelle attività quotidiane di gestione della propria attività.

## <a name="what-is-a-dsr"></a>Che cos’è una richiesta dell’interessato?

Il regolamento generale sulla protezione dei dati (GDPR) attribuisce alle persone (definite nel regolamento "soggetti interessati") il diritto di gestire i dati personali raccolti da un datore di lavoro o da un altro tipo di organizzazione o organismo (definito titolare del trattamento dei dati o semplicemente titolare del trattamento). In base al regolamento GDPR, ai soggetti dei dati vengono assegnati diritti specifici per i dati personali, tra i quali il diritto di ottenere copie dei dati personali stessi, richiedere modifiche di tali dati, limitarne l'elaborazione, eliminarli o riceverli in formato elettronico in modo che possano essere trasferiti a un altro titolare.

In quanto titolare, è necessario prendere in considerazione ogni richiesta dell’interessato e fornire una risposta sostanziale, eseguendo l'azione richiesta o fornendo una spiegazione del motivo per cui la richiesta non può essere soddisfatta dal titolare. Un titolare deve rivolgersi al proprio consulente legale o alla conformità relativamente all'idoneità di qualsiasi richiesta dell’interessato specifica.

È possibile che nel completamento di una richiesta siano coinvolti diversi processi, soggetti alle regole di conformità al GDPR dell'organizzazione.
  
- **Individuazione**. Il processo di determinazione dei dati necessari per completare una richiesta dell’interessato.
- **Accesso**. Il recupero e la potenziale trasmissione al soggetto interessato delle informazioni individuate.
- **Rettifica**. Implementare le modifiche o altre modifiche ai dati personali richieste.
- **Restrizione**. Modifica dell'accesso o dell'elaborazione dei dati personali, restrizione dell'accesso o rimozione dei dati da Microsoft Cloud.
- **Esportazione**. Fornire un "formato strutturato, comunemente usato e leggibile dalla macchina" dei dati personali del soggetto interessato, come indicato dal "diritto alla portabilità dei dati" del GDPR.
- **Eliminazione**. Rimozione definitiva dei dati personali da Microsoft Cloud.

## <a name="specific-dsr-considerations"></a>Considerazioni specifiche sulle richieste dell’interessato

### <a name="insights-generated-by-microsoft-products-or-services"></a>Informazioni dettagliate generate da prodotti o servizi Microsoft

[Le informazioni dettagliate](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365) potrebbero essere generate da servizi (MyAnalytics e così via) Office 365 include servizi online che forniscono informazioni dettagliate agli utenti e alle organizzazioni che le usano. I dati generati da questi servizi possono produrre dati personali pertinenti a una richiesta dell’interessato. Seguire il collegamento nell'elenco riportato di seguito per informazioni dettagliate sui processi delle richieste specifici del servizio.  

### <a name="dsrs-for-system-generated-logs"></a>Richieste dell’interessato per i log generati dal sistema

I log e i dati correlati generati da Microsoft potrebbero contenere dati considerati personali secondo la definizione di “dati personali” del GDPR. La possibilità di limitare o rettificare i dati nei log generati dal sistema non è supportata. I dati nei log generati dal sistema costituiscono le azioni effettive eseguite nel cloud Microsoft e i dati di diagnostica e le modifiche a tali dati possono compromettere il record cronologico delle azioni, aumentando i rischi per la sicurezza e di truffe. Microsoft consente di accedere, esportare ed eliminare i log generati dal sistema che potrebbero essere necessari per completare una richiesta dell’interessato. Tra questi tipi di dati rientrano:  

- Dati di utilizzo di prodotti e servizi, ad esempio log di attività dell'utente
- Richieste di ricerca degli utenti e dati della query
- Dati generati da prodotti e servizi, come risultato della funzionalità del sistema e dell'interazione da parte di utenti o di altri sistemi.  

### <a name="yammer-and-kaizala"></a>Yammer e Kaizala

L'eliminazione di un account utente non rimuove i log generati dal sistema per Yammer e Kaizala. Per rimuovere i dati da queste applicazioni, vedere uno degli argomenti seguenti:

- [Gestire le richieste dell'interessato per il GDPR in Yammer Enterprise](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise)
- [Esportare o eliminare i dati dell'organizzazione di un utente in Kaizala](https://docs.microsoft.com/office365/kaizala/export-or-delete-a-user-s-data)

### <a name="national-clouds"></a>Cloud nazionali

In alcuni cloud nazionali, un amministratore IT globale deve eliminare i log generati dal sistema.

### <a name="microsoft-services"></a>Servizi Microsoft

Se l'organizzazione o gli utenti si impegnano con Microsoft a ricevere supporto tecnico relativo ai prodotti e ai servizi Microsoft, alcuni di questi dati possono contenere dati personali. Per altre informazioni, vedere [Richieste dell’interessato per il GDPR relative ai servizi professionali e al supporto tecnico Microsoft](gdpr-dsr-prof-services.md).

### <a name="microsoft-controller-products"></a>Prodotti con titolare Microsoft

In alcune situazioni, gli utenti dell'organizzazione possono accedere ai prodotti o ai servizi Microsoft per cui Microsoft è il titolare del trattamento dei dati. In questi casi, è necessario che gli utenti rivolgano le proprie richieste direttamente a Microsoft, e Microsoft soddisferà le richieste per l'utente direttamente.

### <a name="third-party-products"></a>Prodotti di terze parti

Per i prodotti e i servizi di terze parti a cui è stato eseguito l'accesso tramite l'autenticazione con l'account Microsoft, tutte le richieste dell’interessato devono essere rivolte alla terza parte competente.

## <a name="learn-more"></a>Ulteriori informazioni

- [Centro protezione Microsoft](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
