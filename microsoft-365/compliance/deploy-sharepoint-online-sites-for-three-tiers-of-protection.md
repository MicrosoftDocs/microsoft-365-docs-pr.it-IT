---
title: Distribuire siti di SharePoint Online per tre livelli di protezione
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/27/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
ms.custom:
- Ent_Solutions
ms.assetid: 1e8e3cfd-b878-4088-b941-9940363a5fae
description: 'Sintesi: creare e configurare siti del team di SharePoint Online per diversi livelli di protezione delle informazioni.'
ms.openlocfilehash: 1f67dd1956059162902aefdb194e5e514d063778
ms.sourcegitcommit: a53ec6ab7bf59983780ea7187cd5d56b8b1f4b33
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/07/2020
ms.locfileid: "41855255"
---
# <a name="deploy-sharepoint-online-sites-for-three-tiers-of-protection"></a>Distribuire siti di SharePoint Online per tre livelli di protezione

Usare i passaggi descritti in questo articolo per progettare e distribuire siti del team di SharePoint Online di base, sensibili e con riservatezza elevata. Per altre informazioni su questi tre livelli di protezione, vedere [Proteggere siti e file di SharePoint Online](../security/office-365-security/secure-sharepoint-online-sites-and-files.md).
  
## <a name="baseline-sharepoint-online-team-sites"></a>Siti del team di SharePoint Online di base

La protezione di siti di base include siti del team pubblici e privati. I siti del team pubblici possono essere individuati e usati da qualsiasi persona dell'organizzazione. I siti privati possono essere individuati e usati solo dai membri del gruppo di Office 365 associato al sito del team. Entrambi questi tipi di siti del team consentono ai membri di condividere il sito con altri utenti.
  
### <a name="public"></a>Pubblico

Per creare un sito del team di SharePoint Online di base con accesso pubblico e autorizzazioni, seguire [queste istruzioni](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).

Questa è la configurazione risultante.
  
![Protezione di livello di base per un sito del team di SharePoint Online pubblico.](media/bcd46b8d-3f89-4398-80ce-4da17ee85e03.png)
  
### <a name="private"></a>Privato

Per creare un sito del team di SharePoint Online di base con accesso privato e autorizzazioni, seguire [queste istruzioni](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).
  
Questa è la configurazione risultante.
  
![Protezione di livello di base per un sito del team di SharePoint Online privato.](media/91769026-37e3-4383-ac3c-dbf7aca98e41.png)
  
## <a name="sensitive-sharepoint-online-team-sites"></a>Siti del team di SharePoint Online sensibili

Un sito del team di SharePoint Online riservato viene avviato come sito del team privato.
  
Creare innanzitutto il sito del team di SharePoint Online privato seguendo [queste istruzioni](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).

Successivamente, dal nuovo sito del team di SharePoint Online configurare le altre impostazioni delle autorizzazioni seguendo questi passaggi.

1.  Nella barra degli strumenti del sito del team di SharePoint fare clic sull'icona delle impostazioni, poi su **Autorizzazioni sito**.
2.  Nel riquadro **Autorizzazioni sito** fare clic su **Modifica impostazioni di condivisione** in **Impostazioni di condivisione**.
3.  In **Impostazioni di condivisione** scegliere **Solo i proprietari del sito possono condividere file, cartelle e il sito**, quindi fare clic su **Salva**.

I risultati di queste impostazioni delle autorizzazioni sono i seguenti:

- La possibilità per i membri di condividere con altri membri è disabilitata.
- La possibilità per gli utenti non membri di richiedere l'accesso è abilitata.

Di seguito è riportata la configurazione risultante.
  
![Protezione di livello riservato per un sito del team di SharePoint Online isolato.](media/7a6ab9c6-560a-4674-ac39-8175644dbe6f.png)
  
I membri del sito, attraverso l'appartenenza a uno dei gruppi di accesso, possono ora collaborare in modo sicuro alle risorse del sito.
  
## <a name="highly-confidential-sharepoint-online-team-sites"></a>Siti del team di SharePoint Online con riservatezza elevata

Un sito del team di SharePoint Online estremamente riservato è un sito del team privato con altre impostazioni delle autorizzazioni.

Creare innanzitutto il sito del team di SharePoint Online privato seguendo [queste istruzioni](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).

Successivamente, dal nuovo sito del team di SharePoint Online configurare le altre impostazioni delle autorizzazioni seguendo questi passaggi.

1.  Nella barra degli strumenti del sito del team di SharePoint fare clic sull'icona delle impostazioni, poi su **Autorizzazioni sito**.
2.  Nel riquadro **Autorizzazioni sito** fare clic su **Modifica impostazioni di condivisione** in **Impostazioni di condivisione**.
3.  In **Impostazioni di condivisione** scegliere **Solo i proprietari del sito possono condividere file, cartelle e il sito**.
4. Disattivare **Consenti richieste di accesso** e quindi fare clic su **Salva**.

I risultati di queste impostazioni delle autorizzazioni sono i seguenti:

- La possibilità per i membri di condividere con altri membri è disabilitata.
- La possibilità per gli utenti non membri di richiedere l'accesso è disabilitata.

Di seguito è riportata la configurazione risultante.
  
![Protezione di livello estremamente riservato per un team di SharePoint Online isolato.](media/196359ab-d7ed-4fcf-97b4-61820a74aca4.png)
  
I membri del sito, attraverso l'appartenenza a uno dei gruppi di accesso, possono ora collaborare in modo sicuro alle risorse del sito.
  
## <a name="next-step"></a>Passaggio successivo

[Proteggere i file di SharePoint Online con le etichette di Office 365 e la prevenzione della perdita dei dati](protect-sharepoint-online-files-with-office-365-labels-and-dlp.md)

## <a name="see-also"></a>Vedere anche

[Guida sulla sicurezza Microsoft per organizzazioni che si occupano della campagna politica, no profit e altre organizzazioni Agile](../security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[Adozione del cloud e soluzioni ibride](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
