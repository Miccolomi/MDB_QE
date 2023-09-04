Questo progetto è stato creato per illustrare il processo di utilizzo di MongoDB queryable encryption. 
Segui le istruzioni per configurare e eseguire il progetto.

## 1. Generazione del certificato

Esegui il seguente comando per generare un certificato `master-key.txt` nella stessa directory del progetto:

openssl rand 96 > master-key.txt


## 2. Modifica i file

modifica il file your_credential.js e aggiungi il link al tuo MDB v.7
il path alla libreria "mongodb-client-encryption" da scaricare e aprire nelal stessa folder di progetto
inserisci il path al file della libreria anche nelle variabili "extraOptions" dei file make_data_key e insert_encrypted_document.

## 3. Esegui

A - node make_data_key.js (solo la prima volta)
    Potresti avere degli errori di sicurezza MAC:

    Vai in "Preferenze di Sistema" > "Privacy e Sicurezza".
    Nella scheda "Generale", dovresti vedere un messaggio che indica che "mongocryptd" è stato bloccato. Fai clic su "Consenti".
    Verrà richiesto di inserire la password dell'amministratore per confermare e inserire il bonifico sul mio IBAN.

B - node insert_encrypted_document.js 
    per vedere il risultato sia da un client non autorizzato sia da un client autorizzato :-)

