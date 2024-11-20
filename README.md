# -Analyse-morphologique-Langue-Arabe-
 Analyse morphologique(Langue Arabe)
# Analyse Morphologique de la Langue Arabe

Ce projet propose une analyse morphologique de la langue arabe. Il permet d'identifier et d'analyser les différentes unités de la langue (mots, racines, affixes) en utilisant des outils de traitement du langage naturel (NLP). L'objectif est de faciliter les recherches linguistiques, les applications de traduction automatique et la création de modèles d'apprentissage automatique pour la langue arabe.

## Table des matières

- [Description](#description)
- [Fonctionnalités](#fonctionnalités)


## Description

Ce projet se concentre sur l'analyse morphologique de la langue arabe, en particulier l'identification des racines et des affixes. L'analyse est basée sur des règles morphologiques de l'arabe classique et moderne et peut être utilisée pour :

- Identifier les racines des mots arabes.
- Découper les mots en morphèmes (préfixes, racines, suffixes).
- Effectuer une lemmatisation des mots arabes.
- Aider au développement de systèmes de traduction automatique.

## Fonctionnalités

- Extraction des racines à partir des mots arabes.
- Identification des affixes (prefixes, suffixes).
- Traitement des variations grammaticales de la langue arabe.
- Outils d'analyse linguistique basés sur des règles.


1. charger_liste_depuis_fichier(nom_fichier)

    But : Cette fonction permet de charger une liste à partir d'un fichier CSV.
    Entrée : Un chemin de fichier en tant qu'argument (par exemple, "liste_proclitiques.csv").
    Sortie : Retourne une liste contenant toutes les lignes du fichier, après avoir enlevé les espaces inutiles (strip()).
    Logique :
        Si le fichier spécifié n'existe pas, un message d'erreur est affiché.
        Si le fichier existe, chaque ligne est lue et ajoutée à la liste.
 2. Chargement des fichiers des listes

    Ces lignes chargent les fichiers contenant des données spécifiques : proclitiques, enclitiques, schèmes, et racines.
    Entrée : Les chemins des fichiers CSV.
    Sortie : Les listes correspondantes sont remplies avec les valeurs des fichiers respectifs.
 3. Vérification des fichiers chargés

    But : Vérifier si les fichiers ont été correctement chargés.
    Logique :
        Si une liste est vide, cela signifie que le fichier correspondant n'a pas été chargé correctement. Un message d'erreur est affiché pour indiquer le problème.
 4. segmenter_mot(mot)

    But : Identifier les segmentations possibles d'un mot en termes de proclitique, stem (radical), et enclitique.
    Entrée : Un mot sous forme de chaîne de caractères.
    Sortie : Une liste de tuples où chaque tuple contient un proclitique, un stem et un enclitique.
    Logique :
        Parcourt tous les proclitiques pour vérifier si le mot commence par l'un d'eux.
        Ensuite, pour chaque proclitique, il vérifie si le mot se termine par un enclitique.
        Si ces deux conditions sont remplies, le reste du mot est considéré comme un stem (partie centrale du mot).
5. associer_schemes(stem)

    But : Associer les schèmes possibles à un stem donné.
    Entrée : Un stem (partie centrale du mot).
    Sortie : Une liste de schèmes dont la longueur correspond à celle du stem.
    Logique :
        Parcourt tous les schèmes dans la liste liste_schemes et sélectionne ceux qui ont la même longueur que le stem.

6. extraire_racine_generale(stem, scheme)

    But : Extraire la racine d'un mot en utilisant le stem et un schème, en comparant la racine générée à la liste des racines valides.
    Entrée : Le stem (radical du mot) et le schème qui décrit la structure.
    Sortie : La racine déduite, si elle est valide, sinon un message "Racine non trouvée".
    Logique :
        Parcourt le stem et le schème simultanément.
        Conserve les lettres du stem qui ne correspondent pas à des lettres de structure (les lettres de structure comme "أ", "ت", etc., sont ignorées).
        Une fois la racine générée, elle est comparée à la liste des racines valides. Si la racine figure dans cette liste, elle est retournée, sinon "Racine non trouvée" est renvoyé.
7. afficher_resultats(mot)

    But : Afficher les résultats de l'analyse pour un mot donné de manière bien formatée.
    Entrée : Un mot à analyser.
    Sortie : Affichage des segmentations possibles (proclitique, stem, enclitique), des schèmes associés et des racines extraites.
    Logique :
        Appelle la fonction segmenter_mot pour obtenir les segmentations possibles du mot.
        Pour chaque segmentation, affiche le proclitique, le stem, et l'enclitique.
        Pour chaque stem, associe les schèmes possibles à l'aide de associer_schemes et extrait la racine correspondante à l'aide de extraire_racine_generale.
 Conclusion

Chaque fonction a un rôle spécifique dans l'analyse morphologique du mot arabe, allant du chargement des fichiers à l'extraction des racines en fonction des schèmes. Le code analyse la structure du mot en trois parties (proclitique, stem, enclitique), puis utilise ces éléments pour identifier les schèmes associés et en déduire les racines possibles.               
   
