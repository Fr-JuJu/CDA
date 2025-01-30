Cas d'utilisation : Création d'une commande :
---------------------------------------------

Acteur principal
    Client > Le client a un compte utilisateur valide (sauf s’il crée un compte avant de commander).
             Le catalogue des produits est disponible et mis à jour.
----------------------------------------------------------------------------------------------------------

----------------------------------------------------------------------------------------------------------

Flux nominal : Happy day
------------------------

    Consultation du catalogue > Le client parcourt les rubriques et sélectionne les produits souhaités.

    Ajout des produits au panier > Le client sélectionne un produit et saisit la quantité souhaitée.
                                   Il répète l’opération pour chaque produit désiré.
                                   Il peut visualiser le contenu du panier et modifier les quantités.

    Connexion du client > S’il n’est pas encore connecté, le client saisit son identifiant et son mot de passe.
                          Si c’est un nouveau client particulier, il doit créer un compte avant de poursuivre.

    Validation des adresses > Le client sélectionne ou saisit une adresse de livraison.
                              Il sélectionne ou valide l’adresse de facturation.

    Sélection du mode de paiement > Client particulier : paiement immédiat (CB, PayPal, etc.).
                                    Client professionnel : choix entre paiement différé (virement ou chèque).

    Validation finale de la commande > Un récapitulatif de la commande est affiché.
                                       Le client confirme la commande.
                                       Une confirmation est envoyée par email
------------------------------------------------------------------------------------------------------------             

Sénario Alternatif :
--------------------
Produit en rupture de stock -->Lors de l'ajout d’un produit au panier, le système détecte qu’il n’y a plus de stock disponible.
                               Le client est informé et peut choisir un autre produit ou réduire la quantité.

Connexion échouée --> Si l’identifiant ou le mot de passe est incorrect, un message d’erreur est affiché.
                      Après trois tentatives infructueuses, le compte est temporairement bloqué.

Adresse invalide --> Si l’adresse saisie est incorrecte (format ou champ vide), un message d’erreur est affiché.
                     Le client doit corriger l’erreur avant de poursuivre.

Préconditions

Paiement refusé --> Si le paiement en ligne échoue, le client est invité à essayer une autre méthode.
                    Après trois tentatives, la commande est annulée.

Commande incomplète --> Si le client ne finalise pas la commande après un certain délai, son panier est enregistré mais la commande n'est pas validée.
                        Il peut la retrouver et la valider plus tard.

-------------------------------------------------------------------------------------------------------------------
Postconditions --> La commande est enregistrée et visible dans l’historique du client. 
                   Un bon de livraison et une facture sont générés.
                   Si un paiement a été effectué, la transaction est enregistrée.
-------------------------------------------------------------------------------------------------------------------