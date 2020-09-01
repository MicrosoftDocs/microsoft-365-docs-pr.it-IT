---
title: Altri endpoint non inclusi nel servizio Web per URL e indirizzo IP di Office 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/29/2020
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
ms.openlocfilehash: 821332f573eb8499a01838a5dc9941c9844086a3
ms.sourcegitcommit: 04f196528a7a91b404478553433af3fa94d7eee7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2020
ms.locfileid: "47317506"
---
# <a name="additional-endpoints-not-included-in-the-office-365-ip-address-and-url-web-service"></a>Altri endpoint non inclusi nel servizio Web per URL e indirizzo IP di Office 365

Alcuni endpoint di rete sono stati precedentemente pubblicati e non sono stati inclusi nel [servizio Web per URL e indirizzo IP di Office 365](microsoft-365-ip-web-service.md). L'ambito dei servizi Web sono gli endpoint di rete necessari per la connettività di un utente di Office 365 in una rete perimetrale aziendale. Attualmente non sono inclusi:

1. Connettività di rete che potrebbe essere necessaria da un data center Microsoft a una rete cliente (traffico di rete del server ibrido in ingresso).
2. Connettività di rete dai server in una rete cliente nella rete perimetrale (traffico di rete del server in uscita).
3. Scenari non comuni per i requisiti di connettività di rete di un utente.
4. Requisiti di connettività di risoluzione DNS (non elencati di seguito).
5. Siti attendibili di Internet Explorer o Microsoft Edge.

Escluso il DNS, sono tutti facoltativi per la maggior parte dei clienti, a meno che non sia necessario lo scenario specifico descritto.

| Riga | Scopo | Destinazione | Tipo |
|:-----|:-----|:-----|:-----|
| 1  | [Servizio di importazione](https://support.office.com/article/use-network-upload-to-import-your-organization-pst-files-to-office-365-103f940c-0468-4e1a-b527-cc8ad13a5ea6) per l'inserimento di file e PST | Vedere il [servizio di importazione](https://support.office.com/article/use-network-upload-to-import-your-organization-pst-files-to-office-365-103f940c-0468-4e1a-b527-cc8ad13a5ea6) per i requisiti aggiuntivi. | Scenario in uscita non comune |
| 2  | [Assistente supporto e ripristino Microsoft per Office 365](https://diagnostics.office.com/#/)  | https<span>://</span>autodiscover.outlook.com <BR> <span>https://</span>officecdn.microsoft.com <BR> <span>https://</span>api.diagnostics.office.com <BR> <span>https://</span>apibasic.diagnostics.office.com <BR> <span>https://</span>autodiscover-s.outlook.com <BR> <span>https://</span>cloudcheckenabler.azurewebsites.net <BR> <span>https://</span>dcs-staging.azure-api.net <BR> <span>https://</span>login.live.com <BR> <span>https://</span>login.microsoftonline.com <BR> <span>https://</span>login.windows.net <BR> <span>https://</span>o365diagtelemetry.trafficmanager.net <BR> <span>https://</span>odc.officeapps.live.com <BR> <span>https://</span>offcatedge.azureedge.net <BR> <span>https://</span>officeapps.live.com <BR> <span>https://</span>outlook.office365.com <BR> <span>https://</span>outlookdiagnostics.azureedge.net | Traffico del server in uscita |
| 3  | Azure AD Connect (opzione con SSO) – WinRM e sessione remota di PowerShell | Ambiente STS del cliente (server AD FS e proxy AD FS) \| porte TCP 80 e 443 | Traffico del server in ingresso |
| 4  | STS come server proxy AD FS (solo per clienti federati) | STS del cliente (come proxy AD FS) \| porte TCP 443 o TCP 49443 con ClientTLS | Traffico del server in ingresso |
| 5  | [Messaggistica unificata di Exchange Online/integrazione SBC](https://technet.microsoft.com/library/jj673565.aspx) | Bidirezionale tra session border controller locale e *.um.outlook.com | Solo traffico del server in uscita |
| 6  | Migrazione della cassetta postale. Quando viene avviata la migrazione della cassetta postale da [Exchange ibrido](https://docs.microsoft.com/exchange/exchange-deployment-assistant) locale a Office 365, Office 365 si connette al server pubblicato di Servizi Web Exchange (EWS) / Servizi di replica delle cassette postali (MRS). Se sono necessari gli indirizzi IP NAT utilizzati dai server di Exchange Online per limitare le connessioni in ingresso da specifici intervalli IP di origine, questi sono elencati in [URL e intervalli IP di Office 365](urls-and-ip-address-ranges.md) nell'area dei servizi "Exchange Online". Occorre verificare che non sia influenzato l'accesso agli endpoint EWS pubblicati come OWA, assicurandosi che il proxy MRS si risolve in un FQDN e indirizzo IP pubblico separati prima di limitare i collegamenti TCP 443 da specifici intervalli IP di origine. | Proxy EWS/MRS locale del cliente<br> Porta TCP 443 | Traffico del server in ingresso |
| 7  | Funzioni per coesistenza di [Exchange ibrido](https://docs.microsoft.com/exchange/exchange-deployment-assistant), come la condivisione di informazioni sulla disponibilità. | Server Exchange locale del cliente | Traffico del server in ingresso |
| 8  | Autenticazione proxy di [Exchange ibrido](https://docs.microsoft.com/exchange/exchange-deployment-assistant) | STS locale del cliente | Traffico del server in ingresso |
| 9  | Consente di configurare [Exchange ibrido](https://docs.microsoft.com/exchange/exchange-deployment-assistant) usando la [Configurazione ibrida guidata di Exchange](https://docs.microsoft.com/exchange/hybrid-configuration-wizard) <br> Nota: gli endpoint sono necessari solo per configurare Exchange ibrido  | domains.live.com sulle porte TCP 80 e 443, necessarie solo per la configurazione ibrida guidata di Exchange 2010 SP3<BR> <BR> Indirizzi IP GCC High, DoD: 40.118.209.192/32; 168.62.190.41/32 <BR> <BR> Worldwide Commercial e GCC: *.store.core.windows.net; asl.configure.office.com; mshrcstorageprod.blob.core.windows.net; tds.configure.office.com; mshybridservice.trafficmanager.net <BR>  | Solo traffico del server in uscita |
| 10  | Il servizio di rilevamento automatico è usato negli scenari di [Exchange ibrido](https://docs.microsoft.com/exchange/exchange-deployment-assistant) con [autenticazione moderna ibrida con Outlook per iOS e Android](https://docs.microsoft.com/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth) <BR> <BR> ```*.acompli.net``` <BR> <BR> ```*.outlookmobile.com``` <BR> <BR> ```*.outlookmobile.us``` <BR> <BR> ```52.125.128.0/20``` <BR> ```52.127.96.0/23``` <BR> | Server Exchange locale del cliente in TCP 443 | Traffico del server in ingresso |
| 11  | Autenticazione di Azure AD ibrido di Exchange | *. msappproxy.net | Traffico solo server in uscita TCP |
| 12   | Skype for Business in Office 2016 include la condivisione dello schermo basata su video che utilizza le porte UDP. I precedenti client di Skype for Business in Office 2013 e versioni precedenti utilizzavano la porta RDP su TCP 443. | Porta TCP 443 aperta su 52.112.0.0/14 | Client precedenti di Skype for Business in Office 2013 e versioni precedenti |
| 13   | Connettività server ibrida locale di Skype for Business per Skype for Business online | 13.107.64.0/18, 52.112.0.0/14  <BR> Porte UDP 50.000-59.999 <BR>  Porte TCP 50.000-59.999; 5061 | Connettività in uscita del server Skype for Business locale |
| 14   | La rete PSTN cloud con connettività ibrida locale richiede la connettività di rete aperta agli host locali. Per ulteriori dettagli sulle configurazioni ibride di Skype for Business Online,  | Vedere [Pianificare la connettività ibrida tra Skype for Business Server e Office 365](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-hybrid-connectivity) | Ingresso ibrido locale di Skype for Business |
| 15  | **FQDN di autenticazione e identità** <br> Il nome di dominio completo (FQDN) ```secure.aadcdn.microsoftonline-p.com``` deve essere situato nell'area siti attendibili di Edge o Internet Explorer (IE) del client per poter funzionare. |  | Siti attendibili |
| 16   |  **FQDN di Microsoft Teams** <br> Se si usa Internet Explorer o Microsoft Edge, è necessario attivare i cookie dei siti Web visualizzati e di terze parti e aggiungere i nomi di dominio completo per Teams per i siti attendibili. Si tratta di un'aggiunta all'intera famiglia di FQDN, CDN e telemetrie elencata in riga 14. Vedere [Problemi noti di Microsoft Teams](https://docs.microsoft.com/microsoftteams/known-issues) per ulteriori informazioni. |  | Siti attendibili |
| 17   |  **FQDN di SharePoint Online e OneDrive for Business** <br> Tutti i nomi di dominio completo di ".sharepoint.com" con "\<tenant>" nel nome di dominio completo devono essere situati nell'area siti attendibili di Edge o IE del client per poter funzionare. Oltre all’intera famiglia di FQDN, CDN e telemetria elencata alla riga 14, è necessario aggiungere anche questi endpoint. |  | Siti attendibili |
| 18   | **Yammer**  <br> Yammer è disponibile solo nel browser e necessita di un'autenticazione proxy da parte dell'utente. Tutti i FQDN di Yammer devono essere situati nell'area siti attendibili di Edge o IE del client per poter funzionare. |  | Siti attendibili |
| 19  | Usare [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/) per sincronizzare gli account utente locali con Azure AD. | Vedere[Porte e protocolli necessari per la soluzione ibrida di gestione delle identità](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-ports), [Risolvere i problemi di connettività di Azure AD](https://docs.microsoft.com/azure/active-directory/hybrid/tshoot-connect-connectivity) e [Installazione dell'agente di Azure AD Connect Health](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-health-agent-install#outbound-connectivity-to-the-azure-service-endpoints). | Solo traffico del server in uscita |
| 20  | [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/) con 21 ViaNet in Cina per sincronizzare gli account utente locali con Azure AD. | \*.digicert.com:80 <BR> \*.entrust.net:80 <BR> \*.chinacloudapi.cn:443 <BR> secure.aadcdn.partner.microsoftonline-p.cn:443 <BR>*.partner.microsoftonline.cn:443 <BR> <BR>Vedere anche [Risolvere i problemi in ingresso con i problemi di connettività di Azure AD Connect](https://docs.azure.cn/zh-cn/active-directory/hybrid/tshoot-connect-connectivity). | Solo traffico del server in uscita |
|  21  | Microsoft Stream (richiede il token utente Azure AD). <BR> Office 365 internazionale (incluso GCC) | \*.cloudapp.net <BR> \*.api.microsoftstream.com <BR> \*.notification.api.microsoftstream.com <BR> amp.azure.net <BR> api.microsoftstream.com <BR> az416426.vo.msecnd.net <BR> s0.assets-yammer.com <BR> vortex.data.microsoft.com <BR> web.microsoftstream.com <BR> Porta TCP 443  | Traffico del server in ingresso |
| 22  | Usare il server MFA per le richieste di autenticazione a più fattori, sia per le nuove installazioni del server che per la configurazione con Active Directory Domain Services (AD DS). | Vedere [Introduzione al server Azure Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-deploy#plan-your-deployment).  | Solo traffico del server in uscita |
| 23  | Notifiche di modifica di Microsoft Graph | Gli sviluppatori possono usare le [notifiche di modifica](https://docs.microsoft.com/graph/webhooks?context=graph%2Fapi%2F1.0&view=graph-rest-1.0) per sottoscrivere eventi in Microsoft Graph. | *.cloudapp.net<BR> 104.43.130.21, 137.116.169.230, 13.79.38.63, 104.214.39.228, Cloud pubblico: 168.63.250.205, 52.161.9.202, 40.68.103.62, 13.89.60.223, 23.100.95.104, 40.113.95.219, 104.214.32.10, 168.63.237.145, 52.161.110.176, 52.174.177.183 <BR> Microsoft Cloud for US Government: 52.244.231.173, 52.238.76.151, 52.244.250.211, 52.238.78.108 <BR> Microsoft Cloud Germania: 51.4.231.136, 51.5.243.223, 51.4.226.154, 51.5.244.215 <BR> Microsoft Cloud Cina gestito da 21Vianet: 139.219.15.33, 42.159.154.223, 42.159.88.79, 42.159.155.77<BR> Porta TCP 443 <BR> Nota: gli sviluppatori possono specificare porte diverse al momento della creazione di sottoscrizioni.  | Traffico del server in ingresso |
|||||

## <a name="related-topics"></a>Argomenti correlati

[Gestione degli endpoint di Office 365](managing-office-365-endpoints.md)
  
[Risoluzione dei problemi di connettività di Office 365](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d.aspx)
  
[Connettività client](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b)
  
[Reti per la distribuzione di contenuti](https://support.office.com/article/content-delivery-networks-0140f704-6614-49bb-aa6c-89b75dcd7f1f)
  
[Intervalli IP del data center di Microsoft Azure](https://www.microsoft.com/download/details.aspx?id=41653)
  
[Spazio IP pubblico di Microsoft](https://www.microsoft.com/download/details.aspx?id=53602)
