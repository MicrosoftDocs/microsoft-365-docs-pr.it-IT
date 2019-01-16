---
title: Preparazione dell'organizzazione per Windows 10 Enterprise
description: Istruzioni generali operazioni che è necessario distribuire Enterprise 10 Windows su PC come parte di Microsoft 365 Enterprise.
keywords: Distribuzione di Windows 10 Enterprise documentazione Microsoft 365 Microsoft 365 Microsoft 365 Enterprise
author: JoeDavies-MSFT
localization_priority: Normal
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
ms.author: josephd
ms.openlocfilehash: 21a4198c688e1865a029f18ff3ceeb2155d419e4
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868813"
---
# <a name="step-1-prepare-your-organization-for-windows-10-enterprise"></a>Passaggio 1: Preparare l'organizzazione per Windows 10 Enterprise

*In questo articolo si applica a E3 sia E5 versioni di Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Prima di aggiornare i dispositivi a Windows 10 Enterprise, considerare quanto segue:

- **I domini devono essere aggiunto e verificati** <br>Con una sottoscrizione di Microsoft 365, viene visualizzato un nome di dominio predefinito che termina con onmicrosoft.com (ad esempio contoso.onmicrosoft.com). La maggior parte delle organizzazioni preferiscono utilizzare uno o più domini a cui che sono proprietari in modo che gli indirizzi di posta elettronica terminano con i propri nome di dominio (ad esempio username@contoso.com). Per utilizzare il proprio dominio, è necessario aggiungerlo a Microsoft 365 e verificare che appartenga alla propria azienda. È consigliabile aggiungere e verificare i domini a questo punto in modo che siano pronti per essere ogni volta che si impostano i servizi Microsoft 365, come la posta elettronica e Skype per le aziende.
- **Non è necessario aggiungere utenti al momento** <br>Per utilizzare i servizi Microsoft 365 oppure installare i prodotti Microsoft 365, gli utenti devono account in Microsoft 365 e sono necessarie licenze per i prodotti. Viene illustrato come aggiungere utenti a Microsoft 365 dipende dal numero di utenti e se si dispongono di Active Directory locale. Se non si dispone di Active Directory (o si dispone di Active Directory, ma non si desidera sincronizzare con Microsoft 365), è possibile aggiungere utenti direttamente a Microsoft 365 e assegnare licenze singolarmente o in massa.<br>Se si dispongono di Active Directory locale, è possibile [sincronizzare con Microsoft 365](identity-azure-ad-connect-health.md) per creare gli account utente in Azure Active Directory, directory del cloud utilizzate da Microsoft 365. Con questo metodo, è possibile creare gli account per gli utenti e gruppi di sicurezza che consente di gestire le autorizzazioni per le risorse (ad esempio, documenti o le raccolte siti di SharePoint Online). Sincronizzazione di Active Directory con Microsoft 365 non assegnare licenze agli utenti.
- **Non è necessario per gli utenti con licenza attualmente** <br>Prima che gli utenti possono utilizzare i servizi Microsoft 365 o installare il software dal portale di Microsoft 365, sono necessarie licenze per i prodotti. Come un amministratore di gestione globale o un utente, è possibile assegnare direttamente le licenze di prodotti Microsoft 365 singolarmente o in blocco. È inoltre possibile utilizzare [basata su gruppo di licenze](identity-group-based-licensing.md) per assegnare automaticamente licenze quando gli utenti vengono aggiunti a un gruppo specifico. 
- **Installazione di Office 365 ProPlus indipendente** <br>Recupero di una licenza di Microsoft 365 non installare automaticamente Office 365 ProPlus nei computer client. Vedere [fase 4: Office 365 ProPlus](office365proplus-infrastructure.md) per ulteriori informazioni. 

## <a name="set-windows-diagnostics-data-level"></a>Impostare il livello di dati diagnostica di Windows

Microsoft utilizza i dati di diagnostica da mantenere Windows dispositivi sicura per identificare le tendenze malware e altri rischi e per migliorare la qualità dei servizi Windows e Microsoft. È necessario verificare che il servizio di diagnostica è abilitato un livello minimo di base su tutti gli endpoint dell'organizzazione. *Per impostazione predefinita, questo servizio è abilitato e impostare il livello avanzato.* Tuttavia, è buona norma controllare e assicurarsi ricevono dati sensore. Impostazione dei livelli tramite i criteri sostituisce le impostazioni a livello di dispositivo. 

**Livelli di dati di diagnostica del sistema operativo Windows 10**

È possibile configurare le impostazioni di dati di diagnostica del sistema operativo utilizzando gli strumenti di gestione che già in uso, ad esempio criteri di gruppo, MDM o il Provisioning di Windows. È possibile modificare manualmente le impostazioni utilizzando l'Editor del Registro di sistema. I livelli di dati di diagnostica tramite un criterio di gestione esegue l'override di qualsiasi impostazione di livello del dispositivo.

Utilizzare il valore appropriato nella tabella riportata di seguito quando si configurano i criteri di gestione.

| Livello | Dati raccolti | Valore |
|:--- |:--- |:--- |
| Sicurezza | Solo i dati della protezione. | 0 |
| Di base | I dati di protezione e base del sistema e dei dati sulla qualità. | 1 |
| Avanzato | Protezione dati, base del sistema e dei dati sulla qualità e sui concetti avanzati e affidabilità avanzate. | 2 |
| Full | Dati di protezione, base del sistema e dei dati sulla qualità, sui concetti avanzati e affidabilità avanzata dati e dati di diagnostica completa. | 3 |

È possibile abilitare i dati di diagnostica tramite uno dei seguenti metodi:

* **Microsoft Intune** - se si prevede di utilizzare Intune per gestire i dispositivi, è possibile creare un criterio di configurazione per attivare la configurazione dei criteri di sistema <a href="https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry" target="blank">SystemAllowTelemetry</a> dati di diagnostica. Per ulteriori informazioni sull'impostazione dei criteri di configurazione, vedere [Manage impostazioni e caratteristiche nei dispositivi con Microsoft Intune criteri](https://aka.ms/intuneconfigpolicies).
* **Editor del Registro di sistema** - è possibile utilizzare l'Editor del Registro di sistema per attivare manualmente i dati di diagnostica in ogni dispositivo nell'organizzazione. In alternativa, è possibile scrivere uno script per modificare il Registro di sistema. Se un criterio di gestione esiste già, ad esempio criteri di gruppo o MDM, verrà ignorato questa impostazione del Registro di sistema.
* **Criteri di gruppo** - se non si intende registrare i dispositivi in Intune, è possibile utilizzare un oggetto Criteri di gruppo per impostare il livello di dati di diagnostica dell'organizzazione.
* **Al prompt dei comandi** - è possibile impostare i dati di diagnostica Windows 10 e il servizio per l'avvio automatico con il prompt dei comandi. Questo metodo è ideale per testare il servizio su solo alcuni dispositivi. Attivazione del servizio per l'avvio automatico con questo comando non verrà configurato il livello di dati di diagnostica. Se non è stato configurato un livello di dati di diagnostica tramite gli strumenti di gestione, il servizio funzionerà con il valore predefinito livello avanzato.

Vedere [dati di diagnostica configurare Windows all'interno dell'organizzazione](https://docs.microsoft.com/windows/configuration/configure-windows-diagnostic-data-in-your-organization) per ulteriori informazioni sui dati di diagnostica di Windows e come abilitare che lo in base al metodo scelto.

Come checkpoint provvisorio, vedere i [criteri di completamento](windows10-exit-criteria.md#crit-windows10-step1) relativi a questo passaggio.

## <a name="next-step"></a>Passaggio successivo

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)| [Distribuire Windows 10 aziendale per dispositivi esistenti come un aggiornamento sul posto](windows10-deploy-inplaceupgrade.md) |






