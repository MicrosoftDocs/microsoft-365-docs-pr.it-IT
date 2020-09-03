---
title: Controlli di accesso amministrativo in Microsoft 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
f1.keywords:
- NOCSH
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom: seo-marvel-apr2020
description: In questo articolo viene fornita una panoramica dei controlli di accesso amministrativo e della categorizzazione dei dati in Microsoft 365.
ms.openlocfilehash: 817a5907566435d021fe78d89b5c9476c04318d0
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332593"
---
# <a name="administrative-access-controls-in-microsoft-365"></a>Controlli di accesso amministrativo in Microsoft 365 

Microsoft ha investito fortemente nei sistemi e nei controlli che automatizzano la maggior parte delle operazioni di Microsoft 365, limitando intenzionalmente l'accesso ai contenuti dei clienti da Microsoft. Gli esseri umani regolano il servizio e il software gestisce il servizio. Ciò consente a Microsoft di gestire Microsoft 365 in scala e gestire i rischi di minacce interne ai contenuti dei clienti.

Per impostazione predefinita, i tecnici Microsoft dispongono di privilegi amministrativi pari a zero e di accesso a zero in piedi ai contenuti dei clienti in Microsoft 365. Un tecnico Microsoft può disporre di un accesso limitato, controllato e protetto al contenuto di un cliente per un periodo di tempo limitato. L'accesso è necessario solo per le operazioni di servizio e solo quando è approvato da un membro di Microsoft Senior Management. Per i clienti con licenza archivio protetto, il cliente fornisce l'approvazione di accesso ai propri contenuti ospitati in Microsoft 365.

Microsoft fornisce servizi online utilizzando più moduli di recapito cloud:

- **Cloud pubblici:** Include versioni multi-tenant di Microsoft 365, Azure e di altri servizi ospitati in Nord America, Sud America, Europa, Asia, Australia e così via.
- **Nubi nazionali:** Include tutte le nubi sovrane e di terze parti al di fuori degli Stati Uniti (eccetto quelle riportate in precedenza), ad esempio Microsoft 365 in Cina (gestite da 21Vianet) e Microsoft 365 in Germania (gestite da Microsoft, ma in un modello in cui un amministratore di dati tedesco, Deutsche Telekom, controlla e monitora l'accesso di Microsoft ai dati e ai sistemi dei clienti).
- **Cloud governativi:** Include i servizi Microsoft 365 e Azure che sono disponibili per i clienti del governo degli Stati Uniti.

Ai fini di questo articolo, Microsoft 365 Services include:

- [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online)
- [Exchange Online Protection](https://docs.microsoft.com/Office365/SecurityCompliance/eop/exchange-online-protection-overview)
- [SharePoint Online](https://docs.microsoft.com/sharepoint/sharepoint-online)
- [OneDrive for Business](https://docs.microsoft.com/OneDrive/onedrive)
- [Skype for Business](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online)
- [Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
- [Yammer](https://docs.microsoft.com/yammer/yammer-landing-page)

## <a name="microsoft-365-access-controls"></a>Controlli di accesso di Microsoft 365

Per gli scopi di controllo di accesso, Microsoft categorizza i dati di Microsoft 365 come dati dei clienti o altri tipi di dati.

### <a name="customer-data"></a>Dati cliente


I dati dei clienti sono tutti i dati forniti da o per conto di un cliente quando si utilizzano i servizi Microsoft 365. Si tratta di contenuti dei clienti creati o caricati direttamente dagli utenti di Microsoft 365, tra cui:

- Messaggi di posta elettronica
- Contenuto di SharePoint Online
- Messaggi istantanei
- Elementi del calendario
- Documenti
- Contacts
- Informazioni identificabili dall'utente finale (EUII) (dati univoci per un utente o che sono collegabili a un singolo utente, ma non include il contenuto del cliente)

### <a name="other-types-of-data"></a>Altri tipi di dati

Altri tipi di dati includono:

- **Dati account:** Include i dati amministrativi (informazioni fornite dagli amministratori quando eseguono la registrazione o l'acquisto di servizi) e i dati di pagamento (informazioni sugli strumenti di pagamento, ad esempio i dettagli delle carte di credito).
- **Informazioni identificabili dall'organizzazione:** Include i dati utilizzati per identificare un tenant, i dati di utilizzo e non collegabili a un singolo utente o inclusi nel contenuto del cliente.
- **Metadati di sistema:** Include i registri dei servizi che contengono le impostazioni di configurazione, lo stato del sistema, gli indirizzi IP di Microsoft e le informazioni tecniche sugli abbonamenti e sui tenant.

Microsoft ha stabilito meccanismi di controllo di accesso per garantire che nessuno abbia accesso non autorizzato ai dati dei clienti o ai dati di controllo di accesso. I dati di controllo di accesso gestiscono l'accesso ad altri tipi di dati o funzioni all'interno dell'ambiente, tra cui l'accesso al contenuto del cliente o EUII, le password Microsoft, i certificati di sicurezza e altri dati correlati all'autenticazione. I meccanismi di controllo di accesso proteggono anche dall'accesso fisico, logico o remoto non approvato all'ambiente di produzione Microsoft 365.

Sono disponibili tre categorie di controlli di accesso utilizzati da Microsoft per l'utilizzo di Microsoft 365:

- Controlli di isolamento
- Controlli del personale
- Controlli di tecnologia

Quando vengono combinati, questi controlli consentono di prevenire e rilevare azioni dannose in Microsoft 365. Oltre ai controlli di isolamento, del personale e della tecnologia utilizzati da Microsoft, esiste una quarta categoria di controlli: quelli implementati dai clienti.

Microsoft 365 consente di gestire i dati allo stesso modo in cui i dati vengono gestiti in ambienti locali. La persona che firma un'organizzazione per Microsoft 365 diventa automaticamente un amministratore globale. L'amministratore globale ha accesso a tutte le funzionalità nei portali di gestione e può:

- Creare o modificare gli utenti
- Assegnare ruoli di amministratore ad altri utenti
- Reimposta password utente
- Gestire le licenze utente
- Gestire domini
- Approvare le richieste dell'archivio clienti

È consigliabile che ogni organizzazione configuri almeno due account di amministratore. Per le organizzazioni aziendali di grandi dimensioni, è consigliabile disporre di account di amministrazione specializzati che svolgono funzioni diverse.

Per informazioni sull'assegnazione di ruoli e autorizzazioni di amministratore, vedere [assegnare ruoli di amministratore](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) e [informazioni sui ruoli di amministratore](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

## <a name="related-links"></a>Collegamenti correlati

- [Controlli di isolamento](microsoft-365-isolation-controls.md)
- [Controlli del personale](microsoft-365-personnel-controls.md)
- [Controlli di tecnologia](microsoft-365-technology-controls.md)
- [Monitoraggio e controllo dei controlli di accesso ](microsoft-365-monitoring-and-auditing-access-controls.md)
- [Controlli di accesso di Yammer Enterprise](microsoft-365-yammer-enterprise-access-controls.md)
