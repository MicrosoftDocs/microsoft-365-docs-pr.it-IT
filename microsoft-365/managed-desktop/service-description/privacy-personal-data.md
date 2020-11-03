---
title: Privacy e dati personali
description: Informazioni dettagliate sui dati raccolti, archiviati e utilizzati dal servizio
keywords: GDPR, conservazione, eliminazione, archiviazione, conservazione, elaborazione, sicurezza, controllo
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: 294a3c6c54e28fa03ff6264898e7763325f78c3e
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847769"
---
# <a name="privacy-and-personal-data"></a>Privacy e dati personali

Gli utenti possono ricevere, trasmettere e archiviare i dati su dispositivi gestiti da Microsoft Managed Desktop. Si consideri attendibili che la privacy dei dati sia protetta e utilizzata solo in modo coerente con le loro aspettative. In questo articolo viene illustrato in che modo Microsoft Managed Desktop raccoglie, archivia, conserva, elabora, protegge, condivide, verifica ed Esporta i dati personali. Verrà inoltre illustrato in che modo un amministratore può visualizzare, correggere ed eliminare i dati personali.

Microsoft Managed Desktop non utilizza alcun dato personale raccolto come parte di fornire il servizio per la profilatura, la pubblicità o la commercializzazione.

## <a name="data-collection-of-microsoft-managed-desktop"></a>Raccolta di dati di Microsoft Managed Desktop

Quando gli utenti iscrivono i dispositivi aziendali in Microsoft Managed Desktop, la raccolta dei dati viene gestita – sul livello tecnico – tramite Windows e Microsoft Intune. Queste fonti raccolgono dati personali sui dispositivi degli utenti, ad esempio i nomi dei dispositivi per Microsoft Managed Desktop, per poter identificare il dispositivo da gestire e fornire le esperienze di Microsoft Managed Desktop.

Microsoft Managed Desktop non raccoglie i dati da solo per fornire il proprio servizio (ad eccezione delle [informazioni di contatto dell'amministratore it](#it-admin-contact-information). Invece, Microsoft Managed Desktop riutilizza i dati che sono già stati raccolti da altre origini, come Windows e Microsoft Intune. Microsoft Managed Desktop utilizza i dati che questi servizi raccolgono dai dispositivi registrati:

- I dati di diagnostica di Windows provenienti da dispositivi gestiti da Microsoft Managed Desktop vengono inviati agli archivi dati di diagnostica di Microsoft Windows.
- Microsoft Managed Desktop utilizza la [gestione moderna](https://docs.microsoft.com/learn/modules/introduction-to-modern-management-in-microsoft-365/) per la gestione dei dispositivi registrati. Come parte di questo, i dispositivi devono essere registrati nell'Azure Active Directory del tenant.
- Per la distribuzione di una configurazione altamente ottimizzata e sicura per i dispositivi registrati, Microsoft Managed Desktop utilizza Microsoft Intune.
- Microsoft Managed Desktop utilizza i dati di sicurezza di Microsoft Defender Advanced thread Protection per i clienti che utilizzano tale servizio.

## <a name="data-storage-and-sources-in-microsoft-managed-desktop"></a>Archiviazione dei dati e origini in Microsoft Managed Desktop

Dopo che Microsoft Managed Desktop ha ottenuto i dati, deve fornire il servizio, l'archiviazione e l'elaborazione di tali dati procedendo come segue:

### <a name="storing-data-storage-location-and-data-retention"></a>Archiviazione di dati, percorso di archiviazione e conservazione dei dati

Microsoft Managed Desktop archivia i dati in uno o più dei seguenti servizi di archiviazione Microsoft:

- SQL di Azure
- Spazio di archiviazione di Azure

Microsoft Managed Desktop archivia i propri dati negli Stati Uniti. I dati personali vengono conservati da Microsoft Managed Desktop per un massimo di 30 giorni.

## <a name="data-usage-of-microsoft-managed-desktop"></a>Utilizzo dei dati di Microsoft Managed Desktop

Microsoft Managed Desktop utilizza i dati seguenti:


| Origini dati |Utilizzo con Microsoft Managed Desktop  |
|---------|---------|
|Dati di Azure Active Directory     | Utilizzato nei report creati per gli amministratori tenant, che sono disponibili nel portale di amministrazione di Microsoft Managed Desktop.        |
|Dati di Intune     | Utilizzato nei report creati per gli amministratori tenant, che sono disponibili nel portale di amministrazione di Microsoft Managed Desktop.        |
|Microsoft Defender ATP     |  Utilizzato per l'indirizzamento di minacce alla sicurezza rilevate su dispositivi registrati da Microsoft Managed Desktop ' s Security Operations Center (SOC).  |
|Dati di diagnostica di Windows     |Utilizzato per determinare lo stato di aggiornamento dei dispositivi gestiti, nonché per fornire e migliorare l'offerta IT-as-a-Service (ITaaS) di Microsoft Managed Desktop.         |
|Dati dei contatti amministrativi     | Utilizzato da Microsoft Managed Desktop per comunicare con gli amministratori dei tenant.        |


### <a name="entities-processed-by-microsoft-managed-desktop"></a>Entità elaborate da Microsoft Managed Desktop

Microsoft Managed Desktop elabora queste entità per fornire il servizio:

- Dati del dispositivo
- Impostazioni di sicurezza del dispositivo
- Sistema operativo e hardware del dispositivo
- Informazioni aggregate sull'integrità dei dispositivi
- Informazioni di diagnostica del dispositivo
- Dati del tenant
- Risorse di Azure Active Directory
- Criteri e dati di configurazione
- Microsoft Defender per i metadati dell'endpoint
- Dati di diagnostica di Windows
- Dati sull'utilizzo di prodotti e servizi

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

I dati di identità utilizzati da Microsoft Managed Desktop sono archiviati da Azure Active Directory in una posizione geografica in base all'indirizzo fornito dall'organizzazione durante la sottoscrizione di un servizio Microsoft online, ad esempio Office 365 o Azure. Vedere [Microsoft Azure: dove sono i dati dei clienti?](http://azuredatacentermap.azurewebsites.net/) per una mappa che mostra i datacenter per Azure Active Directory.

Per ulteriori informazioni sulle aree utilizzate da Azure per l'archiviazione dei dati, vedere [Azure Active Directory – dove si trovano i dati](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9).

### <a name="microsoft-intune"></a>Microsoft Intune

I dati di Intune possono essere archiviati in alcune aree geografiche diverse, ad esempio Europa Nord (Irlanda) e Europe West (Paesi Bassi). L'amministratore IT crea un account tenant e sceglie il paese in cui verranno archiviati i dati quando si iscrivono inizialmente ai servizi di Intune. Per un elenco delle posizioni dei datacenter utilizzati da Intune, vedere [Microsoft Intune-dove sono i dati dei clienti?](http://intunedatacentermap.azurewebsites.net/). Per ulteriori informazioni sull'archiviazione dei dati e sull'utilizzo da parte di Intune, vedere [raccolta di dati in Intune](https://docs.microsoft.com/intune/privacy-data-collect).

### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender ATP

Microsoft Defender per i dati dell'endpoint può essere memorizzato in poche aree geografiche diverse. Per questo motivo, Defender for endpoint opera nei data center di Microsoft Azure nell'Unione europea, nel Regno Unito e negli Stati Uniti, come indicato in [Microsoft Defender for endpoint, ovvero nelle posizioni di archiviazione dei dati](http://intunedatacentermap.azurewebsites.net/). Per ulteriori informazioni sull'archiviazione dei dati e sull'utilizzo da parte di Defender per endpoint, vedere [quali dati contiene Microsoft Defender per endpoint Collect?](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy#what-data-does-microsoft-defender-atp-collect)

### <a name="windows-10"></a>Windows 10

Come indicato nell' [informativa sulla privacy di Microsoft](https://privacy.microsoft.com/privacystatement), "i dati personali raccolti da Microsoft possono essere archiviati ed elaborati nella propria area geografica, negli Stati Uniti e in qualsiasi altro paese in cui Microsoft o i suoi affiliati, consociati o provider di servizi gestiscono le strutture. [...] In genere, il percorso di archiviazione principale si trova nell'area del cliente o negli Stati Uniti, spesso con un backup in un centro dati in un'altra area. Le posizioni di archiviazione vengono scelte per operare in modo efficiente, per migliorare le prestazioni e per creare ridondanze al fine di proteggere i dati se si verifica un'interruzione o un altro problema. Si eseguono misure per garantire che i dati raccolti in questa informativa sulla privacy siano elaborati in base alle disposizioni di questa dichiarazione e ai requisiti della legge applicabile laddove si trovano i dati. "

Per ulteriori informazioni sulla raccolta di dati di diagnostica di Windows 10, vedere la sezione ["dove archiviare ed elaborare i dati personali"](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule) dell'informativa sulla privacy di Microsoft.

## <a name="data-access-protection"></a>Protezione dall'accesso ai dati

L'accesso diretto agli archivi dati interni di Microsoft Managed Desktop è limitato in diversi modi:

- Richiede l'approvazione del livello di piombo ingegneristico.
- Sono sia controllati che temporali.
- Richiede l'utilizzo di una workstation estremamente protetta e con restrizioni.
- Tutti i dati vengono crittografati durante l'archiviazione.
- Non esiste un accesso permanente.
- L'accesso al portale di gestione interno di Microsoft Managed Desktop richiede una workstation estremamente protetta e riservata.

## <a name="processing-personal-data-in-a-compliant-manner"></a>Elaborazione dei dati personali in modo conforme
Microsoft Managed Desktop elabora i dati personali con sistemi certificati ISO. Per ulteriori informazioni, vedere [Compliance](../intro/compliance.md).

## <a name="profiling-and-marketing"></a>Profiling e marketing

Microsoft Managed Desktop non utilizza alcun dato personale raccolto come parte di fornire il servizio per la profilatura, la pubblicità o la commercializzazione.

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>Richieste degli interessati nell'ambito del GDPR e del CCPA

Il [regolamento generale sulla protezione dei dati (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) dell'Unione europea fornisce diritti alle persone (note nel regolamento come soggetti dei dati) per gestire i dati personali raccolti da un datore di lavoro o da un altro tipo di agenzia o organizzazione (noto come titolare del trattamento dei dati o solo controller). Nell'ambito del regolamento GDPR i dati personali hanno una definizione molto ampia, ovvero sono tutti i dati riferiti a una persona fisica identificata o identificabile. In base al regolamento GDPR, ai soggetti dei dati vengono assegnati diritti specifici relativamente ai dati personali, tra i quali il diritto di ottenerne copie, richiedere correzioni, limitarne l'elaborazione, eliminarli o riceverli in formato elettronico in modo che possano essere trasferiti a un altro titolare. Una richiesta formale da un soggetto interessato a un titolare del trattamento di agire sui dati personali viene definita una Richiesta dell’interessato  o DSR.

Analogamente, il California Consumer Privacy Act (CCPA) fornisce i diritti e gli obblighi di privacy per i consumatori della California, compresi i diritti simili ai diritti del soggetto dei dati di GDPR, ad esempio il diritto di eliminare, accedere e ricevere (la portabilità) le loro informazioni personali. Il CCPA prevede anche alcune divulgazioni, protezioni contro la discriminazione quando si sceglie di esercitare i diritti e "opt-out/opt-in" requisiti per alcuni trasferimenti di dati classificati come "vendite". In generale, la definizione di vendite include la condivisione di dati a titolo oneroso. Per altre informazioni sul CCPA, vedere il [California Consumer Privacy Act](https://docs.microsoft.com/microsoft-365/compliance/offering-ccpa?view=o365-worldwide) e le [Domande frequenti sul California Consumer Privacy Act](https://docs.microsoft.com/microsoft-365/compliance/ccpa-faq?view=o365-worldwide).

Nella sezione seguente viene illustrato il modo in cui Microsoft Managed Desktop consente ai controller di individuare, accedere e agire sui dati personali o sulle informazioni personali utilizzate da Microsoft Managed Desktop.

> [!NOTE]
> Se si cercano informazioni generali su GDPR, vedere la [sezione GDPR](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted) del Service Trust Portal.

### <a name="it-admin-contact-information"></a>Informazioni di contatto dell'amministratore IT

Un amministratore tenant può visualizzare, correggere ed eliminare i propri dati personali (come le proprie informazioni di contatto) direttamente nella sezione contatti di amministrazione del portale Microsoft Managed Desktop.

### <a name="user-related-personal-data"></a>Dati personali relativi agli utenti

Oltre a ciò, Microsoft Managed Desktop non raccoglie i dati personali. Invece, si basa su e utilizza i dati personali raccolti da altri servizi Microsoft Enterprise online. Gli amministratori IT che desiderano rispondere alle richieste degli utenti per visualizzare, correggere ed eliminare i dati personali possono utilizzare le rispettive funzionalità dei servizi sottostanti su cui Microsoft Managed Desktop dipende. Se si è interessati alla visualizzazione o all'eliminazione dei dati personali utilizzati da questi servizi, vedere prima le richieste dell'interessato [per l'](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure) articolo di GDPR.

Inoltre, utilizzare le seguenti linee guida per esercitare richieste DSR per i servizi gestiti da Microsoft Managed Desktop dipende dalla raccolta dei dati personali:

- [Azure Active Directory](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure?view=o365-worldwide)
- [Microsoft Intune](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-intune?view=o365-worldwide)
- [Microsoft Defender per endpoint](https:/docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- [Windows 10](https://docs.microsoft.com/windows/privacy/windows-10-and-privacy-compliance)
