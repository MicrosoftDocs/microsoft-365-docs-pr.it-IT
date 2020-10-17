---
title: Automatizzare le licenze e l'appartenenza ai gruppi per l'ambiente di testing di Microsoft 365 per l'organizzazione
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Configurare la gestione delle licenze basate su gruppo e l'appartenenza a gruppi dinamici nell'ambiente di testing di Microsoft 365 per l'organizzazione.
ms.openlocfilehash: d770e7be3b0b55855f1fee26a45d55260c3074cb
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487577"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a>Automatizzare le licenze e l'appartenenza ai gruppi per l'ambiente di testing di Microsoft 365 per l'organizzazione

*Questa guida del laboratorio di testing può essere utilizzata solo per Microsoft 365 per gli ambienti di testing dell'organizzazione.*

La gestione delle licenze basate su gruppo assegna o rimuove automaticamente le licenze per un account utente basato sull'appartenenza a un gruppo. L'appartenenza a un gruppo dinamico aggiunge o rimuove membri a un gruppo in base alle proprietà degli account utente, ad esempio **reparto** o **paese**. In questo articolo vengono illustrati sia l'aggiunta che la rimozione dei membri del gruppo nell'ambiente di testing di Microsoft 365 per l'organizzazione.

La configurazione delle licenze automatiche e l'appartenenza a gruppi dinamici nell'ambiente di testing di Microsoft 365 per l'organizzazione implica due fasi:

- [Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: configurare e testare l'appartenenza a gruppi dinamici e la gestione automatica delle licenze](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Per una mappa visiva su tutti gli articoli della guida del laboratorio di testing di Microsoft 365 for Enterprise, accedere a [microsoft 365 per la guida dello stack del laboratorio di testing dell'organizzazione](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione

Se si desidera testare solo la licenza automatizzata e l'appartenenza al gruppo in modo semplice con i requisiti minimi, seguire le istruzioni contenute in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se si desidera testare la licenza automatizzata e l'appartenenza a un gruppo in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testing Automatic Licensing and Group Membership non richiede l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS). È disponibile come opzione in modo che sia possibile testare la licenza automatizzata e l'appartenenza ai gruppi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>Fase 2: configurare e testare l'appartenenza a gruppi dinamici e la gestione automatica delle licenze

Innanzitutto, creare un nuovo gruppo denominato Sales e aggiungere una regola di appartenenza a un gruppo dinamico in modo che gli account utente con il **reparto** impostato su **vendite** aderiscano automaticamente al gruppo Sales.

1. In un'istanza privata del browser Internet, accedere all'interfaccia di [amministrazione di microsoft 365](https://admin.microsoft.com) con l'account di amministratore globale dell'abbonamento al laboratorio di testing di Microsoft 365 E5.
2. In una scheda separata del browser, accedere al portale di Azure all'indirizzo [https://portal.azure.com](https://portal.azure.com) .
3. Nel portale di Azure, immettere **gruppi** nella casella di ricerca e quindi selezionare **gruppi**.
4. nel riquadro **tutti i gruppi** selezionare **nuovo gruppo**.
5. In **tipo di gruppo**selezionare **Microsoft 365**.
6. In **nome gruppo**immettere **Sales**.
7. In **tipo di appartenenza**, selezionare **utente dinamico**.
8. Selezionare **membri dinamici degli utenti**.
9. Nel riquadro **delle regole di appartenenza dinamica** : 
   - Selezionare la proprietà **Department** .
   - Selezionare l'operatore **Equals** .
   - Nella casella **valore** immettere **Sales**.
10. Selezionare **Salva**.
11. Selezionare **Crea**.

Successivamente, configurare il gruppo vendite in modo che ai membri venga assegnata automaticamente la licenza Microsoft 365 E5.

1. Selezionare il gruppo **vendite** e quindi fare clic su **licenze**.
2. Nel riquadro **Aggiorna assegnazioni licenze** selezionare **Microsoft 365 E5**e quindi fare clic su **Salva**.
3. Chiudere la scheda del portale di Azure nel browser.

Successivamente, testare l'appartenenza a gruppi dinamici e la gestione delle licenze automatiche nell'account User 4:

1. Nella scheda **Microsoft Office Home** del browser selezionare **admin**.
2. Nella scheda dell'interfaccia di **amministrazione di Microsoft 365** selezionare **utenti attivi**.
3. Nella pagina **utenti attivi** selezionare l'account **User 4** .
4. Nel riquadro **User 4** , selezionare **modifica** per **licenze di prodotto**.
5. Nel riquadro **licenze di prodotto** disabilitare la licenza **Microsoft 365 E5** e quindi fare clic su **Salva**  >  **Chiudi**.
6. Nelle proprietà dell'account User 4, verificare che non siano state assegnate licenze di prodotto e che non vi siano appartenenze a gruppi.
7. Per **informazioni sui contatti**, selezionare **modifica**.
8. Nel riquadro **modifica informazioni contatto** selezionare informazioni di **contatto**.
9. Nella casella **Department** immettere **Sales**e quindi fare clic su **Salva**  >  **Chiudi**.
10. Attendere alcuni minuti, quindi selezionare periodicamente l'icona **Aggiorna** nell'angolo in alto a destra del riquadro account User 4.

Nel tempo, dovrebbe essere visualizzato il seguente:

- Proprietà **appartenenze a gruppi** aggiornata con il gruppo **Sales** .
- Proprietà delle **licenze di prodotto** aggiornate con la licenza **Microsoft 365 E5** .

Vedere questi articoli per distribuire l'appartenenza a gruppi dinamici e la gestione automatica delle licenze in produzione:

- [Gestione delle licenze basate su gruppo in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [Gruppi dinamici in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a>Passaggio successivo

Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.

## <a name="see-also"></a>Vedere anche

[Roadmap dell'identità](identity-roadmap-microsoft-365.md)

[Guide ai lab di test di Microsoft 365 per le aziende](m365-enterprise-test-lab-guides.md)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Microsoft 365 per la documentazione relativa all'organizzazione](https://docs.microsoft.com/microsoft-365-enterprise/)
