# Politique de sécurité

> Politique de sécurité par défaut pour l'ensemble des dépôts de l'organisation **Dedalus-ERP-PAS**.
> Un dépôt peut définir sa propre `SECURITY.md` pour la remplacer.

La sécurité des logiciels de santé que nous éditons est une priorité. Nos
applications traitent des données sensibles (données patient, flux
d'interopérabilité HL7/HPRIM/HPK/IHE PAM) et sont soumises à des exigences
réglementaires (**RGPD**, hébergement de données de santé — **HDS**) : nous
prenons tout signalement de vulnérabilité au sérieux.

## Signaler une vulnérabilité

**Ne créez jamais d'issue publique, de pull request ou de message de commit
décrivant une faille de sécurité.** Une divulgation publique expose nos clients
avant qu'un correctif ne soit disponible.

Utilisez l'un des canaux privés suivants, par ordre de préférence :

1. **GitHub Private Vulnerability Reporting** — pour un dépôt hébergé sur
   GitHub : onglet **Security → Report a vulnerability**. C'est le canal
   privilégié : le signalement reste confidentiel et suit le cycle de correction
   via une *security advisory*.
2. **Contact sécurité** — à défaut (notamment pour les dépôts hébergés sur
   GitLab), écrivez à `<security-contact@dedalus.com>`
   *(à confirmer / remplacer par l'adresse ou le PSIRT officiel Dedalus)*.

Merci d'inclure autant d'éléments que possible :

- le dépôt, la version / le tag et l'environnement concernés ;
- une description de l'impact (données exposées, escalade de privilèges, etc.) ;
- les étapes de reproduction ou un *proof of concept* ;
- toute piste de correction ou de contournement connue.

## Ce à quoi vous pouvez vous attendre

- **Accusé de réception** sous **5 jours ouvrés**.
- Une **évaluation** de la sévérité et de la portée, puis un échange sur le
  calendrier de correction.
- Une **divulgation coordonnée** : nous publions les détails une fois le
  correctif disponible et déployé chez les clients concernés.
- Un **remerciement** pour votre signalement responsable, si vous le souhaitez.

## Périmètre

Cette politique couvre le code et les configurations hébergés dans les dépôts de
l'organisation `Dedalus-ERP-PAS`. Les vulnérabilités portant sur des produits
Dedalus déployés chez un client (infrastructure, installation spécifique)
doivent être remontées via le canal support / PSIRT habituel du client.

## Versions supportées

Sauf mention contraire dans le dépôt concerné, seules les **versions
actuellement maintenues** (dernière version stable et branches de maintenance
actives) reçoivent des correctifs de sécurité.
