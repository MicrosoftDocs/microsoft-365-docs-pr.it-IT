---
title: Criteri uscita dell'infrastruttura per la gestione dei dispositivi mobili
description: Microsoft 365 Enterprise include la gestione dei dispositivi mobili tramite Microsoft Intune. Esaminare i requisiti e i prerequisiti, configurare Intune utilizzando la risorsa di Azure Active Directory, registrare i dispositivi iOS, macOS, Android e Windows, distribuire le app, creare un profilo di configurazione, utilizzare criteri di conformità e abilitare l'accesso condizionale per dispositivi mobili gestione dei dispositivi con Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365 Documentation, gestione dei dispositivi mobili, Intune
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2019
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: 14f216fe352d9108fe69028731f4c94dfb9d19f7
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291233"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a>Criteri uscita dell'infrastruttura per la gestione dei dispositivi mobili

![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

*Ciò si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

Verificare che la configurazione soddisfi i seguenti requisiti per l'infrastruttura di gestione dei dispositivi mobili.

- Intune è configurato, insieme alla creazione di utenti e gruppi di Azure AD per applicare le regole dell'organizzazione per i dispositivi.
- Sono stati registrati dispositivi in Intune in modo che i dispositivi possano ricevere i criteri creati dall'utente.
- Le app vengono aggiunte ai dispositivi cosicché gli utenti possano accedere ai servizi cloud Microsoft 365 dell'organizzazione, ad esempio Exchange Online e SharePoint Online.
- Le funzionalità e le impostazioni sono configurate e applicate ai dispositivi tramite gli utenti e i gruppi di Azure AD creati dall'utente; tra le altre cose, sono incluse l'attivazione dell'antivirus e la limitazione di app specifiche.
- Sono presenti criteri di conformità che richiedono un firewall o una lunghezza della password specifici su un dispositivo. Se i dispositivi non sono conformi, l'accesso condizionato blocca l'accesso ai dati dell'organizzazione.



## <a name="results-and-next-steps"></a>Risultati e passaggi successivi

I dispositivi vengono registrati in Intune e configurati con i criteri corretti.

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| Se si seguono le fasi per la distribuzione end-to-end di Microsoft 365 Enterprise, la fase successiva è la [protezione delle informazioni](infoprotect-infrastructure.md). |
