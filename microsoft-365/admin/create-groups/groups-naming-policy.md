---
title: Criteri di denominazione dei gruppi di Office 365
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
description: Informazioni su come creare un criterio di denominazione per i gruppi di Office 365.
ms.openlocfilehash: 50ea076e22680a444cb9acf04466a7e7d052bb7a
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42241393"
---
# <a name="office-365-groups-naming-policy"></a>Criteri di denominazione dei gruppi di Office 365

Per applicare una strategia di denominazione coerente per i gruppi creati dagli utenti dell'organizzazione, è possibile utilizzare un criterio di denominazione del gruppo. I criteri di denominazione consentono all'utente e agli utenti di identificare la funzione del gruppo, dell'appartenenza, dell'area geografica o di chi ha creato il gruppo. Il criterio di denominazione può anche contribuire alla categorizzazione dei gruppi nella rubrica. È possibile utilizzare il criterio per bloccare le parole specifiche che vengono utilizzate nei nomi e negli alias di gruppo.

I criteri di denominazione vengono applicati ai gruppi creati in tutti i carichi di lavoro dei gruppi (come Outlook, Microsoft teams, SharePoint, planner, Yammer e così via). Viene applicato sia al nome del gruppo sia all'alias di gruppo. Viene applicato quando un utente crea un gruppo e quando viene modificato il nome o l'alias del gruppo per un gruppo esistente.

> [!TIP]
> I criteri di denominazione del gruppo di Office 365 si applicano solo ai gruppi di Office 365. Non si applica ai gruppi di distribuzione creati in Exchange Online. Per creare un criterio di denominazione per i gruppi di distribuzione, vedere [Create a Distribution Group Naming Policy](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).

I criteri di denominazione del gruppo sono composti dalle funzionalità seguenti:

- **Criteri di denominazione dei suffissi**: è possibile utilizzare prefissi o suffissi per definire la convenzione di denominazione di gruppi (ad esempio,\_"\_GRP US\_My Group Engineering"). I prefissi o suffissi possono essere stringhe fisse o attributi utente come [Department] che verranno sostituiti in base all'utente che crea il gruppo.

- **Parole bloccate personalizzate**: è possibile caricare una serie di parole bloccate specifiche per la propria organizzazione che verrebbero bloccate nei gruppi creati dagli utenti. Ad esempio: ""CEO, Payroll, HR" (CEO, Buste paga, RU)".

## <a name="licensing-requirements"></a>Requisiti per la licenza

L'utilizzo dei criteri di denominazione di Azure AD per i gruppi di Office 365 richiede che siano in possesso, ma non necessariamente, di una licenza di Azure Active Directory Premium P1 o di una licenza di Azure AD Basic EDU per ogni utente univoco (compresi gli ospiti) che sia membro di uno o più gruppi di Office 365.
Questa operazione è necessaria anche per l'amministratore che crea i criteri di denominazione dei gruppi.

## <a name="prefix-suffix-naming-policy"></a>Prefisso-suffisso Naming Policy

I prefissi e i suffissi possono essere stringhe fisse o attributi utente.

### <a name="fixed-strings"></a>Stringhe fisse

È possibile utilizzare stringhe brevi che consentono di differenziare i gruppi nell'elenco indirizzi globale e nel NAV sinistro dei carichi di lavoro di gruppo. Alcuni dei suffissi comuni prefissi sono parole chiave come "GRP\_Name", "\#Name", "\_Name"

### <a name="attributes"></a>Attributi

È possibile utilizzare gli attributi che consentono di identificare chi ha creato il gruppo come [Department] e dove è stato creato da like [Country].

|||
|:-----|:-----|
|**Esempi**|Criterio = "GRP [GroupName] [Department]"|
||Reparto dell'utente = Progettazione|
||Nome del gruppo creato = "GRP Mio gruppo Progettazione"|

Gli attributi di Azure Active Directory (Azure AD) supportati sono [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion], [title]

- Gli attributi utente non supportati sono considerati stringhe fisse. Ad esempio, [Codicepostale]"

- Gli attributi di estensione e gli attributi personalizzati non sono supportati.

È consigliabile usare attributi contenenti valori compilati per tutti gli utenti dell'organizzazione e non usare attributi con valori lunghi.

### <a name="things-to-look-out-for"></a>Elementi di cui eseguire la ricerca

- Durante la creazione dei criteri, la lunghezza totale delle stringhe di prefisso e suffisso è limitata a 53 caratteri.

- Prefissi e suffissi possono contenere caratteri speciali supportati nel nome e nell'alias del gruppo. Quando i prefissi e suffissi contengono caratteri speciali non consentiti nell'alias del gruppo, questi vengono rimossi e applicati all'alias del gruppo. In questo caso, quindi, i prefissi e suffissi applicati al nome del gruppo sarebbero diversi da quelli applicati all'alias del gruppo.

- Se si utilizzano i gruppi connessi di Yammer Office 365, evitare di usare i seguenti caratteri nei criteri di denominazione: \#@ \[, \], \<,, \>e. Se questi caratteri sono inclusi nei criteri di denominazione, gli utenti di Yammer regolari non potranno creare gruppi.

## <a name="custom-blocked-words"></a>Parole bloccate personalizzate

È possibile immettere un elenco separato da virgole di parole bloccate che verranno bloccate nei nomi e negli alias di gruppo.

Il controllo delle parole bloccate viene effettuato sul nome del gruppo immesso dall'utente. Pertanto, se l'utente immette ' darnit ' e\_' prefix ' è il criterio di denominazione\_,' prefix darnit ' avrà esito negativo.

Non vengono eseguite ricerche in una stringa secondaria. in particolare, è necessaria una corrispondenza esatta tra il nome immesso dall'utente e le parole bloccate personalizzate per attivare un errore. La ricerca di sottostringhe non viene eseguita in modo che gli utenti possono usare parole normali come "rinculo" anche se "culo" è una parola bloccata.

**Aspetti da cercare**:

- Per le parole bloccate non viene fatta distinzione tra maiuscole e minuscole.

- Quando si immette una parola bloccata, il client del gruppo mostrerà un messaggio di errore con la parola bloccata.

- Per le parole bloccate usate non sono previste limitazioni sul limite di caratteri.

- Vi è un limite superiore di 5000 parole che possono essere impostate come parole bloccate.

## <a name="admin-override"></a>Override per gli amministratori

Alcuni amministratori non sono soggetti a questi criteri in tutti gli endpoint e i carichi di lavoro di gruppo, possono quindi creare gruppi con le parole bloccate e con le convenzioni di denominazione che preferiscono. L'elenco seguente contiene i ruoli di amministratore non soggetti ai criteri di denominazione del gruppo.

- Amministratore globale

- Supporto partner - Livello 1

- Supporto partner - Livello 2

- Amministratore degli account utente

- Ruoli con autorizzazioni di scrittura nella directory

## <a name="how-to-set-up-the-naming-policy"></a>Come configurare i criteri di denominazione

Per impostare i criteri di denominazione:

1. In [Azure Active Directory](https://aad.portal.azure.com), in **gestione**, fare clic su **gruppi**.
2. In **Impostazioni**fare clic su **criteri di denominazione**.
3. Scegliere la scheda **criteri di denominazione dei gruppi** .
4. In **criterio corrente**scegliere se si desidera richiedere un prefisso o un suffisso o entrambi, quindi selezionare le caselle di controllo appropriate.
5. Scegliere tra l' **attributo** e la **stringa** per ogni riga e quindi specificare l'attributo o la stringa.
6. Dopo aver aggiunto i prefissi e i suffissi necessari, fare clic su **Salva**.

![Schermata delle impostazioni dei criteri di denominazione del gruppo in Azure Active Directory](../media/groups-naming-policy-azure.png)

## <a name="naming-policy-experiences-across-office-365-apps"></a>Esperienza dei criteri di denominazione nelle app di Office 365

Le app di Office 365 sono state aggiornate in modo da mostrare un'anteprima del nome di gruppo in base ai criteri di denominazione (con prefissi e suffissi) quando un utente digita il nome e l'alias di gruppo. Quando l'utente immette parole bloccate visualizza un messaggio di errore e può rimuoverle.

## <a name="outlook-on-the-web"></a>Outlook sul web

Outlook sul Web (in precedenza noto come Outlook Web App o OWA) Visualizza il nome decorato dei criteri di denominazione quando l'utente digita un nome di gruppo o un alias di gruppo. Quando un utente immette una parola bloccata personalizzata, nell'interfaccia utente viene visualizzato un messaggio di errore insieme alla parola, in modo che l'utente possa rimuoverla. Di seguito sono illustrati gli snapshot di Outlook sul Web.

![Visualizzazione affiancata dei criteri di denominazione del gruppo nei gruppi di Office 365](../media/1a21657a-c542-4d9e-ac7d-887ac542a9d9.png)

## <a name="outlook-desktop"></a>Outlook desktop

I gruppi creati in Outlook desktop sono conformi ai criteri di denominazione. L'app desktop Outlook non mostra ancora l'anteprima dei criteri di denominazione e non restituisce errori relativi alle parole bloccate personalizzate quando l'utente immette il nome del gruppo. Tuttavia, i criteri di denominazione verranno applicati automaticamente alla selezione di creazione/modifica e gli utenti verranno presentati con errori se sono presenti parole bloccate personalizzate nel nome o nell'alias del gruppo.

## <a name="microsoft-teams"></a>Microsoft Teams

Microsoft teams Visualizza il nome decorato dei criteri di denominazione quando l'utente digita il nome di un team. Quando un utente immette una parola bloccata personalizzata, viene visualizzato un messaggio di errore insieme alla parola bloccata in modo che l'utente possa rimuoverla.

![Esempio di criteri di denominazione dei gruppi in Microsoft teams bloccato](../media/7c904546-5853-4642-949a-a55dbb004eca.png)

## <a name="sharepoint"></a>SharePoint

SharePoint Visualizza il nome dei criteri di denominazione quando l'utente digita un nome di sito o un indirizzo di posta elettronica di gruppo. Quando un utente immette una parola bloccata personalizzata, viene visualizzato un messaggio di errore insieme alla parola, in modo che l'utente possa rimuoverla.

![Criteri di denominazione dei gruppi-nome bloccato del sito di SharePoint](../media/cf0d6158-fd32-4a93-ac24-2e037102c42c.png)

## <a name="microsoft-stream"></a>Microsoft Stream

Microsoft Stream mostra il nome decorato dei criteri di denominazione quando l'utente digita il nome o l'alias di posta elettronica di un gruppo. Quando un utente immette una parola bloccata personalizzata, viene visualizzato un messaggio di errore con la parola, in modo che l'utente possa rimuoverla.

![Esempio di criteri di denominazione dei gruppi bloccati per Microsoft Stream](../media/9748f52a-3814-41a6-9ac1-4e8cd4c91011.png)

## <a name="outlook-ios-and-android-app"></a>App Outlook per iOS e Android

I gruppi creati nelle app Outlook sono conformi ai criteri di denominazione. Outlook Mobile Visualizza l'anteprima dei criteri di denominazione quando si immette il nome del gruppo. Quando un utente immette una parola bloccata personalizzata, viene visualizzato un messaggio di errore per la creazione del gruppo, in modo che l'utente possa rimuovere la parola bloccata.

## <a name="planner"></a>Planner

Planner è conforme ai criteri di denominazione. Planner Visualizza l'anteprima dei criteri di denominazione quando si immette il nome del piano. Quando un utente immette una parola bloccata personalizzata, viene visualizzato un messaggio di errore per la creazione del piano, in modo che l'utente possa rimuovere la parola bloccata.

![Criteri di denominazione dei gruppi-esempio di creazione di un nuovo piano bloccato](../media/ea692b44-3a56-4e6d-bcb8-8444fe5bbc4f.png)

## <a name="dynamics-365-for-customer-engagement"></a>Dynamics 365 per l'impegno dei clienti

Dynamics 365 per l'impegno dei clienti è conforme ai criteri di denominazione. Dynamics 365 Visualizza il nome decorato dei criteri di denominazione quando l'utente digita un nome di gruppo o un alias di posta elettronica di gruppo. Quando l'utente immette una parola bloccata personalizzata, viene visualizzato un messaggio di errore con la parola bloccata in modo che l'utente possa rimuoverla.

![Dynamics 365](../media/8190331c-6779-42bd-a6b3-f7007428c8ae.png)

## <a name="school-data-sync-sds"></a>School Data Sync (SDS)

I gruppi creati tramite SDS sono conformi ai criteri di denominazione, ma i criteri non vengono applicati automaticamente. Gli amministratori di SDS devono aggiungere i prefissi e suffissi ai nomi delle classi per cui occorre creare gruppi e quindi caricarli in SDS. In caso contrario, la creazione o modifica di gruppi avrà esito negativo.

## <a name="outlook-customer-manager-ocm"></a>Gestione dei clienti di Outlook (OCM)

Outlook Customer Manager è conforme ai criteri di denominazione. I criteri di denominazione vengono applicati automaticamente al gruppo creato in gestione clienti di Outlook. Se una qualsiasi delle parole all'interno di "All Sales Team" è definita come una parola bloccata personalizzata, la creazione del gruppo in OCM verrà bloccata. L'utente non sarà in grado di creare il gruppo OCM e verrà bloccato utilizzando l'app OCM. "

## <a name="classroom-app"></a>App Classroom

I gruppi creati nell'app Classroom sono compatibili con i criteri di denominazione, ma i criteri non vengono applicati automaticamente e non viene mostrata un'anteprima dei criteri di denominazione quando gli utenti inseriscono il nome di un gruppo di classe. Gli utenti devono quindi immettere il nome decorato del gruppo di classe con prefissi e suffissi. In caso contrario, la creazione o modifica del gruppo di classe avrà esito negativo con errori.

## <a name="power-bi"></a>Power BI

I gruppi creati nelle aree di lavoro di Power BI sono conformi ai criteri di denominazione, ma il criterio di denominazione non viene applicato automaticamente. L'anteprima dei criteri di denominazione non viene visualizzata agli utenti quando si immette un nome dell'area di lavoro di Power BI.

Il nome consigliato, con il criterio di denominazione applicato, viene visualizzato nei dettagli dell'errore su Crea o modifica aree di lavoro. Questo significa che gli utenti devono immettere il nome dell'area di lavoro decorata con prefissi e suffissi. In caso contrario, l'area di lavoro creare o modificare avrà esito negativo con errori.

## <a name="yammer"></a>Yammer

Quando un utente ha eseguito l'accesso a Yammer con il proprio account di Azure Active Directory crea un gruppo o modifica un nome di gruppo, il nome del gruppo sarà conforme ai criteri di denominazione. Ciò vale sia per i gruppi di Office 365 connessi che per tutti gli altri gruppi di Yammer.

Se è stato creato un gruppo di Office 365 connesso prima che il criterio di denominazione sia sul posto, il nome del gruppo non seguirà automaticamente i criteri di denominazione. Quando un utente modifica il nome del gruppo, viene richiesto di aggiungere il prefisso e il suffisso.

Se i criteri di denominazione includono caratteri che non possono essere inclusi nei nomi dei gruppi di Yammer, solo gli amministratori saranno in grado di creare un gruppo connesso in Yammer.

## <a name="staffhub"></a>StaffHub

I team di StaffHub non seguono i criteri di denominazione, ma il gruppo di Office 365 sottostante. Al nome del team StaffHub non si applicano prefissi e suffissi e le parole bloccate personalizzate non vengono controllate. Tuttavia, StaffHub applica i prefissi e i suffissi e rimuove le parole bloccate dal gruppo di Office 365 sottostante.

## <a name="exchange-powershell"></a>PowerShell di Exchange

I cmdlet di Exchange PowerShell sono conformi ai criteri di denominazione. Se nei nomi e negli alias di gruppo non viene seguita la convenzione di denominazione, gli utenti ricevono messaggi di errore con i suffissi e prefissi suggeriti e per le parole bloccate personalizzate.

## <a name="azure-active-directory-powershell-cmdlets"></a>Cmdlet di Azure Active Directory PowerShell

I cmdlet di Azure Active Directory PowerShell sono conformi ai criteri di denominazione. Se nei nomi e negli alias di gruppo non viene seguita la convenzione di denominazione, gli utenti ricevono messaggi di errore con i suffissi e prefissi suggeriti e per le parole bloccate personalizzate.

## <a name="exchange-admin-center"></a>Interfaccia di amministrazione di Exchange

L'interfaccia di amministrazione di Exchange (EAC) è conforme ai criteri di denominazione. Durante le azioni di creazione e modifica, se nei nomi e negli alias di gruppo non viene seguita la convenzione di denominazione, gli utenti ricevono messaggi di errore con i suffissi e prefissi suggeriti e per le parole bloccate personalizzate.

## <a name="microsoft-365-admin-center"></a>Interfaccia di amministrazione di Microsoft 365

L'interfaccia di amministrazione di Microsoft 365 è conforme ai criteri di denominazione. Durante le azioni di creazione e modifica, i criteri di denominazione vengono applicati automaticamente. Se gli utenti immettono parole bloccate personalizzate, ricevono errori appropriati. L'interfaccia di amministrazione di Microsoft 365 non mostra ancora l'anteprima dei criteri di denominazione e non restituisce gli errori di Word bloccati personalizzati, quando l'utente immette il nome del gruppo.

## <a name="azure-active-directory-portal"></a>Portale di Azure Active Directory

Il portale di Azure Active Directory è conforme ai criteri di denominazione. Il portale di Azure Active Directory Visualizza l'anteprima dei criteri di denominazione quando si immette il nome del gruppo. Quando un utente immette una parola bloccata personalizzata, viene visualizzato un messaggio di errore per la creazione del gruppo, in modo che l'utente possa rimuovere la parola bloccata.

## <a name="more-articles-on-naming-policy"></a>Altri articoli sui criteri di denominazione

[Applicazione di un criterio di denominazione per i gruppi di Office 365 in Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=868340)

[Cmdlet di Azure Active Directory per la configurazione delle impostazioni di gruppo](https://go.microsoft.com/fwlink/?linkid=868341)
