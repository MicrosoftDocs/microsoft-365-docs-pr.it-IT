---
title: Sito di SharePoint per le risorse digitali estremamente riservate di Contoso Corporation
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/18/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: 'Riepilogo: informazioni sul modo in cui Contoso ha implementato un sito di SharePoint per dati altamente regolamentati per semplificare la collaborazione tra i team di ricerca.'
ms.openlocfilehash: caad341c6a44b3270f2bdecd4ab4d8378c11db2c
ms.sourcegitcommit: 237589a0c8a24510e5c8f3b8b4747d944ad0afbf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "38699716"
---
# <a name="sharepoint-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a>Sito di SharePoint per le risorse digitali estremamente riservate di Contoso Corporation

Le risorse più importanti di Contoso sono la proprietà intellettuale in forma di segreti commerciali, come le tecniche di produzione proprietarie e le specifiche di progettazione per i prodotti in sviluppo. Tali risorse erano in formato digitale, originariamente memorizzate come file in un sito di SharePoint Server 2016. Quando Contoso ha distribuito Microsoft 365 Enterprise, volevano passare al cloud le risorse digitali locali per semplificare l'accesso e una collaborazione più aperta tra i team di ricerca di Parigi, Mosca, New York, Pechino e Bangalore. 
  
Tuttavia, a causa della loro natura sensibile, l'accesso a questi file deve essere:

- Limitato all'insieme di utenti autorizzati ad accedervi. 
- Protetto con un criterio di prevenzione della perdita di dati (DLP) per impedire agli utenti di distribuirli all'esterno del sito.
- Crittografati e protetti con autorizzazioni per impedire agli utenti non autorizzati di accedere ai propri contenuti, anche se sono distribuiti all'esterno del sito.

Gli amministratori di sicurezza e di SharePoint nel reparto IT di Contoso hanno deciso di utilizzare un [sito di SharePoint per dati altamente regolamentati](teams-sharepoint-online-sites-highly-regulated-data.md).
  
Contoso ha utilizzato questi passaggi per creare e proteggere i siti del team di SharePoint per i propri team di ricerca.

## <a name="step-1-created-a-private-sharepoint-team-site"></a>Passaggio 1: creazione di un sito del team di SharePoint privato

Per proteggere l'accesso al sito di SharePoint, Contoso ha configurato i [criteri di accesso di SharePoint consigliati](sharepoint-file-access-policies.md).

Successivamente, contoso IT Admins ha compilato un elenco degli account utente per i ricercatori negli uffici Parigi, Mosca, New York, Pechino e Bangalore. 

Successivamente, un amministratore IT di Contoso ha creato un nuovo sito del team privato denominato **Research** e ha aggiunto tutti gli account utente per i suoi ricercatori.

Successivamente, sono state configurate le impostazioni di autorizzazione aggiuntive per il sito per impedire ai ricercatori di condividere l'accesso al sito e impedire ai non ricercatori di richiedere l'accesso al sito.

## <a name="step-2-configured-the-site-for-a-restrictive-dlp-policy"></a>Passaggio 2: configurazione del sito per un criterio DLP restrittivo

Per prima cosa, gli amministratori di Contoso hanno applicato l'etichetta di conservazione di Office 365 **altamente riservata** esistente alla cartella documenti del sito di **ricerca** .

Successivamente, è stato creato un nuovo criterio DLP di Office 365 denominato **Research** :

- Utilizza l'etichetta di conservazione di Office 365 **estremamente riservata** . 
- Blocca gli utenti quando tentano di condividere un asset digitale nel sito di **ricerca** esterno a contoso.

Per informazioni dettagliate sulla configurazione, vedere [proteggere i file di SharePoint con etichette di conservazione e DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).

## <a name="step-3-created-an-office-365-sensitivity-sublabel-for-the-site"></a>Passaggio 3: creazione di una sottoetichetta di riservatezza di Office 365 per il sito

Gli amministratori di Contoso hanno creato una nuova sottoetichetta di sensitivity di Office 365 denominata **Research Teams** dell'etichetta **altamente riservata** che:

- Richiede la crittografia.
- Consente le autorizzazioni di creazione condivisa per il gruppo **Research** Office 365
- Si applica al gruppo **Research** Office 365

Ecco la configurazione risultante del sito del team di **ricerca** per le risorse estremamente riservate.

![La configurazione risultante del sito del team di ricerca per le risorse estremamente riservate](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

I file nelle cartelle del sito di **ricerca** sono protetti da:

- Le autorizzazioni per il sito, che consentono l'accesso solo ai membri del gruppo **Research** Office 365.
- Il criterio DLP di **ricerca** , che utilizza l'etichetta di conservazione e le impostazioni **estremamente riservate** che impediscono la condivisione dei file con gli utenti esterni.
- La sottoetichetta di sensitivity dei **team di ricerca** , con la crittografia e le autorizzazioni che viaggiano con il file se sono state spostate o copiate dal sito di **ricerca** .

Di seguito è riportato un esempio di un file archiviato nel sito di **ricerca** con la sottoetichetta di riservatezza dei **team di ricerca** assegnati.

![La configurazione risultante del sito del team di ricerca per le risorse estremamente riservate](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config-example-file.png)


## <a name="step-4-migrated-the-on-premises-sharepoint-research-data"></a>Passaggio 4: migrazione dei dati di ricerca di SharePoint locali

Gli amministratori di Contoso hanno spostato tutti i file di ricerca locali nel sito di SharePoint Server 2016 locale in cartelle nel nuovo sito di SharePoint per la **ricerca** .

## <a name="step-5-trained-their-researchers"></a>Passaggio 5: formazione dei ricercatori

Il personale di sicurezza di Contoso ha formato i membri del gruppo **Research** Office 365 in un corso obbligatorio che ha eseguito i seguenti controlli:

- Informazioni su come accedere al nuovo sito di **ricerca** e ai file esistenti.
- Come creare nuovi file sul sito e caricare nuovi file memorizzati localmente.
- Dimostrazione del modo in cui il criterio DLP della **ricerca** blocca i file dalla condivisione esterna.
- Come assegnare etichette ai file con la sottoetichetta di sensitivity dei **team di ricerca** .
- Dimostrazione del modo in cui l'etichetta secondaria dei **team di ricerca** protegge un file anche quando viene perso dal sito.

Il risultato finale è un ambiente sicuro in cui i ricercatori possono collaborare tra Contoso in un ambiente sicuro su file contenenti informazioni sulla ricerca. 

Se un documento di ricerca con la sottoetichetta del **team di ricerca** lascia il sito di **ricerca** , è crittografato e accessibile solo ai membri del gruppo **Research** Office 365 con credenziali dell'account utente valide.

## <a name="next-step"></a>Passaggio successivo

[Distribuzione](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise nell'organizzazione.

## <a name="see-also"></a>Vedere anche

[Raccolta di produttività di Microsoft 365](https://aka.ms/productivitylibrary)https://aka.ms/productivitylibrary)
