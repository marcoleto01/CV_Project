# CV_Project

Autori: Marco Leto (247453),  Francesca Daniele (247108)


## Descrizione del Progetto
Il progetto ha come obiettivo la creazione di un modello di Instance Segmentation basato su Mask R-CNN, specializzato nel riconoscimento e nella segmentazione di cavi e tralicci nelle immagini. L'implementazione è stata sviluppata in PyTorch, utilizzando una variante avanzata del modello Mask_resnet50_fpn_v2 che include miglioramenti a vari moduli architetturali.

## Analisi Dataset

![Dataset Analysis](https://github.com/user-attachments/assets/279eea8b-40a9-4f5d-bdf5-bc14f5340da7)


## Aumento del Dataset 
![Data Augmentation](https://github.com/user-attachments/assets/3eabfbd4-f568-4fda-915e-0401d79721ca)


## Parametri di Addestramento

- **Learning Rate**: scelto tramite ricerca a griglia tra valori diversi, con il migliore risultato ottenuto a **5e-4**.
- **Numero di Epoch**: 100.
- **Ottimizzatore**: `Adam`, per l'aggiornamento dei pesi.
- **Scheduler**: `OneCycleLR`, per regolare dinamicamente il learning rate.
- **Batch Size**: testato con valori di 8 e 16.
- **Pesi della Backbone**: inizializzati a `DEFAULT`, pre-addestrati sul dataset COCO-val2017.

## Risultati del Modello

Le prestazioni del modello sono state misurate utilizzando il Mean Average Precision (mAP) per bounding box (bbox) e segmentazione (segm):
- **Batch Size 16**:
  - `mAP@50` bbox: **65,4%**
  - `mAP@50` segm: **47,5%**
- **Batch Size 8**:
  - `mAP@50` bbox: **62,5%**
  - `mAP@50` segm: **44,8%**
