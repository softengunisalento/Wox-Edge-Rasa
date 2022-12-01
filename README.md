<div align="center">
    <a href="https://www.unisalento.it">
        <img src="imgReadme/unilogo.png" width="50%" height="50%" >
    </a>
</div>

> Implementazione di un intent matching layer stand-alone a supporto dell'interazione vocale con ATM evoluti in dispositivi constrained 

## Cos'è? 

Il progetto Wox Edge si colloca nel programma MilanoHub di Banca d’Italia ovvero il centro di innovazione realizzato dalla Banca d’Italia per sostenere l’evoluzione digitale del mercato finanziario. L'obiettivo prepostosi è la creazione di un ATM evoluto di ultima generazione che possa effettivamente aiutare chiunque abbia bisogno di supporto o voglia effetture operazioni sul proprio conto senza dover interagire manualmente con esso.

Obiettivi raggiunti:

• Completato: Configurare l’assistente in lingua Italiana;

• Completato: Rendere il sistema "stand-alone";

• Completato ma non ottimizzato: Ottimizzarlo per qualsiasi fascia d’età;

• Progettato ma non implementato: Renderlo raggiungibile tramite API;


Per fare ciò ci si è serviti di Rasa

## Knowledge Base

la Knowledge Base da configurare su Rasa era la seguente:

• Intent Totali: 401

• Frasi di addestramento totali: 2984 

• Intent di FallBack totali: 32

## Struttura file nlu.json


Di seguito la struttura del file json con alcuni esempi:

{ 
  "rasa_nlu_data": {
    "common_examples": [
      {
        "text": "Vorrei acquistare una box per la ricarica della macchina elettrica",
        "intent": "PR - (Prestito Green) Finalità Ricarica veicoli - IND (finalita-prestito-green)"
      },
{
        "text": "Ricarica di 100 euro",
        "intent": "- (LOG) - Accredito Denaro",
        "entities": [
          {
            "start": 0,
            "end": 8,
            "value": "Ricarica",
            "entity": "operazione_accredito"
          },
          {
            "start": 12,
            "end": 15,
            "value": "100",
            "entity": "number"
          },
          {
            "start": 16,
            "end": 20,
            "value": "euro",
            "entity": "currency-name"
          }
        ]
      },
      
      
## Struttura file domain.yml

intents:
  - '- (CONTEXT) - Anticipo Trattamento di Fine Servizio - DIR'
  - '- (CONTEXT) - Casa e Famiglia - DIR'
  - '- (CONTEXT) - Cessione del Quinto Pensione - DIR'
  - '- (CONTEXT) - Cessione del Quinto Stipendio - DIR'
  - '- (CONTEXT) - Leasing Autoveicoli - DIR'
  - '- (CONTEXT) - Leasing Nautico - DIR'
  - '- (CONTEXT) - Leasing Sicurezza - DIR'
  - '- (CONTEXT) - Mastercard Debit - DIR'
  - '- (CONTEXT) - Mastercard Platinum - DIR'
  - '- (CONTEXT) - Mastercard Platinum - DIR,'
  - '- (CONTEXT) - Mastercard Prepaid - DIR'
  - '- (CONTEXT) - Mutuo - DIR'
  - '- (CONTEXT) - Noleggio Lungo Termine - DIR'
  - '- (CONTEXT) - Persona in Chiaro - DIR'
  - '- (CONTEXT) - Prestito Green - DIR'
  - '- (CONTEXT) - Prestito Prontotuo - DIR'
  - '- (CONTEXT) - Prestito d'Onore - DIR'
  - '- (CONTEXT) - Protezione Vita - DIR'
  - '- (CONTEXT) - Sella Premium - DIR'
  - '- (CONTEXT) - Sella Start - DIR'
  - ...


responses:
  utter_-_(CONTEXT)_-_Anticipo_Trattamento_di_Fine_Servizio_-_DIR:
  - text : Se ti interessa conoscere di più sull'Anticipo del Trattamento di Fine Servizio, posso fornirti una descrizione generale sul prodotto oppure rispondere ad alcune domande più specifiche. Per esempio, puoi chiedermi qualcosa a proposito dei destinatari o del rimborso.
  utter_-_(CONTEXT)_-_Casa_e_Famiglia_-_DIR:
  - text :Riguardo l'assicurazione Casa e Famiglia posso fornirti una descrizione generica oppure posso rispondere a domande specifiche riguardanti costi ed eventi coperti. Scegli tu che cosa chiedermi!
  - ...









