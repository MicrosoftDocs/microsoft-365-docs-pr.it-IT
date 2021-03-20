---
title: Privacy e dati personali
description: Dettagli sui dati raccolti, archiviati e utilizzati dal servizio
keywords: GDPR, conservazione, eliminazione, archiviazione, conservazione, elaborazione, sicurezza, controllo
ms.service: m365-md
ms.sitesec: library
author: jaimeo
manager: laurawi
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
audience: Admin, ITPro
ms.localizationpriority: normal
ms.openlocfilehash: 3f1a251d98be5b3a9fefa5c1f6d5d5562516d5d5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908175"
---
# <a name="privacy-and-personal-data"></a>Privacy e dati personali

Gli utenti possono ricevere, trasmettere e archiviare dati nei dispositivi gestiti da Microsoft Managed Desktop. Si fidano che la privacy dei dati sia protetta e usata solo in modo coerente con le loro aspettative. In questo articolo viene illustrato come Microsoft Managed Desktop raccoglie, archivia, conserva, elabora, protegge, condivide, controlla ed esporta i dati personali. Scoprirai anche come un amministratore può visualizzare, correggere ed eliminare i dati personali.

Microsoft Managed Desktop non utilizza i dati personali raccolti nell'ambito della fornitura del servizio per scopi di profilatura, pubblicità o marketing.

## <a name="data-collection-of-microsoft-managed-desktop"></a>Raccolta dati di Microsoft Managed Desktop

Quando gli utenti registrano i dispositivi aziendali in Microsoft Managed Desktop, la raccolta dei dati viene gestita a livello tecnico tramite Windows e Microsoft Intune. Queste origini raccolgono dati personali sui dispositivi degli utenti, ad esempio i nomi dei dispositivi per Microsoft Managed Desktop per poter identificare il dispositivo da gestire e fornito con le esperienze Microsoft Managed Desktop.

Microsoft Managed Desktop non raccoglie i dati da solo per fornire il proprio servizio (ad eccezione delle informazioni di contatto [dell'amministratore IT.](#it-admin-contact-information) Microsoft Managed Desktop riutilizza invece i dati già raccolti da altre origini, ad esempio Windows e Microsoft Intune. Microsoft Managed Desktop usa i dati raccolti da questi servizi dai dispositivi registrati:

- I dati di diagnostica di Windows dai dispositivi gestiti da Microsoft Managed Desktop vengono inviati agli archivi dati di diagnostica di Windows di Microsoft.
- Microsoft Managed Desktop usa [la gestione moderna](/learn/modules/introduction-to-modern-management-in-microsoft-365/) per la gestione dei dispositivi registrati. Come parte della "gestione moderna", i dispositivi devono essere registrati in Azure Active Directory del tenant.
- Per distribuire la configurazione altamente ottimizzata e sicura ai dispositivi registrati, Microsoft Managed Desktop usa Microsoft Intune.
- Microsoft Managed Desktop usa i dati di intelligence per la sicurezza di Microsoft Defender Advanced Thread Protection per i clienti che usano quel servizio.

## <a name="data-storage-and-sources-in-microsoft-managed-desktop"></a>Archiviazione e origini dati in Microsoft Managed Desktop

Dopo che Microsoft Managed Desktop ottiene i dati, deve fornire il servizio, l'archiviazione e l'elaborazione di questi dati nel modo seguente:

### <a name="storing-data-storage-location-and-data-retention"></a>Archiviazione di dati, posizione di archiviazione e conservazione dei dati

Microsoft Managed Desktop archivia i dati in uno o più dei seguenti servizi di archiviazione Microsoft:

- Azure SQL
- Archiviazione di Azure
- Dynamics 365

Microsoft Managed Desktop archivia i propri dati negli Stati Uniti. I dati personali vengono conservati da Microsoft Managed Desktop per un massimo di 30 giorni, ad eccezione dei dati di avviso per i dispositivi Microsoft Managed Desktop raccolti da Microsoft Defender for Endpoint. I dati effettivi dell'avviso (che potrebbero includere dati personali) vengono archiviati per 180 giorni. I dati degli avvisi con i dati personali rimossi vengono archiviati per un massimo di due anni. In conformità al Regolamento generale sulla protezione dei dati (GDPR) e al California Consumer Privacy Act (CCPA), Microsoft Managed Desktop rispetta i diritti dell'utente per tutti i dati personali archiviati nei dati di avviso.

### <a name="staff-location"></a>Posizione del personale

I team Microsoft Managed Desktop Operations e Security Operations si trovano negli Stati Uniti e in India.

## <a name="data-usage-of-microsoft-managed-desktop"></a>Utilizzo dei dati di Microsoft Managed Desktop

Microsoft Managed Desktop usa questi dati:


| Origini dati |Utilizzo con Microsoft Managed Desktop  |
|---------|---------|
|Dati di Azure Active Directory     | Usato nei report creati per gli amministratori tenant, disponibili nel portale di amministrazione di Microsoft Managed Desktop.        |
|Dati di Intune     | Usato nei report creati per gli amministratori tenant, disponibili nel portale di amministrazione di Microsoft Managed Desktop.        |
|Microsoft Defender per endpoint     |  Usato per affrontare le minacce alla sicurezza rilevate nei dispositivi registrati dal Security Operations Center (SOC) di Microsoft Managed Desktop.  |
|Dati di diagnostica di Windows     |Usato per determinare lo stato di aggiornamento dei dispositivi gestiti e per fornire e migliorare l'offerta IT-as-a-Service (ITaaS) di Microsoft Managed Desktop.         |
|Dati di contatto dell'amministratore     | Utilizzato da Microsoft Managed Desktop per comunicare con gli amministratori tenant.        |


### <a name="entities-processed-by-microsoft-managed-desktop"></a>Entità elaborate da Microsoft Managed Desktop

Microsoft Managed Desktop elabora queste entità per fornire il servizio:

- Dati del dispositivo
- Impostazioni di sicurezza del dispositivo
- Hardware e sistema operativo del dispositivo
- Informazioni aggregate sull'integrità dei dispositivi
- Informazioni di diagnostica del dispositivo
- Dati tenant
- Risorse di Azure Active Directory
- Criteri e dati di configurazione
- Metadati e dati di avviso di Microsoft Defender for Endpoint
- Dati di diagnostica di Windows
- Dati sull'utilizzo di prodotti e servizi

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

I dati di identità utilizzati da Microsoft Managed Desktop vengono archiviati da Azure Active Directory in una posizione geografica in base all'indirizzo fornito dall'organizzazione durante la sottoscrizione di un servizio online Microsoft, ad esempio Office 365 o Azure. Vedere [Microsoft Azure: dove sono i dati dei clienti?](http://azuredatacentermap.azurewebsites.net/) per una mappa che mostra i data center per Azure Active Directory.

Per ulteriori informazioni sulle aree geografiche utilizzate da Azure per l'archiviazione dei dati, vedere [Azure Active Directory- Dove si trovano i dati.](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9)

### <a name="microsoft-intune"></a>Microsoft Intune

I dati di Intune possono essere archiviati in alcune aree geografiche diverse, ad esempio Europa Nord (Irlanda) e Europa Occidentale (Paesi Bassi). L'amministratore IT crea un account tenant e sceglie il paese in cui verranno archiviati i dati quando inizialmente si registrano nei servizi intune. Per un elenco delle posizioni dei data center usate da Intune, vedere [Microsoft Intune: Dove sono i dati dei clienti?](http://intunedatacentermap.azurewebsites.net/). Per altre informazioni sull'archiviazione dei dati e sull'uso da parte di Intune, vedi [Raccolta dati in Intune.](/intune/privacy-data-collect)

### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender per endpoint

I dati di Microsoft Defender for Endpoint possono essere archiviati in alcune aree geografiche diverse. Per questo motivo, Defender for Endpoint opera nei data center di Microsoft Azure nell'Unione Europea, nel Regno Unito e negli Stati Uniti, come indicato in [Microsoft Defender for Endpoint— Data storage locations](http://intunedatacentermap.azurewebsites.net/). Per altre informazioni sull'archiviazione dei dati e sull'uso da parte di Defender per Endpoint, vedi Quali dati vengono raccolti [da Microsoft Defender per Endpoint?](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy#what-data-does-microsoft-defender-atp-collect)

### <a name="windows-10"></a>Windows 10

Come indicato nell'Informativa sulla [privacy di Microsoft,](https://privacy.microsoft.com/privacystatement)"i dati personali raccolti da Microsoft possono essere archiviati ed elaborati nella tua area geografica, negli Stati Uniti e in qualsiasi altro paese in cui Microsoft o le sue consociate, filiali o provider di servizi gestiscono strutture. [...] In genere, la posizione di archiviazione principale si trova nell'area geografica del cliente o negli Stati Uniti, spesso con un backup in un datacenter in un'altra area geografica. Le località di archiviazione vengono scelte per funzionare in modo efficiente, migliorare le prestazioni e creare licenzianze per proteggere i dati in caso di interruzione o altro problema. Microsoft prende misure per garantire che i dati raccolti ai sensi della presente informativa sulla privacy vengano elaborati in base alle disposizioni della presente informativa e ai requisiti della legge applicabile ovunque si trovino i dati."

Per altre informazioni sulla raccolta dei dati di diagnostica di Windows 10, vedi la sezione "Dove archiviamo ed eseiamo i dati [personali"](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule) dell'Informativa sulla privacy Microsoft.

## <a name="data-access-protection"></a>Protezione dell'accesso ai dati

L'accesso diretto agli archivi dati interni di Microsoft Managed Desktop è limitato in diversi modi:

- Richiede l'approvazione del livello di lead di progettazione.
- Il controllo e il tempo sono limitati.
- Richiede l'utilizzo di una workstation altamente protetta e con restrizioni.
- Tutti i dati vengono crittografati durante l'archiviazione.
- Non esiste alcun accesso permanente.
- L'accesso al portale di gestione interno di Microsoft Managed Desktop richiede una workstation altamente protetta e con restrizioni.

## <a name="processing-personal-data-in-a-compliant-manner"></a>Trattamento dei dati personali in modo conforme
Microsoft Managed Desktop elabora i dati personali con sistemi certificati ISO. Per ulteriori informazioni, vedere [Compliance.](../intro/compliance.md)

## <a name="profiling-and-marketing"></a>Profilatura e marketing

Microsoft Managed Desktop non utilizza i dati personali raccolti nell'ambito della fornitura del servizio per scopi di profilatura, pubblicità o marketing.

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>Richieste degli interessati nell'ambito del GDPR e del CCPA

Il Regolamento generale sulla protezione dei dati [(GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) dell'Unione Europea concede ai soggetti (noti come soggetti del regolamento) il diritto di gestire i dati personali raccolti da un datore di lavoro o da un altro tipo di agenzia o organizzazione (noto come controllore dei dati o semplicemente controller). Nell'ambito del regolamento GDPR i dati personali hanno una definizione molto ampia, ovvero sono tutti i dati riferiti a una persona fisica identificata o identificabile. In base al regolamento GDPR, ai soggetti dei dati vengono assegnati diritti specifici relativamente ai dati personali, tra i quali il diritto di ottenerne copie, richiedere correzioni, limitarne l'elaborazione, eliminarli o riceverli in formato elettronico in modo che possano essere trasferiti a un altro titolare. Una richiesta formale da un soggetto interessato a un titolare del trattamento di agire sui dati personali viene definita una Richiesta dell’interessato  o DSR.

Analogamente, il CCPA fornisce diritti e obblighi di privacy ai consumatori della California, inclusi diritti simili ai diritti soggetti ai dati del GDPR, ad esempio il diritto di eliminare, accedere e ricevere (portabilità) le proprie informazioni personali. Il CCPA prevede anche alcune divulgazioni, protezioni contro la discriminazioni quando si eleminano diritti di esercizio e requisiti di "rifiuto esplicito/consenso esplicito" per determinati trasferimenti di dati classificati come "vendite". In generale, la definizione di vendite include la condivisione di dati a titolo oneroso. Per altre informazioni sul CCPA, vedere il [California Consumer Privacy Act](/compliance/regulatory/offering-ccpa?view=o365-worldwide) e le [Domande frequenti sul California Consumer Privacy Act](/compliance/regulatory/ccpa-faq?view=o365-worldwide).

Nella sezione seguente viene illustrato in che modo Microsoft Managed Desktop consente ai controller di trovare, accedere e agire sui dati personali o sulle informazioni personali utilizzate da Microsoft Managed Desktop.

> [!NOTE]
> Per informazioni generali sul GDPR, vedere la sezione [GDPR](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted) del Service Trust Portal.

### <a name="it-admin-contact-information"></a>Informazioni di contatto dell'amministratore IT

Un amministratore tenant può visualizzare, correggere ed eliminare i propri dati personali (ad esempio le proprie informazioni di contatto) direttamente nella sezione Contatto amministratore di Microsoft Managed Desktop Portal.

## <a name="microsoft-defender-for-endpoint-alert-data"></a>Dati di avviso di Microsoft Defender per endpoint

Gli amministratori della sicurezza possono richiedere l'estrazione o l'eliminazione dei dati personali relativi agli avvisi di Microsoft Defender for Endpoint in un dispositivo gestito da Microsoft Managed Desktop nel proprio ambiente. L'amministratore della sicurezza deve accedere al portale di amministrazione di Microsoft Managed Desktop [e](https://aka.ms/memadmin) inviare una richiesta di supporto. Seleziona **Tipo di** richiesta  di supporto di Richiesta di **modifica,** Categoria di sicurezza e **Sottocategoria** di Altro **e** quindi specifica i nomi dei dispositivi pertinenti nella descrizione insieme alla richiesta di estrazione o eliminazione dei dati.

### <a name="user-related-personal-data"></a>Dati personali correlati all'utente

A parte questo, Microsoft Managed Desktop non raccoglie i dati personali da solo. Si basa invece sui dati personali raccolti e utilizzati da altri Microsoft Enterprise Online Services. Gli amministratori IT che desiderano rispondere alle richieste degli utenti per visualizzare, correggere ed eliminare i propri dati personali possono utilizzare le rispettive funzionalità dei servizi sottostanti da cui Dipende Microsoft Managed Desktop. Se si è interessati a visualizzare o eliminare i dati personali utilizzati da questi servizi, vedere prima l'articolo Richieste degli interessati di Azure per il [GDPR.](/compliance/regulatory/gdpr-dsr-Azure)

Inoltre, utilizzare le indicazioni seguenti per esercitare DSR per i servizi da cui Microsoft Managed Desktop dipende per la raccolta dei dati personali:

- [Azure Active Directory](/compliance/regulatory/gdpr-dsr-Azure?view=o365-worldwide)
- [Microsoft Intune](/compliance/regulatory/gdpr-dsr-Intune?view=o365-worldwide)
- [Microsoft Defender per Endpoint](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- [Windows 10](/windows/privacy/windows-10-and-privacy-compliance)