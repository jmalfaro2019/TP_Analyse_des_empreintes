# TP Analyse des empreintes

TP d'IA & santé sur le jeu de données **HUMAPS-4D** : segmentation des actions à partir
de l'empreinte plantaire (pression) et apprentissage d'un classifieur (PyTorch).

Notebook : [`tp1.ipynb`](tp1.ipynb)

## Prérequis

- **Python 3.14**
- Les données `HUMAPS_donnees/` (non versionnées, voir `.gitignore`) :
  voir `HUMAPS_donnees/README.md` et <https://humaps4d.wp.imt.fr/>

Le notebook lit `HUMAPS_donnees/Events` et `HUMAPS_donnees/Pressure` relativement au
dossier courant : **il doit être lancé depuis la racine du dépôt.**

## Installation

```powershell
python -m venv .venv
.venv\Scripts\python -m pip install --upgrade pip
.venv\Scripts\python -m pip install -r requirements.txt
.venv\Scripts\python -m ipykernel install --user --name tp-empreintes --display-name "Python (tp-empreintes)"
```

Sous Linux / macOS, remplacer `.venv\Scripts\python` par `.venv/bin/python`.

## Exécution

Ouvrir `tp1.ipynb` dans Jupyter (Lab ou Notebook) et sélectionner le kernel
**Python (tp-empreintes)**.

En ligne de commande :

```powershell
.venv\Scripts\python -m jupyter lab
```

## Dépendances

`requirements.txt` est généré avec `pip freeze` : toutes les versions sont épinglées,
ce qui garantit un environnement reproductible d'une machine à l'autre.

```powershell
.venv\Scripts\python -m pip freeze > requirements.txt
```

PyTorch est installé en version **CPU** depuis l'index officiel
(`--extra-index-url https://download.pytorch.org/whl/cpu`), ce qui évite de télécharger
les CUDA (~2 Go) pour un TP CPU. Pour une version GPU, remplacer la ligne `torch` par
l'index correspondant (`https://download.pytorch.org/whl/cu124`, etc.).

## Notes

- `.venv/` est ignoré par git : chaque poste crée son propre environnement à partir de
  `requirements.txt`.
- Le kernel `tp-empreintes` est enregistré au niveau utilisateur (`--user`) et apparaît
  dans la liste des kernels de Jupyter.
