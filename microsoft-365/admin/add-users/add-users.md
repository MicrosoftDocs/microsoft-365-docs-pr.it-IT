---
title: Aggiungere utenti e assegnare licenze
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365_Setup
- Adm_O365_TOC
ms.custom:
- okr_smb
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Informazioni su come aggiungere utenti e assegnare licenze a Microsoft 365 contemporaneamente.
ms.date: 07/01/2020
ms.openlocfilehash: 97b7118f4052d4ab4e0ffe8ecec96f32e4042108
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2021
ms.locfileid: "52024014"
---
# <a name="add-users-and-assign-licenses-at-the-same-time"></a>Aggiungere utenti e assegnare licenze contemporaneamente

Per poter accedere a [Microsoft 365 per le aziende](https://www.microsoft.com/microsoft-365/business), è necessario che ogni persona del team abbia un account utente. Il modo più semplice per aggiungere account utente consiste nell'aggiungerli uno alla volta nell'interfaccia di amministrazione di Microsoft 365. Dopo questo passaggio, gli utenti hanno le licenze di Microsoft 365, le credenziali di accesso e le cassette postali di Microsoft 365.

## <a name="before-you-begin"></a>Prima di iniziare

Per aggiungere utenti e assegnare le licenze è necessario essere un amministratore globale, delle licenze o degli utenti. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).

## <a name="watch-add-users-in-the-admin-center"></a>Guardare: Aggiungere utenti nell'interfaccia di amministrazione

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]

> [!NOTE]
> I passaggi usati nel video mostrano un punto di partenza diverso per l'aggiunta di utenti, ma i passaggi rimanenti sono gli stessi della procedura seguente.

## <a name="add-users-one-at-a-time"></a>Aggiungere utenti uno alla volta

 ::: moniker range="o365-worldwide"

1. Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.

::: moniker-end 

2. Andare a **Utenti**  >  **Utenti attivi** e selezionare **Aggiungi un utente**.
3. Nel riquadro **Configura le impostazioni di base**, inserire le informazioni di base dell'utente e quindi selezionare **Avanti**.
    - **Nome** Immettere il nome e il cognome, il nome visualizzato e il nome utente.
    - **Dominio** Scegliere il dominio per l'account utente. Se ad esempio il nome utente è Pio e il suo dominio è contoso.com, questo utente eseguirà l'accesso digitando pio@contoso.com.
    - **Impostazioni password** Scegliere se usare la password creata automaticamente o creare una password complessa per l'utente.
    - L'utente dovrà cambiare la password dopo 90 giorni. Oppure si può selezionare **Chiedi all'utente di cambiare la password al primo accesso**.
    - Scegliere se si vuole  inviare la password tramite posta elettronica quando l'utente viene aggiunto.
4. Nel riquadro **Assegna licenze di prodotto**, selezionare la posizione e la licenza appropriata per l'utente. Se non ci sono licenze disponibili, è sempre possibile aggiungere un utente e acquistare licenze aggiuntive. Espandere **App** e selezionare o deselezionare le app per cui l'utente ha una licenza. Selezionare **Avanti**.
5. Nel riquadro **Impostazioni facoltative** espandere **Ruoli** per rendere l'utente amministratore. Espandere **informazioni profilo** per aggiungere altre informazioni sull'utente.
6. Selezionare **Avanti**, esaminare le impostazioni del nuovo utente, apportare le modifiche desiderate, quindi selezionare **Completa l'aggiunta**, quindi **Chiudi**.

## <a name="add-multiple-users-at-the-same-time"></a>Aggiungere più utenti contemporaneamente

Per aggiungere più utenti contemporaneamente, è possibile usare uno dei metodi seguenti:

- **Usare un foglio di calcolo per aggiungere persone in blocco.** Vedere [Aggiungere più utenti contemporaneamente](../../enterprise/add-several-users-at-the-same-time.md).
- **Automatizzare il processo di aggiunta di account e assegnazione delle licenze.** Vedere[Creare account utente con Microsoft 365 PowerShell](../../enterprise/create-user-accounts-with-microsoft-365-powershell.md). Questo metodo è adeguato se si ha già familiarità con i cmdlet di Windows PowerShell.
- **Si usa ActiveDirectory?** [Configurare la sincronizzazione della directory per Microsoft 365](../../enterprise/set-up-directory-synchronization.md). Usare Azure AD Connect per replicare gli account utente di Active Directory (e altri oggetti Active Directory) in Microsoft 365. Con la sincronizzazione vengono aggiunti solo gli account utente. Sarà necessario assegnare le licenze agli utenti sincronizzati perché possano usare la posta elettronica e altre app di Office.
- **Si sta migrando da Exchange?** Vedere[Modalità di migrazione della posta elettronica a Office 365](/Exchange/mailbox-migration/mailbox-migration). Quando si esegue la migrazione di più cassette postali a Microsoft 365 usando il metodo di migrazione completa, a fasi o ibrida di Exchange, gli utenti vengono aggiunti automaticamente nell'ambito della migrazione. Con la migrazione vengono aggiunti solo gli account utente. Sarà necessario assegnare le licenze agli utenti perché possano usare la posta elettronica e altre app di Office. Se non si assegna una licenza a un utente, la cassetta postale viene disabilitata allo scadere del periodo di prova di 30 giorni. Informazioni su come[assegnare le licenze agli utenti](../manage/assign-licenses-to-users.md)nell'interfaccia di amministrazione di Microsoft 365.

## <a name="next-steps"></a>Passaggi successivi

Dopo aver aggiunto un utente, si riceve una notifica tramite posta elettronica da Microsoft. con l'ID utente e la password della persona, che potrà quindi accedere a Microsoft 365. Usare il consueto processo per la comunicazione di nuove password. Condividere con loro la [guida introduttiva per i dipendenti](../../business-video/employee-quick-setup.md), ricca di informazioni su come, ad esempio, [scaricare e installare le app di Office in un PC o un Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) e [configurare le app di Office e la posta elettronica in un dispositivo mobile](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).

## <a name="related-content"></a>Contenuti correlati

[Aggiungere un nuovo dipendente a Microsoft 365](add-new-employee.md) (articolo)\
[Aggiungere più utenti contemporaneamente a Microsoft 365](../../enterprise/add-several-users-at-the-same-time.md) (articolo)\
[Ripristinare un utente in Microsoft 365](restore-user.md) (articolo)\
[Assegnare licenze agli utenti](../manage/assign-licenses-to-users.md) (articolo)\
[Eliminare un utente dall'organizzazione](delete-a-user.md) (articolo)