---
title: Aggiungere i contatti di amministratore nel portale di amministrazione di Microsoft Managed Desktop
description: Indicare gli utenti che devono contattare per ogni area di interesse.
keywords: Microsoft Managed Desktop, Microsoft 365, Service, documentazione
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 014404ab38ff5871289be186dec150115c3be6ec
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277542"
---
# <a name="add-admin-contacts-in-microsoft-managed-desktop-admin-portal"></a>Aggiungere i contatti di amministratore nel portale di amministrazione di Microsoft Managed Desktop

Esistono diversi modi in cui il servizio Microsoft Managed Desktop comunica con i clienti. Per semplificare la comunicazione e verificare che i contatti migliori siano stati verificati, è necessario fornire un set di contatti di amministratore. Microsoft Managed Desktop IT Operations contatterà queste persone per risolvere i problemi di assistenza per il tenant. 

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a>Azure Active Directory Access per il portale di amministrazione di Microsoft Managed Desktop

Il portale di amministrazione di Microsoft Managed Desktop richiede che gli utenti che accedono al portale dispongano di uno di questi ruoli di Azure Active Directory (AD):
- Amministratore globale
- Amministratore del servizio Intune
- Amministratore fatturazione
- Amministratore del supporto tecnico

L'amministratore globale deve essere quello di registrazione del cliente in Microsoft Managed Desktop.  Tutti e cinque i ruoli dispongono dello stesso accesso all'interno del portale di amministrazione per avviare e visualizzare le attività.  Per ulteriori informazioni sull'assegnazione di questi ruoli in Azure AD, vedere [autorizzazioni per il ruolo di amministratore in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles). 

## <a name="admin-contact-focus-areas"></a>Aree di interesse per i contatti amministrativi

I contatti amministrativi devono essere la persona o il gruppo migliore in grado di rispondere alle domande e prendere decisioni per diverse aree di interesse.  Microsoft Managed Desktop Operations contatterà questi contatti di amministrazione per le domande relative alle richieste di supporto presentate dal cliente.  Questi contatti di amministratore ricevono notifiche per gli aggiornamenti delle richieste di supporto e i nuovi messaggi.  Tra queste aree sono incluse le seguenti:

Area di interesse | Per domande su
--- | ---
App | Risoluzione dei problemi relativi agli imballaggi delle app
Dispositivi | Integrità del dispositivo, risoluzione dei problemi con i dispositivi Microsoft Managed Desktop
Sicurezza | Risoluzione dei problemi di sicurezza con i dispositivi Microsoft Managed Desktop
Altro | Per i problemi non coperti da altre aree

Chiunque sia scelto per questi contatti deve avere le conoscenze e l'autorità necessarie per prendere decisioni per l'ambiente desktop Microsoft gestito. Quando si esegue l'onboarding dell'ambiente Microsoft Managed Desktop, viene richiesto di aggiungere contatti per il supporto tecnico e la sicurezza locali. 

I contatti amministrativi sono necessari quando si [Invia una richiesta di supporto](../working-with-managed-desktop/support.md). È necessario disporre di un contatto di amministrazione per l'area dello stato attivo della richiesta di supporto. 

**Per aggiungere contatti di amministratore**

1.  Accedere al [portale di amministrazione di Microsoft managEd desktop](http://aka.ms/mwaasportal). 

2.  In **supporto**, selezionare **contatti di amministratore**. 

    ![Menu di supporto, contatti amministrativi](images/admincontacts.png)

3. Seleziona **Aggiungi**.

    ![Pulsante di aggiunta al portale di amministrazione](images/adminadd.png)

4.  Selezionare un' **area di messa a fuoco** e immettere le informazioni per il contatto. 

    ![elenco delle aree di interesse](images/areaoffocus.png)

5. Ripetere l'attività per ogni area di interesse. 

