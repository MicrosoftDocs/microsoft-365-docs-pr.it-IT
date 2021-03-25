---
title: Esaminare eventi ed errori tramite il Visualizzatore eventi
description: Ottenere descrizioni e ulteriori passaggi per la risoluzione dei problemi (se necessario) per tutti gli eventi segnalati dal servizio Microsoft Defender for Endpoint.
keywords: risoluzione dei problemi, visualizzatore eventi, riepilogo del registro, codice di errore, non riuscito, Microsoft Defender per il servizio endpoint, non può essere avviato, interrotto, non può essere avviato
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 05/21/2018
ms.technology: mde
ms.openlocfilehash: 98c0f790c228989b261b95f3b87cdc9d18e4fa76
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068581"
---
# <a name="review-events-and-errors-using-event-viewer"></a>Esaminare eventi ed errori tramite il Visualizzatore eventi

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- Visualizzatore eventi
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

Puoi esaminare gli ID evento nel [Visualizzatore eventi](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) nei singoli dispositivi.

Ad esempio, se i dispositivi non vengono visualizzati nell'elenco **Dispositivi,** potrebbe essere necessario cercare gli ID evento nei dispositivi. È quindi possibile utilizzare questa tabella per determinare ulteriori passaggi per la risoluzione dei problemi.

**Aprire il Visualizzatore eventi e trovare il registro eventi del servizio Microsoft Defender for Endpoint:**

1. Scegliere **Start** dal menu Windows, digitare **Visualizzatore eventi** e premere **INVIO.**

2. Nell'elenco dei registri, in **Log Summary**, scorrere fino a visualizzare **Microsoft-Windows-SENSE/Operational**. Fare doppio clic sull'elemento per aprire il registro.

   a.  Puoi anche accedere al registro espandendo Registri **applicazioni** e servizi  >  **Microsoft**  >  **Windows**  >  **SENSE** e fai clic su **Operativo.**

   > [!NOTE]
   > SENSE è il nome interno usato per fare riferimento al sensore comportamentale che alimenta Microsoft Defender per Endpoint.

3. Gli eventi registrati dal servizio verranno visualizzati nel registro. Per un elenco degli eventi registrati dal servizio, vedere la tabella seguente.

<table>
<tbody style="vertical-align:top;">
<tr>
<th>ID evento</th>
<th>Messaggio</th>
<th>Descrizione</th>
<th>Azione</th>
</tr>
<tr>
<td>1</td>
<td>Servizio Microsoft Defender for Endpoint avviato (versione <code>variable</code> ).</td>
<td>Si verifica durante l'avvio, l'arresto e l'onbboarding del sistema.</td>
<td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
<td>2 </td>
<td>Arresto del servizio Microsoft Defender for Endpoint.</td>
<td>Si verifica quando il dispositivo viene arrestato o offboarded.</td>
<td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
<td>3 </td>
<td>Avvio del servizio Microsoft Defender for Endpoint non riuscito. Codice di errore: <code>variable</code> .</td>
<td>Servizio non avviato.</td>
<td>Esaminare altri messaggi per determinare le possibili cause e i passaggi per la risoluzione dei problemi.</td>
</tr>
<tr>
<td>4 </td>
<td>Microsoft Defender for Endpoint service ha contattato il server all'indirizzo <code>variable</code> .</td>
<td>Variabile = URL del Defender per i server di elaborazione degli endpoint.<br>
Questo URL corrisponde a quello visualizzato nel firewall o nell'attività di rete.</td>
<td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
<td>5 </td>
<td>Microsoft Defender for Endpoint service failed to connect to the server at <code>variable</code> .</td>
<td>Variabile = URL del Defender per i server di elaborazione degli endpoint.<br>
Il servizio non è stato in grado di contattare i server di elaborazione esterni in tale URL.</td>
<td>Verificare la connessione all'URL. Vedere <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</td>
</tr>
<tr>
<td>6 </td>
<td>Il servizio Microsoft Defender for Endpoint non è stato onboarding e non sono stati trovati parametri di onboarding.</td>
<td>Il dispositivo non è stato eseguito correttamente e non verrà segnalato al portale.</td>
<td>L'onboarding deve essere eseguito prima di avviare il servizio.<br>
Verificare che le impostazioni e gli script di onboarding siano stati distribuiti correttamente. Prova a ridistribuire i pacchetti di configurazione.<br>
Vedi <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard di dispositivi Windows 10.</a></td>
</tr>
<tr>
<td>7 </td>
<td>Microsoft Defender for Endpoint service failed to read the onboarding parameters. Errore: <code>variable</code> .</td>
<td>Variabile = descrizione dettagliata dell'errore. Il dispositivo non è stato eseguito correttamente e non verrà segnalato al portale.</td>
<td>Verificare che le impostazioni e gli script di onboarding siano stati distribuiti correttamente. Prova a ridistribuire i pacchetti di configurazione.<br>
Vedi <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard di dispositivi Windows 10.</a></td>
</tr>
<tr>
<td>8 </td>
<td>Microsoft Defender for Endpoint service failed to clean its configuration. Codice di errore: <code>variable</code> .</td>
<td><b>Durante l'onboarding:</b> Il servizio non è riuscito a pulire la configurazione durante l'onboarding. Il processo di onboarding continua. <br><br> <b>Durante l'offboarding:</b> Il servizio non è riuscito a pulire la configurazione durante l'offboarding. Il processo di offboarding è terminato ma il servizio continua a essere in esecuzione.
 </td>
<td><b>Onboarding:</b> Non è necessaria alcuna azione. <br><br> <b>Offboarding:</b> Riavviare il sistema.<br>
Vedi <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard di dispositivi Windows 10.</a></td>
</tr>
<tr>
<td>9 </td>
<td>Microsoft Defender for Endpoint service failed to change its start type. Codice di errore: <code>variable</code> .</td>
<td><b>Durante l'onboarding:</b> Il dispositivo non è stato eseguito correttamente e non verrà segnalato al portale. <br><br><b>Durante l'offboarding:</b> Impossibile modificare il tipo di avvio del servizio. Il processo di offboarding continua. </td>
<td>Verificare che le impostazioni e gli script di onboarding siano stati distribuiti correttamente. Prova a ridistribuire i pacchetti di configurazione.<br>
Vedi <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard di dispositivi Windows 10.</a></td>
</tr>
<tr>
<td>10  </td>
<td>Microsoft Defender for Endpoint service failed to persist the onboarding information. Codice di errore: <code>variable</code> .</td>
<td>Il dispositivo non è stato eseguito correttamente e non verrà segnalato al portale.</td>
<td>Verificare che le impostazioni e gli script di onboarding siano stati distribuiti correttamente. Prova a ridistribuire i pacchetti di configurazione.<br>
Vedi <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard di dispositivi Windows 10.</a></td>
</tr>
<tr>
<td>11 </td>
<td>Onboarding o ri-onboarding di Defender per il servizio endpoint completato.</td>
<td>Il dispositivo è stato eseguito correttamente.</td>
<td>Normale notifica operativa; non è necessaria alcuna azione.<br>
La visualizzazione del dispositivo nel portale potrebbe richiedere diverse ore.</td>
</tr>
<tr>
<td>12 </td>
<td>Microsoft Defender for Endpoint non è riuscito ad applicare la configurazione predefinita.</td>
<td>Il servizio non è stato in grado di applicare la configurazione predefinita.</td>
<td>Questo errore dovrebbe risolversi dopo un breve periodo di tempo.</td>
</tr>
<tr>
<td>13</td>
<td>Microsoft Defender per l'ID dispositivo endpoint calcolato: <code>variable</code> .</td>
<td>Normale processo operativo.</td>
<td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
<td>15 </td>
<td>Microsoft Defender for Endpoint non può avviare il canale di comando con URL: <code>variable</code> .</td>
<td>Variabile = URL del Defender per i server di elaborazione degli endpoint.<br>
Il servizio non è stato in grado di contattare i server di elaborazione esterni in tale URL.</td>
<td>Verificare la connessione all'URL. Vedere <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</td>
</tr>
<tr>
<td>17 </td>
<td>Microsoft Defender for Endpoint service failed to change the Connected User Experiences and Telemetry service location. Codice di errore: <code>variable</code> .</td>
<td>Si è verificato un errore con il servizio di telemetria di Windows.</td>
<td><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Verificare che il servizio dati di diagnostica sia abilitato.</a><br>
Verificare che le impostazioni e gli script di onboarding siano stati distribuiti correttamente. Prova a ridistribuire i pacchetti di configurazione.<br>
Vedi <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard di dispositivi Windows 10.</a></td>
</tr>
<tr>
<td>18 </td>
<td>Configurazione guidata (Windows Welcome) completata.</td>
<td>Il servizio verrà avviato solo al termine dell'installazione degli aggiornamenti di Windows.</td>
<td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
<td>19</td>
<td>Configurazione guidata (Windows Welcome) non è ancora stata completata.</td>
<td>Il servizio verrà avviato solo al termine dell'installazione degli aggiornamenti di Windows.</td>
<td>Normale notifica operativa; non è necessaria alcuna azione.<br>
Se l'errore persiste dopo un riavvio del sistema, assicurati che tutti gli aggiornamenti di Windows siano installati completamente.</td>
</tr>
<tr>
<td>20</td>
<td>Impossibile attendere il completamento della Configurazione guidata (Installazione di Windows). Codice di errore: <code>variable</code> .</td>
<td>Errore interno.</td>
<td>Se l'errore persiste dopo un riavvio del sistema, assicurati che tutti gli aggiornamenti di Windows siano installati completamente.</td>
</tr>
<tr>
<td>25</td>
<td>Il servizio Microsoft Defender for Endpoint non è riuscito a reimpostare lo stato di integrità nel Registro di sistema. Codice di errore: <code>variable</code> .</td>
<td>Il dispositivo non è stato eseguito correttamente.
Verrà segnalata al portale, tuttavia il servizio potrebbe non essere visualizzato come registrato in SCCM o nel Registro di sistema.</td>
<td>Verificare che le impostazioni e gli script di onboarding siano stati distribuiti correttamente. Prova a ridistribuire i pacchetti di configurazione.<br>
Vedi <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard di dispositivi Windows 10.</a></td>
</tr>
<tr>
<td>26</td>
<td>Microsoft Defender for Endpoint service non è riuscito a impostare lo stato di onboarding nel Registro di sistema. Codice di errore: <code>variable</code> .</td>
<td>Il dispositivo non è stato eseguito correttamente.<br>
Verrà segnalata al portale, tuttavia il servizio potrebbe non essere visualizzato come registrato in SCCM o nel Registro di sistema.</td>
<td>Verificare che le impostazioni e gli script di onboarding siano stati distribuiti correttamente. Prova a ridistribuire i pacchetti di configurazione.<br>
Vedi <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard di dispositivi Windows 10.</a></td>
</tr>
<tr>
<td>27</td>
<td>Microsoft Defender for Endpoint service failed to enable SENSE aware mode in Microsoft Defender Antivirus. Processo di onboarding non riuscito. Codice di errore: <code>variable</code> .</td>
<td>In genere, Microsoft Defender Antivirus entra in uno stato passivo speciale se un altro prodotto antimalware in tempo reale viene eseguito correttamente nel dispositivo e il dispositivo segnala a Defender for Endpoint.</td>
<td>Verificare che le impostazioni e gli script di onboarding siano stati distribuiti correttamente. Prova a ridistribuire i pacchetti di configurazione.<br>
Vedi <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard di dispositivi Windows 10.</a><br>
Verificare che la protezione antimalware in tempo reale venga eseguita correttamente.</td>
</tr>
<tr>
<td>28</td>
<td>Registrazione del servizio Esperienze utente connesse all'endpoint e telemetria di Microsoft Defender per endpoint non riuscita. Codice di errore: <code>variable</code> .</td>
<td>Si è verificato un errore con il servizio di telemetria di Windows.</td>
<td><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Verificare che il servizio dati di diagnostica sia abilitato.</a><br>
Verificare che le impostazioni e gli script di onboarding siano stati distribuiti correttamente. Prova a ridistribuire i pacchetti di configurazione.<br>
Vedi <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard di dispositivi Windows 10.</a></td>
</tr>
<tr>
<td>29</td>
<td>Impossibile leggere i parametri di offboarding. Tipo di errore: %1, Codice errore: %2, Descrizione: %3 </td>
<td>Questo evento si verifica quando il sistema non&#39;i parametri di offboarding.</td>
<td>Assicurati che il dispositivo abbia accesso a Internet, quindi esegui di nuovo l'intero processo di offboarding. Assicurati che il pacchetto di offboarding non sia scaduto.</td>
</tr>
<tr>
<td>30</td>
<td>Microsoft Defender for Endpoint service failed to disable SENSE aware mode in Microsoft Defender Antivirus. Codice di errore: <code>variable</code> .</td>
<td>In genere, Microsoft Defender Antivirus entra in uno stato passivo speciale se un altro prodotto antimalware in tempo reale viene eseguito correttamente nel dispositivo e il dispositivo segnala a Defender for Endpoint.</td>
<td>Verificare che le impostazioni e gli script di onboarding siano stati distribuiti correttamente. Prova a ridistribuire i pacchetti di configurazione.<br>
Vedi <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard di dispositivi Windows 10</a><br>
Verificare che la protezione antimalware in tempo reale venga eseguita correttamente.</td>
</tr>
<tr>
<td>31</td>
<td>Annullamento della registrazione di Esperienze utente connesse e telemetria di Microsoft Defender per endpoint non riuscito. Codice di errore: <code>variable</code> .</td>
<td>Si è verificato un errore con il servizio di telemetria di Windows durante l'onboarding. Il processo di offboarding continua.</td>
<td><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Verificare la presenza di errori con il servizio di telemetria di Windows.</a></td>
</tr>
<tr>
<td>32</td>
<td>Microsoft Defender for Endpoint service failed to request to stop itself after offboarding process. Codice errore: %1</td>
<td>Si è verificato un errore durante l'offboarding.</td>
<td>Riavviare il dispositivo.</td>
</tr>
<tr>
<td>33</td>
<td>Microsoft Defender for Endpoint service failed to persist SENSE GUID. Codice di errore: <code>variable</code> .</td>
<td>Un identificatore univoco viene usato per rappresentare ogni dispositivo che segnala al portale.<br>
Se l'identificatore non viene salvato in modo permanente, è possibile che lo stesso dispositivo venga visualizzato due volte nel portale.</td>
<td>Controlla le autorizzazioni del Registro di sistema nel dispositivo per assicurarti che il servizio possa aggiornare il Registro di sistema.</td>
</tr>
<tr>
<td>34</td>
<td>Microsoft Defender for Endpoint service failed to add itself as a dependency on the Connected User Experiences and Telemetry service, causing onboarding process to fail. Codice di errore: <code>variable</code> .</td>
<td>Si è verificato un errore con il servizio di telemetria di Windows.</td>
<td><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Verificare che il servizio dati di diagnostica sia abilitato.</a><br>
Verificare che le impostazioni e gli script di onboarding siano stati distribuiti correttamente. Prova a ridistribuire i pacchetti di configurazione.<br>
Vedi <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard di dispositivi Windows 10.</a></td>
</tr>
<tr>
<td>35</td>
<td>Il servizio Microsoft Defender for Endpoint non è riuscito a rimuovere se stesso come dipendenza dal servizio Esperienze utente connesse e telemetria. Codice di errore: <code>variable</code> .</td>
<td>Si è verificato un errore con il servizio di telemetria di Windows durante l'offboarding. Il processo di offboarding continua.
</td>
<td>Verificare la presenza di errori con il servizio dati di diagnostica Windows.</td>
</tr>
<tr>
<td>36</td>
<td>Registrazione delle esperienze utente connesse all'endpoint e del servizio di telemetria di Microsoft Defender per endpoint completata. Codice di completamento: <code>variable</code> .</td>
<td>Registrazione di Defender per Endpoint con il servizio Esperienze utente connesse e telemetria completata.</td>
<td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
<td>37</td>
<td>Microsoft Defender for Endpoint Un modulo sta per superare la quota. Modulo: %1, Quota: {%2} {%3}, Percentuale di utilizzo della quota: %4.</td>
<td>Il dispositivo ha quasi usato la quota allocata della finestra corrente di 24 ore. Sta per essere limitato.</td>
<td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
<td>38</td>
<td>La connessione di rete viene identificata come bassa. Microsoft Defender for Endpoint contatta il server ogni %1 minuti. Connessione a consumo: %2, Internet disponibile: %3, rete gratuita disponibile: %4.</td>
<td>Il dispositivo utilizza una rete a consumo/a pagamento e contatta il server con minore frequenza.</td>
<td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
<td>39</td>
<td>La connessione di rete viene identificata normalmente. Microsoft Defender for Endpoint contatta il server ogni %1 minuti. Connessione a consumo: %2, Internet disponibile: %3, rete gratuita disponibile: %4.</td>
<td>Il dispositivo non utilizza una connessione a consumo/a pagamento e contatta il server come al solito.</td>
<td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
<td>40</td>
<td>Lo stato della batteria è identificato come basso. Microsoft Defender for Endpoint contatta il server ogni %1 minuti. Stato batteria: %2.</td>
<td>Il dispositivo ha un livello di batteria basso e contatta il server con minore frequenza.</td>
<td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
<td>41</td>
<td>Lo stato della batteria viene identificato come normale. Microsoft Defender for Endpoint contatta il server ogni %1 minuti. Stato batteria: %2.</td>
<td>Il dispositivo non ha un livello di batteria basso e contatta il server come al solito.</td>
<td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
<td>42</td>
<td>Il componente WDATP di Microsoft Defender for Endpoint non è riuscito a eseguire l'azione. Componente: %1, Azione: %2, Tipo eccezione: %3, Messaggio eccezione: %4</td>
<td>Errore interno. Avvio del servizio non riuscito.</td>
<td>Se l'errore persiste, contattare il supporto tecnico.</td>
</tr>
<tr>
<td>43</td>
<td>Il componente WDATP di Microsoft Defender for Endpoint non è riuscito a eseguire l'azione. Componente: %1, Azione: %2, Tipo eccezione: %3, Errore eccezione: %4, Messaggio eccezione: %5</td>
<td>Errore interno. Avvio del servizio non riuscito.</td>
<td>Se l'errore persiste, contattare il supporto tecnico.</td>
</tr>
<tr>
<td>44</td>
<td>Offboarding di Defender per il servizio endpoint completato.</td>
<td>Il servizio è stato offboarded.</td>
<td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
<td>45</td>
<td>Impossibile eseguire la registrazione e avviare la sessione di traccia eventi [%1]. Codice errore: %2</td>
<td>Errore durante l'avvio del servizio durante la creazione della sessione ETW. Ciò ha causato un errore di avvio del servizio.</td>
<td>Se l'errore persiste, contattare il supporto tecnico.</td>
</tr>
<tr>
<td>46</td>
<td>Impossibile registrare e avviare la sessione di traccia eventi [%1] a causa della mancanza di risorse. Codice errore: %2. Ciò è molto probabile perché sono presenti troppe sessioni di traccia eventi attive. Il servizio verrà ritentato tra 1 minuto.</td>
<td>Si è verificato un errore durante l'avvio del servizio durante la creazione della sessione ETW a causa della mancanza di risorse. Il servizio è stato avviato ed è in esecuzione, ma non segnala alcun evento sensore fino all'avvio della sessione ETW.</td>
<td>Normale notifica operativa; non è necessaria alcuna azione. Il servizio tenterà di avviare la sessione ogni minuto.</td>
</tr>
<tr>
<td>47</td>
<td>La sessione di traccia eventi è stata registrata e avviata correttamente, recuperata dopo i precedenti tentativi non riusciti.</td>
<td>Questo evento segue l'evento precedente dopo l'avvio corretto della sessione ETW.</td>
<td>Normale notifica operativa; non è necessaria alcuna azione.</td>
</tr>
<tr>
<td>48</td>
<td>Impossibile aggiungere un provider [%1] alla sessione di traccia eventi [%2]. Codice di errore: %3. Ciò significa che gli eventi di questo provider non verranno segnalati.</td>
<td>Impossibile aggiungere un provider alla sessione ETW. Di conseguenza, gli eventi del provider non vengono segnalati.</td>
<td>Controllare il codice di errore. Se l'errore persiste, contattare il supporto tecnico.</td>
</tr>
</tr>
</tbody>
</table>

>Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-eventerrorcodes-belowfoldlink)

## <a name="related-topics"></a>Argomenti correlati
- [Onboard di dispositivi Windows 10](configure-endpoints.md)
- [Configurare le impostazioni del proxy del dispositivo e della connettività Internet](configure-proxy-internet.md)
- [Risolvere i problemi di Microsoft Defender per Endpoint](troubleshoot-onboarding.md)
