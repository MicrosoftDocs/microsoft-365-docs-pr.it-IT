---
title: Sito di SharePoint Online per le risorse digitali estremamente riservate di Contoso Corporation
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/15/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: 'Riepilogo: informazioni su come Contoso ha implementato un sito di SharePoint Online per dati altamente regolamentati per semplificare la collaborazione tra i team di ricerca.'
ms.openlocfilehash: 6c61d02c802a77afeb93a58b59114741c6630f9e
ms.sourcegitcommit: c6eab4a9f1b70e7ff0db6b2a1128a4db2591cbaf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2019
ms.locfileid: "37369527"
---
# <a name="sharepoint-online-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a>Sito di SharePoint Online per le risorse digitali estremamente riservate di Contoso Corporation

 **Riepilogo:** Come Contoso ha implementato un sito di SharePoint Online per dati altamente regolamentati per semplificare la collaborazione tra i propri team di ricerca.
  
Le risorse più importanti di Contoso sono la proprietà intellettuale in forma di segreti commerciali, come le tecniche di produzione proprietarie e le specifiche di progettazione per i prodotti in sviluppo. Tali risorse sono in formato digitale, archiviate originariamente come file in un sito di SharePoint Server 2016. Quando Contoso ha distribuito Microsoft 365 Enterprise, volevano passare al cloud le risorse digitali locali per semplificare l'accesso e una collaborazione più aperta tra i team di ricerca di Parigi, Mosca, New York, Pechino e Bangalore. 
  
Tuttavia, a causa della loro natura sensibile, l'accesso a questi file deve essere:

- Limitato all'insieme di utenti autorizzati a visualizzarli o modificarli, con autorizzazioni in uscita per il sito amministrate solo da amministratori di SharePoint. 
- Protetto con la prevenzione della perdita di dati (DLP) per impedire agli utenti di distribuirli all'esterno del sito.
- Crittografati e protetti con gli elenchi di controllo di accesso per impedire agli utenti non autorizzati di accedere ai propri contenuti, anche se sono distribuiti all'esterno del sito.

Gli amministratori di sicurezza e di SharePoint nel reparto IT di Contoso hanno deciso di utilizzare un [sito di SharePoint Online per dati altamente regolamentati](teams-sharepoint-online-sites-highly-regulated-data.md).
  
Contoso ha utilizzato questi passaggi per creare e proteggere i siti del team di SharePoint Online per i propri team di ricerca.

## <a name="step-1-reviewed-and-verified-the-members-of-research-team-groups"></a>Passaggio 1: Revisione e verifica dei membri dei gruppi del team di ricerca

Contoso IT Admins ha eseguito una revisione del set di gruppi di sicurezza per i propri team di ricerca. Sono stati rimossi tutti coloro che non erano un ricercatore o che non avevano bisogno di accedere alle risorse di ricerca. 

Sono stati creati anche questi nuovi gruppi di sicurezza:

- **Ricerca-amministratori**  Set di amministratori di SharePoint che dispongono del controllo completo sul sito, inclusa la possibilità di modificare le autorizzazioni.
- **Membri della ricerca**  Set di gruppi di sicurezza per i team di ricerca di tutto il mondo.
- **Ricerca-visualizzatori**  Il set di utenti di gestione, ad esempio i dirigenti dell'organizzazione di ricerca, che può solo visualizzare le risorse nel sito.

## <a name="step-2-created-an-isolated-sharepoint-online-team-site"></a>Passaggio 2: creazione di un sito del team di SharePoint Online isolato 

Contoso SharePoint Admins ha creato per la prima volta un nuovo sito del team denominato **Research**. Sono quindi configurati:

- Il livello di autorizzazione controllo completo per l'utilizzo del gruppo di SharePoint proprietari di ricerca, che dispone del gruppo di sicurezza **Research-Admins** come membro
- Il livello di autorizzazione modifica per l'utilizzo del gruppo di SharePoint membri della ricerca, che ha come membro il gruppo di sicurezza **membri della ricerca** .
- Il livello di autorizzazione di lettura per l'utilizzo del gruppo di SharePoint visitors Research, che dispone del gruppo di sicurezza dei **visualizzatori di ricerca** come membro

Di seguito sono riportati i livelli di autorizzazione di SharePoint, i gruppi di SharePoint e i relativi membri.

![Livelli di autorizzazione di SharePoint, gruppi di SharePoint e relativi membri](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/spo-permissions.png)

Successivamente, sono state configurate restrizioni aggiuntive per il sito.

Per informazioni dettagliate sulla configurazione, vedere [deploy an isolated SharePoint Online Team Site](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site).

## <a name="step-3-configured-the-site-for-a-restrictive-dlp-policy"></a>Passaggio 3: configurazione del sito per un criterio DLP restrittivo

Per prima cosa, gli amministratori di Contoso hanno applicato l'etichetta di conservazione di Office 365 **estremamente riservata** al sito di **ricerca** .

Successivamente, è stato creato un nuovo criterio DLP di Office 365 denominato **Research** :

- Utilizza l'etichetta di conservazione di Office 365 **estremamente riservata** . 
- Viene applicato al sito di **ricerca** .
- Blocca gli utenti quando tentano di condividere un asset digitale nel sito di **ricerca** esterno a contoso.

Per informazioni dettagliate sulla configurazione, vedere [proteggere i file di SharePoint Online con etichette di conservazione e DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).

## <a name="step-4-created-an-azure-information-protection-sub-label-for-the-site"></a>Passaggio 4: creazione di un'etichetta secondaria di Azure Information Protection per il sito

Gli amministratori di Contoso hanno creato una nuova etichetta secondaria di Azure Information Protection denominata **Research** dell'etichetta **altamente riservata** predefinita in un criterio con ambito che:

- Richiede la crittografia.
- Consente l'accesso completo da parte dei membri del gruppo di sicurezza **membri della ricerca** .
- Consente l'accesso in lettura ai membri del gruppo di sicurezza **ricerca-visualizzatori** .

Successivamente, hanno distribuito il client Azure Information Protection ai dispositivi dei membri del team di ricerca.

Per informazioni dettagliate sulla configurazione, vedere [proteggere i file di SharePoint Online con Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection). 

Ecco la configurazione risultante del sito di **ricerca** per le risorse estremamente riservate.

![La configurazione risultante del sito * * Research * * per le risorse estremamente riservate](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

I file nelle cartelle del sito di **ricerca** sono protetti da:

- La sottoetichetta **Research** Azure Information Protection, che applica la crittografia e permssions a ogni file che viaggia con il file quando viene spostato o copiato dal sito di **ricerca** .
- Il criterio DLP di **ricerca** , che utilizza l'etichetta di conservazione **estremamente riservata** e le impostazioni che impediscono la condivisione dei file con gli utenti esterni.
- Il set di autorizzazioni per i siti, che consentono l'accesso solo ai membri dei gruppi di sicurezza e dell'amministrazione di ricerca-spettatori **e dei** **visualizzatori** dai membri del gruppo di sicurezza **Research-Admins** .

## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a>Passaggio 5: migrazione dei dati di ricerca di SharePoint locali

Gli amministratori di Contoso hanno spostato tutti i file di ricerca locali nel sito di SharePoint Server 2016 locale in cartelle nel nuovo sito di **ricerca** di SharePoint Online.

## <a name="step-6-trained-their-users"></a>Passaggio 6: formazione dei propri utenti 

Il personale di sicurezza di Contoso ha formato i team di ricerca in un corso obbligatorio che ha superato:

- Informazioni su come accedere al nuovo sito di **ricerca** di SharePoint Online e ai file esistenti.
- Come creare nuovi file sul sito e caricare nuovi file memorizzati localmente.
- Dimostrazione del modo in cui il criterio DLP blocca la condivisione esterna dei file.
- Informazioni su come utilizzare il client Azure Information Protection per etichettare i file di ricerca con l'etichetta secondaria **Research** .
- Dimostrazione del modo in cui l'etichetta secondaria di **ricerca** protegge un file anche quando viene perso dal sito.

Il risultato finale è un ambiente sicuro in cui i ricercatori possono collaborare all'interno dell'organizzazione in un ambiente sicuro. 

Se un documento di ricerca con l' **etichetta secondaria di ricerca è** fuoriuscito dal sito di **ricerca** , è crittografato e accessibile solo ai membri dei gruppi di sicurezza **membri** della ricerca e ai **visualizzatori** di ricerca con credenziali valide.

## <a name="next-step"></a>Passaggio successivo

[Distribuzione](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise nell'organizzazione.

