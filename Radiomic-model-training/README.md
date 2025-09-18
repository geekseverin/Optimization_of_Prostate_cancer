# Stage-M2-CIC-Radiomic
Dépots de l'ensemble des traveaux de recherche de Master

Ce dépot correspond à l'ensemble des étapes de la radiomic. Nous auront

+ En premier point nous auront l'agorithme d'extraction des caractéristique radiomic qui est dans le notebook ADC_T2_Features_Extractions.ipynb

+ En deuxième lieu nous entrainons nos modèles de classification sur les données extrait à partir du notebook T2_ProstateX_Model_Training.ipynb et 
+ le ADC_ProstateX_Model_Training

+ En troisième lieu nous procédont graphes statistique dans le notebook statistic analysis.ipynb

1 - Extraction des features Radiomic
Notre Datase lesion contient les images IRM de proste de pondération de diffusion ADC et les séquences de pondération T2 , chacun avec son masque 
permettant de segmenter uniquement la partie tumorale.

# Prérequis
* Créer un environnement virtuel
* Avoir un notebook jupyter déjà installer
* Télécharger les données à partir du lien drive associé à se dépôt (lien drive pour les données de IRM de la prostate.dotx)
* Mettre le dataset dans télécharger dans le dossier cloner
* Déziper le le dataset lesion.zip
* Installer les bibliothèque du fichier requierment.txt (Ce fichier ne précise pas de version car seul les versions recentes seront pris n charge)

Voivi l'arborescence des dossier pour la sauvegarde:

                                !--T2
            !------------Image--!  # Comporte les images IRM de la prostate                
            !                   !--ADC
            !------------Patient_ID   # Dans ce dossier nous alons récupérer les indexes les patients en 
            !                           fonction du Grade de Gleason.
            !                                   !--------GG1
            !                                   !--------GG2   ( Dans le dossier Img_msk_resambled nous normalisons les image
    lesions !-------------Img_msk_resambled-----!--------GG3     en fontion de leurs masques en fonction de leurs grade de Gleason 
            !                                   !--------GG4     avant de procéder à l'extraction ) 
            !                                   !--------GG5
            !
            !-----------ADC_T2_Images_Analyses # Nous récuperons dans ce dossier les feautures radiomic en fonction du grade de Gleason
            !
            !             !--T2
            !-------------Masks   #Comporte les Masks de chaque image
                          !--ADC
                          
            
NB: Tous ses dossiers son déjà créer et existent déjà dans le zip du dossier lesions. Mettre le fichier notebook         
    ADC_T2_Features_Extractions.ipynb dans le même repertoire que le dossier lesion après le dézipage. 
    Vous n'aurez qu'à cloner le projet , activer votre environnement virtuel puis installer les librairies du fichier requierement.txt
