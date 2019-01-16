---
title: Automatizzare l'appartenenza al gruppo e sulle licenze per l'ambiente di test Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: Configurare basata su gruppo di gestione delle licenze e l'appartenenza al gruppo dinamica nell'ambiente di test Microsoft 365 aziendale.
ms.openlocfilehash: 45a78af202f2d9ab029683aae4d95ed9a3370b08
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868667"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a>Automatizzare l'appartenenza al gruppo e sulle licenze per l'ambiente di test Microsoft 365 Enterprise

Basata su gruppo di licenze automaticamente assegna o rimuove le licenze per un account utente in base all'appartenenza. L'appartenenza al gruppo dinamico aggiunge o rimuove i membri di un gruppo basato sulla proprietà degli account utente, ad esempio reparto o paese. In questo articolo esaminato una dimostrazione di entrambi nel proprio ambiente di test Microsoft 365 aziendale.

Esistono due fasi per impostare l'appartenenza al gruppo di licenze automatico e dinamica nell'ambiente di test Microsoft 365 aziendale:

1. Creare l'ambiente di test Microsoft 365 Enterprise.
2. Configurare e testare l'appartenenza al gruppo dinamico e la gestione automatica delle licenze.

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Fare clic [qui](https://aka.ms/m365etlgstack) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Preparare l'ambiente di testing Microsoft 365 Enterprise

Se si desidera testare gestione automatica delle licenze e l'appartenenza al gruppo in un modo semplice con i requisiti minimi, seguire le istruzioni di [configurazione di base semplificata](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se si desidera testare gestione automatica delle licenze e l'appartenenza al gruppo in un'azienda simulata, seguire le istruzioni [nell'autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Test automatizzati licenze e l'appartenenza al gruppo non richiede l'ambiente di testing simulato enterprise, che include una rete intranet simulata connessione a Internet e la sincronizzazione delle directory per una foresta Windows Server Active Directory. Viene fornito qui come un'opzione in modo che sia possibile testare gestione automatica delle licenze e l'appartenenza al gruppo e sperimentare in un ambiente che rappresenta una tipica organizzazione. 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>Fase 2: Configurare e testare l'appartenenza al gruppo dinamico e la gestione automatica delle licenze

Per prima cosa, si crea un nuovo gruppo di vendite e aggiungere una regola di appartenenza al gruppo dinamico in modo che gli account utente con il reparto impostato su vendite vengono aggiunti automaticamente al gruppo vendite.

1. Utilizza un'istanza del browser Internet privata, effettuare l'accesso al portale di Office in [https://office.com](https://office.com) con l'account amministratore globale della sottoscrizione di prova di Office 365 E5.
2. In una scheda separata del browser, accedere al portale di Azure in [https://portal.azure.com](https://portal.azure.com).
3. Nel portale di Azure fare clic su **Azure Active Directory > Utenti e gruppi > Tutti i gruppi**.
4. Su blade **tutti i gruppi** , fare clic su **nuovo gruppo**.
5. In **tipo di gruppo**, selezionare **Office 365**.
6. In **nome gruppo**digitare **vendite**.
7. In **tipo di appartenenza**, selezionare **utente dinamica** .
8. Fare clic su **Aggiungere query dinamica**.
9. Selezionare **Reparto** in **Dove aggiungere utenti**
10. Nel campo successivo, selezionare **Uguale a**.
11. Nel campo successivo digitare **vendite**.
12. Fare clic su **Aggiungi query** e quindi su **Crea**.
13. Chiudere server blade **gruppo** e i **gruppi di tutti i gruppi** .

Punto, configurare il gruppo di vendita in modo che i membri vengono assegnati automaticamente Office 365 E5 e mobilità aziendale + sicurezza E5 licenze.

1. Su blade **Panoramica** per Azure Active Directory, fare clic su **licenze > tutti i prodotti**.
2. Nell'elenco, selezionare **Enterprise Mobility + Security E5** e **Office 365 Enterprise E5**, quindi fare clic su **Assegna**.
3. Su blade **assegnare licenze** , fare clic su **utenti e gruppi**.
4. Nell'elenco dei gruppi, selezionare il gruppo di **Sales** .
5. Fare clic su **Seleziona**, quindi su **Assegna**.
6. Chiudere la scheda del portale di Azure nel browser.

Successivamente, testare l'appartenenza al gruppo dinamico e licenze automatica dell'account utente 4. 

1. Nella scheda **Home page di Microsoft Office** nel browser, fare clic su **amministratore**.
2. Dalla scheda di **interfaccia di amministrazione di Office** , fare clic su **utenti attivi**.
3. Nella pagina **utenti** fare clic sull'account **utente 4** .
4. Nel riquadro di **utente 4** , fare clic su **Modifica** per **le licenze del prodotto**.
5. Nel riquadro di **licenze per i prodotti** , attivare la **mobilità aziendale + E5 di sicurezza** e le licenze di **Office 365 Enterprise E5** disattivato e quindi fare clic su **salvare > Chiudi**.
6. Nelle proprietà dell'account utente 4, verificare che non è stati assegnati alcun licenze per i prodotti e non sono disponibili appartenenze ai gruppi.
7. Per **informazioni di contatto**, scegliere **Modifica** .
8. Nel riquadro **informazioni contatto modificare** , fare clic su **informazioni di contatto**.
9. Nel campo **reparto** digitare **Sales**e quindi fare clic su **salvare > Chiudi**.
10. Attendere qualche minuto e quindi periodicamente l'icona Aggiorna in alto a destra del riquadro di account utente 4. 

Nel tempo dovrebbe essere visualizzato il:

- **Appartenenze a gruppi** della proprietà con il gruppo di **Sales** .
- **Licenze per i prodotti** della proprietà con le licenze **Enterprise mobilità + sicurezza E5** e **Office 365 Enterprise E5** .

Nella fase di identità per informazioni e collegamenti per distribuire l'appartenenza al gruppo dinamico e la gestione automatica delle licenze nell'ambiente di produzione, vedere la procedura seguente:

- [Configurare l'assegnazione automatica delle licenze](identity-group-based-licensing.md)
- [Configurare l'appartenenza a gruppi dinamici](identity-automatic-group-membership.md)

## <a name="next-step"></a>Passaggio successivo

Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.

## <a name="see-also"></a>Vedere anche

[Fase 2: identità](identity-infrastructure.md)

[Guide al lab di test di Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Distribuzione di Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentazione di Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
