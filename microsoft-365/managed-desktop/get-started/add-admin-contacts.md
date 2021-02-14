---
title: Aggiungere e verificare i contatti degli amministratori nel portale di amministrazione
description: Indicare chi contattare per ogni area di interesse.
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8b287200b1c94ff350f7ba00cf0c4e6bc1b4a71f
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289262"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a>Aggiungere e verificare i contatti degli amministratori nel portale di amministrazione

Esistono diversi modi in cui il servizio Microsoft Managed Desktop comunica con i clienti. Per semplificare la comunicazione e garantire che stiamo controllando con le persone giuste, è necessario fornire un set di contatti di amministratore. Microsoft Managed Desktop IT Operations contatta queste persone per assistenza nella risoluzione dei problemi relativi al tenant.

> [!IMPORTANT]
> Questi contatti potrebbero essere già stati aggiunti nel portale di amministrazione. In tal caso, verificare che l'elenco contatti sia accurato, perché Microsoft Managed **Desktop** deve essere in grado di contattarli in caso di grave incidente.

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a>Accesso ad Azure Active Directory per il portale di amministrazione di Microsoft Managed Desktop

Il portale di amministrazione di Microsoft Managed Desktop richiede che gli utenti che accedono al portale dispongono di uno di questi ruoli di Azure Active Directory (AD):
- Amministratore globale
- Amministratore del servizio Intune
- Ruolo con autorizzazioni di lettura globali
- Amministratore del supporto tecnico

L'amministratore globale deve essere l'unico a registrare l'organizzazione in Microsoft Managed Desktop. Tutti e cinque i ruoli hanno lo stesso accesso nel portale di amministrazione per avviare e visualizzare le attività. Per altre informazioni sull'assegnazione di questi ruoli in Azure AD, vedere [Autorizzazioni del ruolo amministratore in Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 

## <a name="admin-contact-areas-of-focus"></a>Aree di contatto dell'amministratore incentrate

I contatti dell'amministratore devono essere la persona o il gruppo migliori in grado di rispondere alle domande e prendere decisioni per diverse aree di interesse. **Microsoft Managed Desktop Operations contatta questi contatti dell'amministratore per le domande relative alle richieste di supporto inviate dal cliente.** Questi contatti dell'amministratore riceveranno notifiche per gli aggiornamenti delle richieste di supporto e i nuovi messaggi. Queste aree includono:

Area di stato attivo | Per domande su
--- | ---
Creazione di pacchetti dell'app | Risoluzione dei problemi di creazione di pacchetti di app
Dispositivi | Integrità dei dispositivi, risoluzione dei problemi con i dispositivi Microsoft Managed Desktop
Sicurezza | Risoluzione dei problemi di sicurezza con i dispositivi Microsoft Managed Desktop
Help desk IT | nei casi in cui il personale di supporto si conse tasser ticket utente al di fuori delle aree di supporto di Microsoft Managed Desktop 
Altro | Per problemi non coperti da altre aree

**Chiunque scegli per questi contatti deve avere le conoscenze e l'autorità necessarie per prendere decisioni per il tuo ambiente Microsoft Managed Desktop.** Quando si esegue l'onboarded dell'ambiente Microsoft Managed Desktop, viene richiesto di aggiungere contatti per l'helpdesk locale e la sicurezza. 

I contatti dell'amministratore sono necessari quando [invii una richiesta di supporto.](../service-description/support.md) Dovrai avere un contatto amministratore per l'area di interesse della richiesta di supporto. 

**Per aggiungere contatti di amministrazione**

1.  Accedere al portale [di amministrazione di Microsoft Managed Desktop.](https://aka.ms/mwaasportal) 

2.  In **Supporto** selezionare **Contatti amministratore.** 

    ![Menu Supporto, contatti dell'amministratore nella parte superiore selezionata](../../media/admincontacts.png)

3. Selezionare **Aggiungi**.

    ![Portale di amministrazione, pulsante Aggiungi, a sinistra di Esporta e aggiorna](../../media/adminadd.png)

4.  Seleziona **un'area di interesse** e immetti le informazioni per il contatto. 

    ![l'elenco delle aree di interesse, ad esempio Altri, App e Sicurezza](../../media/areaoffocus.png)

5. Ripetere l'operazione per ogni area dello stato attivo. 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Procedura per iniziare a usare Microsoft Managed Desktop

1. Aggiungere e verificare i contatti dell'amministratore nel portale di amministrazione (questo argomento)
2. [Modificare l'accesso condizionale](conditional-access.md)
3. [Assegnare licenze](assign-licenses.md)
4. [Installare il portale aziendale di Intune sui dispositivi](company-portal.md)
5. [Abilitare Enterprise State Roaming](enterprise-state-roaming.md)
6. [Configurare dispositivi Microsoft Managed Desktop](set-up-devices.md)
7. [Preparare gli utenti a usare i dispositivi](get-started-devices.md)
8. [Distribuire le app sui dispositivi](deploy-apps.md)
