---
title: Proteggere i file nei team con etichette di riservatezza
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: 5b9c8e41-25d2-436d-89bb-9aecb9ec2b80
description: 'Sintesi: applicare etichette di riservatezza per proteggere i file in un team estremamente riservato.'
ms.openlocfilehash: b263aeae335b83cadb45b16d70a2a45d56f1cbd3
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083370"
---
# <a name="protect-files-in-teams-with-sensitivity-labels"></a><span data-ttu-id="90458-103">Proteggere i file nei team con etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="90458-103">Protect files in teams with sensitivity labels</span></span>


<span data-ttu-id="90458-104">Diversamente da un'etichetta di riservatezza per dati altamente regolamentati, che chiunque può applicare a qualsiasi file, un team estremamente riservato deve avere una propria etichetta o sottoetichetta, in modo che i file a cui è assegnata:</span><span class="sxs-lookup"><span data-stu-id="90458-104">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a highly confidential team needs its own label or sublabel so that assigned files:</span></span>

- <span data-ttu-id="90458-105">Siano crittografati singolarmente.</span><span class="sxs-lookup"><span data-stu-id="90458-105">Are individually encrypted.</span></span>
- <span data-ttu-id="90458-106">Contengano autorizzazioni personalizzate in modo che solo i membri del team possano aprirli.</span><span class="sxs-lookup"><span data-stu-id="90458-106">Contain custom permissions so that only members of the team can open it.</span></span>

<span data-ttu-id="90458-107">Per implementare questo ulteriore livello di sicurezza per i file archiviati nel sito di SharePoint sottostante di un team, è necessario configurare un'etichetta di riservatezza personalizzata, autonoma o come sottoetichetta dell'etichetta generale per i dati altamente regolamentati.</span><span class="sxs-lookup"><span data-stu-id="90458-107">To accomplish this additional level of security for files stored in the underlying SharePoint site of a team, you must configure a customized sensitivity label that is either its own label or a sublabel of the general label for highly regulated data.</span></span> <span data-ttu-id="90458-108">Solo i membri del team vedranno l'etichetta personalizzata o la sottoetichetta nel proprio elenco di etichette.</span><span class="sxs-lookup"><span data-stu-id="90458-108">Only team members will see the customized label or sublabel in their list of labels.</span></span>

<span data-ttu-id="90458-109">Usare un'etichetta di riservatezza quando è necessario un numero limitato di etichette sia per l'uso globale che per i singoli team privati.</span><span class="sxs-lookup"><span data-stu-id="90458-109">Use a sensitivity label when you need a small number of labels for both global use and individual private teams.</span></span> 

<span data-ttu-id="90458-110">Usare una sottoetichetta di riservatezza se si ha un numero elevato di etichette o se si vogliono organizzare le etichette per i team estremamente riservati sotto l'etichetta per i dati altamente regolamentati.</span><span class="sxs-lookup"><span data-stu-id="90458-110">Use a sensitivity sublabel when you have a large number of labels or want to organize labels for highly confidential teams under the highly regulated label.</span></span>

<span data-ttu-id="90458-111">Seguire [queste istruzioni ](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) per configurare un'etichetta separata o una sottoetichetta con le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="90458-111">Use [these instructions](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a separate label or a sublabel with the following settings:</span></span>

- <span data-ttu-id="90458-112">Il nome dell'etichetta o della sottoetichetta contiene il nome del team</span><span class="sxs-lookup"><span data-stu-id="90458-112">The name of the label or sublabel contains the name of the team</span></span>
- <span data-ttu-id="90458-113">La crittografia è abilitata</span><span class="sxs-lookup"><span data-stu-id="90458-113">Encryption is enabled</span></span>
- <span data-ttu-id="90458-114">Il gruppo di Office 365 per il team ha autorizzazioni di creazione condivisa</span><span class="sxs-lookup"><span data-stu-id="90458-114">The Office 365 group for the team has Co-Author permissions</span></span>

<span data-ttu-id="90458-115">Una volta creata, pubblicare la nuova etichetta o sottoetichetta per gli utenti, che potranno quindi applicarla ai file in locale prima di caricarli nel team o dopo che il file sarà archiviato nel team.</span><span class="sxs-lookup"><span data-stu-id="90458-115">After creating, publish the new label or sublabel for your users, who can then apply them to files either locally before uploading them to the team or later once the file is stored in the team.</span></span>

<span data-ttu-id="90458-116">Ecco la configurazione del team estremamente riservato che utilizza etichette di riservatezza per le autorizzazioni e la crittografia dei file.</span><span class="sxs-lookup"><span data-stu-id="90458-116">Here is the configuration of the highly confidential team that uses sensitivity labels for file encryption and permissions.</span></span>

![Protezione di base per un team pubblico.](../../media/highly-confidential-team-dlp-sensitivity-labels.png)


## <a name="see-also"></a><span data-ttu-id="90458-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90458-118">See Also</span></span>

[<span data-ttu-id="90458-119">Proteggere i file in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="90458-119">Secure files in Microsoft Teams</span></span>](secure-files-in-teams.md)
  
[<span data-ttu-id="90458-120">Adozione del cloud e soluzioni ibride</span><span class="sxs-lookup"><span data-stu-id="90458-120">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
