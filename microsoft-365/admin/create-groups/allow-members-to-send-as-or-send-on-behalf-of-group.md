---
title: Consenti ai membri di inviare messaggi o Invia per conto di un gruppo
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: Informazioni su come consentire ai membri di inviare messaggi di posta elettronica come gruppo di Microsoft 365 o di inviare messaggi di posta elettronica per conto di un gruppo di Microsoft 365.
ms.openlocfilehash: ce4527321468ee01864177fc1a607fab6a474481
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049388"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a>Consenti ai membri di inviare messaggi o Invia per conto di un gruppo

Un membro di un gruppo di Microsoft 365 a cui sono state concesse le autorizzazioni **Invia come** o **Invia per conto** di può inviare messaggi di posta elettronica come gruppo o per conto del gruppo. In questo argomento viene illustrato in che modo un amministratore può impostare queste autorizzazioni.
  
Ad esempio, se Megan Bowen fa parte del gruppo **Training** Microsoft 365 e ha l'autorizzazione **Invia come** per il gruppo, se invia un messaggio di posta elettronica come gruppo, avrà l'aspetto del gruppo di **formazione** inviato al messaggio di posta elettronica. 
  
L'autorizzazione **Invia per conto** di consente a un utente di inviare messaggi di posta elettronica per conto di un gruppo di Microsoft 365. Ad esempio, se Alex Wilber è parte del gruppo **Marketing** Microsoft 365 e ha l'autorizzazione **Invia per conto** di e invia un messaggio di posta elettronica come gruppo, il messaggio di posta elettronica è simile a quello inviato da **Alex Wilber per conto del marketing**.

> [!IMPORTANT]
> È possibile configurare **Invia come** o **Invia per conto** di un utente specificato, ma non di entrambi. Se si configurano entrambi, il valore predefinito sarà **Send As**.

> [!TIP]
> Vedere [inviare messaggi di posta elettronica da o per conto di un gruppo di Microsoft 365](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx) per informazioni su come utilizzare Outlook e Outlook sul Web per inviare messaggi di posta elettronica da un gruppo.
    
## <a name="allow-members-to-send-email-as-a-group"></a>Consenti ai membri di inviare messaggi di posta elettronica come gruppo

In questa sezione viene descritto come consentire agli utenti di inviare messaggi di posta elettronica come gruppo nell'interfaccia di [amministrazione di Exchange](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.
  
1. Nell'interfaccia <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">di amministrazione di Exchange</a>, accedere a **gruppi**di **destinatari** \> .
    
2. Selezionare **modifica**![icona](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) gruppo modifica sul gruppo che si desidera consentire agli utenti di inviare.   
    
3. Selezionare **delega gruppo**.
    
4. Nella sezione **Invia come** selezionare il **+** segno per aggiungere gli utenti che si desidera inviare come gruppo. 
    
    ![Selezionare il segno più per aggiungere gli utenti che si desidera inviare come gruppo Microsoft 365](../../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. Digitare per cercare o selezionare un utente dall'elenco. Fare clic su **OK** e su **Salva**.
    
    ![Digitare per cercare o selezionare un utente dall'elenco](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a>Consenti ai membri di inviare messaggi di posta elettronica per conto di un gruppo

In questa sezione viene descritto come consentire agli utenti di inviare messaggi di posta elettronica per conto di un gruppo nell'interfaccia di amministrazione di Exchange (EAC) in Exchange Online.
  
1. Nell'interfaccia <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">di amministrazione di Exchange</a>, accedere a **gruppi**di **destinatari** \> .
    
2. Selezionare **modifica** ![icona](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) di modifica gruppo sul gruppo che si desidera consentire agli utenti di inviare. 
    
3. Selezionare **delega gruppo**.
    
4. Nella sezione Invia per conto di selezionare il **+** segno per aggiungere gli utenti che si desidera inviare come gruppo. 
    
    ![Selezionare il segno più per aggiungere gli utenti che si desidera inviare come gruppo Microsoft 365](../../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. Digitare per cercare o selezionare un utente dall'elenco. Fare clic su **OK** e su **Salva**.
    
    ![Digitare per cercare o selezionare un utente dall'elenco](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a>Articoli correlati

[Altre informazioni sui gruppi di Microsoft 365](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Add-RecipientPermission](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[Set-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616189)
