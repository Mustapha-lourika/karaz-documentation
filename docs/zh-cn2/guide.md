 <div id='définition-dun-schéma-xsd-sous-karaz'> 
 
## Définition d’un schéma XSD sous KARAZ
 


Il s’agit du fichier central de tout modèle métier Karaz. Le .xsd décrit les données métier propres au modèle et qui seront:
<ul>
<li>
Exploitées par les processus appliqués au modèle

</li>
<br>
<li>
Affichées par les vues associées au modèle


</li>
</ul>
<img src="images\imag42.png" style="padding:3px;width:550px;height:350px">
 </div>
 <div id='éléments-dun-schéma-xsd'>

## Eléments d’un schéma XSD

Un schéma XSD sous Karaz peut contenir 3 catégories d’éléments :
<table>
<tr>
<th>
Eléments simples
</th>
<th>
Eléments Complexes
</th>
<th>
Eléments multiples

</th>
</tr>
<tr>
<td>
<ul>
<li>
Int
</li>
<li>
long
</li>
<li>
string
</li>
<li>
double
</li>
<li>

Date
</li>
<li>
dateTime
</li>
</ul>
</td>
<td>
<ul>
<li>
Elément de référence

</li>
<li>
Elément d’attachement


</li>
<li>
  Eléments importés

</li>
<li>
Eléments de facette

</li>
</ul>

</td>
<td>
<ul>
<li>

Liste
</li>
<li>
Tableau
</li>
</ul>

</td>
</tr>

</table>
</div>

### Eléments simples

> Les éléments de type <b>  int/long </b> permettent de stoker les données métier de type entier ou entier long.
 Ces éléments sont servis aux utilisateurs à travers des vues formulaire
 Le widget utilisé pour servir un entier est : integer 
 
 > Les éléments de type double permet de stoker les information métier de type  décimal avec virgule.
Ces éléments sont servis dans les vues formulaire à travers le widget : double

> Les éléments de type Date et DateTime permettent de stoker les informations métier de type  date 
Ces éléments sont servis dans les vues formulaire à travers les widgets date ,date time.

> Les éléments de type string  sont parmi les plus utilisés. Il permettent de stoker les données métier de type  chaine de caractère .
Ces éléments sont servis dans les vues formulaire à travers les widgets : text/textArea/select/boolean/stringToggler/htmlEditor

### Eléments Complexes

#### Elément de référence

<img src="images\imag43.png" style="padding:3px">




<ul>

<li>
Les éléments de type référence permettent de faire une jointure xml entre plusieurs modèles.
</li>
<li>

Ils permettent ainsi de relier les modèles entre eux</li>
<li>
Ces éléments sont servis dans les vues formulaire à travers les widgets : reference
</li>
</ul>

<table>
<tr>
<th>
Attribut
</th>
<th>
Type
</th>
<th>
Description
</th>
<th>
Utilisation
</th>
</tr>
<tr>
<th>
dataObjectId
</th>
<td>
long
</td>
<td>
ID karaz de l’objet référencé
</td>

<td>
Utilisé pour accéder à l’objet
</td>
</tr>
<tr>
<th>
description
</th>
<td>
String
</td>
<td>
Sequence de l’objet référencé (IndexString1)
</td>
<td>
Utilisé pour afficher l’intitulé de l’objet
</td>
</tr>
<tr>
<th>
modelQN
</th>
<td>
String 
</td>
<td>
Identifier le nom de l’objet  référencé 
</td>
<td>
Utilisé pour visualiser l’objet
</td>
</tr>
</table>

#### Elément attachement 

Les attachements Karaz sont les documents attachés aux objets métiers. Un document peut être attaché soit manuellement par un utilisateur soit automatiquement par le système :
<ul>
<li>
<b> Attachement Manuelle : </b>
se fait directement par l’utilisateur via le formulaire d’une activité manuelle. Il charge alors un document à partir de sa machine en utilisant le service UploadFile pour le chargement du fichier et le service KarazRepository pour le stockage dans la GED interne de Karaz.

</li>
<li>
<b> Attachement automatique : </b> Attachement automatique : se fait par le système à travers l’une des 3 actions :
<ol>
<li>
Directement à travers une activité automatique
</li>
<li>
indirectement dans une activité manuelle à travers une action distante (Remote action). Exemple (i.e bouton Imprimer) 

</li>
<li>
Via un menu Rapport dans les vues de consultation 
</li>
</ol>
</li>
<li>
Dans le cas de l’attachement automatique, seul le service KarazRepository est utilisé pour le stockage des fichiers générés dans la GED interne de Karaz.

</li>

</ul>

Karaz Modeler propose un type préconstruit  «kfx:attachment» qui permet de gérer l’attachement.

<img src="images\imag44.png" style="padding:3px">

<table>

  <tr>
    <th>
      Attribut
    </th>
    <th>
 Type
    </th>
    <th>
      Description
    </th>
    <th>
      Utilisation
    </th>
  </tr>
  <tr>
    <td>
      fileId
    </td>
    <td>
      long
    </td>
    <td>
      Sequence au niveau GED Karaz
    </td>
    <td>
      Récupéré par le service KarazRepository sous forme de séquence numérique continue
    </td>
  </tr>
  <tr>
    <td>
gedId
    </td>
    <td>
String
    </td>
    <td>
      Identifiant complexe au niveau GED Karaz
    </td>
    <td>
      Récupéré par le service KarazRepository sous forme d’une longue chaine alphanumérique
    </td>
  </tr>
  <tr>
    <td>
fileName
    </td>
    <td>
String
    </td>
    <td>
Nom du fichier
    </td>
    <td>
Affiché en FileCombo
    </td>
  </tr>
  <tr>
    <td>
      fileSize
    </td>
    <td>
      long
   </td>
    <td>
Taille de fichier on Octet
    </td>
    <td>
      Affichage spéciale
   </td>
  </tr>
  <tr>
    <td>
      fileSignature
 </td>
<td>
String
    </td>
    <td>
MD5 du contenu de fichier
    </td>
    <td>
      Affichage spéciale pour vérification du transfert
   </td>
  </tr>
  <tr>
    <td>
fileTime
    </td>
    <td>
      Time
    </td>
    <td>
Date/heure de chargement
    </td>
    <td>
Afficage spéciale
    </td>
  </tr>
  <tr>
    <td>
      maxSize
      </td>
    <td>
long
    </td>
    <td>
Taille maxiamele de chargement
    </td>
    <td>
      Spécifié avant le chargement. Utilisé pour une validation côté client avant de démarrer le chargement.
    </td>
  </tr>
  <tr>
    <td>
      mime
    </td>
    <td>
String
    </td>
    <td>
      Type de mimes acceptés, i.e: « application/pdf » ou « image/* ». C’est un élément multiple.
    </td>
    <td>
      Spécifié avant le chargement. Utilisé pour une validation côté client avant de démarrer le chargement.
</td>
  </tr>
  <tr>
    <td>
      version
   </td>
    <td>
int
    </td>
 <td>
numéro de version GED
    </td>
<td>
    </td>
</tr>

  <tr>
    <td>
      attachmentName
   </td>
    <td>
      String
   </td>
<td>
      Catégorie de l'attachement
</td>

<td>
      Utilisé par KarazRepository pour une validation côté serveur de l’extension et de la taille. Utilisé aussi pour le classement GED des documents par catégorie.

   </td>


  </tr>
  </table>
 
  Les attachements sont servis dans les vues formulaire à travers les widgets :
  <ul>
  <li>
<b> FileCombo :</b> qui permet de télécharger le fichier attache.
</li>
<li>
<b> FileDownload :</b> qui permet de télécharger le fichier.</li>
<li>
<b> Html Iframe : </b> qui permet de visualiser directement le contenu du fichier
</li>
</ul>

####  Elément importé

<ul>
<li>
Il est possible sous KARAZ d'importer  dan un modèle,  un schéma ou une partie d'un  schéma d'un autre modèle.
</li>
<li>
Les éléments importés  sont identifiables au niveau du schéma  XSD à travers la valeur  de  l’attribut  « Prefix »
</li>
</ul>
<table>
<tr>
<td>
<img src="images\imag45.png" style="padding:3px">
</td>
<td>
<img src="images\imag46.png" style="padding:3px">
</td>
</tr>
</table>

#### Elément facette

Les éléments de type facette permettent d’importer un schéma XSD on se basant sur un projet existant.


<img src="images/imag47.png" style="padding:3px;width:200px;height:500">

pour ajouter des facettes au schéma xsd il faut les configurer dans kconfig.xml

###   Eléments multiples d’un schéma XSD.

<ul>
<li>
Un élément multiple  permet de définir une collection d’éléments (listes ou tables). 

</li>
<br>
<li>
Ces éléments peuvent être consultées par les utilisateurs directement dans la vue formulaire. Les widgets utilise pour servir un élément multiple sont  : Table/For/Foreach 

</li>
</ul>

## explications des éléments d’un schéma XSD

Le schéma xsd porte toujours  le nom de  modèle 

<img src="images\imag48.png" style="padding:3px;width:600px;height:400px">


Si on a des blocs  répétitifs (dans cet exemple validation1 et validation2),on utilise un élément abstrait pour factoriser ces éléments:
<table>
<tr>
<td>

<img src="images\imag50.png" style="padding:3px">
</td>

<td>
<img src="images\imag51.png" style="padding:3px;width:300;height:300px">
</td>
</tr>
</table>
dans ce cas on peut ajouter des élément de type 'tns:validation1': <br>
<img src="images\imag52.png" style="padding:3px;width:500px">

### les propriétés des éléments de shéma xsd

<img src="images\imag49.png" style="padding:3px;width:500px">
<ul>
<li>
<b> Name:</b> c'est le nom de l'élément de shéma xsd.le nom ne doit ni commencer  ni terminer par une espace. 
</li>
<li>
<b>Optionnal: </b> Si pour un élément   On coche Optional ,cet élément  ne va pas apparaitre dans le fichier d'initialisation de processus (..-ini.xml)
</li>
<li>
<b> Nillable : </b>Elle est appliquée pour les dates Si on coche 'Nillable'  Ça signifie que  la date peut  être nulle 
</li>
<li>
<b> Indexed :</b> Si on coche 'indexed' pour un élément, ce dernier  sera généré dans le fichier '..-indexation.xml'.
</l>
</ul>


































