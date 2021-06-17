---
title: Aggiungere e verificare i contatti degli amministratori nel portale di amministrazione
description: Dicci chi contattare per ogni area di interesse.
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 65d7647e9000152d2eeb8d6bf36e8d45a0d4fa90
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984701"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a>Aggiungere e verificare i contatti degli amministratori nel portale di amministrazione

Esistono diversi modi in cui Microsoft Managed Desktop servizio comunica con i clienti. Per semplificare la comunicazione e verificare che stiamo controllando con le persone giuste, è necessario fornire un set di contatti di amministratore. Microsoft Managed Desktop Le operazioni IT contattano queste persone per assistenza nella risoluzione dei problemi relativi al tenant.

> [!IMPORTANT]
> Questi contatti potrebbero essere già stati aggiunti nel portale di amministrazione. In tal caso, è necessario verificare che l'elenco dei contatti  sia accurato, perché Microsoft Managed Desktop essere in grado di raggiungerli se si verifica un incidente grave.

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a>Azure Active Directory accesso per Microsoft Managed Desktop admin portal

Microsoft Managed Desktop Il portale di amministrazione richiede che gli utenti che accedono al portale Azure Active Directory (AD):
- Amministratore globale
- Amministratore del servizio Intune
- Ruolo con autorizzazioni di lettura globali
- Service Support Administrator

L'amministratore globale deve essere quello per registrare l'organizzazione in Microsoft Managed Desktop. Tutti e cinque i ruoli hanno lo stesso accesso nel portale di amministrazione per avviare e visualizzare le attività. Per ulteriori informazioni sull'assegnazione di questi ruoli in Azure AD, vedere [Autorizzazioni del ruolo di amministratore in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles). 

## <a name="admin-contact-areas-of-focus"></a>Aree di contatto dell'amministratore

I contatti dell'amministratore devono essere la persona o il gruppo migliori in grado di rispondere alle domande e prendere decisioni per diverse aree di interesse. **Microsoft Managed Desktop Le operazioni contattano questi contatti dell'amministratore per domande relative alle richieste di supporto inviate dal cliente.** Questi contatti di amministratore riceveranno notifiche per gli aggiornamenti delle richieste di supporto e i nuovi messaggi. Queste aree includono:

Area di messa a fuoco | Per domande su
--- | ---
Creazione di pacchetti dell'app | Risoluzione dei problemi di creazione di pacchetti delle app
Dispositivi | Integrità dei dispositivi, risoluzione dei problemi con Microsoft Managed Desktop dispositivi
Sicurezza | Risoluzione dei problemi di sicurezza Microsoft Managed Desktop dispositivi
Help desk IT | nei casi in cui il personale di supporto si tasser i ticket utente al di fuori Microsoft Managed Desktop aree di supporto 
Altro | Per problemi non coperti da altre aree

**Chiunque scegli per questi contatti deve avere le conoscenze e l'autorità necessarie per prendere decisioni per il tuo Microsoft Managed Desktop ambiente.** Quando si esegue l'onboard Microsoft Managed Desktop locale, viene richiesto di aggiungere contatti per l'helpdesk locale e la sicurezza. 

I contatti di amministratore sono necessari quando [invii una richiesta di supporto](../service-description/support.md). Dovrai avere un contatto amministratore per l'area di interesse della richiesta di supporto. 

**Per aggiungere contatti di amministratore**

1.  Accedi a [Microsoft Endpoint Manager](https://endpoint.microsoft.com). 

2.  In **Amministrazione tenant** cerca la sezione Microsoft Managed Desktop quindi seleziona Contatti di **amministratore.**  

3. Selezionare **Aggiungi**.

4.  Seleziona **un'area di stato attivo** e immetti le informazioni per il contatto. 

    ![l'elenco delle aree di interesse, ad esempio Altre, App e Sicurezza](../../media/areaoffocus.png)

5. Ripetere l'operazione per ogni area dello stato attivo. 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Passaggi per iniziare a usare Microsoft Managed Desktop

1. Aggiungere e verificare i contatti di amministratore nel portale di amministrazione (questo argomento)
2. [Modificare l'accesso condizionale](conditional-access.md)
3. [Assegnare licenze](assign-licenses.md)
4. [Installare il portale aziendale di Intune sui dispositivi](company-portal.md)
5. [Abilitare Enterprise State Roaming](enterprise-state-roaming.md)
6. [Configurare dispositivi Microsoft Managed Desktop](set-up-devices.md)
7. [Preparare gli utenti a usare i dispositivi](get-started-devices.md)
8. [Distribuire le app sui dispositivi](deploy-apps.md)
