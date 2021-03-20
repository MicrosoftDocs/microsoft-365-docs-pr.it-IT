---
title: Automatizzare le licenze e l'appartenenza ai gruppi per l'ambiente di testing di Microsoft 365 per le aziende
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
description: Configurare le licenze basate su gruppi e l'appartenenza a gruppi dinamici nell'ambiente di testing di Microsoft 365 per le aziende.
ms.openlocfilehash: 26840e2884202a0fa9c4bb563f3d7c653482ef87
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905369"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a>Automatizzare le licenze e l'appartenenza ai gruppi per l'ambiente di testing di Microsoft 365 per le aziende

*Questa guida al laboratorio di testing può essere utilizzata solo per gli ambienti di testing di Microsoft 365 per le aziende.*

Le licenze basate su gruppo assegnano o rimuove automaticamente le licenze per un account utente in base all'appartenenza al gruppo. L'appartenenza a un gruppo dinamico aggiunge o rimuove membri a un gruppo in base alle proprietà dell'account utente, ad esempio **Department** o **Country.** Questo articolo illustra come aggiungere e rimuovere membri del gruppo nell'ambiente di testing di Microsoft 365 per le aziende.

La configurazione della licenza automatica e dell'appartenenza a gruppi dinamici nell'ambiente di testing di Microsoft 365 per le aziende prevede due fasi:

- [Fase 1: creare l'ambiente di testing di Microsoft 365 per le aziende](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: configurare e testare l'appartenenza a gruppi dinamici e le licenze automatiche](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Per una mappa visiva a tutti gli articoli nello stack guida del laboratorio di testing di Microsoft 365 per le aziende, passare a [Microsoft 365 per enterprise Test Lab Guide Stack.](../downloads/Microsoft365EnterpriseTLGStack.pdf)
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: creare l'ambiente di testing di Microsoft 365 per le aziende

Se si desidera testare solo le licenze automatizzate e l'appartenenza ai gruppi in modo leggero con i requisiti minimi, seguire le istruzioni in [Configurazione di base lightweight](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se si desidera testare le licenze automatizzate e l'appartenenza a gruppi in un'azienda simulata, seguire le istruzioni in [Autenticazione pass-through.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Il test delle licenze automatizzate e dell'appartenenza ai gruppi non richiede l'ambiente di testing aziendale simulato, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di Servizi di dominio Active Directory. Viene fornito qui come opzione in modo da poter testare le licenze automatizzate e l'appartenenza ai gruppi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>Fase 2: configurare e testare l'appartenenza a gruppi dinamici e le licenze automatiche

Innanzitutto, crea un nuovo gruppo denominato Sales e aggiungi una regola di appartenenza a un gruppo dinamico in modo che gli account utente con **Department** impostato su **Sales** si uniranno automaticamente al gruppo Sales.

1. In un'istanza privata del browser Internet, accedere all'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com) con l'account amministratore globale dell'abbonamento al laboratorio di testing di Microsoft 365 E5.
2. In una scheda separata del browser passare al portale di Azure all'indirizzo [https://portal.azure.com](https://portal.azure.com) .
3. Nel portale di Azure immettere **i gruppi** nella casella di ricerca e quindi selezionare **Gruppi**.
4. nel riquadro **Tutti i** gruppi selezionare **Nuovo gruppo**.
5. In **Tipo di gruppo** selezionare Microsoft **365.**
6. In **Nome gruppo** immettere **Vendite.**
7. In **Tipo di appartenenza** selezionare **Utente dinamico**.
8. Selezionare **Membri utente dinamici**.
9. Nel riquadro **Regole di appartenenza** dinamiche: 
   - Selezionare la **proprietà del** reparto.
   - Selezionare **l'operatore Equals.**
   - Nella casella **Valore** immettere **Vendite**.
10. Selezionare **Salva**.
11. Selezionare **Crea**.

Configurare quindi il gruppo Vendite in modo che ai membri sia assegnata automaticamente la licenza di Microsoft 365 E5.

1. Selezionare il **gruppo** Vendite e quindi **Licenze**.
2. Nel riquadro **Aggiorna assegnazioni licenze** selezionare **Microsoft 365 E5** e quindi selezionare **Salva**.
3. Nel browser chiudere la scheda Portale di Azure.

Testare quindi l'appartenenza a gruppi dinamici e le licenze automatiche nell'account Utente 4:

1. Nella scheda **Microsoft Office Home** del browser seleziona **Amministratore.**
2. Nella scheda Interfaccia di amministrazione di **Microsoft 365** selezionare **Utenti attivi**.
3. Nella pagina **Utenti attivi** selezionare l'account **Utente 4.**
4. Nel riquadro **Utente 4** selezionare **Modifica** per **Licenze prodotto**.
5. Nel riquadro **Licenze prodotto** disabilitare la licenza di **Microsoft 365 E5** e quindi selezionare **Salva**  >  **chiudi.**
6. Nelle proprietà dell'account Utente 4 verificare che non siano state assegnate licenze di prodotto e che non vi siano appartenenze a gruppi.
7. Per **Informazioni di contatto,** selezionare **Modifica.**
8. Nel riquadro **Modifica informazioni contatto** selezionare Informazioni di **contatto**.
9. Nella casella **Reparto** immettere **Vendite** e quindi selezionare **Salva**  >  **chiudi.**
10. Attendere alcuni minuti e quindi selezionare periodicamente l'icona **Aggiorna** nell'angolo superiore destro del riquadro Account utente 4.

Nel tempo dovrebbe essere visualizzato:

- **Proprietà memberships** del gruppo aggiornata con il **gruppo Sales.**
- **Proprietà licenze** di prodotto aggiornata con la **licenza di Microsoft 365 E5.**

Vedi questi articoli per distribuire l'appartenenza a gruppi dinamici e le licenze automatiche in produzione:

- [Licenze basate su gruppo in Azure Active Directory](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [Gruppi dinamici in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a>Passaggio successivo

Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.

## <a name="see-also"></a>Vedere anche

[Guida di orientamento all'identità](identity-roadmap-microsoft-365.md)

[Guide ai lab di test di Microsoft 365 per le aziende](m365-enterprise-test-lab-guides.md)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Documentazione di Microsoft 365 for enterprise](/microsoft-365-enterprise/)