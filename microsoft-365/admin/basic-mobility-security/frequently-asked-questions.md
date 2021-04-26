---
title: Domande frequenti su Mobilità e sicurezza di base
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
ms.openlocfilehash: 14e12678ec210325f63914594fb6debcf7abb880
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023894"
---
# <a name="basic-mobility-and-security-frequently-asked-questions-faq"></a>Domande frequenti su Mobilità e sicurezza di base

Questo articolo contiene le domande frequenti su Dispositivi mobili e sicurezza di base, una funzionalità che consente di gestire e proteggere i dispositivi mobili in Microsoft 365. Se non riesci a trovare una risposta alla tua domanda, contattaci lasciando un commento nella pagina in modo che possiamo prendere in considerazione l'aggiunta della domanda a questo articolo.

## <a name="how-can-i-get-basic-mobility-and-security-i-dont-see-it-in-the-microsoft-365-admin-center"></a>Come posso ottenere dispositivi mobili e sicurezza di base? Non viene visualizzato nell'interfaccia di amministrazione di Microsoft 365

1.  Attivare Dispositivi mobili e sicurezza di base andando alla pagina Sicurezza di [Office 365 & conformità.](https://protection.office.com/)

2.  Vai a Prevenzione della perdita di dati > gestione dei dispositivi.

## <a name="how-can-i-get-started-with-device-management-in-basic-mobility-and-security"></a>Come posso iniziare a usare la gestione dei dispositivi in Dispositivi mobili e sicurezza di base?

Sono disponibili quattro passaggi per iniziare a usare La mobilità e la sicurezza di base: 

1. Attivare Dispositivi mobili e sicurezza di base andando a [Office 365 Security & Compliance](https://protection.office.com/).

2. Vai a Prevenzione della perdita di dati > gestione dei dispositivi > criteri dispositivo.
    
3. Creare criteri di gestione dei dispositivi e applicarli a gruppi di utenti impostati nei gruppi di sicurezza. È consigliabile iniziare distribuendo i criteri in un piccolo gruppo di test. Per altre info, vedi [Creare criteri di sicurezza dei dispositivi in Dispositivi mobili e sicurezza di base.](create-device-security-policies.md)

4. Agli utenti a cui è stato applicato un criterio viene richiesto di registrare i dispositivi quando tentano di accedere ai dati di Microsoft 365. Per altre info, vedi [Registrare il dispositivo mobile usando Dispositivi mobili e sicurezza di base.](enroll-your-mobile-device.md)

Per ulteriori informazioni, vedere [Set up Basic Mobility and Security.](set-up.md)

## <a name="im-trying-to-set-up-basic-mobility-and-security-but-it-seems-stuck-the-microsoft-365-service-health-has-been-showing-provisioning-for-a-while-what-can-i-do"></a>Si sta tentando di configurare La mobilità di base e la sicurezza, ma sembra bloccata. Integrità dei servizi di Microsoft 365 mostra il "provisioning" da un po' di tempo. per correggere il problema?

Potrebbe essere necessario del tempo per prepararsi al servizio. Al termine del provisioning, verrà visualizzata la pagina Dispositivi mobili e sicurezza di base. Se hai atteso 24 ore e lo stato è ancora provisioning, contatta il supporto e ti aieremo a capire qual è il problema.

## <a name="what-can-i-do-if-device-enrollment-fails"></a>Cosa posso fare se la registrazione dei dispositivi ha esito negativo?

Se si verificano problemi durante la registrazione di un dispositivo, controllare quanto segue:

- Assicurati che il dispositivo non sia già registrato con un altro provider di gestione dei dispositivi mobili, ad esempio Intune.

- Assicurati che il dispositivo sia impostato sulla data e sull'ora corrette.

- Passare a una rete WIFI o cellulare diversa nel dispositivo.

- Per i dispositivi Android o iOS, disinstalla e reinstalla l'app Portale aziendale intune nel dispositivo.
    
Se la registrazione non funziona ancora, vedi Risolvere i problemi relativi alla [mobilità e alla sicurezza di base.](troubleshoot.md)

## <a name="whats-the-difference-between-intune-and-basic-mobility-and-security"></a>Qual è la differenza tra Intune e Basic Mobility and Security?

La mobilità e la sicurezza di base sono ospitate dal servizio Intune. Si tratta di un sottoinsieme di servizi Intune forniti come ulteriore vantaggio per Microsoft 365 ed è una soluzione basata sul cloud incorporata per la gestione dei dispositivi nell'organizzazione. Per un confronto affiancato tra i due servizi per decidere se usare Intune o Basic Mobility and Security per Microsoft 365 è la soluzione più adatta per te, vedi Scegliere tra Basic Mobility Security e [Intune.](choose-between-basic-mobility-and-security-and-intune.md)

## <a name="how-do-policies-work-for-basic-mobility-and-security-how-do-i-set-them-up-disable-them"></a>Come funzionano i criteri per la mobilità e la sicurezza di base? Come si configurano? Disabilitarli?

Dopo aver completato la configurazione iniziale per Dispositivi mobili e sicurezza di base, è possibile creare criteri e applicarli a gruppi di utenti nel Centro sicurezza & conformità. I criteri richiedono agli utenti dei criteri di registrare i propri dispositivi in Dispositivi mobili e sicurezza di base prima che il dispositivo possa essere usato per accedere ai dati di Microsoft 365. I criteri impostati determinano le impostazioni per i dispositivi mobili, ad esempio la frequenza con cui le password devono essere reimpostate o se è necessaria la crittografia dei dati. Per ulteriori informazioni, vedere [Create device security policies in Basic Mobility and Security](create-device-security-policies.md)and Microsoft   [365 compliance center.](../../compliance/microsoft-365-compliance-center.md)

Per istruzioni dettagliate sulla creazione e la distribuzione dei criteri dei dispositivi, vedi Creare criteri di sicurezza dei dispositivi [in Dispositivi mobili e sicurezza di base.](create-device-security-policies.md)

Se si desidera escludere un gruppo specifico di utenti dai criteri, è possibile aggiungere un gruppo al gruppo di esclusione.

## <a name="can-i-switch-from-exchange-activesync-device-management-to-basic-mobility-and-security-for-microsoft-365"></a>Posso passare dalla gestione Exchange ActiveSync dispositivi a Dispositivi mobili di base e sicurezza per Microsoft 365?

Se si usano già criteri di Exchange ActiveSync per gestire i dispositivi mobili, è possibile iniziare a usare Dispositivi mobili e sicurezza di base seguendo la procedura per configurare Dispositivi mobili e sicurezza di base. Per ulteriori informazioni, vedere [Protect user and device access](../../compliance/protect-access-to-data-and-services.md) e Set up Basic Mobility and [Security.](set-up.md)

Quando si applicano i criteri creati in Dispositivi mobili e sicurezza di base a gruppi di utenti Exchange ActiveSync, questi criteri sostituiscono i criteri cassetta postale dei dispositivi mobili e le regole di accesso ai dispositivi creati in precedenza nell'interfaccia di amministrazione di Exchange per tali utenti.

Dopo la registrazione di un dispositivo in Dispositivi mobili e sicurezza di base, qualsiasi criterio cassetta postale o regola di accesso del dispositivo Exchange ActiveSync dispositivo mobile applicato al dispositivo viene ignorato.

## <a name="i--set-up-basic-mobility-and-security-but-now-i-want-to-remove-it-what-are-the-steps"></a>Ho configurato Dispositivi mobili e sicurezza di base, ma ora voglio rimuoverlo. Quali sono i passaggi?

Purtroppo, non puoi semplicemente "annullare il provisioning" di Base Mobility and Security dopo aver configurato il provisioning. Puoi tuttavia rimuoverlo per gruppi di utenti rimuovendo i gruppi di sicurezza degli utenti dai criteri del dispositivo che hai creato. In caso contrario, puoi disabilitarlo per tutti rimuovendo i criteri del dispositivo in modo che non siano presenti e non vengano applicati. Per altre info, vedi [Disattivare Dispositivi mobili e sicurezza di base.](turn-off.md)