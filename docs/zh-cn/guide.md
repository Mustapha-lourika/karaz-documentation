
 
##  Pourquoi le BPMN dans Karaz? <button>Modifier </button>
Le concept [BPM](https://bpm.com/what-is-bpm)  représente l’un des fondamentaux de la plateforme Karaz. Le choix d’adoption du concept BPM par Ribatis a été motivé par 3 besoins essentiels :
  <ol>
 <li>
Garantir la répartition fine et la traçabilité complète des actions effectuées par les partie-prenantes au processus.

</li>
<br>

<li>
Piloter et optimiser les processus métier en mesurant les performances de chaque acteur et chaque activité et identifier de façon objective et quantitative les pistes de simplification.

</li>
<br>
<li>
Assurer l’évolutivité et la flexibilité des procédures automatisées en permettant la modification à chaud de leur comportement en fonction des évolutions organisationnelles et réglementaires.

</li>
</ol>

## Comment le BPMN est implémenté sous Karaz ? 

La dimension [BPMN](https://www.lucidchart.com/pages/fr/quest-ce-que-le-BPMN) (Business Process Management System) est assurée par la plateforme Karaz à travers les fonctionnalités suivantes :
<ul>
<li>
Un outil de modélisation qui sert à formaliser l’activité de l’organisation en processus. Il permet de définir également les données échangées et les interfaces avec les autres modules;
</li>
<br>

<li>
Des outils de développement pour formaliser la logique qui régit les processus de l’organisation ; 

</li>
<br>

<li>
Un moteur d'exécution qui supervise le déroulement des processus ainsi que les échanges de paramètres ;

</li>
<br>
<li>
Un moteur de règles qui évalue l'état de tous les objets impliqués dans le déroulement des processus et déterminera si les conditions sont remplies pour en lancer, poursuivre ou arrêter l'exécution.
</li>
<br>
<li>
Un référentiel qui mémorise tous les objets manipulés, en particulier les définitions des processus, les règles qui doivent déclencher leur exécution, les contraintes d'intégrité, de sécurité ainsi que les mesures de référence relatives au métier de l’organisation ;

</li>
<br>
<li>
Des outils d'administration qui permettent de régler les paramètres de l'ensemble du système et d'obtenir des indicateurs de performance et des statistiques à partir des données collectées lors de l'exécution des processus ;

</li>
<br>
<li>
En adoptant le concept BPM, Ribatis a implémenté l’ensemble des « Capabilities » exigées par le deux standards BPMN 2.0 et BPEL.
</li>
</ul>

## Eléments de modélisation des processus

La norme BPMN prévoit quatre catégories d’éléments de logigrammes représentant les processus métier. Ces 4 catégories sont toutes implémentées par Karaz :




<table >
  <tr>
   <th>
   Éléments de workflow

   
   </th>
    <th>
    Éléments d'organisation

   </th>
    <th>
    Éléments de lisibilité

   </th>
    <th>
    Comportements spécifiques

   </th>
  </tr>
  <tr>
      <td>
      <ul>
<li> Activities </li>
<li> Events </li>
<li> Gateways </li>
<li> Sequence flow </li> 
</ul>
   </td>
    <td>
     <ul>
<li>Pools </li>
<li> Lanes </li>
</ul>
   </td>
    <td>
    <ul>
    <li>Annotation </li>
<li> Links </li>
<li> Groups </li>
    </ul>
   </td>
    <td>
    <li>Messages </li>
<li> Signals </li>
<li> Timers </li>
<li> Errors </li>
   </td>
  </tr>
</table>

### Les  éléments de workflow

 ####  Les activités

<ul>
<li>
Il s'agit d'une activité ou d'une tâche particulière effectuée par une personne ou un système. Il peut s'agir d’une tâche, sous-process, call activity ;
</li>
<br>

<li>
Karaz utilise plusieurs types d’activités (tâches) et d’autres composantes BPM pour décrire les processus métiers. Ces types sont définis par la notation MBPN 2.0. Chacun de ces types détient sa propre chaine d’actions (workflow interne) que Karaz active à des moments précis de l’exécution du processus ;

</li>
<br>
<li>
6types d’activités ou tâches peuvent être définies au niveau de la plateforme Karaz :
</li>
</ul>

##### Tâche utilisateur

<img src="images\imag6.png" style="float:left;padding:3px"> Une « Tâche Utilisateur » est une tâche associée à une personne physique (ou à un pool de personnes). Karaz assistera cette personne dans la réalisation de la tâche via des formulaires web spécifiés par le designer, et des chaines d’actions pré et post réalisation.<br> <br>

##### Tâche automatique
<br>

<img src="images\imag7.png" style="float:left;padding:3px">
L’activité automatique correspond à une tâche exécutée par le moteur de processus Karaz (Karaz Process Engine). Quand l’activité est prête à démarrer, le moteur va exécuter la chaine des actions associées.<br> <br> <br> 


##### Tâche Manuelle

<img src="images\imag8.png" style="float:left;padding:3px">
Une tâche manuelle est une tâche qui n'est pas gérée par un moteur de processus Karaz. Le moteur de processus ne suit pas le début et la fin d'une telle tâche. Un exemple de ceci pourrait être l’envoi par poste d’une lettre recommandée à un partenaire.<br> <br> <br> 


##### Sous-processus


<img src="images\imag9.png" style="float:left;padding:3px">
Il s’agit d’une activité dont les détails internes ont été modélisés à l'aide d'activités, de passerelles, d'événements et de flux de séquences. Karaz lancera d’autres instances de processus métier et ne clôturera l’activité parente que lorsque tous les sous-processus lancés seront terminés; <br> <br> <br>


#####  Sous-processus Ad’Hoc


<img src="images\imag10.png" style="float:left;padding:3px">
Regroupe des activités qui ne sont pas obligatoirement liées par des relations de séquence.<br> <br> <br> <br> <br> <br>
 
#####  Activités d’appel (Call Activity)

<img src="images\imag11.png" style="float:left;padding:3px">
Une activité d'appel identifie un point dans le processus où un processus global ou une tâche globale est utilisée.<br> <br> <br> <br>

#### Les événements 


#####  Star Event

<img src="images\imag12.png" style="float:left;padding:3px;width:70px;height:70px">

Cette activité marque le début du processus. C’est aussi une activité automatique.
Chaque processus doit avoir une et une seule activité START

<br> <br>

#####  End Event

<img src="images\imag13.png" style="float:left;padding:3px;width:70px;height:70px">

Cette activité marque la fin du processus. C’est aussi une activité automatique.
Chaque processus doit avoir au moins une activité END <br> <br>

##### Intermediate Event

<img src="images\imag14.png" style="float:left;padding:3px;width:70px;height:70px">

Ils sont représentés à l'aide de cercles contenant d'autres symboles qui changent en fonction du type d'événement. On les classe en deux catégories, receveur (Catcher) ou lanceur (thrower) selon leur fonction 

#### Les passerelles 

<ul>
<li>
Il s’agit d’une activité automatique vide (sans aucune chaine d’action). Elle est utilisée pour définir des jointures de transitions (sortantes/entrantes) ou pour marquer un évènement.
</li>
<br>
<li>
Une passerelle constitue dans ce sens un point de décision qui peut ajuster le chemin en fonction des conditions ou des événements. Les entrées sont représentées par des losanges. Elles peuvent être exclusives ou inclusives, parallèles, complexes ou basées sur des données ou événements.
</li>
<br>
<li>
La passerelle exclusive et le type de passerelles le plus utilisé

</li>

</ul>

##### Passerelle exclusive

<img src="images\imag15.png" style="float:left;padding:3px;width:70px;height:70px">

Elle évalue l'état du processus métier et, en fonction de la condition, elle divise le flux en l'un des deux ou plusieurs chemins s'excluant mutuellement.<br> <br>

##### Passerelle inclusive

<img src="images\imag16.png" style="float:left;padding:3px;width:70px;height:70px">

 On peut l’utiliser pour créer des chemins alternatifs mais également parallèles dans un flux de processus. Contrairement à la passerelle exclusive, toutes les expressions de condition sont évaluées. La vraie évaluation d'une condition Expression n'exclut pas l'évaluation d'autres expressions de conditions.<br> <br>
##### Passerelle parallèle

<img src="images\imag17.png" style="float:left;padding:3px;width:70px;height:70px">

Une passerelle parallèle est utilisée pour synchroniser (combiner) des flux parallèles et pour créer des flux parallèles. Une passerelle parallèle crée des chemins parallèles sans vérifier les conditions ; chaque flux séquentiel sortant est passé à l'exécution de cette passerelle. Pour les flux entrants, la passerelle parallèle attendra tous les flux entrants avant de déclencher le flux à travers ses flux de séquence sortants.
.<br> <br>

##### Passerelle  basée sur un évènement
<img src="images\imag18.png" style="float:left;padding:3px;width:70px;height:70px">
Elle représente un point de branchement dans le processus où les chemins alternatifs qui suivent la passerelle sont basés sur les événements qui se produisent plutôt que sur l'évaluation des expressions utilisant des données de processus (comme avec une passerelle exclusive ou inclusive).

### Flux de séquence

Indique l'ordre des activités à effectuer. Il est représenté par une ligne droite fléchée. Il peut s'agir d'un flux conditionnel ou d'un flux par défaut
<img src="images\imag19.png" style="float:left;padding:3px">






### Eléments d’organisation

Il s’agit de conteneurs visuels permettant d’organiser les éléments BPMN 2.0 selon une logique d’acteur, d’organisation, de fonction,…

#### Piste (Pool) 

 Une piste représente les principaux participants d'un processus. Une piste différente peut faire référence à une autre organisation ou à un autre service qui participe à un même processus.

#### Couloir (Lane)

 Les couloirs au sein d'une piste montrent les activités et les flux d'un rôle ou d'un participant, et définissent qui est responsable de quelle partie du processus.<br> <br>
<img src="images\imag20.png" style="float:left;padding:3px;align:center"> <br> <br> <br> <br> <br> <br>

### Eléments de lisibilité

Il s'agit d'une information supplémentaire utilisée par le Business Analyst ou Designer Karaz pour ajouter un niveau de détail nécessaire au logigramme.

##### Groupe
<img src="images\imag21.png" style="float:left;padding:3px;width:70px;height:70px">
Elle représente un point de branchement dans le processus où les chemins alternatifs qui suivent la passerelle sont basés sur les événements qui se produisent plutôt que sur l'évaluation des expressions utilisant des données de processus (comme avec une passerelle exclusive ou inclusive).

##### Annotation
<img src="images\imag22.png" style="float:left;padding:3px;width:70px;height:70px">
Apporte des explications complémentaires sur une partie du diagramme.<br> <br> 

### Comportements spécifiques

Ci-après une liste des éléments personnalisés KARAZ

<img src="images\imag24.png" style="float:right;padding:5px;width:400px;height:270px">
<ul style='padding-top:20px'>
<li>
<b> 'Signal Event' et 'Message Event' </b> :se sont des événements des échange des messages entre les processus
</li>
<li>
<b> 'Send Email', 'Launch Process' et 'Web service Invoker':</b>
 se sont des services task ajoutés par karaz.
karaz builder peut interpréter ces éléments pour faciliter le développement des régles de gestion
</li>
<li>
<b> 'boundary Event'</b>:est un événement lié à une activité
</li>
</ul>

## Workflows internes des activités

<ul>
<li>
L’exécution d’une activité par le moteur Karaz se fait en suivant un workflow interne spécifique. Ce workflow interne à l’activité varie selon le type d’activité et il se déclenche à partir d’un ensemble de ports d’entrées. <br> 
Le choix du port d’entrée dépend de l’état de l’activité et son exécution interne et jalonnée par des « Moments » précis.
Dans la pratique, les deux types d’activités les plus utilisés dans la modélisation des processus métier sous Karaz sont : L’activité automatique et l’activité manuelle. 

</li>
<br>
<li>
Chaque type d’activité dispose de ses propres ports et ses propres moments
Le designer Karaz peut associer des règles de gestion à chacun de ces moments. Il convient de bien comprendre le rôle et l’impact de chacun de ces moments sur l’exécution de l’activité.
</li>
<br> 
<li>
Dans la pratique, les deux types d’activités les plus utilisés dans la modélisation des processus métier sous Karaz sont : L’activité automatique et l’activité manuelle. 
</li>

</ul>

### Héritage des activités

Les activités dans Karaz correspondent à des classes java. Elles héritent toutes de la classe « Activity » 
<img src="images\imag25.png" style="padding:5px;width:400px;height:270px">

### Activités automatiques

Ce workflow interne est valable aussi pour les activités « Start », « End » et « Sub Process » qui sont également des sous type d’activité automatique.

<img src="images\imag26.png" style="padding:5px;width:600px;height:270px">

#### Liste des ports
<table>
<tr>
<th>
Port

</th>
<th>
Type

</th>
<th>
Activation
</th>
</tr>
<tr>
<td>
in

</td>
<td>
Entrée

</td>
<td>
Activé suite à une transition entrante du processus

</td>
</tr>
<tr>
<td>
Error

</td>
<td>
Entrée

</td>
<td>
Activé suite à une réexécution ou une reprise d’un statut « ERROR »

</td>
</tr>
<tr>
<td>
out

</td>
<td>
Sortie

</td>
<td>
Active la suite du processus.

</td>
</tr>
</table>

#### Liste des moments 
<table>
<tr>
<th>
Moment

</th>
<th>
Explication 

</th>
<th>
Méthode JAVA
</th>
</tr>
<tr>
<td>
Create

</td>
<td>
Exécuté, uniquement la première fois que l’activité est activée. On y associé des règles de gestion qui ne doivent s’appliquer que lors de la création de l’activité (notification externe, création de ressources persisté).  Si le moteur Karaz est amené à réactiver l’instance d’activité (suite à une erreur ou à une action effectuée à travers la console ‘Karaz BAM’), ce moment ne sera plus exécuté.

</td>
<td>
create() ;
Toute exception ou erreur sera ignorée (catchée)

</td>
</tr>
<tr>
<td>
Execute

</td>
<td>
C’est le moment principal. Il est exécuté à chaque fois que l’instance d’activité est activée, sauf lors de la Clôture de l’activité par un administrateur à travers la console ‘Karaz BAM’. 


</td>
<td>
execute() ;
Toute exception arrêtera le processus et mettra le statut de l’instance en « ERROR »

</td>
</tr>
<tr>
<td>
Close

</td>
<td>
C’est un moment qui est toujours exécuté, même lors de clôture suite à une action sur ‘Karaz BAM’.  

</td>
<td>
close() ;
Toute exception sera ignorée.

</td>
</tr>
<tr>
<td>
Initialize

</td>
<td>
Exécuté uniquement lors de la réactivation de l’instance suite à une demande ‘Karaz BAM’ ou à une reprise après une erreur. 

</td>

<td>
initialize() ;
Toute exception ou erreur sera ignorée   

</td>
</tr>
<tr>
<td>
Propagation

</td>
<td>
Exécuté pour sélectionner la prochaine transition. Soit pour élire une seule transition (de sortie) parmi plusieurs possibilités, soit pour temporiser la propagation (en attendant un évènement externe).


</td>

<td>
checkTransitionToXXX() ;
Toute exception ou erreur sera ignorée  

</td>
</tr>
</table>

### Activités utilisateur 

 <ul>
<li>
L’activité de type utilisateur est plus complexe que le type automatique ;
</li>
<li>
Cette activité gère les interactions avec l’utilisateur en prenant en compte les différents contextes d’exécution des actions ;
</li>
<li>
Les actions sont exécutées tout en garantissant l’intégrité globale du processus ainsi que celle des objets métier sur lesquels il agit.
</li>
</ul> <br> <br>
<img src="images\imag27.png" style="padding:3px;width:670px;height:370px">

#### Liste des ports

<table>
<tr>
<th>
Port

</th>
<th>
Type

</th>
<th>
Activation
</th>
</tr>
<tr>
<td>
in

</td>
<td>
Entrée

</td>
<td>
Activé suite à une transition entrante de processus.

</td>
</tr>
<tr>
<td>
Error

</td>
<td>
Entrée

</td>
<td>
Activé suite à une réexécution ou une reprise d’un statut « ERROR »

</td>
</tr>
<tr>
<td>
out

</td>
<td>
Sortie

</td>
<td>
Active la suite du processus.

</td>
</tr>
<tr>
<td>
taskOut

</td>
<td>
Sortie

</td>
<td>
Ajoute l’instance dans la corbeille des tâches.

</td>
</tr>

<tr>
<td>
taskIn
</td>
<td>
Entrée
</td>
<td>
Activé quand un utilisateur charge l’instance à partir de la corbeille des tâches.

</td>
</tr>

<tr>
<td>
loaded
</td>
<td>
Sortie
</td>
<td>
Retourne le formulaire de collaboration à l’utilisateur et lui associe un lock sur la tâche. L’instance processus est alors réservée pour l’utilisateur


</td>
</tr>

<tr>
<td>
cancel
</td>
<td>
Entrée
</td>
<td>
Activé quand l’utilisateur annule ou abandonne son lock sur la tâche à effectuer.
 l’utilisateur
</td>
</tr>

<tr>
<td>
submit
</td>
<td>
Entrée
</td>
<td>
Activé lorsque l’utilisateur soumet le formulaire pour validation.

</td>
</tr>

</table>

#### Liste des moments 

<table>
<tr>
<th>
Moment

</th>
<th>
Explication 

</th>
<th>
Méthode JAVA
</th>
</tr>
<tr>
<td>
Create

</td>
<td>
Exécuté, uniquement la première fois que l’activité est activée.

</td>
<td>
create() ;
exception ignorée.

</td>
</tr>
<tr>
<td>
Allocate

</td>
<td>
Calcule les ressources (profiles/utilisateurs) associés à l’instance. 


</td>
<td>
 resource() ;
Toute exception arrêtera le processus et mettra le statut de l’instance en « ERROR »


</td>
</tr>
<tr>
<td>
Close

</td>
<td>
C’est un moment qui est toujours exécuté, même lors de clôture suite à une action sur ‘Karaz BAM’.  

</td>
<td>
close() ;
Toute exception sera ignorée.

</td>
</tr>
<tr>
<td>
Initialize

</td>
<td>
Exécuté uniquement lors de la réactivation de l’instance suite à une demande ‘Karaz BAM’(RESTART) ou à une reprise après une erreur. 

</td>

<td>
initialize() ;
Toute exception causera un statut "ERROR"   

</td>
</tr>
<tr>
<td>
START
</td>
<td>
Exécuté uniquement lorsque l’utilisateur charge un formulaire pour la première fois.
</td>

<td>
start() ; 
exception ignorée   

</td>
</tr>

<tr>
<td>
Load
</td>
<td>
Exécuté, chaque fois que le formulaire est chargé par l’utilisateur.

</td>

<td>
load() ; 
Toute exception causera un statut  « ERROR »


</td>
</tr>


<tr>
<td>
Release

</td>
<td>
Exécuté quand l’utilisateur abandonne la tâche et la remet dans le pool.

</td>

<td>
start() ; 

exception ignorée   


</td>
</tr>


<tr>
<td>
Validate
</td>
<td>
Exécuté lors de la soumission du formulaire pour valider le formulaire. Si aucune erreur n’est déclarée, on passe au moment Close. Sinon, on remet le formulaire à l’utilisateur pour correction. 


</td>

<td>
start() ; 
exceptions considérés comme erreur de validation

</td>
</tr>



<tr>
<td>
Propagation
</td>
<td>
Exécuté pour sélectionner la prochaine transition. Soit pour élire une seule transition (de sortie) parmi plusieurs possibilités, soit pour temporiser la propagation (en attendant un évènement externe)



</td>

<td>
checkTransitionToXXX() ;
Toute exception/erreur sera ignorée  

</td>
</tr>


</table>

#### Status des activités Karaz
<table>
<tr>
<td>
Moment
</td>
<td>
Type activité
</td>
<td>
Méthode Java
</td>
</tr>
<tr>
<td>
Running
</td>
<td>
Automatique

</td>
<td>
L’activité est en cours d’exécution (moment Execute).

</td>
</tr>


<tr>
<td>
Executed 
</td>
<td>
Automatique
</td>
<td>
L’activité vient de terminer son exécution (moment Execute). Il s’agit d’un état instable du processus et non accessible à partir de la console BAM.

</td>

</tr>


<tr>
<td>
Closed

</td>
<td>
Toute Activité

</td>
<td>
L’activité est terminée.

</td>
</tr>


<tr>
<td>
Error

</td>
<td>
Toute Activité

</td>
<td>
L’activité est arrêtée suite à une erreur.

</td>
</tr>




<tr>
<td>
Aborted
</td>
<td>
Toute Activité

</td>
<td>
L’activité est arrêtée par le Moteur Karaz suite à une action préméditée et prévue (Exemple : suppression de l’objet métier).


</td>
</tr>

<td>
Initiated 

</td>
<td>
Toute Activité

</td>
<td>
L’instance d’activité vient d’être réinitialisée (Suite à une erreur ou perte de connexion par exemple). Il s’agit d’un état instable du processus mais reste accessible à partir de la console BAM.

</td>
</tr>
<tr>
<td>
Allocated
</td>
<td>
Tâche Utilisateur

</td>
<td>
La tâche est allouée à tout le pool. Elle n’est encore assignée à aucun utilisateur.


</td>
</tr>
<tr>
<td>
Loaded
</td>
<td>
Tâche Utilisateur

</td>
<td>
La tâche est affectée à une personne (qui vient d’ouvrir le formulaire). Les autres membres du pool, ne peuvent plus y accédée. Sauf si la tâche est libérée à nouveau.

</td>

</tr>

<td>
Started
</td>
<td>
Tâche Utilisateur

</td>
<td>
Indique que l’activité est au moment Start. 
Ce n’est pas un état stable.

</td>

</tr>
<tr>
<td>
TimeOut

</td>
<td>
Toute Activité

</td>
<td>
Le moteur Karaz a fermé l’instance d’activité suite au dépassement de la durée allouée à sa réalisation. Ce statut n’est pas accessible à partir du BAM puisque Karaz passe automatiquement au statut Closed une activité passée par la moment Timeout.

</td>

</tr>


<tr>

<td>
Saving
</td>
<td>
Tâche Utilisateur

</td>
<td>
La tâche est en cours validation. L’activité prend ce statut lorsqu’un problème est survenu au moment de l’enregistrement d’un travail effectué sur une tâche.


</td>


</tr>

<tr>

<td>
Paused
</td>
<td>
Tâche Utilisateur

</td>
<td>
L’utilisateur vient d’enregistrer son formulaire sans valider l’étape. Les données traitées sans enregistrées sur une copie provisoire (XML CC).



</td>


</tr>

<tr>

<td>
Saved
</td>
<td>
Tâche Utilisateur

</td>
<td>
La tâche est validée et les données sont sauvegardées (Xml CC vidé). Il s’agit d’un état provisoire et instable. Il est automatiquement écrasé par le statut « Closed » sauf en cas d’erreur lors de la validation de l’activité.





</td>




</tr>
<tr>

<td>
Propaging
</td>
<td>
Toute Activité

</td>
<td>
L’étape est terminée. Mais le moteur n’a pas encore déterminé la prochaine activité (attente d’autres événements)

</td>




</tr>

<tr>

<td>
Skipped
</td>

<td>
Toute Activité

</td>
<td>
Le moteur Karaz a sauté (court-circuité) cette activité (suite à un paramétrage sur la console d’administration Karaz) 




</td>




</tr>





</table>

###  Karaz Managed Activities and Actions (KMAA)

Ce schéma présente une comparaison entre BPMN 2.0 et les éléments personnalisés par KARAZ

<img src="images\imag28.png" style="padding:3px">

<ul>
<li>
<b> Documentation </b>: cet artefact est utilisé à des fins de documentation.il peut être associé à une activité particulière, sinon il concernera le processus global
</li>
<li>
<b>Validation Task :</b> Une tâche de validation est une tâche de workflow typique dans laquelle un interprète humain  valide les données créées par d'autres collaborateurs.
KMAA prend en charge la persistance et la journalisation des données de validation telles que la connexion du validateur, le temps d'opération et la décision que l'entreprise actuelle doit contenir une occurrence de la facette générique «Support de validation»
</li>
</ul>

## Création de processus

chaque projet  contient ou ou  plusieurs modèles.
dans cette exemple on a deux modèles "Article" et "Collaborateur"
<img src="images\imag30.png" style="padding:3px;width:200px;height:200px"> <br>

  <br>
  
chaque modèle  contient ou ou plusieurs processus .On peut aussi ajouter des autres processus

<img src="images\imag31.png" style="padding:3px;width:300px;height:300px"> <br> <br>


On clique sur 'Open Resource File' pour visualiser le processus : <br>

<img src="images\imag32.png" style="padding:3px;width:200px;height:200px"> <br>

> karaz studio offre une palette qui contient tous les éléments de processus

<img src="images\imag33.png" style="padding:3px;width:250px;height:400px"> <br>

> Un exemple de processus

<img src="images\imag34.png" style="padding:3px;width:350px;height:350px"> <br>

> les propriétés d'une activité utilisateur 

<img src="images\imag35.png" style="padding:3px;width:300px;height:300px"> <br>
<ul>
<li>
<b> time to complete </b> :le délai d'une activité 
</li>

<li>
<b> View Name </b> : l'activité sera charger la vue nommée par ce nom.
</li>

<li>

[Task List](htttps://www.google.com)

</li>

</ul>

> Les propriétés de l'activité 'Send Email'

<table>
<tr>
<td>
<img src="images\imag36.png" style="float:right;padding:3px;width:300px;height:300px"> 
</td>
<td>
<img src="images\imag37.png" style="float:left;padding:3px;width:300px;height:300px"> 
</td>
</tr>

<table>
  <br>
<ul>
<li>
<b> Name:</b> le nom de l'activité 
</li>
<li>
<b>is Deffered:</b>  Si on coche 'is Deffered' le lancement de l'activité sera répétée 'Retry Nbr' fois   chaque 'Retry Delay Sec' secondes 

</li>
<li>
<b>Email templateQN:</b> c'est le lien de Template pour l'email défini dans 'reporting'

</li>

<li>
<b>Email Container Xpath:</b> la facette d'envoi d'email 
</li>


</ul>


> Les propriétés de l'activité 'Launch Process'

<table>
<tr>
<td>
<img src="images\imag38.png" style="float:right;padding:3px;width:300px;height:300px"> 
</td>
<td>
<img src="images\imag39.png" style="float:left;padding:3px;width:300px;height:300px"> 
</td>
</tr>

</table>
  <br>
<ul>
<li>
<b> Name:</b> le nom de l'activité 'Launch Process'
</li>

<li>
<b>Target ProcessQN</b>  le chemin de processus qu'on va lancer.
</li>
<li>
<b>Email templateQN:</b> c'est le lien de Template pour l'email défini dans 'reporting'

</li>

<li>
<b> Container Xpath:</b> c'est la facette  utilisé dans shéma XSD de type 'Launch Process'
</li>
<li>
<b> Is Deffered :</b>Si On coche 'Is Deffered' le système va essayer de lancer le processus chaque 10 secondes jusqu'a la réusssite de lancement. 
</li>


</ul>

###  la génération des EJBs des activiés de processus

pour générer les EJBs de chaque activité on utilise 'Build Stub'.

On trouve les classes générées dans le dossier 'java'


<table>
<tr>
<td>
<img src="images\imag40.png" style="float:right;padding:6px;width:300px;height:300px"> 
</td>
<td>
<img src="images\imag41.png" style="float:left;padding:6px;width:300px;height:300px"> 
</td>
</tr>

</table>























 


































 


