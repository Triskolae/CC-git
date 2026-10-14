| Étape/version testée | Action | Résultat attendu | Résultat constaté |
| --------- | --------- | --------- | --------- |
| 1. Ouverture ou actualisation  | lancement page sur index.html ou F5 | compteur à zéro, confirmation masquée | compteur à zéro, confirmation masquée |
| 2. Première réservation  | Clic sur bouton "réserver une place" | Compteur à 1, Affichage du message "Réservation confirmée. Places réservées : 1" | Compteur à 1, Affichage du message "Réservation confirmée. Places réservées : 1" |
| 3. Trois réservations au total | Clic sur bouton "réserver une place" * 3 | compteur et confirmation indiquent trois places. | compteur et confirmation indiquent trois places. |
| 4. Recommencer  | Clic sur bouton recommencer | Compteur de réservations revient à 0, message de confirmation masqué | Compteur de réservations revient à 0, message de confirmation masqué |
| 5. Nouvelle réservation après remise à zéro | Clic sur bouton recommencer puis clic sur bouton "réserver une place" | Compteur de réservations à 1 et message de confirmation visible | Compteur de réservations à 1 et message de confirmation visible |
| 6. Affichage à 390 px   | rétrécissement de la fenêtre du navigateur à 390px de large | Text et boutons tous lisibles, pas de scroll horizontal | Text et boutons tous lisibles, pas de scroll horizontal |

- Hotfix message de confirmation: avant hotfix: texte invisible car de même couleur que le background, après hotfix texte affiché en blanc (commit be6b85dc132f31765059b3766fcf66e9f6e92fac)

Questions:
- base et branches: A et B partent du commit (67aeb4f9f79876bb333c5589458647676896aea7)
`$ git log --oneline --graph`
*   fbd8c9b Merge branch 'feature/B-confirmation-reservation'
|\  
| * edb67b6 (feature/B-confirmation-reservation) feature(confirmation-reservation): message de confirmation au clic sur le bouton
* | dafe827 (feature/A-presentation-nocturne) feature(presentation-nocturne): change couleur background et texte
|/
* 67aeb4f (tag: depart-cc) Fournir le site fonctionnel des ateliers

- Fusion et fonctionnement: une fusion réussie vérifie que les développements intégrés n'entrent pas en conflit au niveau de l'historique git. Ceux-ci peuvent toutefois comporter des bugs qui seront présent sur la version fusionnée.
ex: merge de la couleur du background et du message de confirmation de même couleur que ce background, ces deux développement étaient fonctionnels indépendemment.

- Commit et publication: après un commit local, il faut pousser la branche committée sur git, et avoir un repository défini en remote.
Commit sur branche main: 638b45561baab4ae5a0f2c6ef46aad3edc000177