@startuml

actor Client
participant "Site e-commerce" as Site

Client -> Site: Consulter le catalogue
Site --> Client: Affiche le catalogue

Client -> Site: Ajouter un produit au panier
Site --> Client: Panier mis à jour

Client -> Site: Se connecter
Site --> Client: Accès accordé

Client -> Site: Saisir les adresses
Site --> Client: Adresses validées

Client -> Site: Choisir mode de paiement
Site --> Client: Paiement validé

Client -> Site: Valider la commande
Site --> Client: Commande confirmée
Site -> Client: Envoi confirmation par email

@enduml

