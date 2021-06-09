---
title: Preparare certificati e profili di rete per Microsoft Managed Desktop
description: Requisiti dei certificati e connettività Wi-Fi
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: a59add6f6821824f189703b3dedd35fda313ec31
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574584"
---
# <a name="prepare-certificates-and-network-profiles-for-microsoft-managed-desktop"></a>Preparare certificati e profili di rete per Microsoft Managed Desktop  
 
L'autenticazione basata su certificato è un requisito comune per i clienti che usano Microsoft Managed Desktop. Potrebbe essere necessario che i certificati Wi-Fi o LAN, per connettersi a soluzioni VPN o per accedere alle risorse interne dell'organizzazione.   
 
Poiché i dispositivi Microsoft Managed Desktop sono aggiunti a Azure Active Directory (Azure AD) e sono gestiti da Microsoft Intune, è necessario distribuire tali certificati utilizzando un'infrastruttura di certificato SCEP (Simple Certificate Enrollment Protocol) o PKCS (Public Key Cryptography Standard) integrata con Intune.    
 
## <a name="certificate-requirements"></a>Requisiti per i certificati 
 
I certificati radice sono necessari per distribuire i certificati tramite un'infrastruttura SCEP o PKCS. Altre applicazioni e servizi dell'organizzazione potrebbero richiedere la distribuzione di certificati radice nei dispositivi Microsoft Managed Desktop di archiviazione.    
 
Prima di distribuire i certificati SCEP o PKCS Microsoft Managed Desktop, è consigliabile raccogliere i requisiti per ogni servizio che richiede un certificato utente o dispositivo nell'organizzazione. Per semplificare questa attività, è possibile utilizzare uno dei modelli di pianificazione seguenti:  
 
- [Modello di certificato PKCS](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/PKCS-certificate-template.xlsx) 
- [Modello di certificato SCEP](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/SCEP-certificate-template.xlsx)

  
## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi di connettività

Per consentire a un dispositivo di essere fornito automaticamente con la configurazione Wi-Fi necessaria per la rete aziendale, potrebbe essere necessario un Wi-Fi di configurazione. È possibile configurare Microsoft Managed Desktop distribuire questi profili nei dispositivi. Se la sicurezza di rete richiede che i dispositivi siano parte del dominio locale, potrebbe anche essere necessario valutare l'infrastruttura di rete di Wi-Fi per verificare che sia compatibile con i dispositivi Microsoft Managed Desktop (i dispositivi Microsoft Managed Desktop sono aggiunti solo ad Azure AD). 
 
Prima di distribuire una configurazione Wi-Fi in Microsoft Managed Desktop, sarà necessario raccogliere i requisiti dell'organizzazione per ogni Wi-Fi rete. Per semplificare questa attività, puoi usare questo modello [di profilo WiFi.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx)
 
 
## <a name="wired-connectivity-requirements-and-8021x-authentication"></a>Requisiti di connettività cablata e autenticazione 802.1x 
 
Se si utilizza l'autenticazione 802.1x per proteggere l'accesso dai dispositivi alla rete locale (LAN), sarà necessario inviare i dettagli di configurazione necessari ai dispositivi Microsoft Managed Desktop. Microsoft Managed Desktop dispositivi che eseguono Windows 10 versione 1809 o successiva supportano la distribuzione di una configurazione 802.1x tramite il provider di servizi di configurazione WiredNetwork. Per ulteriori informazioni, vedere [la documentazione CSP WiredNetwork.](/windows/client-management/mdm/wirednetwork-csp) 
 
Prima di distribuire un profilo di configurazione di rete cablata Microsoft Managed Desktop dispositivi, raccogliere i requisiti dell'organizzazione per la rete aziendale cablata. Dopo l'aggiunta al tenant, è possibile alzarsi di livello al ruolo di amministratore verificando di essere proprietari del dominio, mediante la procedura seguente: 
 
 
1. Accedere a un dispositivo con il profilo 802.1x esistente configurato e connesso alla rete LAN.  
2. Aprire un prompt dei comandi con credenziali amministrative. 
3. Trovare il nome dell'interfaccia LAN eseguendo **netsh interface show interface**. 
4. Esportare il codice XML del profilo LAN eseguendo **netsh lan export profile folder=.  Interface="interface_name"**. 
5. Se devi testare il profilo esportato nel dispositivo Microsoft Managed Desktop, esegui **netsh lan add profile filename="PATH_AND_FILENAME.xml" interface="INTERFACE_NAME"**. 
 
 
## <a name="deploy-certificate-infrastructure"></a>Distribuire l'infrastruttura dei certificati  
 
Se hai già un'infrastruttura SCEP o PKCS esistente con Intune e questo approccio soddisfa i tuoi requisiti, puoi usarlo anche per Microsoft Managed Desktop. Se non esiste già un'infrastruttura SCEP o PKCS, sarà necessario prepararne una.  
 
Per altre informazioni, vedi [Configurare un profilo di certificato per i dispositivi in Microsoft Intune](/intune/certificates-configure). 
 
 
 
## <a name="deploy-a-lan-profile"></a>Distribuire un profilo LAN 
 
Dopo aver esportato il profilo LAN, è possibile preparare i criteri per Microsoft Managed Desktop seguendo questi passaggi:   
 
1. Creare un profilo personalizzato in Microsoft Intune per il profilo LAN usando le impostazioni seguenti (vedere Usare le impostazioni personalizzate per Windows 10 [dispositivi in Intune](/intune/custom-settings-windows-10)). In **Custom OMA-URI Impostazioni** selezionare **Add** e quindi immettere i valori seguenti: 
    - Nome: *Modern Workplace-Windows 10 LAN Profile* 
    - Descrizione: immettere una descrizione che fornisce una panoramica dell'impostazione e altri dettagli importanti. 
    - URI OMA (distinzione tra maiuscole e minuscole): *immetti ./Device/Vendor/MSFT/WiredNetwork/LanXML*
    - Tipo di dati: selezionare **Stringa (file XML).** 
    - XML personalizzato: Upload il file XML esportato.
2. Inviare una richiesta di supporto Microsoft Managed Desktop it operations usando il portale di amministrazione di Microsoft Managed Desktop per esaminare e distribuire il profilo di configurazione in "Modern Workplace Devices – Test". Microsoft Managed Desktop Le operazioni IT ti consentiranno di sapere quando la richiesta viene completata tramite la richiesta di supporto nel portale di amministrazione.
 
## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Distribuire certificati e profilo Wi-Fi/VPN 
 
 
Per distribuire certificati e profili, attenersi alla seguente procedura:

1. Creare un profilo per ognuno dei certificati radice e intermedio (vedere [Create trusted certificate profiles](/intune/protect/certificates-configure#step-3-create-trusted-certificate-profiles). Ognuno di questi profili deve avere una descrizione che includa una data di scadenza nel formato GG/MM/AAAA. **I profili certificato senza una data di scadenza non verranno distribuiti.**
2. Creare un profilo per ogni certificato SCEP o PKCS (vedere [Create a SCEP certificate profile](/intune/protect/certificates-scep-configure#create-a-scep-certificate-profile) o Create a [PKCS certificate profile](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) Ognuno di questi profili deve avere una descrizione che includa una data di scadenza in formato GG/MM/AAAA. **I profili certificato senza una data di scadenza non verranno distribuiti.**
3. Crea un profilo per ogni rete WiFi aziendale (vedi Impostazioni Wi-Fi per Windows 10 [e dispositivi successivi).](/intune/wi-fi-settings-windows)
4. Creare un profilo per ogni VPN aziendale (vedere Windows 10 e Windows impostazioni del dispositivo [Holographic](/intune/vpn-settings-windows-10)per aggiungere connessioni VPN con Intune ).
5. Inviare una richiesta di supporto intitolata "Distribuzione di certificati" o "Distribuzione profili Wi-Fi" a Microsoft Managed Desktop IT Operations usando il portale di amministrazione di Microsoft Managed Desktop per esaminare e distribuire il profilo di configurazione in "Modern Workplace Devices – Test". Microsoft Managed Desktop Le operazioni IT ti consentiranno di sapere quando la richiesta è stata completata tramite la richiesta di supporto nel portale di amministrazione. 
 
## <a name="steps-to-get-ready"></a>Passaggi per prepararsi

1. Esaminare [i prerequisiti per Microsoft Managed Desktop](prerequisites.md).
2. Utilizzare [gli strumenti di valutazione della conformità](readiness-assessment-tool.md).
3. [Prerequisiti per gli account Guest](guest-accounts.md)
4. [Configurazione rete in Microsoft Managed Desktop](network.md)
5. [Preparare certificati e profili di rete per Microsoft Managed Desktop](certs-wifi-lan.md) (questo articolo)
6. [Preparare l'accesso alle risorse locali per Microsoft Managed Desktop](authentication.md)
7. [App in Microsoft Managed Desktop](apps.md)
8. [Preparare unità mappate per Microsoft Managed Desktop](mapped-drives.md)
9. [Preparare risorse di stampa per Microsoft Managed Desktop](printing.md) 
