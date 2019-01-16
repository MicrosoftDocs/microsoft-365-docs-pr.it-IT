---
title: Aggiungere contatti Admin nel portale di amministrazione di Microsoft Desktop gestiti
description: Commenti su chi contattare per ogni area di stato attivo.
keywords: Servizio Microsoft Desktop gestiti, Microsoft 365, documentazione
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 31984609681b6e3b1b6de9996eb8fb0fcf6f5624
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868458"
---
# <a name="add-admin-contacts-in-microsoft-managed-desktop-admin-portal"></a>Aggiungere contatti Admin nel portale di amministrazione di Desktop gestiti Microsoft

Esistono diversi modi in cui il servizio Microsoft Desktop gestiti comunica con i clienti. Per semplificare le comunicazioni e garantire che è stiamo verifica con i contatti ottimali, è necessario fornire un gruppo di contatti di amministrazione. Operazioni IT Desktop gestiti Microsoft verrà contattare queste persone di risoluzione dei problemi per il tenant. 

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a>Azure accesso ad Active Directory per il portale di amministrazione di Desktop gestiti Microsoft

Portale di amministrazione di Desktop gestiti Microsoft deve disporre di accesso al portale di persone uno di questi ruoli Azure Active Directory (AD):
- Amministratore globale
- Amministratore del servizio Intune
- Amministratore fatturazione
- Amministratore del servizio supporto tecnico

L'amministratore globale deve essere quello per registrare il cliente in Microsoft Desktop gestiti.  I cinque ruoli avere lo stesso accesso all'interno del portale di amministrazione per avviare e visualizzare le attività.  Per ulteriori informazioni sull'assegnazione di questi ruoli in Azure Active Directory, vedere [autorizzazioni di ruolo di amministratore in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles). 

## <a name="admin-contact-focus-areas"></a>Amministrazione aree contatto

Contatti di amministrazione devono essere la migliore utente o gruppo che può rispondere alle domande e prendere decisioni per aree diverse.  Microsoft Operations Desktop gestiti contatterà tali contatti Admin per domande riguardanti le richieste di assistenza archiviate dal cliente.  Tali contatti Admin riceverà le notifiche per i nuovi messaggi e gli aggiornamenti di richiesta di supporto.  Queste aree includono:

Area di interesse | Per ulteriori informazioni su
--- | ---
App | Risoluzione dei problemi di creazione del pacchetto App
 Dispositivi  | Prevenzione di dispositivi, la risoluzione dei problemi con i dispositivi Desktop gestiti Microsoft
Sicurezza | Risoluzione dei problemi di sicurezza di dispositivi Desktop gestiti Microsoft
Altro | Per i problemi non rientra altre aree

Chiunque desideri per questi contatti deve disporre dell'autorità per prendere decisioni per l'ambiente Desktop gestito Microsoft le competenze. Se inizio il Microsoft gestita ambiente Desktop, viene richiesto di aggiungere i contatti per la protezione e del supporto tecnico locale. 

Amministrazione dei contatti sono necessarie quando si [Invia una richiesta di supporto](../working-with-managed-desktop/support.md). È necessario disporre di un contatto di amministratore per l'area attiva della richiesta di supporto. 

**Per aggiungere i contatti di amministrazione**

1.  Accedere al [portale di amministrazione di Microsoft Desktop gestiti](http://aka.ms/mwaasportal). 

2.  Nel **supporto**, selezionare i **contatti di amministrazione**. 

    ![Contatti di amministrazione dal menu di supporto](images/admincontacts.png)

3. Selezionare **Aggiungi**.

    ![Pulsante Aggiungi portale di amministrazione](images/adminadd.png)

4.  Selezionare un' **Area di stato attivo** e immettere le informazioni del contatto. 

    ![l'elenco delle aree dell'elemento attivo](images/areaoffocus.png)

5. Ripetere per ogni area di stato attivo. 

