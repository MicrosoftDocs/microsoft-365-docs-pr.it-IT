---
title: Configurare gli utenti e i casi in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 60ffd80b-4376-419d-b6e4-a72029b9907c
description: Informazioni su come configurare i ruoli utente, creare casi e assegnare gli utenti ai casi in Advanced eDiscovery.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8e24354960b517815bef3cf498822d6ce9fd9dbe
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936743"
---
# <a name="set-up-users-and-cases-in-advanced-ediscovery-classic"></a>Configurare gli utenti e i casi in Advanced eDiscovery (Classic)

In questo argomento viene descritto come configurare gli utenti e i casi per Advanced eDiscovery (Classic).
  
> [!IMPORTANT]
> Microsoft continua a investire in nuove versioni di Advanced eDiscovery e annuncia il ritiro di Advanced eDiscovery, noto anche come *Advanced eDiscovery (classico)* o *Advanced eDiscovery v1.0*. Se si usa ancora Advanced eDiscovery v 1.0, passare al più presto ad [Advanced eDiscovery v2.0](overview-ediscovery-20.md), noto anche come *soluzione Advanced eDiscovery in Microsoft 365*. Advanced eDiscovery 2.0 contiene funzionalità simili a quelle disponibili in Advanced eDiscovery v1.0, ma offre anche numerose nuove caratteristiche, come gestione dei responsabili, gestione delle comunicazioni e insiemi da rivedere. Per altre informazioni sul ritiro di Advanced eDiscovery v 1.0, vedere [Ritiro degli strumenti di eDiscovery legacy](legacy-ediscovery-retirement.md#advanced-ediscovery-v10). 
  
## <a name="requirements-to-set-up-users-and-cases"></a>Requisiti per la configurazione degli utenti e dei casi

Prima di configurare i casi e gli utenti in Advanced eDiscovery, è necessario quanto segue:
  
- Per analizzare i dati di un utente tramite Advanced eDiscovery, all'utente (custode dei dati) deve essere assegnata una licenza di Office 365 E5. In alternativa, agli utenti con una licenza di Office 365 E1 o E3 può essere assegnata una licenza di eDiscovery autonoma avanzata. Gli amministratori e i responsabili della conformità assegnati ai casi e utilizzano Advanced eDiscovery per analizzare i dati non hanno bisogno di una licenza E5. 
    
- È necessario essere membri del gruppo di ruoli eDiscovery Manager nel &amp; Centro sicurezza e conformità per creare un caso di eDiscovery e aggiungere membri. Per aggiungersi al gruppo di ruoli eDiscovery Manager nel &amp; Centro sicurezza e conformità, è necessario essere un amministratore globale dell'organizzazione. Se non si è un amministratore globale, è necessario chiedere a un amministratore globale di aggiungerlo al gruppo di ruoli eDiscovery Manager. Per ulteriori informazioni, vedere:
    
  - [Autorizzazioni nel centro sicurezza e conformità di Microsoft 365 &amp;](~/security/office-365-security/protect-against-threats.md)
    
  - [Assegnare le autorizzazioni di eDiscovery nel centro sicurezza e conformità di Microsoft 365 &amp;](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a>Passaggio 1: assegnare autorizzazioni di eDiscovery agli utenti

Il primo passaggio consiste nell'assegnare agli utenti le autorizzazioni dei requisiti nel &amp; Centro sicurezza e conformità in modo che possano essere aggiunte come membri di un caso di eDiscovery. Dopo che un utente è stato aggiunto come membro di un caso nel &amp; Centro sicurezza e conformità, sarà possibile accedere al caso in Advanced eDiscovery.
  
Per assegnare a un utente le autorizzazioni necessarie in modo che possano essere aggiunte come membri di un caso di eDiscovery, vedere il passaggio 1 in [eDiscovery Cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a>Passaggio 2: creare un caso di eDiscovery e aggiungere membri

Il passaggio successivo consiste nel creare un nuovo caso di eDiscovery nel centro sicurezza & compliance e aggiungere membri. I membri del caso saranno quindi in grado di accedere al caso in Advanced eDiscovery.
  
1. Per creare un nuovo caso di eDiscovery, vedere Step 3 in [Get Started with Core eDiscovery](get-started-core-ediscovery.md#step-3-create-a-core-ediscovery-case).

2. Per aggiungere membri a un caso di eDiscovery, vedere passaggio 4 in [Get Started with Core eDiscovery](get-started-core-ediscovery.md#step-4-optional-add-members-to-a-core-ediscovery-case)

## <a name="step-3-go-a-case-in-advanced-ediscovery"></a>Passaggio 3: andare a un caso in Advanced eDiscovery

Dopo aver creato un caso di eDiscovery e aver aggiunto membri, l'utente (o qualsiasi membro del caso) può accedere al caso corrispondente in Advanced eDiscovery. Per accedere a un caso in Advanced eDiscovery, vedere [accesso a un caso in Advanced eDiscovery](quick-setup-for-advanced-ediscovery.md#accessing-a-case-in-advanced-ediscovery).
  
## <a name="see-also"></a>Vedere anche

[Advanced eDiscovery (classico)](office-365-advanced-ediscovery.md)
  
[Preparazione dei dati per Advanced eDiscovery (Classic)](prepare-data-for-advanced-ediscovery.md)
 
