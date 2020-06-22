---
title: Siti del team di SharePoint Online isolati
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 71250a04-fd2d-4c3c-a32b-b8a838b19a54
description: Informazioni sui siti del team di SharePoint Online isolati e sugli usi, i requisiti e le funzionalità con cui possono essere usati.
ms.openlocfilehash: 0646ffc37256702844b550fd1beb841944b2d509
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819534"
---
# <a name="isolated-sharepoint-online-team-sites"></a>Siti del team di SharePoint Online isolati

 **Sintesi:** informazioni sugli utilizzi dei siti del team di SharePoint Online isolati.
  
SharePoint Online team sites are an easy way to quickly create a space for collaboration of notes, documents, articles, a calendar, and other resources in Microsoft Office 365. SharePoint Online team sites are based on a Microsoft 365 group and have a simplified administration model to allow open collaboration with a private set of group members or the entire organization. A default SharePoint Online team site allows members of the Microsoft 365 group to invite other users and control permissions settings.
  
However, in some cases, you want to create a SharePoint Online team site for collaboration where the permissions of that site are more tightly controlled through group membership and SharePoint Online permission levels, which are only managed by SharePoint administrators. We call this an isolated site, which is isolated to the set of users that are either collaborating, viewing its contents, or administering the site. You might need an isolated site for the following:
  
- Un progetto segreto all'interno dell'organizzazione.
    
- La posizione di informazioni altamente riservate o di proprietà intellettuale importante.
    
- Le risorse per un'azione legale intrapresa dall'organizzazione o alla quale è soggetta.
    
- Per condividere un abbonamento a Microsoft 365 tra più organizzazioni con alcune sovrapposizioni, ma per la maggior parte esistono entità aziendali separate.
    
Di seguito sono riportati i requisiti di un sito isolato:
  
- Solo gli amministratori di SharePoint Online possono gestire il sito, la cui amministrazione include l'appartenenza ai gruppi per l'accesso al sito e la configurazione di autorizzazioni personalizzate.
    
- I membri del sito non possono invitare altri membri nel sito del team.
    
- Users who are not members of the isolated site cannot request access to the site. They will receive an access denied web page when they attempt to access any URL associated with the site.
    
The tradeoff of requiring centralized access control and custom permissions by SharePoint Online administrators is that the site remains isolated over time. For example, current members cannot, either intentionally or accidentally, invite or configure custom permissions for other users within the Microsoft 365 subscription who should not be members of the site.
  
Un sito isolato può essere usato con altre funzionalità, ad esempio:
  
- Information Rights Management per garantire che le risorse nel sito rimangano crittografate anche se vengono scaricate in locale e caricate in un altro sito disponibile per l'intera organizzazione.
    
- Prevenzione della perdita dei dati per impedire agli utenti di inviare le risorse del sito, come i file, tramite la posta elettronica.
    
## <a name="next-steps"></a>Passaggi successivi

Per provare a usare un sito del team di SharePoint Online isolato in una sottoscrizione di valutazione, vedere le istruzioni dettagliate disponibili in [Sito team di SharePoint Online isolato nell'ambiente di sviluppo e di testing di Office 365](isolated-sharepoint-online-team-site-dev-test-environment.md).
  
Quando si è pronti a distribuire un sito del team di SharePoint Online isolato in produzione, vedere le considerazioni di progettazione dettagliate in [Progettare un sito del team di SharePoint Online isolato](design-an-isolated-sharepoint-online-team-site.md).
  
## <a name="related-topics"></a>Argomenti correlati

[Progettare un sito del team di SharePoint Online isolato](design-an-isolated-sharepoint-online-team-site.md)
  
[Gestire un sito del team di SharePoint Online isolato](manage-an-isolated-sharepoint-online-team-site.md)

[Distribuire un sito del team di SharePoint Online isolato](deploy-an-isolated-sharepoint-online-team-site.md)


