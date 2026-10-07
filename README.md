# Segmentation d'images avec U-Net

Ce depot rassemble les notebooks du projet V2 de segmentation semantique d'images avec le dataset Cityscapes.

## Contenu

- `dataset_visualisation.ipynb` : exploration et visualisation des images et des annotations Cityscapes.
- `model_unet_baseline.ipynb` : preparation des masques et experimentation avec un modele U-Net de reference.
- `unet_selfdistill.ipynb` : exploration et evaluation d'un modele U-Net avec self-distillation.
- `requirements.txt` : instantane des dependances Python de l'environnement d'origine.

## Donnees

Les notebooks de visualisation et de baseline attendent le dataset Cityscapes extrait a cet emplacement, a la racine du projet :

```text
data/
└── cityscapes/
    ├── leftImg8bit/
    │   ├── train/
    │   ├── val/
    │   └── test/
    └── gtFine/
        ├── train/
        ├── val/
        └── test/
```

Les images doivent conserver le nommage Cityscapes, par exemple `*_leftImg8bit.png`, et les annotations fines `*_gtFine_labelIds.png`. Le dataset n'est pas inclus dans ce depot; il doit etre obtenu aupres de Cityscapes selon ses conditions d'acces.

## Utilisation

1. Clonez le depot et placez-vous dans son dossier.
2. Creez un environnement Python adapte a votre systeme.
3. Installez les dependances necessaires a votre environnement. `requirements.txt` est un instantane de l'environnement d'origine et peut contenir des versions specifiques a une plateforme; adaptez-le si besoin.
4. Lancez Jupyter et ouvrez le notebook voulu :

```bash
python -m pip install jupyter
python -m notebook
```

Executez les cellules depuis la racine du depot afin que les chemins relatifs, notamment `data/cityscapes`, soient resolus correctement. Un GPU est recommande pour l'entrainement.

## Ressources complementaires

Le notebook `unet_selfdistill.ipynb` fait reference a des modules sous `src/` et a des checkpoints sous `checkpoints/`. Ces ressources ne font pas partie des fichiers publies ici; les cellules qui en dependent necessitent de les fournir separement.
