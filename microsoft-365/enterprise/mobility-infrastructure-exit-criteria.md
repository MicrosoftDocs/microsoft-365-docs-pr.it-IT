---
title: Criteri di uscita del dispositivo mobile management dell'infrastruttura
description: Microsoft Enterprise 365 include la gestione di dispositivi mobili utilizzando Microsoft Intune. Esaminare i requisiti e prerequisiti, impostare Intune mediante le risorse di Azure Active Directory, registrare iOS, Mac OS, Android e Windows dispositivi, distribuire apps, creare un profilo di configurazione, utilizzare criteri di conformità e consentire l'accesso condizionale per dispositivi mobili gestione dei dispositivi con Microsoft 365 Enterprise.
keywords: Documentazione Microsoft 365 Microsoft 365 Microsoft 365 Enterprise, la gestione dei dispositivi mobili, Intune
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/10/2018
ms.topic: article
audience: ITPro
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
ms.custom: microsoft-intune
ms.openlocfilehash: b511052698f42a07df5fc25aeaad7fc7f00c2a6e
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868450"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a>Criteri di uscita del dispositivo mobile management dell'infrastruttura

![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

*Ciò vale per le versioni di Microsoft Enterprise 365 E3 ed E5*

Prima di procedere alla fase successiva del processo di distribuzione, assicurarsi che la configurazione soddisfi i requisiti seguenti per l'infrastruttura di gestione di dispositivi mobili.

- Intune è configurato, insieme alla creazione di utenti e gruppi di Azure AD per applicare le regole dell'organizzazione per i dispositivi.
- Sono stati registrati dispositivi in Intune in modo che i dispositivi possano ricevere i criteri creati dall'utente.
- Le app vengono aggiunte ai dispositivi cosicché gli utenti possano accedere ai servizi cloud Microsoft 365 dell'organizzazione, ad esempio Exchange Online e SharePoint Online.
- Le funzionalità e le impostazioni sono configurate e applicate ai dispositivi tramite gli utenti e i gruppi di Azure AD creati dall'utente; tra le altre cose, sono incluse l'attivazione dell'antivirus e la limitazione di app specifiche.
- Sono presenti criteri di conformità che richiedono un firewall o una lunghezza della password specifici su un dispositivo. Se i dispositivi non sono conformi, l'accesso condizionato blocca l'accesso ai dati dell'organizzazione.

## <a name="next-phase"></a>Fase successiva

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| La fase successiva del processo di distribuzione end-to-end per Microsoft 365 Enterprise è [la protezione delle informazioni](infoprotect-infrastructure.md). |
