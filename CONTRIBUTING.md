# Contribuer

> Guide de contribution **par défaut** pour les dépôts GitHub de l'organisation
> **Dedalus-ERP-PAS**. Chaque dépôt peut fournir sa propre `CONTRIBUTING.md`
> (commandes de build, branche cible, scopes, workflow de release) qui **prime**
> sur ce document.

Ce guide décrit le **socle commun** aux différentes familles de projets (Suite,
Hexagone, PMSI…). Les spécificités de chaque projet sont documentées dans son
`README`, ses `docs/` et, le cas échéant, ses ADR.

## Où vit le code

Notre VCS principal est **GitLab self-hosted** (`gitlab-erp-pas.dedalus.lan`) :
la revue s'y fait par **merge request (MR)** avec la CLI `glab`. Une partie des
projets est aussi hébergée sur **GitHub**, où la revue se fait par **pull
request (PR)**. Les deux suivent le même principe : **rien n'atterrit sur `main`
sans revue**.

## Standards partagés

Les conventions transverses (nommage, tests, sécurité, revue…) sont maintenues
dans le dépôt **[`foundation-skills`](https://github.com/Dedalus-ERP-PAS/foundation-skills)**
et installables pour votre assistant IA :

```bash
npx skills add Dedalus-ERP-PAS/foundation-skills -g -y
```

Skills de référence : `coding-standards`, `backend-patterns`,
`react-best-practices`, `vue-best-practices`, `testing-patterns`, `tdd`,
`security-review`, `code-review`, `git-guardrails`.

## Avant de commencer

- Rattachez votre travail à une **issue** (GitHub/GitLab) ou un **ticket Jira**
  (ex. `HEX-1234`, `PWT-5678`) ; pour les décisions d'architecture, à un **ADR**.
- Discutez des changements importants **avant** d'ouvrir une MR/PR.
- Pour une faille de sécurité, suivez la [politique de sécurité](./SECURITY.md)
  — **jamais d'issue publique**.

## Branches

- **Ne poussez jamais directement sur `main`** (ni sur une branche protégée) —
  passez toujours par une MR/PR. Le skill `git-guardrails` bloque `push`,
  `push --force` et `rebase` sur `main` côté agent IA.
- Travaillez sur une branche dédiée. Deux nommages sont courants selon le dépôt :
  - par type : `feat/<scope>`, `fix/<scope>`, `chore/<scope>` ;
  - par issue : `<numéro-issue>-<titre-en-kebab-case>`.
  Suivez la convention du dépôt.

## Commits

**Conventional Commits** est la convention **recommandée** par défaut :

Format : `<type>(<scope>): <description à l'impératif> (<réf>)`

| Type | Usage |
|---|---|
| `feat` | Nouvelle fonctionnalité |
| `fix` | Correction de bug |
| `docs` | Documentation uniquement |
| `refactor` | Restructuration sans changement fonctionnel |
| `perf` | Amélioration de performance |
| `test` | Ajout ou modification de tests |
| `style` | Formatage sans impact fonctionnel |
| `chore` | Maintenance, CI, dépendances |

Règles :

- **En français, à l'impératif** (« ajouter », « corriger »…), sans noms de
  fichiers/fonctions dans le titre.
- Le **scope** est propre au dépôt (nom de service, de module, `deps`, `ci`…).
- Référencez le **ticket/issue** (`#123`, `HEX-1234`) — souvent obligatoire sur
  le premier commit de la branche.
- Certains dépôts appliquent leur propre convention (ex. **préfixe de clé Jira** :
  `PWT-20763 : …`). **Respectez la convention du dépôt** quand elle diffère.
- Un commit = un type ; ne mélangez pas `feat` et `fix`.

> Selon les dépôts, le versioning et le changelog sont automatisés
> (`semantic-release`, `release-please`) à partir des messages de commit :
> rédigez des messages `feat`/`fix` compréhensibles par un non-développeur.

## Merge / Pull requests

- Ciblez la **branche d'intégration du dépôt** (le plus souvent `main`).
- Remplissez le **modèle de MR/PR**, notamment la section **Validation**
  (preuve de test, absence de secret / de texte en dur).
- Assurez-vous que la **CI est verte** (build, lint, tests) avant de demander la
  revue.
- Gardez la MR/PR **focalisée** : un sujet à la fois.

## Revue de code

La revue vise la qualité, la sécurité et la lisibilité. Formulez les retours
**sous forme de questions** plutôt que d'ordres, et hiérarchisez :

- 🔴 **Critique** — à corriger avant fusion ;
- 🟡 **Important** — à traiter ;
- 🟢 **Suggestion** — amélioration optionnelle.

## Qualité

- **Tests** : pyramide ~70 % unitaires / 20 % intégration / 10 % E2E ; E2E
  Playwright (voir `testing-patterns`, `qa-automation`). Traçabilité Xray si le
  dépôt l'utilise.
- **Sécurité** : pas de secret committé, entrées validées, requêtes
  paramétrées ; contexte santé (**RGPD / HDS**, données patient). Voir
  `security-review`.
- **i18n** : pas de texte en dur dans l'UI.
- **Style** : utilisez le linter/formateur du dépôt ; n'ajoutez pas d'outillage
  ad hoc.

## Code de conduite

En participant, vous acceptez notre [code de conduite](./CODE_OF_CONDUCT.md).
