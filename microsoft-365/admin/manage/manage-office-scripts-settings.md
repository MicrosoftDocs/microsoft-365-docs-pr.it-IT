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
description: Informazioni su come gestire le Office script per gli utenti dell'organizzazione.
ms.openlocfilehash: e0cb52c4a8f48ff2310c83ffce61e08a0236ed59
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572310"
---
# <a name="manage-office-scripts-settings"></a>Gestire le impostazioni di Office Scripts

[Office consente](/office/dev/scripts)agli utenti di automatizzare le attività registrando, modificando ed eseguendo script in Excel sul Web. Office Gli script funzionano con Power Automate e gli utenti eseguono script nelle cartelle di lavoro utilizzando il connettore Excel Online (Business). Microsoft 365 amministratori possono gestire le impostazioni Office script dall'Microsoft 365 di amministrazione.

## <a name="before-you-begin"></a>Prima di iniziare

- Per gestire Office impostazioni degli script, devi essere un amministratore globale. Per ulteriori informazioni, vedere [Informazioni sui ruoli di amministratore.](../add-users/about-admin-roles.md)

- Verificare che gli utenti dell'organizzazione dispongono di una licenza valida per un piano commerciale o EDU di Microsoft 365 o Office 365 che includa l'accesso alle app desktop di Office, ad esempio uno dei piani seguenti:

    - Microsoft 365 Business Standard
    - Microsoft 365 Apps for business
    - Microsoft 365 Apps for enterprise
    - Office 365 E3
    - Office 365 E5
    - Office 365 A3
    - Office 365 A5

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a>Gestire la disponibilità Office script e la condivisione degli script

1. Nell'Microsoft 365 di amministrazione passare alla scheda **Impostazioni** \> **Impostazioni** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">organizzazione.</a>

2. Selezionare **Office script**.

3. Office Gli script sono attivati per impostazione predefinita e tutti gli utenti dell'organizzazione possono accedere e usare la funzionalità e condividere gli script. Per disattivare Office script per l'organizzazione, deselezionare la casella di controllo Consenti agli utenti di automatizzare le attività **in Excel sul web.**

4. Se in precedenza è stato disattivato Office Scripts per l'organizzazione e si desidera riattivarlo, selezionare Consenti agli utenti di **automatizzare** le attività in Excel sul web e quindi specificare chi può accedere e usare la funzionalità:

    - Per consentire a tutti gli utenti dell'organizzazione di accedere Office script, lasciare selezionato **Tutti** (impostazione predefinita).

    - Per consentire solo ai membri di un gruppo specifico di accedere e utilizzare gli script di Office, selezionare Gruppo specifico **e** quindi immettere il nome o l'alias di posta elettronica del gruppo per aggiungerlo all'elenco consenti. È possibile aggiungere un solo gruppo all'elenco consenti e deve essere uno dei tipi seguenti:
        - Microsoft 365 gruppo
        - Gruppo di distribuzione
        - Gruppo di sicurezza
        - Gruppo di sicurezza abilitato alla posta elettronica
    
        Per ulteriori informazioni sui diversi tipi di gruppi, vedere [Confronto di gruppi.](../create-groups/compare-groups.md)

5. Per consentire agli utenti con accesso Office Scripts di condividere i propri script con altri utenti dell'organizzazione, selezionare Consenti agli utenti con accesso Office Scripts di condividere i propri script con altri utenti **dell'organizzazione.** La condivisione di script all'esterno di un'organizzazione non è consentita.
 
    > [!NOTE]
    > Se in seguito si disattiva la condivisione degli script per l'organizzazione, gli utenti potranno comunque eseguire script condivisi in precedenza.
 
6. Specificare quali utenti con accesso a Office script possono condividere i propri script:
    
    - Per consentire a tutti gli utenti con accesso Office script di condividere i propri script, lasciare **selezionato Tutti** (impostazione predefinita).

    - Per consentire solo ai membri di un gruppo specifico con accesso Office Scripts di condividere i propri script, selezionare **Gruppo** specifico e quindi immettere il nome o l'alias di posta elettronica del gruppo per aggiungerlo all'elenco consenti. È possibile aggiungere un solo gruppo all'elenco consenti e deve essere uno dei tipi seguenti:
        - Microsoft 365 gruppo
        - Gruppo di distribuzione
        - Gruppo di sicurezza
        - Gruppo di sicurezza abilitato alla posta elettronica
    
        Per ulteriori informazioni sui diversi tipi di gruppi, vedere [Confronto di gruppi.](../create-groups/compare-groups.md)

7. Per consentire agli utenti di eseguire i propri script Office all'interno dei flussi di Power Automate, selezionare Consenti agli utenti con accesso Office Script di eseguire i propri script **con Power Automate**. In questo modo gli utenti possono aggiungere passaggi [del flusso con l'opzione di script Esegui Excel Online (Business) Connector.](/connectors/excelonlinebusiness) 

    - Per consentire a tutti gli utenti con accesso Office Script di utilizzare i propri script nei flussi, lasciare selezionato **Tutti** (impostazione predefinita).

    - Per consentire solo ai membri di un gruppo specifico con accesso Office Scripts di utilizzare i propri script nei flussi, selezionare **Gruppo** specifico e quindi immettere il nome o l'alias di posta elettronica del gruppo per aggiungerlo all'elenco consenti. È possibile aggiungere un solo gruppo all'elenco consenti e deve essere uno dei tipi seguenti:
        - Microsoft 365 gruppo
        - Gruppo di distribuzione
        - Gruppo di sicurezza
        - Gruppo di sicurezza abilitato alla posta elettronica

        Per ulteriori informazioni sui diversi tipi di gruppi, vedere [Confronto di gruppi.](../create-groups/compare-groups.md)

    - Per ulteriori informazioni sull'utilizzo Office script con Power Automate, vedere [Run Office Scripts with Power Automate](/office/dev/scripts/develop/power-automate-integration).

8. Selezionare **Salva**.

    L'applicazione delle modifiche alle impostazioni Office script può richiedere fino a 48 ore.

## <a name="next-steps"></a>Passaggi successivi

Poiché Office Scripts funziona con Power Automate, è consigliabile esaminare i criteri di prevenzione della perdita dei dati (DLP) esistenti per garantire che i dati dell'organizzazione rimangano protetti mentre gli utenti usano Office Script. Per ulteriori informazioni, vedere Criteri di [prevenzione della perdita dei dati (DLP).](/power-automate/prevent-data-loss)

## <a name="related-content"></a>Contenuto correlato

[Office documentazione tecnica script (pagina](/office/dev/scripts/) di collegamento)\
[Introduzione agli Office script in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (articolo)\
[Condivisione Office script in Excel per il Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (articolo)\
[Registrare, modificare e creare Office script in Excel sul web](/office/dev/scripts/tutorials/excel-tutorial) (articolo)
