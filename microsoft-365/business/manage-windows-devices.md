---
title: Consenti la gestione di dispositivi Windows 10 con dominio per essere gestiti da Microsoft 365 for business
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Informazioni su come consentire a Microsoft 365 di proteggere i dispositivi Windows 10 locali con l'aggiunta di Active Directory in pochi passaggi.
ms.openlocfilehash: 857651081fb10856d28dd419333ebef655388407
ms.sourcegitcommit: e6e704cbd9a50fc7db1e6a0cf5d3f8c6cbb94363
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "44564948"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>Consenti la gestione di dispositivi Windows 10 con dominio per essere gestiti da Microsoft 365 Business Premium

Se l'organizzazione utilizza Windows Server Active Directory in locale, è possibile configurare Microsoft 365 Business Premium per proteggere i dispositivi Windows 10, mantenendo comunque l'accesso alle risorse locali che richiedono l'autenticazione locale.
Per impostare questa protezione, è possibile implementare i **dispositivi ibridi di Azure ad Uniti**. Questi dispositivi sono associati sia a Active Directory locale che a Azure Active Directory.

In questo video vengono illustrati i passaggi da eseguire per la configurazione dello scenario più comune, che è anche dettagliato nei passaggi successivi.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a>Prima di iniziare, eseguire la procedura seguente:
- Sincronizzare gli utenti con Azure ad con Azure ad Connect.
- Completare la sincronizzazione di Azure AD Connect unità organizzativa (OU).
- Assicurarsi che tutti gli utenti di dominio sincronizzati dispongano delle licenze per Microsoft 365 Business Premium.

Per la procedura, vedere [sincronizzare gli utenti di dominio a Microsoft](manage-domain-users.md) .

## <a name="1-verify-mdm-authority-in-intune"></a>1. verificare l'autorità MDM in Intune

Andare a portal.azure.com e nella parte superiore della pagina di ricerca di Intune.
Nella pagina Microsoft Intune selezionare **registrazione dispositivo** e nella pagina **Panoramica** verificare che l' **autorità MDM** sia **Intune**.

- Se l' **autorità MDM** è **None**, fare clic sull' **autorità MDM** per impostarla su **Intune**.
- Se l' **autorità MDM** è **Microsoft Office 365**, passare **a dispositivi di**  >  **registrazione** e utilizzare la finestra di dialogo **Aggiungi autorità MDM** sulla destra per aggiungere l'autorità di **MDM** (la finestra di dialogo **Aggiungi autorità MDM** è disponibile solo se l' **autorità MDM** è impostata su Microsoft Office 365).

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. Verificare che Azure AD sia abilitato per l'aggiunta di computer

- Accedere all'interfaccia di amministrazione <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> e selezionare **Azure Active Directory** (selezionare Mostra tutto se Azure Active Directory non è visibile) nell'elenco **admin** Centers. 
- Nell'interfaccia di **amministrazione di Azure Active Directory**passare a **Azure Active Directory** , scegliere **dispositivi** e quindi **Impostazioni dispositivo**.
- Verificare**che gli utenti possano aggiungere dispositivi ad Azure ad** sia abilitato 
    1. Per abilitare tutti gli utenti, impostare su **tutti**.
    2. Per abilitare utenti specifici, impostare su **selezionato** per abilitare un gruppo specifico di utenti.
        - Aggiungere gli utenti di dominio desiderati sincronizzati in Azure AD a un [gruppo di sicurezza](../admin/create-groups/create-groups.md).
        - Scegliere **Seleziona gruppi** per abilitare l'ambito degli utenti MDM per il gruppo di sicurezza.

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. Verificare che Azure AD sia abilitato per MDM

- Andare all'interfaccia di amministrazione <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> e selezionare Seleziona gli amministratori di **endpoint**t (selezionare **Mostra tutto** se **Endpoint Manager** non è visibile)
- Nell'interfaccia di **amministrazione di Microsoft Endpoint Manager**passare alla **Devices**  >  **Windows**  >  **Windows Enrollment**  >  **registrazione automatica**dei dispositivi Windows Windows.
- Verificare che l'ambito dell'utente MDM sia abilitato.

    1. Per registrare tutti i computer, impostare su **tutti** per la registrazione automatica di tutti i computer degli utenti aggiunti a Azure ad e nuovi computer quando gli utenti aggiungono un account di lavoro a Windows.
    2. Impostato su **alcuni** per registrare i computer di un gruppo specifico di utenti.
        -  Aggiungere gli utenti di dominio desiderati sincronizzati in Azure AD a un [gruppo di sicurezza](../admin/create-groups/create-groups.md).
        -  Scegliere **Seleziona gruppi** per abilitare l'ambito degli utenti MDM per il gruppo di sicurezza.

## <a name="4-set-up-service-connection-point-scp"></a>4. configurare il punto di connessione del servizio (SCP)

Questi passaggi sono semplificati da [Configure Hybrid Azure ad join](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join). Per completare la procedura, è necessario utilizzare Azure AD Connect e l'amministratore globale di Microsoft 365 Business Premium e le password di amministratore di Active Directory.

1.  Avviare Azure AD Connect e quindi selezionare **Configure**.
2.  Nella pagina **attività aggiuntive** selezionare **Configura opzioni dispositivo**, quindi fare clic su **Avanti**.
3.  Nella pagina **Panoramica** selezionare **Avanti**.
4.  Nella pagina **connessione ad Azure ad** , immettere le credenziali di un amministratore globale per Microsoft 365 Business Premium.
5.  Nella pagina **Opzioni dispositivo** , selezionare **Configura ibrido di Azure ad join**, quindi selezionare **Avanti**.
6.  Nella pagina **SCP** , per ogni foresta in cui si desidera connettersi ad Azure ad Connect per configurare l'SCP, completare i passaggi seguenti e quindi selezionare **Avanti**:
    - Selezionare la casella accanto al nome della foresta. La foresta dovrebbe essere il nome di dominio dell'annuncio.
    - Nella colonna **servizio di autenticazione** aprire l'elenco a discesa e selezionare nome di dominio corrispondente (è disponibile solo un'opzione solo).
    - Selezionare **Aggiungi** per immettere le credenziali di amministratore del dominio.  
7.  Nella pagina **sistemi operativi del dispositivo** selezionare solo i dispositivi collegati al dominio di Windows 10 o versioni successive.
8.  Nella pagina **pronto per la configurazione** , selezionare **Configure**.
9.  Nella pagina **Configurazione completata** selezionare **Esci**.


## <a name="5-create-a-gpo-for-intune-enrollment--admx-method"></a>5. creare un oggetto Criteri di gruppo per la registrazione di Intune-ADMX, metodo

Utilizzare. File modello ADMX.

1.  Accedere a **Server Manager**  >  **Tools**  >  **Gestione criteri di gruppo**di Active Directory Server, ricerca e Apri Server Manager.
2.  Selezionare il nome di dominio in **domini** e fare clic con il pulsante destro del mouse su **oggetti Criteri di gruppo** per selezionare **nuovo**.
3.  Assegnare un nome al nuovo oggetto Criteri di gruppo, ad esempio "*Cloud_Enrollment*", quindi selezionare **OK**.
4.  Fare clic con il pulsante destro del mouse sul nuovo GPO in **oggetti Criteri di gruppo** e scegliere **modifica**.
5.  In **Editor gestione criteri di gruppo**, passare a criteri di **configurazione del computer**  >  **Policies**  >  **modelli amministrativi**dei  >  **componenti di Windows**  >  **MDM**.
6. Fare clic con il pulsante destro del mouse su **Consenti registrazione automatica MDM utilizzando le credenziali di Azure ad predefinite** e quindi selezionare **attivato**  >  **OK**. Chiudere la finestra dell'editor.

> [!IMPORTANT]
> Se il criterio non viene abilitato per **abilitare la registrazione automatica del MDM utilizzando le credenziali di Azure ad predefinite**, vedere [Get the ultimo modelli amministrativi](#get-the-latest-administrative-templates).

## <a name="6-deploy-the-group-policy"></a>6. distribuire i criteri di gruppo

1.  In Server Manager, in **domini** > oggetti Criteri di gruppo, selezionare il GPO dal passaggio 3 sopra, ad esempio "Cloud_Enrollment".
2.  Selezionare la scheda **ambito** per l'oggetto Criteri di gruppo.
3.  Nella scheda ambito dell'oggetto Criteri di gruppo fare clic con il pulsante destro del mouse sul collegamento al dominio in **collegamenti**.
4.  Selezionare **enforced** per distribuire l'oggetto Criteri di gruppo e quindi fare clic su **OK** nella schermata di conferma.

## <a name="get-the-latest-administrative-templates"></a>Ottenere i modelli amministrativi più recenti

Se il criterio non viene visualizzato, **abilitare la registrazione automatica MDM utilizzando le credenziali di Azure ad predefinite**, potrebbe essere perché non è installato ADMX per Windows 10, versione 1803, versione 1809 o versione 1903. Per risolvere il problema, attenersi alla seguente procedura (Nota: l'ultima MDM. admx è compatibile con le versioni precedenti):

1.  Download: [modelli amministrativi (con estensione ADMX) per l'aggiornamento a Windows 10 maggio 2019 (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).
2.  Installare il pacchetto nel controller di dominio primario (PDC).
3.  Spostarsi, a seconda della versione della cartella: **c:\Programmi (x86) \Microsoft Group Policy\Windows 10 May 2019 Update (1903) v3**.
4.  Rinominare la cartella delle **definizioni dei criteri** nel percorso precedente in **PolicyDefinitions**.
5.  Copiare la cartella **PolicyDefinitions** in **C:\Windows\SYSVOL\domain\Policies**. 
    -   Se si prevede di utilizzare un archivio criteri centrale per l'intero dominio, aggiungere il contenuto di PolicyDefinitions.
6.  Riavviare il controller di dominio principale affinché i criteri siano disponibili. Questa procedura funzionerà anche per qualsiasi versione futura.

A questo punto, è possibile visualizzare i criteri per **abilitare la registrazione automatica MDM utilizzando le credenziali di Azure ad** disponibili.

