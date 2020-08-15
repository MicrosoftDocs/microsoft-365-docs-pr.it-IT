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
ms.openlocfilehash: a25a47b81ce8c119e7aeb44660af32bb9cafb08a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685559"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a>Automatizzare le licenze e l'appartenenza ai gruppi per l'ambiente di testing di Microsoft 365 per l'organizzazione

*Questa guida del laboratorio di testing può essere utilizzata solo per Microsoft 365 per gli ambienti di testing dell'organizzazione.*

La gestione delle licenze basate su gruppo assegna o rimuove automaticamente le licenze per un account utente basato sull'appartenenza a un gruppo. L'appartenenza a un gruppo dinamico aggiunge o rimuove membri a un gruppo in base alle proprietà degli account utente, ad esempio reparto o paese. In questo articolo viene illustrata una dimostrazione di entrambi nell'ambiente di testing di Microsoft 365 per l'organizzazione.

Sono disponibili due fasi per la configurazione della licenza automatica e l'appartenenza a gruppi dinamici nell'ambiente di testing di Microsoft 365 per l'organizzazione:

1. Creare l'ambiente di testing di Microsoft 365 per l'organizzazione.
2. Configurare e testare l'appartenenza a gruppi dinamici e la gestione automatica delle licenze.

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Fare clic [qui](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli disponibili nella serie di guide al lab di test di Microsoft 365 per le aziende.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione

Se si desidera solo testare la licenza automatizzata e l'appartenenza ai gruppi con i requisiti minimi, seguire le istruzioni contenute in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se si desidera testare la licenza automatizzata e l'appartenenza a un gruppo in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> La verifica delle licenze automatizzate e dell'appartenenza ai gruppi non richiede l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS). Viene fornito come opzione in modo che sia possibile testare la licenza automatizzata e l'appartenenza ai gruppi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica. 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>Fase 2: configurare e testare l'appartenenza a gruppi dinamici e la gestione automatica delle licenze

Per prima cosa, è necessario creare un nuovo gruppo di vendita e aggiungere una regola di appartenenza a un gruppo dinamico in modo che gli account utente con il reparto impostato su Sales vengano automaticamente aggiunti al gruppo Sales.

1. Se si utilizza un'istanza privata del browser Internet, accedere all'interfaccia di [amministrazione di microsoft 365](https://admin.microsoft.com) con l'account di amministratore globale dell'abbonamento al laboratorio di testing di Microsoft 365 E5.
2. In una scheda separata del browser, accedere al portale di Azure all'indirizzo [https://portal.azure.com](https://portal.azure.com) .
3. Nel portale di Azure, digitare **gruppi** nella casella di ricerca e quindi fare clic su **gruppi**.
4. nel riquadro **tutti i gruppi** fare clic su **nuovo gruppo**.
5. In **tipo di gruppo**selezionare **Microsoft 365**.
6. In **nome gruppo**digitare **Sales**.
7. In **tipo di appartenenza**, selezionare **utente dinamico**.
8. Fare clic su **membri utente dinamici**.
9. Nel riquadro **delle regole di appartenenza dinamica** : 
   - Selezionare la proprietà **Department** .
   - Selezionare l'operatore **Equals** .
   - Digitare **Sales** in **value**.
10. Fare clic su **Salva**.
11. Fare clic su **Crea**.

Successivamente, è possibile configurare il gruppo vendite in modo che ai membri venga assegnata automaticamente la licenza Microsoft 365 E5.

1. Fare clic sul gruppo **vendite** e quindi su **licenze**.
2. Nel riquadro **Aggiorna assegnazioni licenze** selezionare **Microsoft 365 E5**e quindi fare clic su **Salva**.
3. Chiudere la scheda del portale di Azure nel browser.

Successivamente, è possibile testare l'appartenenza a gruppi dinamici e la gestione delle licenze automatiche nell'account User 4. 

1. Nella scheda **Microsoft Office Home** del browser, fare clic su **amministratore**.
2. Nella scheda dell'interfaccia di **amministrazione di Microsoft 365** fare clic su **utenti attivi**.
3. Nella pagina **utenti attivi** , fare clic sull'account **User 4** .
4. Nel riquadro **User 4** , fare clic su **modifica** per **licenze di prodotto**.
5. Nel riquadro **licenze di prodotto** disabilitare la licenza **Microsoft 365 E5** e quindi fare clic su **Salva > Chiudi**.
6. Nelle proprietà dell'account User 4, verificare che non siano state assegnate licenze di prodotto e che non vi siano appartenenze a gruppi.
7. Fare clic su **modifica** per **informazioni di contatto**.
8. Nel riquadro **modifica informazioni contatto** fare clic su **informazioni di contatto**.
9. Nel campo **reparto** digitare **Sales**e quindi fare clic su **Salva > Chiudi**.
10. Attendere alcuni minuti, quindi fare periodicamente clic sull'icona Aggiorna nell'angolo in alto a destra del riquadro account User 4. 

Nel tempo dovrebbe essere visualizzato il seguente:

- Proprietà **appartenenze a gruppi** aggiornata con il gruppo **Sales** .
- Proprietà delle **licenze di prodotto** aggiornate con la licenza **Microsoft 365 E5** .

Vedere questi articoli per distribuire l'appartenenza a gruppi dinamici e la gestione automatica delle licenze in produzione:

- COLLEGAMENTO TBD
- COLLEGAMENTO TBD

## <a name="next-step"></a>Passaggio successivo

Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.

## <a name="see-also"></a>Vedere anche

[Roadmap dell'identità](identity-roadmap-microsoft-365.md)

[Guide ai lab di test di Microsoft 365 per le aziende](m365-enterprise-test-lab-guides.md)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Microsoft 365 per la documentazione relativa all'organizzazione](https://docs.microsoft.com/microsoft-365-enterprise/)
