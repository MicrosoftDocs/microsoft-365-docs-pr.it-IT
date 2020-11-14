---
title: Servizio di trattamento dei dati per Windows Enterprise Richieste dell’interessato relative al GDPR e alla legge californiana sulla privacy (CCPA)
description: Informazioni su come usare i prodotti, i servizi e gli strumenti di amministrazione Microsoft per trovare i dati personali e agire su di essi in risposta alle richieste degli interessati.
keywords: Microsoft 365, Microsoft 365 Education, Documentazione Microsoft 365, GDPR
localization_priority: Priority
ROBOTS: NOINDEX, NOFOLLOW
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: siosulli
author: DaniHalfin
manager: dansimp
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
ms.openlocfilehash: e4065fc992305976a1309b05a473e15e1f03f09c
ms.sourcegitcommit: e03bc2945e63f7f2638257e530056ae9283b45d9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2020
ms.locfileid: "49070880"
---
# <a name="data-processor-service-for-windows-enterprise-data-subject-requests-for-the-gdpr-and-ccpa"></a>Servizio di trattamento dei dati per le richieste dell'interessato di Windows Enterprise relative al GDPR e al California Consumer Privacy Act (CCPA) 

>[!NOTE]
>Questo argomento è rivolto ai partecipanti al servizio di trattamento dei dati per l'anteprima programma di Windows Enterprise e richiede l'accettazione di condizioni per l'utilizzo specifiche. Per ulteriori informazioni sul programma e accettare le condizioni per l'utilizzo, vedere [https://aka.ms/WindowsEnterprisePublicPreview](https://aka.ms/WindowsEnterprisePublicPreview).

## <a name="introduction-to-data-subject-requests-dsrs"></a>Introduzione alle richieste degli interessati 
Il Regolamento generale europeo sulla protezione dei dati (GDPR) attribuisce alle persone (definite nel regolamento _soggetti interessati_ ) il diritto di gestire i dati personali raccolti da un datore di lavoro o da un altro tipo di ente o organizzazione (definito _titolare del trattamento dei dati_ o semplicemente _titolare del trattamento_ ). Nel GDPR, i dati personali sono definiti molto ampiamente come qualsiasi dato relativo a una persona fisica identificata o identificabile. In base al regolamento GDPR, ai soggetti dei dati vengono assegnati diritti specifici relativamente ai dati personali, tra i quali il diritto di ottenerne copie, richiedere correzioni, limitarne l'elaborazione, eliminarli o riceverli in formato elettronico in modo che possano essere trasferiti a un altro titolare. Una richiesta formale da un soggetto interessato a un titolare del trattamento di agire sui dati personali viene definita una _Richiesta dell’interessato_ o DSR. 

Analogamente, il California Consumer Privacy Act (CCPA) fornisce obblighi e diritti in materia di privacy per i consumatori della California, inclusi diritti simili ai diritti dell'interessato del GDPR, ad esempio il diritto di eliminare, ricevere e accedere alle informazioni personali (portabilità). Nell'ambito dei diritti che i consumatori possono esercitare, il CCPA prevede inoltre l'obbligo per determinate divulgazioni, di protezioni contro la discriminazione e requisiti di consenso o rifiuto esplicito per alcuni trasferimenti di dati classificati come "vendite". In generale, la definizione di vendite include la condivisione di dati a titolo oneroso. Per altre informazioni sul CCPA, vedere il [California Consumer Privacy Act](https://docs.microsoft.com/microsoft-365/compliance/offering-ccpa) e le [Domande frequenti sul California Consumer Privacy Act](https://docs.microsoft.com/microsoft-365/compliance/ccpa-faq).

La guida descrive come utilizzare i prodotti, i servizi e gli strumenti di amministrazione Microsoft per aiutare i nostri clienti titolari del trattamento dei dati a individuare e gestire i dati personali per rispondere alle richieste DSR. In particolare, ciò include come identificare, accedere e usare i dati personali che risiedono nel cloud Microsoft. Di seguito è riportata una rapida panoramica dei processi descritti in questa guida: 

1. **Accedere** : recuperare i dati personali che risiedono nel cloud Microsoft e, se richiesto, fare una copia di tali dati che può essere disponibile per l'interessato. 
2. **Eliminare** : rimuovere in modo definitivo i dati personali che risiedevano nel cloud Microsoft. 
3. **Esportare** : fornire una copia elettronica (in un formato leggibile) dei dati personali al soggetto dei dati. Secondo il CCPA, le informazioni personali sono qualsiasi informazione riguardante una persona fisica identificata o identificabile.

Secondo il CCPA, le informazioni personali sono qualsiasi informazione riguardante una persona fisica identificata o identificabile. Non esiste distinzione tra i ruoli privati, pubblici o professionali di una persona. Il termine definito "informazioni personali" combacia con il termine "dati personali" del GDPR. Tuttavia, il CCPA include anche i dati relativi alla famiglia e al nucleo familiare. Per altre informazioni sul CCPA, vedere il [California Consumer Privacy Act](https://docs.microsoft.com/microsoft-365/compliance/offering-ccpa) e le [Domande frequenti sul California Consumer Privacy Act](https://docs.microsoft.com/microsoft-365/compliance/ccpa-faq).

Ogni sezione di questa guida illustra le procedure tecniche che un'organizzazione titolare del trattamento dei dati può adottare per rispondere a una richiesta DSR per i dati personali nel cloud Microsoft. 

## <a name="terminology"></a>Terminologia

Di seguito vengono fornite le definizioni dei termini importanti nella presente guida. 

* _Titolare:_ la persona fisica o giuridica, l'autorità pubblica, l'agenzia o altro ente che, autonomamente o unitamente ad altri soggetti, determina gli obiettivi e i mezzi del trattamento dei dati personali; laddove gli obiettivi e i mezzi di tale trattamento sono determinati da una normativa europea o di uno specifico Stato membro dell'UE, il titolare del trattamento dei dati o i criteri specifici per la sua designazione potrebbero essere forniti da tale normativa europea o di uno specifico Stato membro dell'UE. 

* _Dati personali e interessato:_ qualsiasi informazione riguardante una persona fisica identificata o identificabile ("interessato"); si considera identificabile la persona fisica che può essere identificata, direttamente o indirettamente, con particolare riferimento a un identificativo come il nome, un numero di identificazione, dati relativi all'ubicazione, un identificativo online o a uno o più elementi caratteristici della sua identità fisica, fisiologica, genetica, psichica, economica, culturale o sociale. 

* _Responsabile del trattamento:_ una persona fisica o giuridica, un'autorità pubblica, un servizio o altro organismo che tratta dati personali per conto del titolare del trattamento. 

* _Dati del cliente:_ tutti i dati compresi file di testo, audio, video o immagini e software, forniti a Microsoft per conto o dal cliente, attraverso i servizi aziendali. 

* _I dati di diagnostica di Windows:_ sono composti da dati tecnici fondamentali inviati da dispositivi Windows e relativi al dispositivo e alle prestazioni di Windows e del software correlato. Attraverso l'analisi aggregata dell'uso di Windows, tali dati vengono usati per mantenere Windows aggiornato, protetto, affidabile, ottimizzato e per buone prestazioni. Alcuni esempi di dati di diagnostica di Windows sono il tipo di hardware usato, le applicazioni installate con le rispettive condizioni di uso e le informazioni sull'affidabilità nei driver dei dispositivi. Alcuni componenti e app di Windows si connettono direttamente ai servizi Microsoft, tuttavia i dati scambiati non sono dati di diagnostica di Windows. Ad esempio, lo scambio di informazioni relative alla posizione dell’utente per il meteo o le notizie locali non è un esempio di dati di diagnostica di Windows. 

## <a name="how-to-use-this-guide"></a>Come usare questa guida 

Se si usa il servizio di trattamento dei dati per i dispositivi registrati a Windows Enterprise, vengono generate alcune informazioni, ossia i dati di diagnostica di Windows, per fornire il servizio.

## <a name="windows-diagnostic-data"></a>Dati di diagnostica di Windows 

Microsoft consente di accedere, eliminare ed esportare i dati di diagnostica Windows associati all'uso da parte dell'utente del servizio di trattamento dei dati per Windows Enterprise.

>[!IMPORTANT]
>La possibilità di rettificare i dati di diagnostica non è supportata. I dati diagnostica di Windows costituiscono le azioni effettive eseguite all’interno di Windows e le modifiche a tali dati potrebbero compromettere il record cronologico delle azioni, aumentare i rischi per la sicurezza e compromettere l’affidabilità. Tutti i dati trattati in questo documento sono da considerarsi dati di diagnostica di Windows. 

## <a name="executing-dsrs-against-windows-diagnostic-data"></a>Esecuzione delle richieste degli interessati rispetto ai dati di diagnostica di Windows 

Microsoft consente di accedere, eliminare ed esportare alcuni dati di diagnostica Windows tramite il portale di Azure e direttamente tramite le API preesistenti.

### <a name="step-1-access"></a>Passaggio 1: accesso 

L'amministratore tenant è l'unica persona all’interno dell'organizzazione che può accedere ai dati di diagnostica di Windows associati all'uso da parte di un utente specifico di un servizio di trattamento dei dati per dispositivi registrati a Windows Enterprise. I dati recuperati per una richiesta di accesso saranno disponibili, tramite esportazione, in formato leggibile dal computer e verranno forniti nei file che consentiranno all'utente di comprendere a quali servizi e dispositivi sono associati i dati. Come indicato in precedenza, i dati recuperati non includeranno dati che potrebbero compromettere la sicurezza o la stabilità del dispositivo Windows. 

Microsoft fornisce un’esperienza portale che consente all'amministratore del tenant del cliente aziendale di gestire le richieste di accesso DSR. [DSR per Azure, parte 2, passaggio 3: esportazione](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure#step-3-export) descrive come eseguire una richiesta di accesso DSR, tramite esportazione, attraverso il portale di Azure.

### <a name="step-2-delete"></a>Passaggio 2: eliminazione 

Microsoft fornisce una modalità di esecuzione delle richieste di eliminazione DSR basate sull'utente, in base a un particolare oggetto di Azure Active Directory.

Per le richieste di eliminazione basate sull’utente, Microsoft fornisce un’esperienza portale che consente all'amministratore tenant del cliente aziendale di gestire le richieste di eliminazione DSR. [DSR per Azure, parte 1, passaggio 5: eliminazione](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure#step-5-delete) descrive come eseguire una richiesta di eliminazione DSR tramite il portale di Azure. 

Microsoft consente di eliminare gli utenti, che a loro volta elimineranno i dati dei clienti, direttamente tramite l’interfaccia di programmazione dell'applicazione preesistente (API). Informazioni dettagliate sono disponibili nella [ documentazione di riferimento dell’interfaccia di programmazione dell'applicazione (API)](https://docs.microsoft.com/graph/api/directory-deleteditems-delete?view=graph-rest-beta). 

>[!IMPORTANT]  
>L'eliminazione dei dati raccolti non interrompe la raccolta ulteriore di dati. Per disattivare la raccolta dei dati, seguire la procedura descritta nella [documentazione di riferimento del rispettivo servizio](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management).
 
 Inoltre, per le richieste di eliminazione basate sull'utente è necessario eliminare l’account utente stesso. 

### <a name="step-3-export"></a>Passaggio 3: esportazione 

L'amministratore tenant è l'unica persona all’interno dell'organizzazione che può accedere ai dati di diagnostica di Windows associati all'uso da parte di un utente specifico di un servizio di trattamento dei dati per dispositivi registrati a Windows Enterprise. I dati recuperati per una richiesta di esportazione saranno disponibili in un formato leggibile dal computer e verranno forniti nei file che consentiranno all'utente di comprendere a quali servizi e dispositivi sono associati i dati. Come indicato in precedenza, i dati recuperati non includeranno dati che potrebbero compromettere la sicurezza o la stabilità del dispositivo Windows. [DSR per Azure, parte 2, passaggio 3: esportazione](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure#step-3-export) descrive come eseguire una richiesta di esportazione DSR tramite il portale di Azure. 

Microsoft consente di esportare i dati dei clienti direttamente tramite l’interfaccia di programmazione dell'applicazione preesistente (API). Informazioni dettagliate sono disponibili nella [ documentazione di riferimento dell’interfaccia di programmazione dell'applicazione (API)](https://docs.microsoft.com/graph/api/user-exportpersonaldata?view=graph-rest-1.0).

## <a name="notify-about-exporting-or-deleting-issues"></a>Notificare problemi riguardanti l'esportazione o l'eliminazione 

Se si verificano problemi durante l'esportazione o l'eliminazione di dati dal portale di Azure, accedere al pannello **Guida e Supporto** del portale di Azure e inviare un nuovo ticket in **Gestione della sottoscrizione > Altre richieste di sicurezza e conformità > Pannello privacy e richieste GDPR**. 
