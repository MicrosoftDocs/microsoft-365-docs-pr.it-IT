---
title: Domande frequenti sulla mobilità e la sicurezza di base
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Domande frequenti sulla mobilità e la sicurezza di base.
ms.openlocfilehash: 5651b9f9742c45f1229e55b298cf78532c835c9a
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876877"
---
# <a name="basic-mobility-and-security-frequently-asked-questions-faq"></a>Domande frequenti sulla mobilità e la sicurezza di base

Questo articolo contiene domande frequenti su Basic Mobility and Security, una funzionalità che consente di gestire e proteggere i dispositivi mobili in Microsoft 365. Se non riesci a trovare una risposta alla tua domanda, contattaci lasciando un commento nella pagina, in modo che possiamo prendere in considerazione l'aggiunta della domanda a questo articolo.

## <a name="how-can-i-get-basic-mobility-and-security-i-dont-see-it-in-the-microsoft-365-admin-center"></a>Come è possibile ottenere funzionalità di mobilità e sicurezza di base? Non viene visualizzato nell'interfaccia di amministrazione di Microsoft 365

1.  Attivare Dispositivi mobili e sicurezza di base dalla pagina Sicurezza e conformità [& di Office 365.](https://protection.office.com/)

2.  Passare a Prevenzione della perdita di dati > gestione dei dispositivi.

## <a name="how-can-i-get-started-with-device-management-in-basic-mobility-and-security"></a>Come posso iniziare a usare la gestione dei dispositivi in Basic Mobility and Security?

Per iniziare a usare Basic Mobility and Security, è necessario eseguire quattro passaggi: 

1. Attivare la funzionalità Di base per dispositivi mobili e sicurezza in [Office 365 Security & Compliance.](https://protection.office.com/)

2. Vai a Prevenzione della perdita di dati > gestione dei dispositivi > criteri dispositivo.
    
3. Creare criteri di gestione dei dispositivi e applicarli a gruppi di utenti impostati nei gruppi di sicurezza. È consigliabile iniziare distribuendo i criteri a un piccolo gruppo di test. Per altre info, vedi [Creare criteri di sicurezza dei dispositivi in Dispositivi mobili e sicurezza di base.](create-device-security-policies.md)

4. Agli utenti a cui è stato applicato un criterio viene richiesto di registrare i dispositivi quando tentano di accedere ai dati di Microsoft 365. Per altre info, vedi [Registrare il dispositivo mobile con Dispositivi mobili e sicurezza di base.](enroll-your-mobile-device.md)

Per ulteriori informazioni, vedere [Set up Basic Mobility and Security.](set-up.md)

## <a name="im-trying-to-set-up-basic-mobility-and-security-but-it-seems-stuck-the-microsoft-365-service-health-has-been-showing-provisioning-for-a-while-what-can-i-do"></a>Si sta provando a configurare Basic Mobility and Security, ma sembra bloccato. Integrità dei servizi di Microsoft 365 mostra il "provisioning" da un po' di tempo. per correggere il problema?

Potrebbe essere necessario del tempo per prepararsi al servizio. Al termine del provisioning, verrà visualizzata la pagina Dispositivi mobili e sicurezza di base. If you've waited 24 hours and the status is still provisioning, please contact Support and we'll help figure out what the issue is. Per le opzioni di supporto, vedere [Serve ancora assistenza?](https://support.microsoft.com/office/frequently-asked-questions-about-basic-mobility-and-security-3871f99c-c9db-4a23-86f9-902c1b02f58d#bkmk_needhelp).

## <a name="what-can-i-do-if-device-enrollment-fails"></a>Cosa posso fare se la registrazione del dispositivo non riesce?

Se si verificano problemi durante la registrazione di un dispositivo, controlla prima di tutto quanto segue:

- Assicurati che il dispositivo non sia già registrato con un altro provider di gestione dei dispositivi mobili, ad esempio Intune.

- Assicurati che il dispositivo sia impostato sulla data e sull'ora corrette.

- Passare a una rete WIFI o cellulare diversa nel dispositivo.

- Per i dispositivi Android o iOS, disinstalla e reinstalla l'app Portale aziendale Intune nel dispositivo.
    
Se la registrazione non funziona ancora, vedere Risolvere i problemi [di sicurezza e mobilità di base.](troubleshoot.md)

## <a name="whats-the-difference-between-intune-and-basic-mobility-and-security"></a>Qual è la differenza tra Intune e Basic Mobility and Security?

Basic Mobility and Security è ospitato dal servizio Intune. Si tratta di un sottoinsieme di servizi intune forniti come ulteriore vantaggio per Microsoft 365 ed è una soluzione basata sul cloud integrata per la gestione dei dispositivi nell'organizzazione. Per un confronto affiancato dei due servizi per decidere se usare Intune o Basic Mobility and Security per Microsoft 365, vedere Scegliere tra Basic Mobility Security e [Intune.](choose-between-basic-mobility-and-security-and-intune.md)

## <a name="how-do-policies-work-for-basic-mobility-and-security-how-do-i-set-them-up-disable-them"></a>Come funzionano i criteri per la mobilità e la sicurezza di base? Come si configurano? Disabilitarli?

Dopo aver completato la configurazione iniziale per Basic Mobility and Security, è possibile creare criteri e applicarli a gruppi di utenti nel Centro sicurezza & conformità. I criteri richiedono agli utenti dei criteri di registrare i propri dispositivi in Sicurezza e mobilità di base prima che il dispositivo possa essere usato per accedere ai dati di Microsoft 365. I criteri impostati determinano le impostazioni per i dispositivi mobili, ad esempio la frequenza con cui le password devono essere reimpostate o se è necessaria la crittografia dei dati. Per altre informazioni, vedere [Creare criteri di sicurezza dei dispositivi nel](create-device-security-policies.md)Centro sicurezza e mobilità di base e Nel Centro conformità Microsoft   [365.](https://support.microsoft.com/office/7e696a40-b86b-4a20-afcc-559218b7b1b8)

Per istruzioni dettagliate sulla creazione e la distribuzione dei criteri dei dispositivi, vedi Creare criteri di sicurezza dei dispositivi [in Dispositivi mobili e sicurezza di base.](create-device-security-policies.md)

Se si desidera escludere un gruppo specifico di utenti dai criteri, è possibile aggiungere un gruppo al gruppo di esclusione.

## <a name="can-i-switch-from-exchange-activesync-device-management-to-basic-mobility-and-security-for-microsoft-365"></a>È possibile passare dalla gestione Exchange ActiveSync dispositivi a Dispositivi mobili e sicurezza di base per Microsoft 365?

Se si usano già i criteri di Exchange ActiveSync per gestire i dispositivi mobili, è possibile iniziare a usare Dispositivi mobili e sicurezza di base seguendo la procedura per configurare Dispositivi mobili e sicurezza di base. Per ulteriori informazioni, vedere [Proteggere l'accesso](https://go.microsoft.com/fwlink/?LinkId=615145) di utenti e dispositivi [e Configurare la mobilità e la sicurezza di base.](set-up.md)

Quando si applicano i criteri creati in Sicurezza e mobilità di base a gruppi di utenti Exchange ActiveSync, questi criteri sostituiscono i criteri cassetta postale dei dispositivi mobili e le regole di accesso ai dispositivi creati in precedenza nell'interfaccia di amministrazione di Exchange per tali utenti.

Dopo la registrazione di un dispositivo in Basic Mobility and Security, qualsiasi criterio cassetta Exchange ActiveSync cassetta postale del dispositivo mobile o regola di accesso al dispositivo applicata al dispositivo viene ignorato.

## <a name="i--set-up-basic-mobility-and-security-but-now-i-want-to-remove-it-what-are-the-steps"></a>Ho configurato Basic Mobility and Security, ma ora voglio rimuoverlo. Quali sono i passaggi?

Purtroppo, non è possibile semplicemente "annullare il provisioning" di Base Mobility and Security dopo aver configurato. Tuttavia, puoi rimuoverlo per i gruppi di utenti rimuovendo i gruppi di sicurezza degli utenti dai criteri dei dispositivi che hai creato. In caso contrario, puoi disabilitarlo per tutti rimuovendo i criteri dei dispositivi in modo che non siano applicati e non applicati. Per altre info, vedi [Disattivare Dispositivi mobili e sicurezza di base.](turn-off.md)