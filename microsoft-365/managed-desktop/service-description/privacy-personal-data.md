---
title: Privacy e dati personali
description: Dettagli sui dati raccolti, archiviati e usati dal servizio
keywords: GDPR, conservazione, eliminazione, archiviazione, conservazione, elaborazione, sicurezza, controllo
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: 7005e09d5a3df158569e132d2954f3b9a0ebf371
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840482"
---
# <a name="privacy-and-personal-data"></a>Privacy e dati personali

Gli utenti possono ricevere, trasmettere e archiviare dati nei dispositivi gestiti da Microsoft Managed Desktop. L'utente è certo che la privacy dei dati sia protetta e usata solo in modo coerente con le proprie aspettative. Questo articolo spiega come Microsoft Managed Desktop raccoglie, archivia, conserva, elabora, protegge, condivide, controlla ed esporta i dati personali. Scoprirai anche come un amministratore può visualizzare, correggere ed eliminare i dati personali.

Microsoft Managed Desktop non utilizza i dati personali raccolti nell'ambito della fornitura del servizio a fini di profilatura, pubblicità o marketing.

## <a name="data-collection-of-microsoft-managed-desktop"></a>Raccolta dati di Microsoft Managed Desktop

Quando gli utenti registrano i dispositivi aziendali in Microsoft Managed Desktop, la raccolta dei dati viene gestita, a livello tecnico, tramite Windows e Microsoft Intune. Queste origini raccolgono i dati personali sui dispositivi degli utenti, ad esempio i nomi dei dispositivi per Microsoft Managed Desktop per poter identificare il dispositivo da gestire e fornito con le esperienze di Microsoft Managed Desktop.

Microsoft Managed Desktop non raccoglie dati da solo per fornire il proprio servizio (ad eccezione delle informazioni di [contatto dell'amministratore IT.](#it-admin-contact-information) Al contrario, Microsoft Managed Desktop riutilizza i dati già raccolti da altre origini, ad esempio Windows e Microsoft Intune. Microsoft Managed Desktop usa i dati raccolti da questi servizi dai dispositivi registrati:

- I dati di diagnostica di Windows dai dispositivi gestiti da Microsoft Managed Desktop vengono inviati agli archivi dati di diagnostica di Windows di Microsoft.
- Microsoft Managed Desktop usa [la gestione moderna](https://docs.microsoft.com/learn/modules/introduction-to-modern-management-in-microsoft-365/) per la gestione dei dispositivi registrati. Come parte della "gestione moderna", i dispositivi devono essere registrati in Azure Active Directory del tenant.
- Per la distribuzione della configurazione altamente ottimizzata e sicura ai dispositivi registrati, Microsoft Managed Desktop usa Microsoft Intune.
- Microsoft Managed Desktop usa i dati di intelligence per la sicurezza di Microsoft Defender Advanced Thread Protection per i clienti che usano tale servizio.

## <a name="data-storage-and-sources-in-microsoft-managed-desktop"></a>Archiviazione dei dati e origini in Microsoft Managed Desktop

Dopo che Microsoft Managed Desktop ottiene i dati, deve fornire il servizio, l'archiviazione e l'elaborazione di questi dati nel modo seguente:

### <a name="storing-data-storage-location-and-data-retention"></a>Archiviazione di dati, posizione di archiviazione e conservazione dei dati

Microsoft Managed Desktop archivia i dati in uno o più dei seguenti servizi di archiviazione Microsoft:

- Azure SQL
- Archiviazione di Azure

Microsoft Managed Desktop archivia i dati negli Stati Uniti. I dati personali vengono conservati da Microsoft Managed Desktop per un massimo di 30 giorni.

### <a name="staff-location"></a>Sede del personale

I team MMD Operations e MMD Security Operations si trovano negli Stati Uniti e in India.

## <a name="data-usage-of-microsoft-managed-desktop"></a>Utilizzo dei dati di Microsoft Managed Desktop

Microsoft Managed Desktop usa questi dati:


| Origini dati |Da usare con Microsoft Managed Desktop  |
|---------|---------|
|Dati di Azure Active Directory     | Usato nei report creati per gli amministratori tenant, disponibili nel portale di amministrazione di Microsoft Managed Desktop.        |
|Dati di Intune     | Usato nei report creati per gli amministratori tenant, disponibili nel portale di amministrazione di Microsoft Managed Desktop.        |
|Microsoft Defender per endpoint     |  Usato per risolvere le minacce alla sicurezza rilevate nei dispositivi registrati dal Security Operations Center (SOC) di Microsoft Managed Desktop.  |
|Dati di diagnostica di Windows     |Usato per determinare lo stato di aggiornamento dei dispositivi gestiti e per fornire e migliorare l'offerta IT-as-a-Service (ITaaS) di Microsoft Managed Desktop.         |
|Dati di contatto dell'amministratore     | Usato da Microsoft Managed Desktop per comunicare con gli amministratori tenant.        |


### <a name="entities-processed-by-microsoft-managed-desktop"></a>Entità elaborate da Microsoft Managed Desktop

Microsoft Managed Desktop elabora queste entità per fornire il servizio:

- Dati del dispositivo
- Impostazioni di sicurezza del dispositivo
- Sistema operativo e hardware del dispositivo
- Informazioni aggregate sull'integrità del dispositivo
- Informazioni di diagnostica del dispositivo
- Dati tenant
- Risorse di Azure Active Directory
- Criteri e dati di configurazione
- Metadati di Microsoft Defender per endpoint
- Dati di diagnostica di Windows
- Dati sull'utilizzo di prodotti e servizi

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

I dati di identità usati da Microsoft Managed Desktop vengono archiviati da Azure Active Directory in una posizione geografica in base all'indirizzo fornito dall'organizzazione durante la sottoscrizione di un servizio online Microsoft, ad esempio Office 365 o Azure. Vedere [Microsoft Azure: dove sono i dati dei clienti?](http://azuredatacentermap.azurewebsites.net/) per una mappa che mostra i datacenter per Azure Active Directory.

Per altre informazioni sulle aree geografiche utilizzate da Azure per l'archiviazione dei dati, vedere [Azure Active Directory: dove si trovano i dati.](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9)

### <a name="microsoft-intune"></a>Microsoft Intune

I dati di Intune possono essere archiviati in alcune aree geografiche diverse, ad esempio Europa Nord (Irlanda) ed Europa occidentale (Paesi Bassi). L'amministratore IT crea un account tenant e sceglie il paese in cui verranno archiviati i dati quando si iscrive inizialmente ai servizi Intune. Per un elenco delle posizioni dei data center usate da Intune, vedere [Microsoft Intune: dove sono i dati dei clienti?](http://intunedatacentermap.azurewebsites.net/). Per altre informazioni sull'archiviazione e sull'uso dei dati da parte di Intune, vedi [Raccolta dati in Intune.](https://docs.microsoft.com/intune/privacy-data-collect)

### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender per endpoint

I dati di Microsoft Defender per endpoint possono essere archiviati in alcune aree geografiche diverse. Per questo motivo, Defender per Endpoint opera nei data center di Microsoft Azure nell'Unione Europea, nel Regno Unito e negli Stati Uniti, come indicato in [Microsoft Defender for Endpoint:](http://intunedatacentermap.azurewebsites.net/)posizioni di archiviazione dei dati. Per altre informazioni sull'archiviazione dei dati e sull'uso da parte di Defender per Endpoint, vedere Quali dati vengono raccolti [da Microsoft Defender per Endpoint?](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy#what-data-does-microsoft-defender-atp-collect)

### <a name="windows-10"></a>Windows 10

Come indicato nell'Informativa sulla privacy di [Microsoft,](https://privacy.microsoft.com/privacystatement)"i dati personali raccolti da Microsoft possono essere archiviati ed elaborati nella tua area geografica, negli Stati Uniti e in qualsiasi altro paese in cui Microsoft o le sue consociate, filiali o provider di servizi gestiscono strutture. [...] In genere, la posizione di archiviazione principale si trova nell'area geografica del cliente o negli Stati Uniti, spesso con un backup in un datacenter in un'altra area geografica. Le località di archiviazione vengono scelte per funzionare in modo efficiente, migliorare le prestazioni e creare licenzianze per proteggere i dati in caso di interruzione o di altro tipo. Microsoft prende le misure necessarie per garantire che i dati raccolti ai sensi della presente informativa sulla privacy vengano elaborati in base alle disposizioni della presente informativa e ai requisiti della legge applicabile, ovunque si trovino i dati".

Per altre informazioni sulla raccolta dei dati di diagnostica di Windows 10, vedi la sezione "Dove vengono archiviati ed evasi i dati [personali"](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule) dell'Informativa sulla privacy di Microsoft.

## <a name="data-access-protection"></a>Protezione dell'accesso ai dati

L'accesso diretto agli archivi dati interni di Microsoft Managed Desktop è limitato in diversi modi:

- Richiede l'approvazione del livello di lead di progettazione.
- Sia il controllo che il tempo sono limitati.
- Richiede l'utilizzo di una workstation con protezione elevata e con restrizioni.
- Tutti i dati vengono crittografati durante l'archiviazione.
- Non esiste alcun accesso permanente.
- L'accesso al portale di gestione interno di Microsoft Managed Desktop richiede una workstation altamente protetta e con restrizioni.

## <a name="processing-personal-data-in-a-compliant-manner"></a>Trattamento dei dati personali in modo conforme
Microsoft Managed Desktop elabora i dati personali con sistemi certificati ISO. Per ulteriori informazioni, vedere [Conformità.](../intro/compliance.md)

## <a name="profiling-and-marketing"></a>Profiling and marketing

Microsoft Managed Desktop non utilizza i dati personali raccolti nell'ambito della fornitura del servizio a fini di profilatura, pubblicità o marketing.

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>Richieste degli interessati nell'ambito del GDPR e del CCPA

Il Regolamento generale sulla protezione dei dati [(GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) dell'Unione Europea concede diritti alle persone (note nel regolamento come soggetti dei dati) per gestire i dati personali raccolti da un datore di lavoro o da un altro tipo di agenzia o organizzazione (noto come il controllore dei dati o solo il controllore). Nell'ambito del regolamento GDPR i dati personali hanno una definizione molto ampia, ovvero sono tutti i dati riferiti a una persona fisica identificata o identificabile. In base al regolamento GDPR, ai soggetti dei dati vengono assegnati diritti specifici relativamente ai dati personali, tra i quali il diritto di ottenerne copie, richiedere correzioni, limitarne l'elaborazione, eliminarli o riceverli in formato elettronico in modo che possano essere trasferiti a un altro titolare. Una richiesta formale da un soggetto interessato a un titolare del trattamento di agire sui dati personali viene definita una Richiesta dell’interessato  o DSR.

Analogamente, il California Consumer Privacy Act (CCPA) fornisce diritti e obblighi in materia di privacy ai consumatori della California, inclusi diritti simili ai diritti dell'soggetto dei dati del GDPR, ad esempio il diritto di eliminare, accedere e ricevere (portabilità) le proprie informazioni personali. Il CCPA fornisce anche alcune divulgazioni, protezioni contro la discriminazione quando si scelgono diritti di esercizio e requisiti di "rifiuto esplicito/consenso esplicito" per determinati trasferimenti di dati classificati come "vendite". In generale, la definizione di vendite include la condivisione di dati a titolo oneroso. Per altre informazioni sul CCPA, vedere il [California Consumer Privacy Act](https://docs.microsoft.com/microsoft-365/compliance/offering-ccpa?view=o365-worldwide) e le [Domande frequenti sul California Consumer Privacy Act](https://docs.microsoft.com/microsoft-365/compliance/ccpa-faq?view=o365-worldwide).

Nella sezione seguente viene illustrato in che modo Microsoft Managed Desktop consente ai controller di trovare, accedere e agire sui dati personali o sulle informazioni personali utilizzate da Microsoft Managed Desktop.

> [!NOTE]
> Per informazioni generali sul GDPR, vedere la sezione [GDPR](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted) del Service Trust Portal.

### <a name="it-admin-contact-information"></a>Informazioni di contatto dell'amministratore IT

Un amministratore tenant può visualizzare, correggere ed eliminare i propri dati personali (ad esempio le proprie informazioni di contatto) direttamente nella sezione Contatto amministratore del portale Microsoft Managed Desktop.

### <a name="user-related-personal-data"></a>Dati personali correlati all'utente

A parte questo, Microsoft Managed Desktop non raccoglie dati personali da solo. Al contrario, si basa sui dati personali raccolti da altri Microsoft Enterprise Online Services. Gli amministratori IT che desiderano rispondere alle richieste degli utenti di visualizzare, correggere ed eliminare i propri dati personali possono utilizzare le rispettive funzionalità dei servizi sottostanti da cui Dipende Microsoft Managed Desktop. Se si è interessati a visualizzare o eliminare i dati personali utilizzati da questi servizi, vedere prima l'articolo Richieste degli interessati per [Azure nell'articolo GDPR.](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure)

Inoltre, utilizzare le seguenti indicazioni per esercitare le DSR per i servizi da cui Microsoft Managed Desktop dipende per la raccolta dei dati personali:

- [Azure Active Directory](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure?view=o365-worldwide)
- [Microsoft Intune](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-intune?view=o365-worldwide)
- [Microsoft Defender per endpoint](https:/docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- [Windows 10](https://docs.microsoft.com/windows/privacy/windows-10-and-privacy-compliance)
