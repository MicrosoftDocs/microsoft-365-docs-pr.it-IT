---
title: Aggiungere app all'icona di avvio delle app degli utenti
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- M365-subscription-management
ms.service: o365-administration
localization_priority: Normal
description: Gli amministratori globali possono aggiungere fino a tre app all'icona di avvio delle app degli utenti.
ms.openlocfilehash: 965fcbbb3f0e22074e3f6c5476d65ade98fea94c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915219"
---
# <a name="pin-apps-to-your-users-app-launcher"></a>Aggiungere app all'icona di avvio delle app degli utenti

Puoi usare i controlli nel portale di Azure Active Directory per aggiungere fino a tre app Office.com e l'icona di avvio delle app per tutti gli utenti dell'organizzazione. È inoltre possibile organizzare gruppi di applicazioni. Qualsiasi app aggiunta può essere successivamente sbloccata dall'utente in qualsiasi momento. Per aggiungere un'app per gli utenti, è necessario essere un amministratore dell'applicazione cloud o un amministratore dell'applicazione in Azure Active Directory o un amministratore globale in Office 365. Per ulteriori informazioni sui ruoli di amministratore, vedere [Ruoli di amministratore in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) e Ruoli di amministratore in Microsoft [365.](../add-users/about-admin-roles.md) 

Per altre informazioni sull'icona di avvio delle app e Office.com, vedi l'articolo di blog sull'icona di avvio delle [app](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) e gli aggiornamenti per office.com e l'articolo del blog sull'icona di avvio delle app di [Office 365.](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503)

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a>Usare il portale di Azure Active Directory per aggiungere app

1. Accedere all'interfaccia di amministrazione di Microsoft 365 all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .
2. Nel riquadro di spostamento sinistro scegliere **Mostra tutto** e in Interfaccia **di amministrazione** scegliere Azure **Active Directory.**
3. In **Azure Active Directory** scegliere Applicazioni **aziendali**  >  **Impostazioni utente**.
4. Nella sezione **Impostazioni di Office 365** scegliere **Aggiungi applicazione.**
5. Scegli le applicazioni che vuoi aggiungere all'icona di avvio delle app degli utenti e quindi scegli **Aggiungi.**

:::image type="content" source="../../media/add-apps.png" alt-text="Impostazioni di Microsoft 365 per aggiungere app.":::

### <a name="pin-a-custom-app"></a>Aggiungere un'app personalizzata

> [!NOTE]
> L'interfaccia utente indicherà se è necessario acquistare ulteriori licenze di Azure AD per usare questa funzionalità. Per ulteriori informazioni, vedere [Prezzi di Azure Active Directory.](https://azure.microsoft.com/pricing/details/active-directory/)

1. In **Azure Active Directory** scegliere Applicazioni **aziendali**  >  **Nuova applicazione** nella parte superiore della pagina Tutte **le** applicazioni.
2. Nella pagina **Add an application** scegliere **Non-gallery application** o Create your own **application** se si è nella versione di anteprima di Azure Active Directory. 
3. Digitare un nome per l'applicazione e quindi assegnare l'utente nella **scheda Utenti e** gruppi.
4. Usa la **scheda Proprietà** per caricare un'icona per l'app.
5. Per assegnare un URL all'app, nella scheda **Single #A0** scegliere **Collegato** e quindi immettere un URL.
6. Scegliere **Salva**.

## <a name="create-application-collections"></a>Creare raccolte di applicazioni

È inoltre possibile creare raccolte applicazioni per gli utenti dell'organizzazione. Per istruzioni, vedere [creare raccolte nel portale App personali nel portale di Azure.](/azure/active-directory/manage-apps/access-panel-collections)