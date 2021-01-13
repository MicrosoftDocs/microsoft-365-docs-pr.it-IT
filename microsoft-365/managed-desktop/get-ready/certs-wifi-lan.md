---
title: Preparare certificati e profili di rete per Microsoft Managed Desktop
description: certs/WiFi/LAN
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: cf31778d773a271ead6a1745197f04eca127ab5d
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841096"
---
# <a name="prepare-certificates-and-network-profiles-for-microsoft-managed-desktop"></a>Preparare certificati e profili di rete per Microsoft Managed Desktop  
 
L'autenticazione basata su certificato è un requisito comune per i clienti che utilizzano Microsoft Managed Desktop. Potrebbe essere necessario disporre di certificati per accedere a Wi-Fi o LAN, per connettersi a soluzioni VPN o per accedere alle risorse interne nell'organizzazione.   
 
Poiché i dispositivi Microsoft Managed Desktop vengono aggiunti a Azure Active Directory (Azure AD) e sono gestiti da Microsoft Intune, è necessario distribuire tali certificati utilizzando un protocollo SCEP (Simple Certificate confirmation Protocol) o un'infrastruttura di certificati PKCS (Public Key Cryptography Standard) integrata con Intune.    
 
## <a name="certificate-requirements"></a>Requisiti per i certificati 
 
I certificati radice sono necessari per distribuire i certificati tramite un'infrastruttura SCEP o PKCS. Altre applicazioni e servizi nell'organizzazione potrebbero richiedere la distribuzione dei certificati radice nei dispositivi Microsoft Managed Desktop.    
 
Prima di distribuire i certificati di SCEP o PKCS in Microsoft Managed Desktop, è necessario raccogliere i requisiti per ogni servizio che richiede un utente o un certificato di dispositivo nell'organizzazione. Per semplificare l'attività, è possibile utilizzare uno dei modelli di pianificazione seguenti:  
 
- [Modello di certificato PKCS](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/PKCS-certificate-template.xlsx) 
- [Modello di certificato di SCEP](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/SCEP-certificate-template.xlsx)

  
## <a name="wi-fi-connectivity-requirements"></a>Requisiti di connettività Wi-Fi

Per consentire a un dispositivo di essere fornito automaticamente con la configurazione Wi-Fi necessaria per la rete aziendale, potrebbe essere necessario un profilo di configurazione Wi-Fi. È possibile configurare Microsoft Managed Desktop per distribuire questi profili nei propri dispositivi. Se la sicurezza della rete richiede che i dispositivi facciano parte del dominio locale, potrebbe essere necessario valutare l'infrastruttura di rete Wi-Fi per assicurarsi che sia compatibile con i dispositivi Microsoft Managed Desktop (i dispositivi Microsoft Managed Desktop sono solo di Azure AD-join). 
 
Prima di distribuire una configurazione di Wi-Fi ai dispositivi Microsoft Managed Desktop, sarà necessario raccogliere i requisiti dell'organizzazione per ogni rete di Wi-Fi. Per semplificare l'attività, è possibile utilizzare questo [modello di profilo WiFi](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx).
 
 
## <a name="wired-connectivity-requirements-and-8021x-authentication"></a>Requisiti di connettività cablata e autenticazione 802.1 x 
 
Se si utilizza l'autenticazione 802.1 x per proteggere l'accesso da dispositivi alla rete locale (LAN), sarà necessario inserire i dettagli di configurazione necessari per i dispositivi Microsoft Managed Desktop. I dispositivi Microsoft Managed Desktop che eseguono Windows 10, versione 1809 o versioni successive supportano la distribuzione di una configurazione 802.1 x tramite il provider di servizi di configurazione di WiredNetwork (CSP). Per ulteriori informazioni, vedere [WIREDNETWORK CSP](https://docs.microsoft.com/windows/client-management/mdm/wirednetwork-csp) Documentation. 
 
Prima di distribuire un profilo di configurazione di rete cablata ai dispositivi Microsoft Managed Desktop, raccogliere i requisiti dell'organizzazione per la rete aziendale cablata. Dopo l'aggiunta al tenant, è possibile alzarsi di livello al ruolo di amministratore verificando di essere proprietari del dominio, mediante la procedura seguente: 
 
 
1. Accedere a un dispositivo che dispone del profilo 802.1 x esistente configurato ed è connesso alla rete LAN.  
2. Aprire un prompt dei comandi con credenziali amministrative. 
3. Individuare il nome dell'interfaccia LAN eseguendo l' **interfaccia netsh interface show**. 
4. Esportare il codice XML del profilo LAN eseguendo **netsh lan export profile folder =.  Interface = "interface_name"**. 
5. Se è necessario testare il profilo esportato sul dispositivo Microsoft Managed Desktop, eseguire **Netsh LAN Add profile filename = "PATH_AND_FILENAME.xml" Interface = "INTERFACE_NAME"**. 
 
 
## <a name="deploy-certificate-infrastructure"></a>Distribuire l'infrastruttura di certificati  
 
Se si dispone già di un'infrastruttura SCEP o PKCS esistente con Intune e questo approccio soddisfa i requisiti, è possibile utilizzarlo anche per Microsoft Managed Desktop. Se non esiste già un'infrastruttura SCEP o PKCS, è necessario prepararne una.  
 
Per ulteriori informazioni, vedere [Configure a certificate profile for your devices in Microsoft Intune](https://docs.microsoft.com/intune/certificates-configure). 
 
 
 
## <a name="deploy-a-lan-profile"></a>Distribuire un profilo LAN 
 
Dopo aver esportato il profilo LAN, è possibile preparare i criteri per Microsoft Managed Desktop attenendosi alla procedura seguente:   
 
1. Creare un profilo personalizzato in Microsoft Intune per il profilo LAN utilizzando le impostazioni seguenti (vedere [Use Custom Settings for Windows 10 Devices in Intune](https://docs.microsoft.com/intune/custom-settings-windows-10)). In **impostazioni di URI OMA personalizzate** selezionare **Aggiungi** e quindi immettere i valori seguenti: 
    - Nome: *Modern Workplace-Windows 10 LAN profile* 
    - Descrizione: immettere una descrizione che fornisce una panoramica dell'impostazione e qualsiasi altro dettaglio importante. 
    - OMA-URI (distinzione tra maiuscole e minuscole): Enter *./Device/vendor/MSFT/WiredNetwork/LanXML*
    - Tipo di dati: selezionare **stringa (file XML)**. 
    - XML personalizzato: caricare il file XML esportato.
2. Inviare una richiesta di supporto alle operazioni IT di Microsoft Managed Desktop tramite il portale di amministrazione di Microsoft Managed Desktop per esaminare e distribuire il profilo di configurazione in "dispositivi di lavoro moderni – test". Microsoft Managed Desktop IT Operations consente di sapere quando la richiesta viene completata tramite la richiesta di supporto nel portale di amministrazione.
 
## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Distribuzione dei certificati e del profilo Wi-Fi/VPN 
 
 
Per distribuire certificati e profili, eseguire la procedura seguente:

1. Creare un profilo per ogni certificato radice e intermedio (vedere [creare profili di certificati attendibili](https://docs.microsoft.com/intune/protect/certificates-configure#step-3-create-trusted-certificate-profiles). Ognuno di questi profili deve avere una descrizione che include una data di scadenza nel formato gg/MM/AAAA. **I profili dei certificati senza una data di scadenza non verranno distribuiti.**
2. Creare un profilo per ogni SCEP o PKCS (vedere [Create a SCEP certificate profile](https://docs.microsoft.com/intune/protect/certificates-scep-configure#create-a-scep-certificate-profile) or [Create a PKCS certificate profile](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) ognuno di questi profili deve avere una descrizione che includa una data di scadenza nel formato gg/mm/aaaa. **I profili dei certificati senza una data di scadenza non verranno distribuiti.**
3. Creare un profilo per ogni rete WiFi aziendale (vedere [Impostazioni Wi-Fi per i dispositivi Windows 10 e versioni successive](https://docs.microsoft.com/intune/wi-fi-settings-windows)).
4. Creare un profilo per ogni VPN aziendale (vedere [Windows 10 e le impostazioni dei dispositivi olografici di Windows per aggiungere connessioni VPN tramite Intune](https://docs.microsoft.com/intune/vpn-settings-windows-10)).
5. Inviare una richiesta di supporto intitolata "distribuzione di certificati" o "distribuzione del profilo Wi-Fi" per le operazioni IT di Microsoft Managed Desktop tramite il portale di amministrazione di Microsoft Managed Desktop per esaminare e distribuire il profilo di configurazione in "dispositivi di lavoro moderni – test". Microsoft Managed Desktop IT Operations consente di sapere quando la richiesta è stata completata tramite la richiesta di supporto nel portale di amministrazione. 
 
 
