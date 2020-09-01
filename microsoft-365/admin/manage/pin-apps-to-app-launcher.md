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
description: In qualità di amministratore globale è possibile aggiungere fino a tre app all'icona di avvio delle app degli utenti.
ms.openlocfilehash: d9b95a20f332a9b1f2f6b0ebba28a70c58677b58
ms.sourcegitcommit: 87449335d9a1124ee82fa2e95e4745155a95a62f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/29/2020
ms.locfileid: "47310876"
---
# <a name="pin-apps-to-your-users-app-launcher"></a>Aggiungere app all'icona di avvio delle app degli utenti

È possibile utilizzare i controlli nel portale di Azure Active Directory per aggiungere fino a tre app a Office.com e l'icona di avvio delle app per tutti gli utenti dell'organizzazione. È anche possibile organizzare gruppi di applicazioni. Qualsiasi applicazione aggiunta può successivamente essere sbloccata dall'utente in qualsiasi momento. Per aggiungere un'app per gli utenti, è necessario essere un amministratore dell'applicazione cloud o un amministratore dell'applicazione in Azure Active Directory o un amministratore globale in Office 365. Per ulteriori informazioni sui ruoli di amministratore, vedere ruoli [di amministratore in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) e [ruoli di amministratore in Microsoft 365](../add-users/about-admin-roles.md). 

Per ulteriori informazioni sull'icona di avvio delle app e Office.com, vedere [Meet the App Launcher](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) and [updates to Office.com and the-Office 365 App Launcher](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) Blog article.

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a>Utilizzare il portale di Azure Active Directory per aggiungere le app

1. Accedere all'interfaccia di amministrazione di Microsoft 365 all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .
2. Nella barra di spostamento sinistra fare clic su **Mostra tutto**e in interfaccia di **Amministrazione**, scegliere **Azure Active Directory**.
3. In **Azure Active Directory**, scegliere **Enterprise applications**  >  **impostazioni utente**applicazioni Enterprise.
4. Nella sezione **impostazioni di Office 365** scegliere **Aggiungi applicazione**.
5. Scegliere le applicazioni che si desidera aggiungere all'icona di avvio delle app degli utenti e quindi fare clic su **Aggiungi**.

:::image type="content" source="../../media/add-apps.png" alt-text="Microsoft 365 Settings to pin Apps.":::

### <a name="pin-a-custom-app"></a>Aggiungere un'app personalizzata

> [!NOTE]
> L'interfaccia utente indicherà se è necessario acquistare altre licenze di Azure ad per l'utilizzo di questa funzionalità. Per ulteriori informazioni, vedere [Azure Active Directory pricing](https://azure.microsoft.com/pricing/details/active-directory/).

1. In **Azure Active Directory**, scegliere **applicazioni Enterprise**  >  **nuova applicazione** nella parte superiore della pagina **tutte le applicazioni** .
2. Nella pagina **Aggiungi applicazione** scegliere **applicazione non raccolta** o **creare un'applicazione personalizzata** se si è nella versione di anteprima di Azure Active Directory. 
3. Digitare un nome per l'applicazione e quindi assegnare l'utente nella scheda **utenti e gruppi** .
4. Utilizzare la scheda **Proprietà** per caricare un'icona per l'app.
5. Per assegnare un URL all'app, nella scheda **Single Sign-on** scegliere **collegato** e quindi immettere un URL.
6. Scegliere **Salva**.

## <a name="create-application-collections"></a>Creare raccolte applicazioni

È inoltre possibile creare raccolte applicazioni per gli utenti dell'organizzazione. Per istruzioni, vedere [create Collections on the My Apps Portal nel portale di Azure](https://docs.microsoft.com/azure/active-directory/manage-apps/access-panel-collections).