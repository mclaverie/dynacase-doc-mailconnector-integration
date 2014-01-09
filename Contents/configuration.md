# Configuration

Le module `dynacase-mailconnector` livre 3 nouvelles familles :

* `MAILBOX` : Boîte aux lettres,
* `SUBMAILBOX` : Dossier de message,
* `EMESSAGE` : Message reçu.

## Famille *Boîte aux lettres*

Cette famille permet de déclarer les informations de récupération de messages
IMAP.

Cette famille est livrée **sans profil**. L'administrateur doit configurer le
profil de la famille afin d'indiquer qui a le droit de créer des boites aux
lettres ainsi que le profil des boites créées.

## Famille *Dossier de message*

Cette famille est livrée avec un profil qui interdit la création **directe**
mais autorise la création par programme à tous les utilisateurs.

Cette famille ne nécessite pas de droit de création directe car les dossiers
sont créés uniquement lors de la récupération de message depuis le serveur IMAP.

Un dossier de message est créé par sous-dossier de l'arborescence IMAP qui doit
être transféré.

## Famille *Message reçu*

Cette famille est livrée **sans profil**. 

L'administrateur doit configurer le profil de la famille afin d'indiquer qui a
le droit de créer des messages.

Généralement, seul le droit "create" (et no "icreate") est à indiquer car les
messages reçus ne sont créés que lors de la récupération de message depuis le
serveur IMAP.

Un document "Message reçu" est créé par message transféré.
