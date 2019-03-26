# workshop-storming-mapping-theater
Description of our workshop where we mix Event Storming and Example mapping


## 1. Introduction (10’)
  « on ne réexplique pas le BDD ;-) on dit juste qu’on veut leur montrer comment articuler 2 techniques très utiles : l’ES et l’EM
  
 - Disclaimer : on ne va pas détailler chaque technique. Juste en faire le minimum pour que vous puissiez voir comment les 2 peuvent s’articuler entre-elles
 - Rappel : l’association est une idée de Bruno à la base, qui a été beaucoup reprise par Kenny avec qui on va faire un atelier à DDD EU

## 2.Event Storming round 1 (20’)
On est deux experts du domaine et on veut vous faire travailler sur un système de reservation de place de théatre. Pensez « events » (postit oranges) et divergez un maximum pour couvrir la big picture. 
 - Début : le client connait la pièce et la séance où il veut aller
 - Fin : le client récupère un ticket lui confirmant la transaction
 - On rappelle rapidos les règles 

## 3. Event Storming round 2 (10’)
Convergez au besoin, réordonnez vos post-it sur la time-line, et commencez à raisonner sur des cas d’erreurs (tous les cas à la marge). 
 - Ex : il n’y a plus de place siège de libre pour cette séance
 - Les erreurs doivent être vu 
 - Pendant l’animation, il faudra que les groupes devinent par eux-même que c’est la partie suggestion de places qui nous intéresse en fait (et pas la partie réservation pour laquelle on a un autre prestataire)
 - On concluera le round en expliquant cette distinction en 2 systèmes et en indiquant que c’est le 1e qui nous intéresse

## 4. Event Storming round 3 (15’)
Identifiez les policies, les règles métiers pour la suggestion des places (appelées aussi invariants métier  ce qui doit être toujours vérifié). Ex: 
  - i.	do not offer any seat that is already booked by another customer
  - ii.	offer seats nearer the middle of a row
  - iii.	offer seats nearer the front
  - iv.	if possible, offer adjacent seats to members of the same party
  - v.	parties of over 6 can be split into groups that sit together, with at least 2 in each group.
  - vi.	avoid leaving single seats unbooked on a row.
  - vii.	as a last resort, offer seats that are not adjacent.

## 5. Example mapping sur 1 ou 2 règles métier (20’)
 - Ex : Dans la mesure du possible, attribuer des sièges devant
 - Tips : Vous avez le droit de dessiner des topologies de théâtre

## 6. Conclusion (10’)
 - Intéressant de considérer les Erreurs comme des Events
 - Les 2 techniques s’articulent bien entre-elles. Pour rappel ici : Event Storming  big picture  / Example mapping  préparer l’équipe de dev avant de coder une story
  - Merci !

__En tout ça fait 1h25__. Il faudra bien penser à lancer le chrono
