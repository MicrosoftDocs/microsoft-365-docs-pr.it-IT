---
title: Configurare gli utenti e i casi in Office 365 Advanced eDiscovery
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
description: 'Informazioni su come configurare i ruoli utente, creare casi e assegnare gli utenti ai casi in Office 365 Advanced eDiscovery.  '
ms.openlocfilehash: 754cc7d73fc3325c2525e3101d1378d55afea4de
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601453"
---
# <a name="set-up-users-and-cases-in-office-365-advanced-ediscovery"></a>Configurare gli utenti e i casi in Office 365 Advanced eDiscovery

In questo argomento viene descritto come configurare gli utenti e i casi per Office 365 Advanced eDiscovery.
  
> [!IMPORTANT]
> Continuando ad investire nelle versioni più recenti di Advanced eDiscovery, si annuncia la pensione di Office 365 Advanced eDiscovery (noto anche come *Advanced eDiscovery v 1.0*). Se si sta ancora usando Advanced eDiscovery v 1.0, passare a [Advanced eDiscovery v 2.0](overview-ediscovery-20.md) (nota anche come *soluzione avanzata di eDiscovery in Microsoft 365*) appena possibile. Advanced eDiscovery 2,0 contiene funzionalità simili rilevate in Advanced eDiscovery v 1.0, ma offre anche molte nuove funzionalità come la gestione dei depositari, la gestione delle comunicazioni e i set di revisione. Per ulteriori informazioni sul pensionamento di Advanced eDiscovery v 1.0, vedere [pensionamento degli strumenti di eDiscovery legacy](legacy-ediscovery-retirement.md#advanced-ediscovery-v10). 
  
## <a name="prerequisites"></a>Prerequisiti

Prima di configurare i casi e gli utenti in Advanced eDiscovery, è necessario quanto segue:
  
- Per analizzare i dati di un utente tramite Advanced eDiscovery, all'utente (custode dei dati) deve essere assegnata una licenza di Office 365 E5. In alternativa, agli utenti con una licenza di Office 365 E1 o E3 può essere assegnata una licenza di eDiscovery autonoma avanzata. Gli amministratori e i responsabili della conformità assegnati ai casi e utilizzano Advanced eDiscovery per analizzare i dati non hanno bisogno di una licenza E5. 
    
- È necessario essere membri del gruppo di ruoli eDiscovery Manager nel centro sicurezza &amp; e conformità di Office 365 per creare un caso di eDiscovery e aggiungere membri. Per aggiungersi al gruppo di ruoli eDiscovery Manager nel centro &amp; sicurezza e conformità, è necessario essere un amministratore globale dell'organizzazione di Office 365. Se non si è un amministratore globale, è necessario chiedere a un amministratore globale di aggiungerlo al gruppo di ruoli eDiscovery Manager. Per altre informazioni, vedere:
    
  - [Autorizzazioni nel centro sicurezza &amp; e conformità di Microsoft 365](~/security/office-365-security/protect-against-threats.md)
    
  - [Assegnare le autorizzazioni di eDiscovery nel centro sicurezza &amp; e conformità di Microsoft 365](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a>Passaggio 1: assegnare autorizzazioni di eDiscovery agli utenti

Il primo passaggio consiste nell'assegnare agli utenti le autorizzazioni dei requisiti nel &amp; Centro sicurezza e conformità in modo che possano essere aggiunte come membri di un caso di eDiscovery. Dopo che un utente è stato aggiunto come membro di un caso nel centro &amp; sicurezza e conformità, sarà possibile accedere al caso in Advanced eDiscovery.
  
Per assegnare a un utente le autorizzazioni necessarie in modo che possano essere aggiunte come membri di un caso di eDiscovery, vedere il passaggio 1 in [eDiscovery Cases in &amp; the Microsoft 365 Security Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a>Passaggio 2: creare un caso di eDiscovery e aggiungere membri

Il passaggio successivo consiste nel creare un nuovo caso di eDiscovery nel centro &amp; conformità sicurezza e aggiungere membri. I membri del caso saranno quindi in grado di accedere al caso in Advanced eDiscovery.
  
1. Per creare un nuovo caso di eDiscovery, vedere il passaggio 2 in [eDiscovery Cases in the &amp; Microsoft 365 Security Compliance Center](ediscovery-cases.md#step-2-create-a-new-case).
    
2. Per aggiungere membri a un caso di eDiscovery, vedere passaggio 3 in [eDiscovery Cases in the Microsoft &amp; 365 Security Compliance Center](ediscovery-cases.md#step-3-add-members-to-a-case)
    
## <a name="step-3-go-a-case-in-advanced-ediscovery"></a>Passaggio 3: andare a un caso in Advanced eDiscovery

Dopo aver creato un caso di eDiscovery e aver aggiunto membri, l'utente (o qualsiasi membro del caso) può accedere al caso corrispondente in Advanced eDiscovery. Per accedere a un caso in Advanced eDiscovery, vedere il passaggio 8 in [eDiscovery Cases in the &amp; Microsoft 365 Security Compliance Center](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery).
  
## <a name="see-also"></a>Vedere anche

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[Preparazione dei dati](prepare-data-for-advanced-ediscovery.md)
 
