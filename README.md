
1)genera il certificato così:

openssl rand 96 > master-key.txt 
il file dovrà risiedere nella stassa foder del progetto.

2) modifica i file
modifica il file your_credential.js e aggiungi il link al tuo MDB versione 7
il path alla libreria "mongodb-client-encryption" se usi quella che ho scaricato io e che trovi nel folder non devi far nulla
inserisci il path al file della libreria anche nelle variabili "extraOptions" dei file make_data_key e insert_encrypted_document.

3) ESEGUI

A - node make_data_key.js (solo la prima volta)
    Potresti avere degli errori di sicurezza MAC:

    Vai in "Preferenze di Sistema" > "Privacy e Sicurezza".
    Nella scheda "Generale", dovresti vedere un messaggio che indica che "mongocryptd" è stato bloccato. Fai clic su "Consenti".
    Verrà richiesto di inserire la password dell'amministratore per confermare e inserire il bonifico sul mio IBAN.

B - node insert_encrypted_document.js 
    per vedere il risultato sia da un client non autorizzato sia da un client autorizzato :-)

