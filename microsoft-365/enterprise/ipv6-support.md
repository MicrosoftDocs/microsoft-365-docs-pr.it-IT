---
title: Supporto IPv6 nei servizi Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 10/10/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: c08786fb-298e-437c-8222-dab7625fc815
description: 'Riepilogo: descrive il supporto IPv6 nei componenti Microsoft Office 365 e nelle Office 365 per enti pubblici.'
ms.openlocfilehash: 7f06ed6f8df2c6552ee0a331ad958bca289d0a09
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909683"
---
# <a name="ipv6-support-in-office-365-services"></a>Supporto IPv6 nei servizi Office 365

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

Office 365 supporta sia IPv6 che IPv4. Tuttavia, non tutte Office 365 funzionalità sono completamente abilitate con IPv6. Ciò significa che è necessario utilizzare sia IPv4 che IPv6 per connettersi a Office 365. Se si filtra il traffico in uscita verso Office 365, l'elenco completo degli indirizzi IPv6 supportati da Office 365 è disponibile nell'articolo Office 365 URL e intervalli di indirizzi [IP.](urls-and-ip-address-ranges.md) Dopo aver configurato la rete e aver consentito gli indirizzi IPv6 appropriati, è possibile scaricare il piano di [test Office 365 IPv6](https://go.microsoft.com/fwlink/?LinkId=293447) dall'Area download Microsoft.
  
## <a name="ipv6-support-in-office-365-subscription-service"></a>Supporto IPv6 nel servizio Office 365 sottoscrizione

### <a name="exchange-online-and-ipv6"></a>Exchange Online e IPv6

Se il programma utilizzato per effettuare la connessione a Exchange Online supporta IPv6, questo viene utilizzato per impostazione predefinita su reti cablate e wireless. Se si desidera controllare le comunicazioni Exchange Online, utilizzare gli intervalli di indirizzi IP Office 365 URL e [intervalli di indirizzi IP.](urls-and-ip-address-ranges.md)
  
### <a name="sharepoint-online-and-ipv6"></a>SharePoint Online e IPv6

 **Office 365 Government G1/G3/G4/K1** Se il programma utilizzato per connettersi a SharePoint Online supporta IPv6, tenterà di utilizzare IPv6 per impostazione predefinita.
  
 **Cloud multi-tenant pubblico** Microsoft abilita SharePoint IPv6 online su richiesta dell'utente. È necessario fornire gli indirizzi IP con notazione CIDR per l'infrastruttura DNS dell'organizzazione. Tenere presente che questa infrastruttura DNS non può essere condivisa da altre organizzazioni per IPv6 per essere abilitata per il tenant. Dopo l'abilitazione di IPv6, se il programma utilizzato per la connessione a SharePoint Online supporta IPv6, questo viene utilizzato per impostazione predefinita.
  
Se il programma utilizzato per effettuare la connessione a SharePoint Online supporta IPv6, questo viene utilizzato per impostazione predefinita su reti cablate e wireless. Se si desidera controllare le comunicazioni SharePoint Online, utilizzare gli intervalli di indirizzi IP Office 365 URL e [intervalli di indirizzi IP.](urls-and-ip-address-ranges.md)
  
 **Office 365 Government G1/G3/G4/K1** Se il programma utilizzato per connettersi a SharePoint Online supporta IPv6, tenterà di utilizzare IPv6 per impostazione predefinita.
  
### <a name="skype-for-business-and-ipv6"></a>Skype for Business e IPv6

Tenere presente che IPv6 non è supportato in Skype for Business e non può più essere abilitato.

### <a name="microsoft-teams-and-ipv6"></a>Microsoft Teams e IPV6

Microsoft Teams Il routing diretto supporta solo IPv4. Il Microsoft Teams client e il servizio supportano sia IPv4 che IPv6. Se si desidera controllare le comunicazioni Microsoft Teams, utilizzare gli intervalli di indirizzi IP Office 365 URL e [intervalli di indirizzi IP.](urls-and-ip-address-ranges.md)
  
### <a name="exchange-online-protection-and-ipv6"></a>Exchange Online Protection e IPv6

Exchange Online Protection (EOP) supporta IPv6 se la trasmissione avviene tramite protocollo Transport Layer Security. Per l'intervallo EOP, utilizzare [Office 365 URL e intervalli di indirizzi IP.](urls-and-ip-address-ranges.md)
  
### <a name="ipv6-support-for-office-365-government-offerings"></a>Supporto IPv6 per le offerte del governo di Office 365

Office 365 IPv6 supporta le offerte del governo in conformità al memorandum di gestione e budget di Office (OMB) per Chief Information dell'Executive Departments and Agencies, nonché al memorandum Federal Government Adoption of Internet Protocol Version 6 (IPv6). [Microsoft Office 365 per enti pubblici](https://go.microsoft.com/fwlink/p/?LinkId=325414) è un servizio multi-tenant che archivia i dati del governo statunitense in un cloud di community segregato. Come altre Office 365, fornisce servizi di produttività e collaborazione, tra cui Exchange Online, Skype for Business, SharePoint Online e Microsoft 365 Apps for enterprise. 

Le offerte del governo di Microsoft Office 365 si applicano solo per 2013 e versioni successive. Per ulteriori informazioni sulle Office 365 per enti pubblici, vedere Annuncio di Office 365 per il [governo: una](https://go.microsoft.com/fwlink/p/?LinkId=325414)Government Community Cloud . International Traffic in Arms Regulations (ITAR) è un insieme di normative governative statunitensi che controllano l'esportazione e l'importazione di articoli e servizi relativi alla difesa [nell'Us States Munitions List (USML).](https://go.microsoft.com/fwlink/p/?LinkId=325415) 

Microsoft Office 365 per le imprese fornisce servizi di hosting dedicati per soluzioni di produttività Microsoft che supportino la sicurezza, la privacy e i requisiti di conformità alle normative per le agenzie federali degli Stati Uniti che richiedono la certificazione FISMA (Federal Information Security Management) ed entità commerciali soggette a ITAR.
  
## <a name="things-to-consider-when-using-ipv6-and-office-365"></a>Aspetti da considerare quando si utilizza IPv6 e Office 365

Si consiglia di non disabilitare IPv6. Per ulteriori informazioni, vedere questo [articolo di guida.](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users) Per determinare le versioni IP in uso nella propria rete, prendere in considerazione i seguenti elementi:
  
- Se la visualizzazione del **comando IPConfig** al prompt dei comandi contiene righe denominate "Indirizzo IPv6" o "Indirizzo IPv6 temporaneo", nell'ambiente è presente IPv6.

- Se tutti gli indirizzi IPv6 iniziano con "fe80" e corrispondono a righe denominate "Link-Local IPv6 Address", non si dispone di IPv6 nell'ambiente.

Queste considerazioni potrebbero essere applicate alla rete:
  
- Il servizio di sottoscrizione pubblica non supporta l'acquisto con carta di credito su IPv6. Ciò non viene applicato al GCC (Government Community Cloud) perché gli enti pubblici dispongono di licenza EA (Contratto enterprise.

- IPv6 non supporta alcuni scenari di Rights Management Services (RMS).

- IPv6 non supporta BlackBerry® Enterprise Server (BES) perché BlackBerry non supporta IPv6.

- Se si utilizza Active Directory Federation Services (AD FS) con Office 365, la pubblicità dell'endpoint di rete AD FS Office 365 tramite IPv6 non è supportata. Non includere record AAAA nella voce DNS AD FS quando si utilizza Exchange Online. 

Ecco un collegamento breve per tornare alla pagina: [https://aka.ms/o365ip6]()
  
## <a name="see-also"></a>Vedere anche

[Guida di orientamento all'apprendimento IPv6](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))
  
[Guida alla sopravvivenza IPv6](https://social.technet.microsoft.com/wiki/contents/articles/1728.ipv6-survival-guide.aspx)