# Orto

Un assistant d'orthographe discret pour macOS. Il vit dans la barre de menus et n'apparaît que lorsque tu sélectionnes du texte : la faute est surlignée en jaune, la correction écrite en rouge, et un clic t'explique la règle.

Pensé pour les personnes dysorthographiques : on voit la faute, on voit la correction, on retient l'astuce.

**[Télécharger la dernière version](../../releases/latest)**

![La pastille Orto sous un message en cours d'écriture](docs/orto-pastille.jpg)

## Ce que fait Orto

- **Tu sélectionnes, Orto relit.** Un mot, une phrase ou un texte entier, dans n'importe quelle app. Une pastille en verre apparaît en bas de l'écran avec ta phrase recopiée, la faute au surligneur et la correction en rouge.
- **Un doute sur un seul mot ?** Double-clique dessus : Orto lit la phrase autour pour savoir s'il faut « terminé » ou « terminer ».
- **Un clic pour comprendre.** La pastille s'ouvre sur la règle, une astuce pour s'en souvenir et des exemples. 78 règles de français sont embarquées (homophones, accords, conjugaison, orthographe d'usage).
- **Corriger en un geste.** « Remplacer » met la version corrigée à la place de ta sélection, « Copier » la met dans le presse-papiers.
- **Reformuler.** Plus clair, plus pro ou plus court.
- **Privé par défaut.** La correction se fait sur ton Mac avec le modèle d'Apple Intelligence. Rien n'est envoyé sur Internet tant que tu ne choisis pas une IA en ligne.

![La vue détaillée : version corrigée, règle, astuce et exemples](docs/orto-detail.jpg)

## Installation

Il faut un Mac Apple Silicon sous **macOS 26 ou plus récent**.

1. Télécharge `Orto-x.y.z.dmg` depuis la page [Releases](../../releases/latest).
2. Ouvre-le et glisse **Orto** dans **Applications**.
3. Lance Orto. Au premier lancement, macOS le bloque parce que l'app n'est pas signée par un compte développeur Apple : ouvre **Réglages Système › Confidentialité et sécurité**, descends jusqu'à « Orto a été bloqué » et clique sur **Ouvrir quand même**.
   Autre possibilité, dans le Terminal : `xattr -dr com.apple.quarantine /Applications/Orto.app`
4. Dans la fenêtre de bienvenue, clique sur **Ouvrir les Réglages** et active **Orto** dans la liste Accessibilité. Orto en a besoin pour lire le texte que tu sélectionnes.

L'icône d'Orto (un « o » souligné) apparaît en haut à droite, dans la barre de menus.

> Après une mise à jour, macOS peut redemander l'autorisation Accessibilité. Si Orto est déjà coché mais ne réagit plus, utilise « Réinitialiser l'autorisation » dans la fenêtre de bienvenue.

## Utilisation

| Geste | Résultat |
| --- | --- |
| Sélectionner du texte (glisser, double-clic, ⇧ + flèches) | La pastille apparaît avec les corrections |
| Cliquer sur la pastille | La règle, l'astuce, la version corrigée |
| `⌃⌥O` | Analyse la sélection à la demande, dans toutes les apps |
| `Échap` | Ferme le panneau |
| Menu Orto › Orto actif | Met Orto en pause |

Quand tout est juste, une petite coche verte passe une seconde et disparaît.

Dans les réglages, tu peux choisir de ne déclencher Orto qu'avec le raccourci, changer le raccourci, placer le panneau en haut de l'écran et lancer Orto au démarrage du Mac.

## Moteurs de correction

| Moteur | Ce qu'il faut | À savoir |
| --- | --- | --- |
| **Sur l'appareil** (par défaut) | Apple Intelligence activé | Gratuit et privé, répond en moins d'une seconde. Peut laisser passer une faute dans les phrases compliquées. |
| **IA en ligne** | Une clé API | Plus fiable et donne une explication propre à ta phrase. Le texte sélectionné est envoyé au fournisseur choisi. |
| Dictionnaire macOS | Rien | Secours automatique si aucun modèle n'est disponible : orthographe des mots seulement. |

Fournisseurs en ligne proposés : OpenAI, Anthropic, Mistral et tout serveur compatible OpenAI, par exemple Ollama en local. La clé est rangée dans le trousseau de macOS.

## Compatibilité

- **Champs de texte natifs et pages web WebKit** (le moteur de Safari) : sélection lue directement, avec la phrase autour.
- **Navigateurs Chromium et apps de messagerie** (Arc, Chrome, Discord, Slack…) : Orto leur demande d'exposer leur texte, comme le ferait un lecteur d'écran. Si la pastille n'apparaît pas dans l'une d'elles, le raccourci prend le relais.
- **Partout ailleurs** : le raccourci `⌃⌥O` fonctionne toujours. En dernier recours, il copie la sélection puis remet ton presse-papiers dans son état d'origine.

Orto ne se déclenche jamais tout seul dans les terminaux et les gestionnaires de mots de passe.
