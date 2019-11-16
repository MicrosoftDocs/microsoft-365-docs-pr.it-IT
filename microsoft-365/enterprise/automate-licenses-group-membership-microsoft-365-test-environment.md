---
title: Automatizzare la gestione delle licenze e dell'appartenenza ai gruppi per l'ambiente di testing Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Configurare la gestione delle licenze basate su gruppo e l'appartenenza a gruppi dinamici nell'ambiente di testing Microsoft 365 Enterprise.
ms.openlocfilehash: fe6380d94919556904a1fb1ac0624fac3496fe30
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673252"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a>Automatizzare la gestione delle licenze e dell'appartenenza ai gruppi per l'ambiente di testing Microsoft 365 Enterprise

*Questa guida del laboratorio di testing può essere utilizzata solo per gli ambienti di testing di Microsoft 365 Enterprise.*

La gestione delle licenze basate su gruppo assegna o rimuove automaticamente le licenze per un account utente basato sull'appartenenza a un gruppo. L'appartenenza a un gruppo dinamico aggiunge o rimuove membri a un gruppo in base alle proprietà degli account utente, ad esempio reparto o paese. In questo articolo viene illustrata una dimostrazione di entrambi nell'ambiente di testing di Microsoft 365 Enterprise.

Sono disponibili due fasi per la configurazione della licenza automatica e l'appartenenza a gruppi dinamici nell'ambiente di testing di Microsoft 365 Enterprise:

1. Creare l'ambiente di testing di Microsoft 365 Enterprise.
2. Configurare e testare l'appartenenza a gruppi dinamici e la gestione automatica delle licenze.

![Guide del laboratorio di testing per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Fare clic [qui](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Creare l'ambiente di testing di Microsoft 365 Enterprise

Se si desidera solo testare la licenza automatizzata e l'appartenenza ai gruppi con i requisiti minimi, seguire le istruzioni contenute in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se si desidera testare la licenza automatizzata e l'appartenenza a un gruppo in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> La verifica delle licenze automatizzate e dell'appartenenza ai gruppi non richiede l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS). Viene fornito come opzione in modo che sia possibile testare la licenza automatizzata e l'appartenenza ai gruppi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica. 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>Fase 2: configurare e testare l'appartenenza a gruppi dinamici e la gestione automatica delle licenze

Per prima cosa, è necessario creare un nuovo gruppo di vendita e aggiungere una regola di appartenenza a un gruppo dinamico in modo che gli account utente con il reparto impostato su Sales vengano automaticamente aggiunti al gruppo Sales.

1. Se si utilizza un'istanza privata del browser Internet, accedere al portale di Office 365 [https://portal.office.com](https://portal.office.com) con l'account di amministratore globale dell'abbonamento al laboratorio di testing di Office 365 E5.
2. In una scheda separata del browser, accedere al portale di Azure all'indirizzo [https://portal.azure.com](https://portal.azure.com).
3. Nel portale di Azure fare clic su **Azure Active Directory > Utenti e gruppi > Tutti i gruppi**.
4. Nel pannello **tutti i gruppi** fare clic su **nuovo gruppo**.
5. In **tipo di gruppo**, selezionare **Office 365**.
6. In **nome gruppo**digitare **Sales**.
7. In **tipo di appartenenza**, selezionare **utente dinamico** .
8. Fare clic su **Aggiungere query dinamica**.
9. Selezionare **Reparto** in **Dove aggiungere utenti**
10. Nel campo successivo, selezionare **Uguale a**.
11. Nel campo successivo digitare **Sales**.
12. Fare clic su **Aggiungi query** e quindi su **Crea**.
13. Chiudere le lame **gruppo** e **gruppi-tutti i gruppi** .

Successivamente, è possibile configurare il gruppo vendite in modo che ai membri vengano assegnate automaticamente le licenze di Office 365 E5 ed Enterprise Mobility + Security E5.

1. Nel pannello **Panoramica** di Azure Active Directory, fare clic su **licenze > tutti i prodotti**.
2. Nell'elenco, selezionare **Enterprise Mobility + Security E5** e **Office 365 Enterprise E5**, quindi fare clic su **Assegna**.
3. Sul blade di **assegnazione della licenza** , fare clic su **utenti e gruppi**.
4. Nell'elenco dei gruppi, selezionare il gruppo **vendite** .
5. Fare clic su **Seleziona**, quindi su **Assegna**.
6. Chiudere la scheda del portale di Azure nel browser.

Successivamente, è possibile testare l'appartenenza a gruppi dinamici e la gestione delle licenze automatiche nell'account User 4. 

1. Nella scheda **Microsoft Office Home** del browser, fare clic su **amministratore**.
2. Nella scheda dell'interfaccia di **amministrazione di Microsoft 365** fare clic su **utenti attivi**.
3. Nella pagina **utenti attivi** , fare clic sull'account **User 4** .
4. Nel riquadro **User 4** , fare clic su **modifica** per **licenze di prodotto**.
5. Nel riquadro **licenze di prodotto** , disattivare le **licenze Enterprise Mobility + Security e5** e **Office 365 Enterprise E5** , quindi fare clic su **Salva > Chiudi**.
6. Nelle proprietà dell'account User 4, verificare che non siano state assegnate licenze di prodotto e che non vi siano appartenenze a gruppi.
7. Fare clic su **modifica** per **informazioni di contatto**.
8. Nel riquadro **modifica informazioni contatto** fare clic su **informazioni di contatto**.
9. Nel campo **reparto** digitare **Sales**e quindi fare clic su **Salva > Chiudi**.
10. Attendere alcuni minuti, quindi fare periodicamente clic sull'icona Aggiorna nell'angolo in alto a destra del riquadro account User 4. 

Nel tempo dovrebbe essere visualizzato il seguente:

- Proprietà **appartenenze a gruppi** aggiornata con il gruppo **Sales** .
- Proprietà delle **licenze di prodotto** aggiornate con le licenze **Enterprise Mobility + Security e5** e **Office 365 Enterprise E5** .

Per informazioni e collegamenti per la distribuzione di appartenenza a gruppi dinamici e licenze automatiche in produzione, vedere questi passaggi nella fase di identità:

- [Configurare l'assegnazione automatica delle licenze](identity-use-group-management.md#identity-group-license)
- [Configurare l'appartenenza a gruppi dinamica](identity-use-group-management.md#identity-dyn-groups)

## <a name="next-step"></a>Passaggio successivo

Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.

## <a name="see-also"></a>Vedere anche

[Fase 2: identità](identity-infrastructure.md)

[Guide al lab di test di Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Distribuzione di Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md).

[Documentazione di Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
