---
title: Sito di SharePoint Online per le risorse digitali altamente riservate di Contoso Corporation
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/01/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom: Ent_Architecture
description: 'Riepilogo: Come Contoso ha implementato un sito di SharePoint Online per altamente regolamentati dati per una collaborazione più semplice tra le ricerche dei team.'
ms.openlocfilehash: 697ddb27b56fd529e9c73b89d9f07b8731ad76c3
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868870"
---
# <a name="sharepoint-online-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a>Sito di SharePoint Online per le risorse digitali altamente riservate di Contoso Corporation

 **Riepilogo:** Modalità di implementazione di un sito di SharePoint Online per i dati per una collaborazione più semplice tra il team di ricerca altamente regolamentati Contoso.
  
Risorse più importante di Contoso relativa proprietà intellettuale sotto forma di segreti commerciali, ad esempio le tecniche di produzione proprietari e progettare le specifiche per i prodotti di sviluppo. Queste attività sono nel formato digitale originariamente memorizzato come file in un sito di SharePoint Server 2016. Quando Contoso distribuito Microsoft 365 Enterprise, si desidera le risorse digitali in locale nel cloud per semplificare l'accesso e la collaborazione più vulnerabili la transizione tra i team di ricerca Parigi, Mosca, New York, Pechino e Bangalore. 
  
Tuttavia, a causa di informazioni sensibili, accedere a tali file deve essere:

- Con limitazioni all'insieme di utenti autorizzati a visualizzare o modificare le loro, con le autorizzazioni in corso per il sito amministrati solo dagli amministratori di SharePoint. 
- Protetto con dati prevenzione della perdita (DLP) per impedire agli utenti di distribuirli all'esterno del sito.
- Accesso crittografato e protetto con controllo elenchi per impedire agli utenti non autorizzati di accedere al relativo contenuto, anche se sono distribuiti all'esterno del sito.

Gli amministratori di SharePoint e sicurezza in Contoso del reparto IT ha deciso di utilizzare un [sito di SharePoint Online per regolamentato altamente dati](teams-sharepoint-online-sites-highly-regulated-data.md).
  
Contoso utilizzata la procedura seguente per creare e proteggere un siti del team di SharePoint Online per i team di ricerca.

## <a name="step-1-reviewed-and-verified-the-members-of-research-team-groups"></a>Passaggio 1: Leggere e verificato i membri dei gruppi di team di ricerca

Gli amministratori IT di Contoso eseguita una verifica dell'insieme di gruppi di sicurezza per i team di ricerca. Vengono rimossi tutti gli utenti che non è stato ricercatori o non sono necessarie di accedere alle risorse di ricerca. 

Vengono inoltre e creati i nuovi gruppi di sicurezza:

- **Amministratori della ricerca**  Gruppo di amministratori di SharePoint con il controllo completo del sito, inclusa la possibilità di modificare le autorizzazioni.
- **Membri di ricerca**  Insieme di gruppi di sicurezza per i team di ricerca in tutto il mondo.
- **Visualizzatori di ricerca**  L'insieme di utenti di gestione, ad esempio dirigenti nell'organizzazione di ricerca, che possono visualizzare le risorse del sito.

## <a name="step-2-created-an-isolated-sharepoint-online-team-site"></a>Passaggio 2: Creazione di un sito del team di SharePoint Online isolato 

Gli amministratori di Contoso SharePoint innanzitutto creati un nuovo sito del team denominata **ricerca**. Quindi configurate:

- Il livello di autorizzazione controllo completo per l'utilizzo del gruppo dei proprietari di ricerca di SharePoint, che presenta il gruppo di sicurezza **Admins Research** come membro
- Il livello di autorizzazione Modifica per l'utilizzo del gruppo di SharePoint membri Research, che presenta il gruppo di sicurezza **Membri Research** come membro
- Il livello di autorizzazione di lettura per l'utilizzo del gruppo di SharePoint visitatori Research, che presenta il gruppo di sicurezza **Visualizzatori Research** come membro

Ecco i livelli di autorizzazione di SharePoint risultanti, i gruppi di SharePoint e i relativi membri.

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/spo-permissions.png)

Successivamente, vengono configurate restrizioni aggiuntive per il sito.

Per informazioni dettagliate sulla configurazione, vedere [distribuzione di un sito del team di SharePoint Online isolato](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site).

## <a name="step-3-configured-the-site-for-a-restrictive-office-365-label-dlp-policy"></a>Passaggio 3: Configurare il sito per un'etichetta di Office 365 restrittivo criterio DLP

Per prima cosa, gli amministratori di Contoso applicato l'etichetta di Office 365 **Altamente riservati** al sito di **ricerca** .

Successivamente, vengono creati un nuovo criterio DLP di Office 365 denominata **ricerca** :

- Utilizza l'etichetta di Office 365 **Altamente riservati** . 
- Viene applicato al sito di **ricerca** .
- Impedisce agli utenti di condivisione di documenti.

Per informazioni dettagliate sulla configurazione, vedere [file proteggere SharePoint Online con etichette di Office 365 e DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).

## <a name="step-4-created-an-azure-information-protection-sub-label-for-the-site"></a>Passaggio 4: Creazione di un'etichetta secondaria Azure Information Protection per il sito

Gli amministratori di Contoso creati una nuova etichetta secondaria Azure Information Protection denominato **Research** dell'etichetta **Altamente riservati** predefinito in un criterio con ambito che:

- Richiede la crittografia.
- Consente l'accesso completo dai membri del gruppo di sicurezza **Membri Research** .
- Consente l'accesso in lettura dai membri del gruppo di protezione **Visualizzatori Research** .

Successivamente, vengono distribuiti client Azure Information Protection per i dispositivi di membri del team di ricerca.

Per informazioni dettagliate sulla configurazione, vedere [file proteggere SharePoint Online con la protezione delle informazioni di Azure](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection). 

Di seguito è la configurazione del sito di **ricerca** per le risorse altamente riservati risultante.

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a>Passaggio 5: Eseguire la migrazione di dati di ricerca di SharePoint locale

Gli amministratori di Contoso spostati che tutti locale ricerca file nel sito di SharePoint Server 2016 locale alle cartelle del nuovo sito di SharePoint Online di **ricerca** .

## <a name="step-6-trained-their-users"></a>Passaggio 6: Addestrati agli utenti 

Personale addetto alla protezione Contoso addestrati i team di ricerca in un corso obbligatorio che li tramite eseguito l'accesso:

- Modalità di accesso del nuovo sito di SharePoint Online di **ricerca** e i relativi file esistente.
- Come creare nuovi file sul sito e caricare nuovi file memorizzati localmente.
- Una dimostrazione di come il criterio DLP consente di bloccare i file da condiviso esternamente.
- Come utilizzare il client di Azure Information Protection per etichettare i file di ricerca con l'etichetta secondaria di **ricerca** .
- Una dimostrazione di come etichetta secondaria **Research** protegge un file anche quando viene compromesso dal sito.

Il risultato finale è un ambiente protetto in cui i ricercatori possono collaborare in tutta l'organizzazione in un ambiente protetto. 

Se un documento di ricerca con l'etichetta secondaria di **ricerca** sia compromesso dal sito di **ricerca** , è possibile accedere solo ai membri dei gruppi di sicurezza **Membri Research** e **Visualizzatori di ricerche** con le credenziali valide e crittografati.

## <a name="next-step"></a>Passaggio successivo

[Distribuire](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise nell'organizzazione.

