---
title: Gestire le impostazioni degli script di Office
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
ms.openlocfilehash: 12a80f277f6d17a8e7f5228f6948e70b7a93be11
ms.sourcegitcommit: 97ef8f846939c3d31bb0638edf07bb89463ace0b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/28/2020
ms.locfileid: "47300835"
---
# <a name="manage-office-scripts-settings"></a>Gestire le impostazioni degli script di Office

Gli script di Office consentono agli utenti di automatizzare le attività tramite la registrazione, la modifica e l'esecuzione di script in Excel sul Web. Office Scripts è compatibile con Power automatizzate e gli utenti eseguono script nelle cartelle di lavoro utilizzando il connettore Excel online (business). Microsoft 365 admins è in grado di gestire le impostazioni degli script di Office dall'interfaccia di amministrazione di Microsoft 365.

## <a name="before-you-begin"></a>Prima di iniziare

- Per gestire le impostazioni degli script di Office, è necessario essere un amministratore globale. Per ulteriori informazioni, vedere [informazioni sui ruoli di amministratore](../add-users/about-admin-roles.md).

- Verificare che gli utenti dell'organizzazione dispongano di una licenza valida per un piano commerciale o EDU di Microsoft 365 o Office 365 che includa l'accesso alle app desktop di Office, ad esempio uno dei seguenti piani:

    - Microsoft 365 Business Standard
    - Microsoft 365 Apps for business
    - Microsoft 365 Apps for enterprise
    - Office 365 E3
    - Office 365 E5
    - Office 365 A3
    - Office 365 A5

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a>Gestire la disponibilità degli script di Office e la condivisione degli script

1. Nell'interfaccia di amministrazione di Microsoft 365 passare alla scheda **Impostazioni** \> **org** Settings \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> .

2. Selezionare **script di Office**.

3. Gli script di Office sono attivati per impostazione predefinita e tutti gli utenti dell'organizzazione possono accedere e usare la funzionalità e condividere gli script. Per disattivare gli script di Office per l'organizzazione, deselezionare la casella di controllo **Consenti agli utenti di automatizzare le attività in Excel sul Web** .

4. Se in precedenza sono stati disattivati gli script di Office per l'organizzazione e si desidera riattivarla, selezionare **Consenti agli utenti di automatizzare le attività in Excel sul Web**e quindi specificare chi può accedere e usare la caratteristica:

    - Per consentire a tutti gli utenti dell'organizzazione di accedere e utilizzare gli script di Office, lasciare **tutti** (impostazione predefinita) selezionati. 

    - Per consentire l'accesso e l'utilizzo di script di Office solo ai membri di un gruppo specifico, selezionare **gruppo specifico**e quindi immettere il nome o l'alias di posta elettronica del gruppo per aggiungerlo all'elenco Consenti. È possibile aggiungere un solo gruppo all'elenco Consenti e deve essere uno dei tipi seguenti:
        - Gruppo Microsoft 365
        - Gruppo di distribuzione
        - Gruppo di sicurezza
        - Gruppo di sicurezza abilitato alla posta elettronica
    
        Per ulteriori informazioni sui diversi tipi di gruppi, vedere [confronto di gruppi](../create-groups/compare-groups.md).

5. Per consentire agli utenti con accesso agli script di Office di condividere i propri script con altri membri dell'organizzazione, selezionare **Consenti agli utenti di accedere agli script di Office di condividere i propri script con altri membri dell'organizzazione**. La condivisione di script all'esterno di un'organizzazione non è consentita.
 
    > [!NOTE]
    > Se in seguito si disattiva la condivisione degli script per l'organizzazione, gli utenti potranno comunque eseguire script condivisi in precedenza.
 
6. Specificare gli utenti con accesso agli script di Office che possono condividere gli script seguenti:
    
    - Per consentire a tutti gli utenti con accesso agli script di Office di condividere gli script, lasciare **tutti** (impostazione predefinita) selezionati.

    - Per consentire solo ai membri di un gruppo specifico di accedere agli script di Office di condividere gli script, selezionare **gruppo specifico**e quindi immettere il nome o l'alias di posta elettronica del gruppo per aggiungerlo all'elenco Consenti. È possibile aggiungere un solo gruppo all'elenco Consenti e deve essere uno dei tipi seguenti:
        - Gruppo Microsoft 365
        - Gruppo di distribuzione
        - Gruppo di sicurezza
        - Gruppo di sicurezza abilitato alla posta elettronica
    
        Per ulteriori informazioni sui diversi tipi di gruppi, vedere [confronto di gruppi](../create-groups/compare-groups.md).

7. Selezionare **Salva**.

    Per rendere effettive le modifiche apportate alle impostazioni di Office script, possono essere necessarie fino a 48 ore.

## <a name="next-steps"></a>Passaggi successivi

Poiché Office scripts funziona con Power automatizzate, è consigliabile esaminare i criteri di prevenzione della perdita di dati (DLP, Data Loss Prevention) esistenti per garantire la protezione dei dati dell'organizzazione mentre gli utenti utilizzano gli script di Office. Per ulteriori informazioni, vedere [criteri di prevenzione della perdita di dati (DLP)](/power-automate/prevent-data-loss).

## <a name="related-content"></a>Contenuto correlato

[Documentazione tecnica di Office scripts](/office/dev/scripts/) (pagina collegamento) \
[Introduzione agli script di Office in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (articolo) \
[Condivisione degli script di Office in Excel per il Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (articolo) \
[Registrare, modificare e creare script di Office in Excel sul Web](/office/dev/scripts/tutorials/excel-tutorial) (articolo)