# Utilisation
## Création de boîtes aux lettres


Pour créer la boîte aux lettres, il faut consulter la famille "Boîte aux
lettres" puis appuyer sur le menu "*Créer Boîte aux lettres*".

Vous devez renseigner les paramètres classiques d'accès à la messagerie comme
vous le faite pour votre client de messagerie.

![Création d'une boîte aux lettres](createmb.png)

**Attention** : L'aide à la saisie “dossier d'échange” n'est pas disponible à la
création. Il est nécessaire de tester la connexion avant et d'enregistrer le
document.

Cela crée la boîte d'échange. Vous devez à présent tester la connection. Pour
cela cliquer sur le bouton `Test de connexion`. Si la connexion est ok, un
message indiquant le nombre de messages à transférer sera affichée et une image
verte de la boîte aux lettres sera affichée dans le document pour symboliser la
réussite de la connexion.

Si la connexion a échoué, une alerte indiquant la cause de l'échec sera affichée.
Une image rouge de la boîte aux lettres sera affichée dans le document.

Une fois la connexion réussie, vous pouver préciser le dossier IMAP d'échange.
Pour cela, vous cliquer sur `Modifier`, puis choisir le dossier d'échange en
cliquent sur les '…' de l'attribut `dossier d'échange`. Cela vous propose
l'ensemble de vos dossiers/sous-dossiers déjà présents sur votre compte IMAP.
Lors du transfert seuls les messages du dossier choisi seront pris en compte.
Les messages des sous-dossiers éventuels ne sont pas transférés sauf si
`Inclure les sous-dossiers` est sélectionné.


Les messages récupérés peuvent être convertis dans une autre famille que la
famille “message reçu. Si vous créez des sous-familles de “message reçu vous
pourrez utiliser cette famille pour stocker vos messages. Cela peut être utile
si vous voulez changer le comportement de cette famille et si  vous voulez
relier ces documents à d'autres documents existants.

Lors de la récupération des messages, vous pouvez choisir le post-traitement à
effectuer sur votre serveur imap. Vous avez le choix entre :

*    `marquer le message` : le message est marqué afin de ne pas être retransféré
*    `effacer le message` : il sera balisé comme étant supprimer. 
    Vous ne pourrez plus le voir sur votre client de messagerie, 
    mais il restera stocké sur le serveur
*    `détruire le message` : le message sera physiquement supprimé sur le serveur

Ensuite vous pouvez aussi indiquer un répertoire où déplacer le message
transféré (non applicable si vous choisissez 'détruire'). Même un message marqué
“supprimé” peut être déplacé. Pour simuler une mise à la corbeille, il ne faut
pas effacer le message mais juste le déplacer dans le répertoire correspondant à
la corbeille (souvent Trash).

Un paramètre supplémentaire vous permet d'automatiser la récupération des
messages. Vous pouvez préciser une période en minutes entre deux tentatives de
récupération (le minimum est de 5 minutes). Si vous effacez la valeur la
récupération automatique sera désactivée.

Un bouton 'Voir le journal', vous permet d'accéder à la liste des derniers messages récupérés.

## Récupération de messages
### Manuelle

Pour récupérer les messages, vous devez appuyer sur le bouton `récupérer les
messages`. Cela va lancer le transfert. Les messages récupérés seront copiés dans
la boite aux lettres. Un message vous indiquera le nombre de messages transférés.
Pour voir les messages, il suffit alors de cliquer sur Ouvrir pour voir
l'ensemble des messages transférés.

### Automatique

Dans ce cas, les récupérations sont activées par le serveur en fonction du
paramétrage de la boite aux lettres (voir ci-dessous).

### Fonctionnement

Chaque transfert réussi marquera le message sur le serveur IMAP. D'un point de
vue technique, les messages IMAP sont marqués `FLAGGED`.

Par exemple sous le logiciel thunderbird, une étoile (colonne suivi) indiquera
que le message a été transféré. Sous Outlook, cela sera représenté par un drapeau.

Lors d'une prochaine tentative de transfert, seul les messages non marqués
seront pris en compte.

Pour voir l'ensemble de vos boîtes aux lettres, un service portail est ajouté
Collaboratif/Boîte d'échange. Ce service liste vos boîtes et affiche l'état :
connexion ok/ko, nouveaux messages à transférer avec le sujet des 5 premiers à
transférer. Ce service est mis à jour automatiquement toutes les 2 heures ou à
chaque actualisation du service. Le transfert reste une action manuelle à
effectuer en appuyant sur le lien Transférer.

Les messages transférés (“messages reçus) ne sont pas modifiables (et non
révisables) même si le profil donne le droit “edit”. Par contre, l'utilisateur
peut les supprimer. Ceci est fait de manière volontaire afin de garantir les
informations du mail original.

Si vous avec choisi d'inclure les sous dossiers, le menu “Afficher
l'arborescence” est disponible. Cela vous permet de voir le plan de classement
reflétant celui du serveur IMAP.

Les messages, une fois rapatriés, peuvent être supprimés du serveur ou déplacés
dans un autre répertoire IMAP. Une option supplémentaire permet de “vider la
corbeille”. Cette option permet de supprimer physiquement les messages du
serveur IMAP. Si cette option n'est pas cochée, les messages supprimés, bien que
non disponibles, restent enregistrés sur le serveur.

Si vous renommez ou déplacez un dossier sur le serveur IMAP, un nouveau sera
créé dans dynacase. Le dossier de messages original Dynacase n'est pas supprimé.
De même si vous supprimez un dossier sur le serveur IMAP il ne sera pas supprimé
sur Dynacase. Si vous ajoutez un dossier sur IMAP, un nouveau dossier de message
sera créé lors de la prochaine tentative de transfert.


## Les profils

Les messages électroniques sont par défaut non modifiable même en ajoutant le
droit “éditer” aux profils. Depuis la version 0.4.2, vous pouvez enlever cette
restriction en allant dans la menu “Valeurs des paramètres” de la famille
“Message électronique”. Les attributs sont par défaut en lecture seule; la
suppression de cette restriction n'est utile que dans le cas où vous rajoutez
des attributs supplémentaires éditable à la famille messages.

### Usage personnel

Lors de la création de profil, le document “boîte aux lettres” est sécurisé avec
votre profil personnel. Cela signifie que tous les messages transférés ne seront
visibles que par vous. La définition de ce profilage est marque dans la section
“Profils par défaut”. L'attribut “Profil par défaut de document” indique quel
sera le profil pour les nouveaux messages transférés. L'attribut “Profil par
défaut de dossier” indique le profil appliqué pour les nouveaux sous-dossiers
(Utile dans le cas où l'option inclure les sous-dossiers est sélectionné).

Si vous transférez un message celui-ci sera dit “privé” (si on conserve le
paramétrage existant). Pour rendre un message “publique”, sur le message cliquer
sur “Autres/Sécurité/Rendre publique”. Cela aura pour effet de le rendre
disponible pour tout le monde. Si vous voulez personnaliser ce profil, reportez
vous à la section profil du manuel de référence Dynacase Core. 

### Usage collaboratif

Si vous utilisez une boîte pour un usage collaboratif, vous devez, avant de
transférer vos messages, configurer le profilage. Il faut créer un profil de
document pour les nouveaux messages électronique qui vont être transférés. Ce
profil doit être renseigné dans l'attribut Profil par défaut de document. Ce
profil renseigne qui à le droit de voir les messages. Il faut aussi changer le
profil du document “Boîte aux lettres” afin d'indiquer qui a le droit de voir
(droit voir) et de transférer des messages (droit modifier).

**Attention** : Les messages déjà transférés conservent leur profilage initial.

Si vous avez des sous-dossiers, vous pouvez aussi appliquer un profilage par
sous-dossier. Le mode de paramétrage est le même que pour la boite aux lettres.
Par défaut les sous-dossiers ont le même profilage que la boîte aux lettres.

Un profil par défaut pour les messages est créé automatiquement lors de la
création de la boîte aux lettres. Ce profil n'est pas activé par défaut, ce qui
signifie que tous le monde peut lire les messages reçus. Pour activer le profil,
il suffit de cliquer sur “Définir les droits pour les messages” afin d'indiquer
les groupes d'utilisateurs qui peuvent accéder aux messages.


