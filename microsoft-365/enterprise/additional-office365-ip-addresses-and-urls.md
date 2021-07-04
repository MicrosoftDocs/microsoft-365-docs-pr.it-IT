---
title: Altri endpoint non inclusi nel servizio Web per URL e indirizzo IP di Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/19/2021
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- MOM160
- BCS160
ms.assetid: ''
description: 'Riepilogo: il nuovo servizio Web endpoint non include un numero limitato di endpoint per scenari specifici.'
hideEdit: true
ms.openlocfilehash: 76bfc947460d4c513207c3a53b2f4536282c65e1
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289152"
---
# <a name="additional-endpoints-not-included-in-the-office-365-ip-address-and-url-web-service"></a>Altri endpoint non inclusi nel servizio Web per URL e indirizzo IP di Office 365

Alcuni endpoint di rete sono stati precedentemente pubblicati e non sono stati inclusi nel [servizio Web per URL e indirizzo IP di Office 365](microsoft-365-ip-web-service.md). L'ambito dei servizi Web sono gli endpoint di rete necessari per la connettività di un utente di Office 365 in una rete perimetrale aziendale. Attualmente non sono inclusi:

1. Connettività di rete che potrebbe essere necessaria da un data center Microsoft a una rete cliente (traffico di rete del server ibrido in ingresso).
2. Connettività di rete dai server in una rete cliente nella rete perimetrale (traffico di rete del server in uscita).
3. Scenari non comuni per i requisiti di connettività di rete di un utente.
4. Requisiti di connettività di risoluzione DNS (non elencati di seguito).
5. Siti attendibili di Internet Explorer o Microsoft Edge.

Escluso il DNS, sono tutti facoltativi per la maggior parte dei clienti, a meno che non sia necessario lo scenario specifico descritto.

<br>

****

|Riga|Scopo|Destinazione|Tipo|
|---|---|---|---|
|1 |[Servizio di importazione](https://support.office.com/article/use-network-upload-to-import-your-organization-pst-files-to-office-365-103f940c-0468-4e1a-b527-cc8ad13a5ea6) per l'inserimento di file e PST|Vedere il [servizio di importazione](https://support.office.com/article/use-network-upload-to-import-your-organization-pst-files-to-office-365-103f940c-0468-4e1a-b527-cc8ad13a5ea6) per i requisiti aggiuntivi.|Scenario in uscita non comune|
|2 |[Assistente supporto e ripristino Microsoft per Office 365](https://diagnostics.office.com/#/)|<https://autodiscover.outlook.com> <br> <https://officecdn.microsoft.com> <br> <https://api.diagnostics.office.com> <br> <https://apibasic.diagnostics.office.com> <br> <https://autodiscover-s.outlook.com> <br> <https://cloudcheckenabler.azurewebsites.net> <br> <https://login.live.com> <br> <https://login.microsoftonline.com> <br> <https://login.windows.net> <br> <https://o365diagtelemetry.trafficmanager.net> <br> <https://odc.officeapps.live.com> <br> <https://offcatedge.azureedge.net> <br> <https://officeapps.live.com> <br> <https://outlook.office365.com> <br> <https://outlookdiagnostics.azureedge.net>|Traffico del server in uscita|
|3 |Azure AD Connect (opzione con SSO) – WinRM e sessione remota di PowerShell|Ambiente STS del cliente (server AD FS e proxy AD FS) \| porte TCP 80 e 443|Traffico del server in ingresso|
|4 |STS come server proxy AD FS (solo per clienti federati)|STS del cliente (come proxy AD FS) \| porte TCP 443 o TCP 49443 con ClientTLS|Traffico del server in ingresso|
|5 |[Messaggistica unificata di Exchange Online/integrazione SBC](/exchange/voice-mail-unified-messaging/telephone-system-integration-with-um/configuration-notes-for-session-border-controllers)|Bidirezionale tra Session Border Controller locale e \* .um.outlook.com|Solo traffico del server in uscita|
|6 |Migrazione delle cassette postali. Quando la migrazione delle cassette postali viene avviata da Exchange ibrido locale [a](/exchange/exchange-deployment-assistant) Office 365, Office 365 si connetterà al server Servizi Web Exchange pubblicato/Servizi di replica delle cassette postali (MRS). Se sono necessari gli indirizzi IP NAT utilizzati dai server Exchange Online per limitare le connessioni in ingresso da intervalli IP di origine specifici, questi sono elencati negli intervalli [DI URL &](urls-and-ip-address-ranges.md) di Office 365 nell'area di servizio "Exchange Online". <p> È necessario assicurarsi che l'accesso agli endpoint EWS pubblicati come OWA non sia incisivo assicurandosi che il proxy MRS si risolva in un fqdn e un indirizzo IP pubblico separati prima di limitare le connessioni TCP 443 da intervalli IP di origine specifici.|Proxy EWS/MRS locale del cliente <br> Porta TCP 443|Traffico del server in ingresso|
|7 |Funzioni per coesistenza di [Exchange ibrido](/exchange/exchange-deployment-assistant), come la condivisione di informazioni sulla disponibilità.|Server Exchange locale del cliente|Traffico del server in ingresso|
|8 |Autenticazione proxy di [Exchange ibrido](/exchange/exchange-deployment-assistant)|STS locale del cliente|Traffico del server in ingresso|
|9 |Consente di configurare [Exchange ibrido](/exchange/exchange-deployment-assistant) usando la [Configurazione ibrida guidata di Exchange](/exchange/hybrid-configuration-wizard) <p> Nota: gli endpoint sono necessari solo per configurare Exchange ibrido|domains.live.com sulle porte TCP 80 e 443, necessarie solo per la configurazione ibrida guidata di Exchange 2010 SP3 <p> Indirizzi IP GCC High, DoD: 40.118.209.192/32; 168.62.190.41/32 <p> Worldwide Commercial & GCC: \* .store.core.windows.net; asl.configure.office.com; tds.configure.office.com; mshybridservice.trafficmanager.net ; <br> aka.ms/hybridwizard; <br> shcwreleaseprod.blob.core.windows.net/shcw/ \* ;|Solo traffico del server in uscita|
|10 |Il servizio di rilevamento automatico è usato negli scenari di [Exchange ibrido](/exchange/exchange-deployment-assistant) con [autenticazione moderna ibrida con Outlook per iOS e Android](/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth) <p> `*.acompli.net` <br> `*.outlookmobile.com` <br> `*.outlookmobile.us` <br> `52.125.128.0/20` <br> `52.127.96.0/23`|Server Exchange locale del cliente in TCP 443|Traffico del server in ingresso|
|11 |Exchange'autenticazione ibrida di Azure AD|*.msappproxy.net|Traffico solo server in uscita TCP|
|12 |Skype for Business in Office 2016 include la condivisione dello schermo basata su video che utilizza le porte UDP. I precedenti client di Skype for Business in Office 2013 e versioni precedenti utilizzavano la porta RDP su TCP 443.|Porta TCP 443 aperta su 52.112.0.0/14|Client precedenti di Skype for Business in Office 2013 e versioni precedenti|
|13 |Connettività server ibrida locale di Skype for Business per Skype for Business online|13.107.64.0/18, 52.112.0.0/14 <br> Porte UDP 50.000-59.999 <br> Porte TCP 50.000-59.999; 5061|Connettività in uscita del server Skype for Business locale|
|14 |La rete PSTN cloud con connettività ibrida locale richiede la connettività di rete aperta agli host locali. Per ulteriori dettagli sulle configurazioni ibride di Skype for Business Online,|Vedere [Pianificare la connettività ibrida tra Skype for Business Server e Office 365](/skypeforbusiness/hybrid/plan-hybrid-connectivity)|Ingresso ibrido locale di Skype for Business|
|15|**FQDN di autenticazione e identità** <p> Il nome di dominio completo (FQDN) `secure.aadcdn.microsoftonline-p.com` deve essere situato nell'area siti attendibili di Edge o Internet Explorer (IE) del client per poter funzionare.||Siti attendibili|
|16 |**FQDN di Microsoft Teams** <p> Se si usa Internet Explorer o Microsoft Edge, è necessario attivare i cookie dei siti Web visualizzati e di terze parti e aggiungere i nomi di dominio completo per Teams per i siti attendibili. Si tratta di un'aggiunta all'intera famiglia di FQDN, CDN e telemetrie elencata in riga 14. Vedere [Problemi noti di Microsoft Teams](/microsoftteams/known-issues) per ulteriori informazioni.||Siti attendibili|
|17 |**FQDN di SharePoint Online e OneDrive for Business** <p> Tutti i nomi di dominio completo di ".sharepoint.com" con "\<tenant\>" nel nome di dominio completo devono essere situati nell'area siti attendibili di Edge o IE del client per poter funzionare. Oltre all’intera famiglia di FQDN, CDN e telemetria elencata alla riga 14, è necessario aggiungere anche questi endpoint.||Siti attendibili|
|18 |**Yammer**  <br> Yammer è disponibile solo nel browser e necessita di un'autenticazione proxy da parte dell'utente. Tutti i FQDN di Yammer devono essere situati nell'area siti attendibili di Edge o IE del client per poter funzionare.||Siti attendibili|
|19|Usare [Azure AD Connect](/azure/active-directory/hybrid/) per sincronizzare gli account utente locali con Azure AD.|Vedere[Porte e protocolli necessari per la soluzione ibrida di gestione delle identità](/azure/active-directory/hybrid/reference-connect-ports), [Risolvere i problemi di connettività di Azure AD](/azure/active-directory/hybrid/tshoot-connect-connectivity) e [Installazione dell'agente di Azure AD Connect Health](/azure/active-directory/hybrid/how-to-connect-health-agent-install#outbound-connectivity-to-the-azure-service-endpoints).|Solo traffico del server in uscita|
|20|[Azure AD Connect](/azure/active-directory/hybrid/) con 21 ViaNet in Cina per sincronizzare gli account utente locali con Azure AD.|\*.digicert.com:80 <BR> \*.entrust.net:80 <BR> \*.chinacloudapi.cn:443 <br> secure.aadcdn.partner.microsoftonline-p.cn:443 <br> \*.partner.microsoftonline.cn:443 <p> Vedere anche [Risolvere i problemi in ingresso con i problemi di connettività di Azure AD Connect](https://docs.azure.cn/zh-cn/active-directory/hybrid/tshoot-connect-connectivity).|Solo traffico del server in uscita|
| 21|Microsoft Stream (richiede il token utente Azure AD). <br> Office 365 internazionale (incluso GCC)|\*.cloudapp.net <br> \*.api.microsoftstream.com <br> \*.notification.api.microsoftstream.com <br> amp.azure.net <br> api.microsoftstream.com <br> az416426.vo.msecnd.net <br> s0.assets-yammer.com <br> vortex.data.microsoft.com <br> web.microsoftstream.com <br> Porta TCP 443|Traffico del server in ingresso|
|22|Usare il server MFA per le richieste di autenticazione a più fattori, sia per le nuove installazioni del server che per la configurazione con Active Directory Domain Services (AD DS).|Vedere [Introduzione al server Azure AD Multi-Factor Authentication.](/azure/active-directory/authentication/howto-mfaserver-deploy#plan-your-deployment)|Solo traffico del server in uscita|
|23|Notifiche di modifica di Microsoft Graph <p> Gli sviluppatori possono usare le [notifiche di modifica](/graph/webhooks?context=graph%2fapi%2f1.0&view=graph-rest-1.0) per sottoscrivere eventi in Microsoft Graph.|\*.cloudapp.net <br> 104.43.130.21, 137.116.169.230, 13.79.38.63, 104.214.39.228 <p> Public Cloud: 168.63.250.205, 52.161.9.202, 40.68.103.62, 13.89.60.223, 23.100.95.104, 40.113.95.219, 104.214.32.10, 168.63.237.145, 52.161.110.176, 52.174.177.183, 13.85.192.59, 13.85.192.123, 13.86.37.15, 13.89.108.233, 13.89.104.147, 20.44.210.83, 20.44.210.146, 40.76.162.99, 40.76.162.42, 40.74.203.28, 40.74.203.27, 51.104.159.213, 51.104.159.181, 51.124.75.43, 51.124.73.177, 51.138.90.7, 51.138.90.52, 52.139.153.222, 52.139.170.157, 52.139.170.47, 52.142.114.29, 52.142.115.31, 52.147.213.251, 52.147.213.181, 52.148.24.136, 52.148.27.39, 52.148.115.48, 52.148.114.238, 52.154.246.238, 52.159.23.209, 52.159.17.84, 52.184.94.140 <p> Microsoft Cloud for US Government: 52.244.231.173, 52.238.76.151, 52.244.250.211, 52.238.78.108, 52.243.147.249, 52.243.148.19, 52.243.157.104, 52.243.157.105, 52.244.33.45, 52.244.35.174, 52.244.111.156, 52.244.111.170 <p> Microsoft Cloud Germania: 51.4.231.136, 51.5.243.223, 51.4.226.154, 51.5.244.215, 51.4.150.206, 51.4.150.235, 51.5.147.130, 51.5.148.1033 <p> Microsoft Cloud China gestito da 21Vianet: 139.219.15.33, 42.159.154.223, 42.159.88.79, 42.159.155.77, 40.72.155.199, 40.72.155.216, 40.125.138.23, 40.125.136.69, 42.159.72.35, 42.159.72.47, 42.159.180.55, 42.159.180.56 <br> Porta TCP 443 <p> Nota: gli sviluppatori possono specificare porte diverse al momento della creazione di sottoscrizioni.|Traffico del server in ingresso|
|

## <a name="related-topics"></a>Argomenti correlati

[Gestione degli endpoint di Office 365](managing-office-365-endpoints.md)
  
[Monitorare la connettività di Microsoft 365](./monitor-connectivity.md)
  
[Connettività client](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b)
  
[Reti per la distribuzione di contenuti](https://support.office.com/article/content-delivery-networks-0140f704-6614-49bb-aa6c-89b75dcd7f1f)
  
[Intervalli IP di Azure e tag di servizio - Cloud pubblico](https://www.microsoft.com/download/details.aspx?id=56519)

[Intervalli IP di Azure e tag di servizio - Cloud per enti pubblici statunitensi](https://www.microsoft.com/download/details.aspx?id=57063)

[Intervalli IP di Azure e tag di servizio - Germania Cloud](https://www.microsoft.com/download/details.aspx?id=57064)

[Intervalli IP di Azure e tag di servizio - China Cloud](https://www.microsoft.com/download/details.aspx?id=57062)
  
[Spazio IP pubblico di Microsoft](https://www.microsoft.com/download/details.aspx?id=53602)
