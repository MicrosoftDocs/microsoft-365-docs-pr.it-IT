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
description: 'Riepilogo: in questo articolo viene descritto il supporto IPv6 nei componenti di Microsoft Office 365 e nelle offerte governative di Office 365.'
ms.openlocfilehash: f671e8caf868ebbed628a155b73ce6fe413949a9
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235607"
---
# <a name="ipv6-support-in-office-365-services"></a>Supporto IPv6 nei servizi Office 365

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

Office 365 supporta sia IPv6 che IPv4. Tuttavia, non tutte le funzionalità di Office 365 sono completamente abilitate con IPv6. Questo significa che è necessario utilizzare sia IPv4 che IPv6 per connettersi a Office 365. Se si sta filtrando il traffico in uscita in Office 365, l'elenco completo degli indirizzi IPv6 supportati da Office 365 è disponibile nell'articolo [office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md). Una volta configurata la rete e gli indirizzi IPv6 corretti sono consentiti, è possibile scaricare il [piano di testing IPv6 di Office 365](https://go.microsoft.com/fwlink/?LinkId=293447) dall'area download Microsoft.
  
## <a name="ipv6-support-in-office-365-subscription-service"></a>Supporto IPv6 nel servizio di sottoscrizione di Office 365

### <a name="exchange-online-and-ipv6"></a>Exchange Online e IPv6

Se il programma utilizzato per effettuare la connessione a Exchange Online supporta IPv6, questo viene utilizzato per impostazione predefinita su reti cablate e wireless. Se si desidera controllare le comunicazioni con Exchange Online, utilizzare gli intervalli di indirizzi IP negli [URL di Office 365 e negli intervalli di indirizzi IP](urls-and-ip-address-ranges.md).
  
### <a name="sharepoint-online-and-ipv6"></a>SharePoint Online e IPv6

 **Office 365 governo G1/G3/G4/K1** Se il programma utilizzato per la connessione a SharePoint Online supporta IPv6, tenterà di utilizzare IPv6 per impostazione predefinita.
  
 **Cloud pubblico multi-tenant** Microsoft Abilita IPv6 di SharePoint Online su richiesta. È necessario fornire gli indirizzi IP CIDR notated per l'infrastruttura DNS dell'organizzazione. Tenere presente che questa infrastruttura DNS non può essere condivisa da altre organizzazioni per IPv6 per essere abilitata per il tenant. Dopo l'abilitazione di IPv6, se il programma utilizzato per la connessione a SharePoint Online supporta IPv6, questo viene utilizzato per impostazione predefinita.
  
Se il programma utilizzato per effettuare la connessione a SharePoint Online supporta IPv6, questo viene utilizzato per impostazione predefinita su reti cablate e wireless. Se si desidera controllare le comunicazioni a SharePoint Online, utilizzare gli intervalli di indirizzi IP negli [URL di Office 365 e negli intervalli di indirizzi IP](urls-and-ip-address-ranges.md).
  
 **Office 365 governo G1/G3/G4/K1** Se il programma utilizzato per la connessione a SharePoint Online supporta IPv6, tenterà di utilizzare IPv6 per impostazione predefinita.
  
### <a name="skype-for-business-and-ipv6"></a>Skype for business e IPv6

Tieni presente che IPv6 non è supportato in Skype for business e non può più essere abilitato.

### <a name="microsoft-teams-and-ipv6"></a>Microsoft teams e IPV6

Il routing diretto di Microsoft teams supporta solo IPv4. Il servizio Microsoft teams e il client supportano sia IPv4 che IPv6. Se si desidera controllare le comunicazioni a Microsoft teams, utilizzare gli intervalli di indirizzi IP negli [URL di Office 365 e negli intervalli di indirizzi IP](urls-and-ip-address-ranges.md).
  
### <a name="exchange-online-protection-and-ipv6"></a>Exchange Online Protection e IPv6

Exchange Online Protection (EOP) supporta IPv6 se la trasmissione avviene tramite protocollo Transport Layer Security. Per l'intervallo EOP, utilizzare gli [intervalli di indirizzi IP e URL di Office 365](urls-and-ip-address-ranges.md).
  
### <a name="ipv6-support-for-office-365-government-offerings"></a>Supporto IPv6 per le offerte del governo di Office 365

Office 365 IPv6 supporta le offerte del governo in conformità al memorandum di gestione e budget di Office (OMB) per Chief Information dell'Executive Departments and Agencies, nonché al memorandum Federal Government Adoption of Internet Protocol Version 6 (IPv6). [Microsoft Office 365 per Government](https://go.microsoft.com/fwlink/p/?LinkId=325414) è un servizio multi-tenant che memorizza i dati del governo degli Stati Uniti in un cloud comunitario segregato. Analogamente ad altre offerte di Office 365, fornisce servizi di produttività e collaborazione, tra cui Exchange Online, Skype for business, SharePoint Online e Microsoft 365 Apps for Enterprise. 

Le offerte del governo di Microsoft Office 365 si applicano solo per 2013 e versioni successive. Per ulteriori informazioni sulle offerte governative di Office 365, vedere [annunciare office 365 per Government: un cloud della community del governo degli Stati Uniti](https://go.microsoft.com/fwlink/p/?LinkId=325414). International Traffic in Arms Regulations (ITAR) è un insieme di regolamenti del governo degli Stati Uniti che controllano l'esportazione e l'importazione di articoli e servizi relativi alla difesa nella [lista di munizioni degli Stati Uniti (USML)](https://go.microsoft.com/fwlink/p/?LinkId=325415). 

Microsoft Office 365 per le imprese fornisce servizi di hosting dedicati per soluzioni di produttività Microsoft che supportino la sicurezza, la privacy e i requisiti di conformità alle normative per le agenzie federali degli Stati Uniti che richiedono la certificazione FISMA (Federal Information Security Management) ed entità commerciali soggette a ITAR.
  
## <a name="things-to-consider-when-using-ipv6-and-office-365"></a>Aspetti da considerare quando si utilizza IPv6 e Office 365

Si consiglia di non disabilitare IPv6. Per ulteriori informazioni, vedere l' [articolo relativo alle linee guida](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users). Per determinare le versioni IP in uso nella propria rete, prendere in considerazione i seguenti elementi:
  
- Se la visualizzazione del comando **ipconfig** al prompt dei comandi contiene righe denominate "indirizzo IPv6" o "indirizzo IPv6 temporaneo", si dispone di IPv6 nell'ambiente.

- Se tutti gli indirizzi IPv6 iniziano con "FE80" e corrispondono a righe denominate "indirizzo IPv6 locale del collegamento", non si dispone di IPv6 nell'ambiente.

Queste considerazioni potrebbero essere applicate alla rete:
  
- Il servizio di sottoscrizione pubblica non supporta l'acquisto con carta di credito su IPv6. Ciò non viene applicato al GCC (Government Community Cloud) perché gli enti pubblici dispongono di licenza EA (Contratto enterprise.

- IPv6 non supporta alcuni scenari di Rights Management Services (RMS).

- IPv6 non supporta BlackBerry® Enterprise Server (BES) perché BlackBerry non supporta IPv6.

- Se si utilizza Active Directory Federation Services (ADFS) con Office 365, la pubblicità dell'endpoint di rete ad FS con Office 365 tramite IPv6 non è supportata. Quando si utilizza Exchange Online, non è necessario includere i record AAAA nella voce DNS ADFS. 

Ecco un collegamento breve per tornare alla pagina: [https://aka.ms/o365ip6](https://aka.ms/o365ip6)
  
## <a name="see-also"></a>Vedere anche

[Guida di orientamento all'apprendimento IPv6](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))
  
[Guida alla sopravvivenza IPv6](https://social.technet.microsoft.com/wiki/contents/articles/1728.ipv6-survival-guide.aspx)
