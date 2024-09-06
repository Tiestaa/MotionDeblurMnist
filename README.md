## Descrizione progetto
Come dataset di partenza é stato utilizzato MNIST.
Per generare il dataset da utilizzare, sono state create delle coppie formate da immagine con blur - immagine originale, dove l'immagine originale rappresenta la ground truth, da utilizzare durante la fase di training per il calcolo dell'errore.
L'obiettivo é la realizzazione di una Rete Neurale che faccia deblur delle immagini: a partire dall'immagine blurrata, si cerca di ottenere l'immagine originale, quella di partenza.

## Architettura rete
La rete costruita si basa sulla UNet.
In particolare é una Unet con tre blocchi di discesa/salita.
Tuttavia, le immagini di partenza sono 28x28. Quindi senza alcun preprocessing non si potrebbe usare una rete a tre livelli di discesa, in quanto 28 > 14 > 7 > 3 > 6 > 12 > 24 (dimensione partenza-arrivo diversa, quindi impossibilitá di fare skip connections).
Per risolvere questo problema é bastato raddoppiare la dimensione dell'input cercando di mantenere i rapporti tra i 28x28 pixel. Le immagini cosí generate sono 56x56.

## Training
Si sono utilizzate 50 epoche con adattamento del learning rate e early stopping, per prevenire l'overfitting.
___

Per maggiori informazioni sulla rete consultare il notebook python presente.
