---
title: Gestire le impostazioni di Office Scripts
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Informazioni su come gestire le impostazioni degli script di Office per gli utenti dell'organizzazione.
ms.openlocfilehash: 75d0a9d9e98652fc11eab7e8a7d6c826be031f6e
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058424"
---
# <a name="manage-office-scripts-settings"></a>Gestire le impostazioni di Office Scripts

Gli script di Office consentono agli utenti di automatizzare le attività registrando, modificando ed eseguendo script in Excel sul Web. Gli script di Office funzionano con Power Automate e gli utenti eseguono script nelle cartelle di lavoro utilizzando il connettore Di Excel Online (Business). Gli amministratori di Microsoft 365 possono gestire le impostazioni degli script di Office dall'interfaccia di amministrazione di Microsoft 365.

## <a name="before-you-begin"></a>Informazioni preliminari

- Per gestire le impostazioni degli script di Office, è necessario essere un amministratore globale. Per ulteriori informazioni, vedere [Informazioni sui ruoli di amministratore.](../add-users/about-admin-roles.md)

- Assicurarsi che gli utenti dell'organizzazione hanno una licenza valida per un piano commerciale o EDU di Microsoft 365 o Office 365 che include l'accesso alle app desktop di Office, ad esempio uno dei piani seguenti:

    - Microsoft 365 Business Standard
    - Microsoft 365 Apps for business
    - Microsoft 365 Apps for enterprise
    - Office 365 E3
    - Office 365 E5
    - Office 365 A3
    - Office 365 A5

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a>Gestire la disponibilità degli script di Office e la condivisione degli script

1. Nell'interfaccia di amministrazione di Microsoft 365 passare alla scheda **Impostazioni** \> **organizzazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Servizi.</a>

2. Selezionare **Script di Office.**

3. Gli script di Office sono attivati per impostazione predefinita e tutti gli utenti dell'organizzazione possono accedere e utilizzare la funzionalità e condividere gli script. Per disattivare gli script di Office per l'organizzazione, deselezionare la casella di controllo Consenti agli utenti di automatizzare le attività **in Excel sul Web.**

4. Se in precedenza sono stati disattivati gli script di Office per l'organizzazione e si desidera riattivarlo, selezionare Consenti agli utenti di **automatizzare** le attività in Excel sul Web e quindi specificare chi può accedere e utilizzare la funzionalità:

    - Per consentire a tutti gli utenti dell'organizzazione di accedere e utilizzare gli script di Office, lasciare selezionato **Tutti** (impostazione predefinita).

    - Per consentire solo ai membri di un gruppo specifico di accedere e utilizzare gli script di Office, selezionare Gruppo specifico **e** quindi immettere il nome o l'alias di posta elettronica del gruppo per aggiungerlo all'elenco Consenti. È possibile aggiungere un solo gruppo all'elenco Consenti e deve essere uno dei tipi seguenti:
        - Gruppo di Microsoft 365
        - Gruppo di distribuzione
        - Gruppo di sicurezza
        - Gruppo di sicurezza abilitato alla posta elettronica
    
        Per ulteriori informazioni sui diversi tipi di gruppi, vedere [Confrontare i gruppi.](../create-groups/compare-groups.md)

5. Per consentire agli utenti con accesso agli script di Office di condividere i propri script con altri utenti dell'organizzazione, selezionare Consenti agli utenti con accesso agli script di Office di condividere i propri script con altri utenti **dell'organizzazione.** La condivisione di script all'esterno di un'organizzazione non è consentita.
 
    > [!NOTE]
    > Se successivamente si disattiva la condivisione degli script per l'organizzazione, gli utenti potranno comunque eseguire script condivisi in precedenza.
 
6. Specificare quali utenti con accesso agli script di Office possono condividere i propri script:
    
    - Per consentire a tutti gli utenti con accesso agli script di Office di condividere i propri script, lasciare selezionato **Tutti** (impostazione predefinita).

    - Per consentire solo ai membri di un gruppo specifico con accesso agli script di Office di condividere i propri script, selezionare Gruppo specifico **e** quindi immettere il nome o l'alias di posta elettronica del gruppo per aggiungerlo all'elenco Consenti. È possibile aggiungere un solo gruppo all'elenco Consenti e deve essere uno dei tipi seguenti:
        - Gruppo di Microsoft 365
        - Gruppo di distribuzione
        - Gruppo di sicurezza
        - Gruppo di sicurezza abilitato alla posta elettronica
    
        Per ulteriori informazioni sui diversi tipi di gruppi, vedere [Confrontare i gruppi.](../create-groups/compare-groups.md)

7. Per consentire agli utenti di eseguire i propri script di Office all'interno dei flussi di Power Automate, selezionare Consenti agli utenti con accesso agli script di Office di eseguire i **propri script con Power Automate.** Ciò consente agli utenti di aggiungere passaggi del flusso con l'opzione di script Esegui del connettore [di Excel Online (Business).](/connectors/excelonlinebusiness) 

    - Per consentire a tutti gli utenti con accesso agli script di Office di utilizzare i propri script nei flussi, lasciare selezionato **Tutti** (impostazione predefinita).

    - Per consentire solo ai membri di un gruppo specifico con accesso agli script di Office di utilizzare i propri script nei flussi, selezionare **Gruppo** specifico e quindi immettere il nome o l'alias di posta elettronica del gruppo per aggiungerlo all'elenco Consenti. È possibile aggiungere un solo gruppo all'elenco Consenti e deve essere uno dei tipi seguenti:
        - Gruppo di Microsoft 365
        - Gruppo di distribuzione
        - Gruppo di sicurezza
        - Gruppo di sicurezza abilitato alla posta elettronica

        Per ulteriori informazioni sui diversi tipi di gruppi, vedere [Confrontare i gruppi.](../create-groups/compare-groups.md)

    - Per ulteriori informazioni sull'utilizzo degli script di Office con Power Automate, incluso l'impatto dei criteri di prevenzione della perdita dei dati, vedere Eseguire script di [Office con Power Automate.](/office/dev/scripts/develop/power-automate-integration)

8. Selezionare **Salva**.

    L'applicazione delle modifiche alle impostazioni degli script di Office può richiedere fino a 48 ore.

## <a name="next-steps"></a>Passaggi successivi

Poiché gli script di Office funzionano con Power Automate, è consigliabile esaminare i criteri di prevenzione della perdita dei dati esistenti per garantire che i dati dell'organizzazione rimangano protetti mentre gli utenti utilizzano gli script di Office. Per ulteriori informazioni, vedere Criteri di prevenzione della perdita [dei dati (DLP).](/power-automate/prevent-data-loss)

## <a name="related-content"></a>Contenuti correlati

[Documentazione tecnica degli script di Office](/office/dev/scripts/) (pagina di collegamento)\
[Introduzione agli script di Office in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (articolo)\
[Condivisione di script di Office in Excel per il Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (articolo)\
[Registrare, modificare e creare script di Office in Excel sul Web](/office/dev/scripts/tutorials/excel-tutorial) (articolo)
