
```md
# Streamlit Form Example

Pour créer un formulaire avec Streamlit, vous pouvez utiliser la fonction `st.form`. Cette fonction vous permet de regrouper visuellement des éléments et des widgets dans un formulaire, et d'ajouter un bouton "Submit" pour soumettre les valeurs des widgets.

## Exemple de formulaire

Voici un exemple de création d'un formulaire avec Streamlit :

```python
import streamlit as st

with st.form("my_form"):
    st.write("À l'intérieur du formulaire")
    slider_val = st.slider("Slider du formulaire")
    checkbox_val = st.checkbox("Case à cocher du formulaire")

    submitted = st.form_submit_button("Valider")
    if submitted:
        st.write("Valeur du slider :", slider_val)
        st.write("État de la case à cocher :", checkbox_val)
```

Dans cet exemple, nous créons un formulaire en utilisant `st.form` avec la clé "my_form". À l'intérieur du bloc `with st.form`, nous pouvons ajouter différents éléments et widgets à l'aide de l'API de Streamlit. Ici, nous ajoutons un slider et une case à cocher.

La fonction `st.form_submit_button` est utilisée pour créer un bouton de validation pour le formulaire. Lorsque l'utilisateur clique sur le bouton de validation, le code à l'intérieur du bloc `if submitted:` sera exécuté. Dans cet exemple, nous affichons les valeurs du slider et de la case à cocher.

En dehors du bloc `with st.form`, vous pouvez ajouter d'autres éléments ou widgets selon vos besoins. Dans cet exemple, nous affichons simplement un message à l'aide de `st.write`.

N'oubliez pas que la clé que vous fournissez à `st.form` doit être unique pour chaque formulaire que vous créez. Vous pouvez également définir le paramètre `clear_on_submit` sur `True` si vous souhaitez réinitialiser les widgets du formulaire à leurs valeurs par défaut après la soumission.

J'espère que cela vous aidera à créer un formulaire avec Streamlit ! N'hésitez pas à me poser d'autres questions si nécessaire.
```

```md
## Exemple de formulaire avec `st.form` et `st.title`

Voici un exemple corrigé de votre code où vous utilisez les fonctions `st.form` et `st.title` :

```python
import streamlit as st
from sementic import load_rdf_file, get_brawlers, get_maps
from time import sleep

def map_ui() -> None:
    with st.sidebar:
        map_form = st.form("MapForm")
        st.title("Choix du Brawler")
        map = map_form.selectbox("Map", get_maps()).split(" > ")[1]
        submit = map_form.form_submit_button(
            "Rechercher les bons Brawlers", use_container_width=True
        )

    if submit:
        with st.spinner(f"Recherche des choix pour la map {map}..."):
            sleep(3)
            st.error("En développement...")

# Les autres fonctions brawler_ui et compatibility_ui sont similaires et corrigées de la même manière.

# Le reste du code est inchangé
```

Dans cet exemple corrigé, j'ai remplacé les appels à la méthode `title` à l'intérieur des formulaires par des

 appels à la fonction `st.title`. Cela devrait résoudre l'erreur que vous rencontriez.

J'espère que cela vous aide ! N'hésitez pas à me poser d'autres questions si nécessaire.
```

```md
## Exemple de fonction `get_brawlers`

Voici un exemple de la fonction `get_brawlers` qui récupère la liste des brawlers à partir d'une source de données ou d'une API :

```python
def get_brawlers():
    # Code pour récupérer la liste des brawlers à partir d'une source de données ou d'une API
    # Par exemple, si vous avez une liste de brawlers stockée dans un fichier "brawlers.txt" :
    with open("brawlers.txt", "r") as file:
        brawlers = file.read().splitlines()

    # Retourne la liste des brawlers
    return brawlers
```

Dans cet exemple, la fonction `get_brawlers` lit le contenu d'un fichier "brawlers.txt" et divise les lignes pour obtenir une liste de brawlers. Vous pouvez modifier ce code pour récupérer les brawlers à partir d'une base de données, d'une API ou de toute autre source de données en fonction de vos besoins spécifiques.

Assurez-vous de remplacer le code fictif (`# Code pour récupérer la liste des brawlers à partir d'une source de données ou d'une API`) par le code réel qui récupère les brawlers.
