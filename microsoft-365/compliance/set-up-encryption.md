---
title: Configurare la crittografia in Office 365 Enterprise
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/2/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e86fc991-0161-4f01-9c1c-d25e87733d06
description: Con Office 365, alcune funzionalità di crittografia sono attivate per impostazione predefinita. altre funzionalità possono essere configurate per soddisfare determinati requisiti legali o di conformità.
ms.openlocfilehash: f758bc026ee1ef8b071b92d29c950c3f436305a3
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "38686423"
---
# <a name="set-up-encryption-in-office-365-enterprise"></a>Configurare la crittografia in Office 365 Enterprise

La crittografia può proteggere il contenuto dalla lettura da parte di utenti non autorizzati. Poiché la [crittografia in Office 365](encryption.md) può essere eseguita utilizzando diverse tecnologie e metodi, non esiste un singolo luogo in cui si attiva o si configura la crittografia. In questo articolo vengono fornite informazioni sui vari modi in cui è possibile impostare o configurare la crittografia come parte della strategia di protezione delle informazioni.
  
> [!TIP]
> Se si desiderano ulteriori informazioni tecniche sulla crittografia, vedere [informazioni di riferimento tecnico sulla crittografia in Office 365](technical-reference-details-about-encryption.md).
  
Con Office 365, sono disponibili diverse funzionalità di crittografia per impostazione predefinita. Ulteriori funzionalità di crittografia possono essere configurate per soddisfare determinati requisiti legali o di conformità. Nella tabella seguente vengono descritti diversi metodi di crittografia per diversi scenari.
  
|**Scenario**|**Metodi di crittografia**|
|:-----|:-----|
|I file vengono salvati nei computer Windows  <br/> |La crittografia a livello di computer può essere completata tramite BitLocker nei dispositivi Windows. In qualità di amministratore aziendale o Pro IT, è possibile configurarlo utilizzando Microsoft Deployment Toolkit (MDT). Vedere [configurare MDT per BitLocker](https://go.microsoft.com/fwlink/?linkid=849282).  <br/> |
|I file vengono salvati nei dispositivi mobili  <br/> |Alcuni tipi di dispositivi mobili crittografano i file salvati nei dispositivi per impostazione predefinita. Con le [funzionalità di gestione dei dispositivi mobili incorporati per office 365](https://support.office.com/article/a1da44e5-7475-4992-be91-9ccec25905b0), è possibile impostare criteri che determinano se consentire ai dispositivi mobili di accedere ai dati in Office 365. Ad esempio, è possibile impostare un criterio che consenta solo i dispositivi che crittografano il contenuto per accedere ai dati di Office 365. Vedere [creare e distribuire i criteri di sicurezza del dispositivo](https://support.office.com/article/d310f556-8bfb-497b-9bd7-fe3c36ea2fd6).  <br/> Per un ulteriore controllo su come i dispositivi mobili interagiscono con Office 365, è possibile considerare l'aggiunta di [Microsoft Intune](https://aka.ms/qzln04). Vedere [scegliere tra MDM per Office 365 e Microsoft Intune](https://support.office.com/article/c93d9ab9-efb2-4349-9b93-30c30562ee22).  <br/> |
|È necessario controllare le chiavi di crittografia utilizzate per crittografare i dati nei data center di Microsoft  <br/> | In qualità di amministratore di Office 365, è possibile controllare le chiavi di crittografia dell'organizzazione e quindi configurare Office 365 per utilizzarle per crittografare i dati a riposo nei data center di Microsoft.  <br/> [Controllare i dati in Office 365 con Customer Key](controlling-your-data-using-customer-key.md) <br/> [Chiave del cliente per le domande frequenti su Office 365](service-encryption-with-customer-key-faq.md) <br/> |
|Le persone stanno comunicando tramite posta elettronica (Exchange Online)  <br/> | In qualità di amministratore di Exchange Online, sono disponibili diverse opzioni per la configurazione della crittografia della posta elettronica. Queste funzionalità sono:  <br/>  Utilizzo di [Office 365 Message Encryption (OME)](set-up-new-message-encryption-capabilities.md) con Azure Rights Management (Azure RMS) per consentire agli utenti di inviare messaggi crittografati all'interno o all'esterno dell'organizzazione  <br/>  Utilizzo di [S/MIME per la firma e la crittografia dei messaggi](https://aka.ms/c6dozg) per crittografare e firmare digitalmente i messaggi di posta elettronica  <br/>  Utilizzo di TLS per [configurare i connettori per il flusso di posta sicura con un'altra organizzazione](https://aka.ms/hs809p) <br/>  Vedere la [crittografia della posta elettronica in Office 365](https://aka.ms/hic3f7).  <br/> |
|È possibile accedere ai file dai siti del team o dalle raccolte documenti (OneDrive for business o SharePoint Online)  <br/> |Quando si utilizzano file salvati in OneDrive for business o SharePoint Online, vengono utilizzate le connessioni TLS. Questo è incorporato in Office 365 automaticamente. Vedere [crittografia dei dati in OneDrive for business e SharePoint Online](https://go.microsoft.com/fwlink/?linkid=526379).  <br/> |
|I file sono condivisi nelle riunioni online e nelle conversazioni di messaggistica istantanea (Skype for business online)  <br/> |Quando gli utenti utilizzano i file che usano Skype for business online, TLS viene utilizzato per la connessione. Questo è incorporato in Office 365 automaticamente. Vedere [sicurezza e archiviazione (Skype for business online)](https://aka.ms/nuq4ws).  <br/> |

## <a name="additional-information"></a>Informazioni aggiuntive

Per ulteriori informazioni sulle soluzioni di protezione dei file che includono le opzioni di crittografia, vedere [File Protection Solutions in Office 365](https://www.microsoft.com/download/details.aspx?id=55523).