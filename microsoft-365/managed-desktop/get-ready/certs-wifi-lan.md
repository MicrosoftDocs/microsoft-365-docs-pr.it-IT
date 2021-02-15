---
title: Preparare certificati e profili di rete per Microsoft Managed Desktop
description: certs/wifi/lan
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
 
L'autenticazione basata su certificati è un requisito comune per i clienti che usano Microsoft Managed Desktop. Potrebbe essere necessario che i certificati Wi-Fi o LAN, per connettersi a soluzioni VPN o per accedere alle risorse interne dell'organizzazione.   
 
Poiché i dispositivi Microsoft Managed Desktop sono aggiunti ad Azure Active Directory (Azure AD) e sono gestiti da Microsoft Intune, è necessario distribuire tali certificati utilizzando un'infrastruttura di certificati SCEP (Simple Certificate Enrollment Protocol) o PKCS (Public Key Cryptography Standard) integrata con Intune.    
 
## <a name="certificate-requirements"></a>Requisiti per i certificati 
 
I certificati radice sono necessari per distribuire i certificati tramite un'infrastruttura SCEP o PKCS. Altre applicazioni e servizi dell'organizzazione potrebbero richiedere la distribuzione di certificati radice nei dispositivi Microsoft Managed Desktop.    
 
Prima di distribuire i certificati SCEP o PKCS in Microsoft Managed Desktop, è consigliabile raccogliere i requisiti per ogni servizio che richiede un certificato utente o dispositivo nell'organizzazione. Per semplificare questa attività, è possibile utilizzare uno dei modelli di pianificazione seguenti:  
 
- [Modello di certificato PKCS](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/PKCS-certificate-template.xlsx) 
- [Modello di certificato SCEP](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/SCEP-certificate-template.xlsx)

  
## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi connettività

Per consentire a un dispositivo di essere fornito automaticamente con la configurazione Wi-Fi necessaria per la rete aziendale, potrebbe essere necessario un Wi-Fi di configurazione. È possibile configurare Microsoft Managed Desktop per distribuire questi profili nei dispositivi. Se la sicurezza di rete richiede che i dispositivi siano parte del dominio locale, potrebbe essere necessario valutare anche l'infrastruttura di rete di Wi-Fi per verificare che sia compatibile con i dispositivi Microsoft Managed Desktop (i dispositivi Microsoft Managed Desktop sono aggiunti solo ad Azure AD). 
 
Prima di distribuire una configurazione Wi-Fi nei dispositivi Microsoft Managed Desktop, sarà necessario raccogliere i requisiti dell'organizzazione per ogni Wi-Fi rete. Per semplificare questa attività, puoi usare questo modello [di profilo WiFi.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx)
 
 
## <a name="wired-connectivity-requirements-and-8021x-authentication"></a>Requisiti di connettività cablata e autenticazione 802.1x 
 
Se si utilizza l'autenticazione 802.1x per proteggere l'accesso dai dispositivi alla rete locale (LAN), sarà necessario inviare i dettagli di configurazione necessari ai dispositivi Microsoft Managed Desktop. I dispositivi Microsoft Managed Desktop che eseguono Windows 10 versione 1809 o successiva supportano la distribuzione di una configurazione 802.1x tramite il provider di servizi di configurazione (CSP) WiredNetwork. Per altre informazioni, vedi la documentazione del provider di servizi di configurazione [WiredNetwork.](https://docs.microsoft.com/windows/client-management/mdm/wirednetwork-csp) 
 
Prima di distribuire un profilo di configurazione della rete cablata ai dispositivi Microsoft Managed Desktop, raccogliere i requisiti dell'organizzazione per la rete aziendale cablata. Dopo l'aggiunta al tenant, è possibile alzarsi di livello al ruolo di amministratore verificando di essere proprietari del dominio, mediante la procedura seguente: 
 
 
1. Accedere a un dispositivo con il profilo 802.1x esistente configurato ed è connesso alla rete LAN.  
2. Aprire un prompt dei comandi con credenziali amministrative. 
3. Trovare il nome dell'interfaccia LAN eseguendo **netsh interface show interface.** 
4. Esportare il codice XML del profilo LAN eseguendo **netsh lan export profile folder=.  Interface="interface_name"**. 
5. Se è necessario testare il profilo esportato nel dispositivo Microsoft Managed Desktop, eseguire **netsh lan add profile filename="PATH_AND_FILENAME.xml" interface="INTERFACE_NAME".** 
 
 
## <a name="deploy-certificate-infrastructure"></a>Distribuire l'infrastruttura dei certificati  
 
Se hai già un'infrastruttura SCEP o PKCS esistente con Intune e questo approccio soddisfa i tuoi requisiti, puoi usarlo anche per Microsoft Managed Desktop. Se non esiste già un'infrastruttura SCEP o PKCS, sarà necessario prepararne una.  
 
Per altre informazioni, vedere [Configurare un profilo di certificato per i dispositivi in Microsoft Intune.](https://docs.microsoft.com/intune/certificates-configure) 
 
 
 
## <a name="deploy-a-lan-profile"></a>Distribuire un profilo LAN 
 
Dopo aver esportato il profilo LAN, è possibile preparare i criteri per Microsoft Managed Desktop seguendo questi passaggi:   
 
1. Creare un profilo personalizzato in Microsoft Intune per il profilo LAN usando le impostazioni seguenti (vedere Usare le impostazioni personalizzate per i dispositivi [Windows 10 in Intune).](https://docs.microsoft.com/intune/custom-settings-windows-10) In **Impostazioni URI OMA personalizzate** selezionare **Aggiungi** e quindi immettere i valori seguenti: 
    - Nome: *Profilo LAN Workplace-Windows 10* 
    - Descrizione: immettere una descrizione che fornisce una panoramica dell'impostazione e altri dettagli importanti. 
    - URI OMA (maiuscole/minuscole): *immettere ./Device/Vendor/MSFT/WiredNetwork/LanXML*
    - Tipo di dati: select **String (file XML).** 
    - XML personalizzato: carica il file XML esportato.
2. Inviare una richiesta di supporto a Microsoft Managed Desktop IT Operations usando il portale di amministrazione di Microsoft Managed Desktop per esaminare e distribuire il profilo di configurazione in "Modern Workplace Devices – Test". Microsoft Managed Desktop IT Operations ti consente di sapere quando la richiesta viene completata tramite la richiesta di supporto nel portale di amministrazione.
 
## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Distribuire certificati e profilo Wi-Fi/VPN 
 
 
Per distribuire certificati e profili, attenersi alla seguente procedura:

1. Creare un profilo per ogni certificato radice e intermedio (vedere [Creare profili di certificato attendibili).](https://docs.microsoft.com/intune/protect/certificates-configure#step-3-create-trusted-certificate-profiles) Ognuno di questi profili deve avere una descrizione che includa una data di scadenza nel formato GG/MM/AAAA. **I profili certificato senza una data di scadenza non verranno distribuiti.**
2. Creare un profilo per ogni certificato SCEP o PKCS (vedere Creare un profilo di certificato [SCEP](https://docs.microsoft.com/intune/protect/certificates-scep-configure#create-a-scep-certificate-profile) o Creare un profilo certificato [PKCS)](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)Ognuno di questi profili deve avere una descrizione che includa una data di scadenza nel formato GG/MM/AAAA. **I profili certificato senza una data di scadenza non verranno distribuiti.**
3. Crea un profilo per ogni rete WiFi aziendale (vedi impostazioni [Wi-Fi per i dispositivi Windows 10 e versioni successive).](https://docs.microsoft.com/intune/wi-fi-settings-windows)
4. Creare un profilo per ogni VPN aziendale (vedere le impostazioni dei dispositivi [Windows 10 e Windows Holographic](https://docs.microsoft.com/intune/vpn-settings-windows-10)per aggiungere connessioni VPN con Intune).
5. Inviare una richiesta di supporto intitolata "Distribuzione dei certificati" o "Distribuzione del profilo Wi-Fi" alle operazioni IT di Microsoft Managed Desktop usando il portale di amministrazione di Microsoft Managed Desktop per esaminare e distribuire il profilo di configurazione in "Dispositivi aziendali moderni - Test". Microsoft Managed Desktop IT Operations ti consente di sapere quando la richiesta è stata completata tramite la richiesta di supporto nel portale di amministrazione. 
 
 
