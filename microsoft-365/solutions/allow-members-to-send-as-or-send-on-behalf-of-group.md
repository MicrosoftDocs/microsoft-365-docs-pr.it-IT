---
title: Consentire ai membri di inviare come o inviare per conto di un gruppo
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: Informazioni su come consentire ai membri di inviare messaggi di posta elettronica come gruppo di Microsoft 365 o per conto di un gruppo di Microsoft 365.
ms.openlocfilehash: 6dff559eceec1b719f31d577d7fff8f604636a47
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663584"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a>Consentire ai membri di inviare come o inviare per conto di un gruppo

Un membro di un gruppo di Microsoft  365 a cui sono state concesse le autorizzazioni Invia come o Invia per conto di può inviare messaggi di posta elettronica come gruppo o per conto del gruppo.  In questo articolo viene illustrato in che modo un amministratore globale o di Exchange può impostare queste autorizzazioni.
  
Ad esempio, se Megan Bowen fa parte del gruppo Formazione  **di** Microsoft 365 e dispone delle autorizzazioni Invia come  per il gruppo, se invia un messaggio di posta elettronica come gruppo, avrà l'aspetto che il gruppo Formazione ha inviato il messaggio di posta elettronica. 
  
**L'autorizzazione Invia per conto di** consente a un utente di inviare messaggi di posta elettronica per conto di un gruppo di Microsoft 365. Ad esempio, se Alex Wilber fa parte del gruppo **Marketing**  di Microsoft 365 e dispone delle autorizzazioni Invia per conto di e invia un messaggio di posta elettronica come gruppo, il messaggio di posta elettronica sembra essere stato inviato da **Alex Wilber** per conto di Marketing.

> [!IMPORTANT]
> È possibile configurare **Invia come** o Invia per **conto di** un determinato utente, ma non entrambi. Se si configurano entrambi, per impostazione predefinita verrà **utilizzato Invia come.**

> [!TIP]
> Vedere Inviare messaggi di posta elettronica da o per conto di un gruppo di [Microsoft 365](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) per informazioni su come usare Outlook e Outlook sul Web per inviare messaggi di posta elettronica da un gruppo.
    
## <a name="allow-members-to-send-email-as-a-group"></a>Consentire ai membri di inviare messaggi di posta elettronica come gruppo

In questa sezione viene illustrato come consentire agli utenti di inviare messaggi di posta elettronica come gruppo nell'interfaccia di amministrazione di [Exchange](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.
  
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Nell'interfaccia di amministrazione di Exchange,</a>accedere a Gruppi **di** \> **destinatari.**
    
2. Selezionare **l'icona** Modifica gruppo nel gruppo che si desidera consentire ![ agli utenti di ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) inviare come.   
    
3. Selezionare **delega gruppo**.
    
4. Nella sezione **Invia come** selezionare il segno per aggiungere gli utenti che si **+** desidera inviare come gruppo. 
    
    ![Screenshot della finestra di dialogo Invia come](../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. Digitare per cercare o selezionare un utente dall'elenco. Selezionare **OK** e **Salva.**
    
    ![Digitare per cercare o selezionare un utente dall'elenco](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a>Consentire ai membri di inviare messaggi di posta elettronica per conto di un gruppo

In questa sezione viene illustrato come consentire agli utenti di inviare messaggi di posta elettronica per conto di un gruppo nell'interfaccia di amministrazione di Exchange (EAC) in Exchange Online.
  
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Nell'interfaccia di amministrazione di Exchange,</a>accedere a Gruppi **di** \> **destinatari.**
    
2. Selezionare **l'icona** Modifica gruppo nel gruppo che si desidera consentire ![ agli utenti di ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) inviare come. 
    
3. Selezionare **delega gruppo**.
    
4. Nella sezione Invia per conto di selezionare il segno per aggiungere gli utenti che **+** si desidera inviare come gruppo. 
    
    ![Screenshot della finestra di dialogo Invia per conto di](../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. Digitare per cercare o selezionare un utente dall'elenco. Selezionare **OK** e **Salva.**
    
    ![Digitare per cercare o selezionare un utente dall'elenco](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a>Articoli correlati

[Procedura dettagliata per la pianificazione della governance della collaborazione](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Creare il piano di governance della collaborazione](collaboration-governance-first.md)

[Altre informazioni sui gruppi di Microsoft 365](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Add-RecipientPermission](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[Set-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616189)
