---
title: Power BI nell'organizzazione
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- PWB150
ms.assetid: d7941332-8aec-4e5e-87e8-92073ce73dc5
ROBOTS: NOINDEX
description: Informazioni su Power BI e su come gli utenti dell'organizzazione possono utilizzare questo servizio di analisi aziendale.
ms.openlocfilehash: cabe489915061a773c0faeb8687695f2672fe478
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399303"
---
# <a name="power-bi-in-your-organization"></a>Power BI nell'organizzazione

Questa pagina illustra in che modo gli utenti dell'organizzazione possono usare Power BI e come controllare in che modo l'organizzazione acquisisce il servizio.
    
## <a name="what-is-power-bi"></a>Che cos'è Power BI?

Microsoft Power BI consente agli utenti di visualizzare dati, condividere scoperte e collaborare in nuovi modi intuitivi. Per altre informazioni, vedere il [sito Web di Power BI](https://powerbi.microsoft.com/en-us/).
  
## <a name="does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements"></a>Power BI soddisfa i requisiti di conformità nazionali, regionali e specifici del settore?

Per ulteriori informazioni sulla conformità a Power BI, vedere il [Centro protezione Microsoft](https://go.microsoft.com/fwlink/?LinkId=785324).
  
## <a name="how-do-users-sign-up-for-power-bi"></a>In che modo gli utenti si iscrivono a Power BI?

In qualità di amministratore, è possibile iscriversi a Power BI tramite il [sito Web di Power bi](https://powerbi.microsoft.com/en-us/). È inoltre possibile eseguire la registrazione tramite la pagina acquisto servizi nell'interfaccia di amministrazione di Microsoft 365. Quando un amministratore si iscrive per Power BI, può assegnare licenze di sottoscrizione utente agli utenti che devono avere accesso.
  
Inoltre, i singoli utenti dell'organizzazione potrebbero essere in grado di iscriversi a Power BI tramite il [sito Web di Power BI](https://powerbi.microsoft.com/en-us/). Quando un utente dell'organizzazione si iscrive a Power BI, gli viene assegnata automaticamente una licenza di Power BI.
  
## <a name="how-do-individual-users-in-my-organization-sign-up"></a>In che modo si iscrivono i singoli utenti dell'organizzazione?

Esistono tre possibili scenari:
  
### <a name="scenario-1-your-organization-already-has-an-existing-microsoft-365-environment-and-the-user-signing-up-for-power-bi-already-has-an-microsoft-365-account"></a>Scenario 1: l'organizzazione dispone già di un ambiente Microsoft 365 esistente e l'utente che effettua l'iscrizione a Power BI dispone già di un account Microsoft 365.

In questo scenario, se un utente ha già un account aziendale o dell'istituto di istruzione nel tenant (ad esempio contoso.com) ma non ha ancora Power BI, Microsoft attiverà semplicemente il piano per tale account e l'utente riceverà automaticamente una notifica relativa all'uso del servizio Power BI.
  
### <a name="scenario-2-your-organization-has-an-existing-microsoft-365-environment-and-the-user-signing-up-for-power-bi-doesnt-have-an-microsoft-365-account"></a>Scenario 2: l'organizzazione dispone di un ambiente Microsoft 365 esistente e l'utente che effettua l'iscrizione a Power BI non dispone di un account Microsoft 365.

In questo scenario, l'utente dispone di un indirizzo di posta elettronica nel dominio dell'organizzazione (ad esempio, contoso.com) ma non dispone ancora di un account Microsoft 365. In questo caso, l'utente può iscriversi a Power BI per ricevere automaticamente un account. In questo modo l'utente potrà accedere al servizio Power BI. Ad esempio, se un dipendente denominato Nancy utilizza l'indirizzo di posta elettronica del lavoro (ad esempio, Nancy@contoso.com) per iscriversi, Microsoft aggiungerà automaticamente Nancy come utente nell'ambiente Contoso Microsoft 365 e attiverà Power BI per tale account.
  
### <a name="scenario-3-your-organization-does-not-have-a-microsoft-365-environment-connected-to-your-email-domain"></a>Scenario 3: l'organizzazione non dispone di un ambiente Microsoft 365 connesso al dominio di posta elettronica.

L'organizzazione non deve intraprendere alcuna azione amministrativa per poter usufruire di Power BI.
  
> [!IMPORTANT]
> Se l'organizzazione dispone di più domini di posta elettronica e si preferisce che tutte le estensioni di indirizzi di posta elettronica siano nello stesso tenant, prima che gli utenti creino il tenant principale, aggiungere tutti i domini dell'indirizzo di posta elettronica al tenant prima che gli utenti creino il tenant principale. Non esiste un meccanismo automatico per spostare gli utenti tra i tenant dopo che sono stati creati. Per ulteriori informazioni su questo processo, vedere [se si dispone di più domini, è possibile controllare il tenant a cui vengono aggiunti gli utenti?](#if-i-have-multiple-domains-can-i-control-the-tenant-that-users-are-added-to) più avanti in questo articolo e [aggiungere un dominio a Office 365](../setup/add-domain.md) online. 
  
## <a name="how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today"></a>Come cambierà la gestione delle identità per gli attuali utenti dell'organizzazione?

Se nell'organizzazione è già presente un ambiente Microsoft 365 e tutti gli utenti dell'organizzazione dispongono di account Microsoft 365, la gestione delle identità non cambierà.
  
Se nell'organizzazione è già presente un ambiente Microsoft 365 ma non tutti gli utenti dell'organizzazione dispongono di account Microsoft 365, verrà creato un utente nel tenant e verranno assegnate le licenze in base all'indirizzo di posta elettronica del lavoro o dell'Istituto di istruzione dell'utente. Questo significa che il numero di utenti da gestire in un determinato momento aumenterà man mano che nuovi utenti nell'organizzazione si iscriveranno al servizio.
  
Se la directory viene gestita in locale e si usa Active Directory Federation Services (ADFS), Microsoft non aggiungerà utenti al tenant e tutti gli utenti che proveranno ad aggiungersi al tenant riceveranno un messaggio che li invita a contattare l'amministratore dell'organizzazione.
  
Se l'organizzazione non dispone di un ambiente Microsoft 365 connesso al proprio dominio di posta elettronica, non verranno apportate modifiche alla modalità di gestione delle identità. Gli utenti verranno aggiunti a una nuova directory di utenti basata sul cloud e si avrà la possibilità di scegliere se assumere il ruolo di amministratore del tenant per gestirli.
  
## <a name="what-is-the-process-to-manage-a-tenant-created-by-microsoft-for-my-users"></a>Qual è la procedura per gestire un tenant creato da Microsoft per gli utenti?

Se Microsoft ha creato un tenant, è possibile chiedere di gestirlo eseguendo la procedura seguente:
  
1. Aggiungersi al tenant [iscrivendosi a Power BI](https://go.microsoft.com/fwlink/?LinkId=522448) con il dominio dell'indirizzo di posta elettronica che corrisponde al domino del tenant da gestire. Se ad esempio Microsoft ha creato il tenant contoso.com, sarà necessario aggiungersi con un indirizzo di posta elettronica che termina con @contoso.com. 
    
2. Richiedere il controllo di amministratore verificando di essere proprietari del dominio. Dopo l'aggiunta al tenant, è possibile alzarsi di livello al ruolo di amministratore verificando di essere proprietari del dominio, mediante la procedura seguente:
 
::: moniker range="o365-worldwide"
   
3. Accedere a [https://admin.microsoft.com](https://admin.microsoft.com).
 

::: moniker-end

::: moniker range="o365-germany"

3. Passare a [https://portal.office.de](https://portal.office.de).

::: moniker-end

::: moniker range="o365-21vianet"

3. Passare a [https://portal.partner.microsoftonline.cn](https://portal.partner.microsoftonline.cn).

::: moniker-end

    
4. Selezionare l'icona di avvio delle app in alto a sinistra e scegliere **Amministratore**.
    
    ![Icona di avvio delle app con l'applicazione di amministrazione evidenziata](../../media/4eea9dbc-591b-48be-9916-322d41c6525b.png)
  
5. Leggere le istruzioni riportate nella pagina **diventa amministratore** e quindi selezionare **Sì, voglio essere l'amministratore**.
    
    > [!NOTE]
    >  Se questa opzione non viene visualizzata, esiste già un amministratore sul posto. 
  
## <a name="if-i-have-multiple-domains-can-i-control-the-tenant-that-users-are-added-to"></a>Se si dispone di più domini, è possibile controllare il tenant a cui vengono aggiunti gli utenti?

Se non si fa niente, verrà creato un tenant per ogni domino o sottodominio di posta elettronica degli utenti.
  
Se si vuole che gli utenti stiano nello stesso tenant indipendentemente dalle estensioni dei loro indirizzi di posta elettronica:
  
- Creare in anticipo un tenant di destinazione oppure usare un tenant esistente e aggiungere tutti gli attuali domini e sottodomini da consolidare al suo interno. Quindi, tutti gli utenti con un indirizzo di posta elettronica che termina con questi domini e sottodomini verranno automaticamente aggiunti al tenant di destinazione quando si iscrivono.
    
> [!IMPORTANT]
> Non esiste un meccanismo automatizzato supportato per trasferire gli utenti da un tenant all'altro dopo la creazione. Per ulteriori informazioni sull'aggiunta di domini a un singolo tenant di Microsoft 365, vedere [aggiungere un dominio a Office 365](../setup/add-domain.md). 
  
> [!IMPORTANT]
> Per ulteriori informazioni e indicazioni sulla gestione dei tenant, vedere [che cos'è Power bi Administration?](https://docs.microsoft.com/power-bi/service-admin-administering-power-bi-in-your-organization). 
  
## <a name="how-can-i-prevent-users-from-joining-my-existing-tenant"></a>In che modo è possibile impedire agli utenti di partecipare al tenant esistente?

È possibile eseguire operazioni come amministratore per impedire agli utenti di partecipare al tenant esistente. Se si blocca questo, i tentativi degli utenti di accedere avranno esito negativo e verranno indirizzati a contattare l'amministratore dell'organizzazione. Non è necessario ripetere questa procedura se la distribuzione automatica delle licenze è già stata disabilitata prima (ad esempio, Office 365 Education per studenti, docenti e personale).
  
Questa procedura richiede l'uso di Windows PowerShell. Per informazioni su Windows PowerShell, vedere [Guida introduttiva di PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=286814).
  
Per eseguire la procedura seguente, è necessario installare la versione più recente di 64 bit del [modulo di PowerShell di Azure Active Directory V2](https://www.powershellgallery.com/packages/AzureADPreview/2.0.2.5).
  
Dopo aver selezionato il collegamento, selezionare **Esegui** per eseguire il pacchetto del programma di installazione. 
  
 **Disabilitare l'aggiunta automatica al tenant**: usare questo comando di Windows PowerShell per impedire ai nuovi utenti di aggiungersi a un tenant gestito:
  
Per disabilitare l'aggiunta automatica di nuovi utenti al tenant:  `Set-MsolCompanySettings -AllowEmailVerifiedUsers $false`
  
Per abilitare l'aggiunta automatica di nuovi utenti al tenant:  `Set-MsolCompanySettings -AllowEmailVerifiedUsers $true`
  
> [!NOTE]
> Questo blocco impedisce ai nuovi utenti dell'organizzazione di iscriversi a Power BI. Gli utenti che si iscrivono a Power BI prima della disabilitazione delle nuove iscrizioni per l'organizzazione manterranno le proprie licenze. Vedere il [come si rimuove Power BI per gli utenti che hanno già effettuato l'iscrizione?](#how-do-i-remove-power-bi-for-users-that-already-signed-up) per istruzioni su come è possibile rimuovere l'accesso a Power BI per gli utenti che in precedenza avevano effettuato l'iscrizione al servizio. 
  
## <a name="how-can-i-allow-users-to-join-my-existing-tenant"></a>Come si può consentire agli utenti di partecipare al tenant esistente?

Per consentire agli utenti di aggiungersi al tenant, eseguire il comando opposto a quello descritto nella domanda precedente:  `Set-MsolCompanySettings -AllowEmailVerifiedUsers $true`
  
## <a name="how-do-i-verify-if-i-have-the-block-on-in-the-tenant"></a>Come si verifica se è attivato il blocco nel tenant?

Usare il seguente script di PowerShell:  `Get-MsolCompanyInformation | fl allow*`
  
## <a name="how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi"></a>Come è possibile impedire agli utenti di iniziare a usare Power BI?

 **Disabilitare la distribuzione automatica delle licenze**: Usare questo script di Windows PowerShell per disabilitare la distribuzione automatica delle licenze per gli attuali utenti. Non è necessario ripetere questa procedura se la distribuzione automatica delle licenze è già stata disabilitata prima (ad esempio, Office 365 Education per studenti, docenti e personale). 
  
Per disabilitare la distribuzione automatica delle licenze per gli attuali utenti:  `Set-MsolCompanySettings -AllowAdHocSubscriptions $false`
  
Per abilitare la distribuzione automatica delle licenze per gli attuali utenti:  `Set-MsolCompanySettings -AllowAdHocSubscriptions $true`
  
> [!NOTE]
> Il flag *AllowAdHocSubscriptions* viene utilizzato per controllare diverse funzionalità utente nell'organizzazione, inclusa la possibilità per gli utenti di iscriversi al servizio Azure Rights Management. La modifica di questo contrassegno avrà effetto su tutte queste funzionalità. 
  
## <a name="how-can-i-allow-my-existing-users-to-sign-up-for-power-bi"></a>Come si può consentire agli utenti di iscriversi a Power BI?

Per consentire agli utenti di iscriversi a Power BI, eseguire il comando opposto a quello descritto nella domanda precedente:  `Set-MsolCompanySettings -AllowAdHocSubscriptions $true`
  
## <a name="how-do-i-remove-power-bi-for-users-that-already-signed-up"></a>Come si rimuove Power BI per gli utenti che hanno già effettuato l'iscrizione?

Se un utente ha effettuato l'iscrizione a Power BI ma non si vuole più consentirgli di accedere al servizio, è possibile rimuovere la licenza di Power BI di tale utente.

::: moniker range="o365-worldwide"

> [!NOTE]
> Se non si usa la nuova interfaccia di amministrazione di Microsoft 365, è possibile attivarla selezionando l'opzione **Prova la nuova interfaccia di amministrazione** che si trova nella parte superiore della home page.
  
1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.
    
2. Individuare l'utente per il quale si desidera rimuovere la licenza, quindi selezionarne il nome.
    
3. Nella scheda **licenze e app** deselezionare la casella di controllo **Microsoft Power bi** .
    
4. Selezionare **Salva modifiche**.

::: moniker-end

  
::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.

2. Individuare l'utente per il quale si desidera rimuovere la licenza, quindi selezionarne il nome.
    
3. Accanto a **licenze di prodotto**, selezionare **modifica**. 
    
4. Disattiva l'opzione **Microsoft Power bi** .
    
5. Selezionare **Salva**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.

2. Individuare l'utente per il quale si desidera rimuovere la licenza, quindi selezionarne il nome.
    
3. Accanto a **licenze di prodotto**, selezionare **modifica**. 
    
4. Disattiva l'opzione **Microsoft Power bi** .
    
5. Selezionare **Salva**.

::: moniker-end 


## <a name="how-do-i-know-when-new-users-have-joined-my-tenant"></a>Come si può sapere se nuovi utenti si aggiungono al tenant?

Ai nuovi utenti che si aggiungono al tenant nell'ambito di questo programma viene assegnata una licenza univoca che è possibile filtrare nel riquadro degli utenti attivi del dashboard di amministrazione.
  
Per creare questa nuova visualizzazione, nell'interfaccia di amministrazione, seguire la procedura descritta in [creare una visualizzazione utente personalizzata](../add-users/create-edit-or-delete-a-custom-user-view.md#create-a-custom-user-view). In **licenza prodotto assegnato**selezionare **Microsoft Power bi**. Dopo aver creato la nuova visualizzazione, sarà possibile visualizzare tutti gli utenti del tenant che si sono iscritti al programma.
  
## <a name="are-there-any-additional-things-i-should-be-prepared-for"></a>È necessario prepararsi per altro?

Potrebbe verificarsi un aumento nella richiesta di reimpostazione delle password. Per informazioni su questo processo, vedere [Reimpostazione della password di un utente](../add-users/reset-passwords.md).
  
È possibile rimuovere un utente dal tenant tramite il processo standard nell'interfaccia di amministrazione. Se tuttavia l'utente ha ancora un indirizzo di posta elettronica attivo dell'organizzazione, potrà riaggiungersi a meno che non si impedisca a tutti di aggiungersi.
  
## <a name="why-did-1-million-licenses-for-microsoft-power-bi-show-up-in-my-tenant"></a>Perché le licenze 1 milione per Microsoft Power BI sono state visualizzate nel tenant?

Gli utenti di un'organizzazione idonea sono a loro volta idonei a usare il servizio Microsoft Power BI e queste licenze rappresentano la capacità disponibile per i nuovi utenti di Power BI nel tenant. Per queste licenze non vengono addebitati costi. Se si è scelto di consentire agli utenti di iscriversi a Power BI da soli, al termine del processo di iscrizione viene assegnata una delle licenze gratuite disponibili. È inoltre possibile scegliere di assegnare tali licenze agli utenti tramite l'interfaccia di amministrazione.
  
## <a name="is-this-free-will-i-be-charged-for-these-licenses"></a>È gratuito? Verrà addebitato un costo per queste licenze?

Queste licenze sono valide per la versione gratuita di Power BI. Se si è interessati a funzionalità aggiuntive, prendere in considerazione la versione Power BI Pro.
  
## <a name="why-1-million-licenses"></a>Perché un milione di licenze?

È stato scelto un numero sufficiente perché la maggior parte delle organizzazioni avrebbe ampie licenze per fornire questo vantaggio senza indugio ai propri utenti.
  
## <a name="what-if-i-need-more-than-1-million-licenses"></a>Che cosa succede se servono più di un milione di licenze?

Se è necessario acquisire altre licenze, contattare il rappresentante Microsoft per altre informazioni.
