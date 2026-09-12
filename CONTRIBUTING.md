# CONTRIBUTING.md — Guide de contribution

Merci de votre intérêt pour ce projet ! Voici comment contribuer efficacement.

## Table des matières

- [Questions](#questions)
- [Ouvrir une issue](#ouvrir-une-issue)
- [Workflow Git](#workflow-git)
- [Conventions de commit](#conventions-de-commit)
- [Processus de Pull Request](#processus-de-pull-request)
- [Code Review](#code-review)
- [Tests](#tests)

---

## Questions

avant de poser une question, vérifiez :

- La section [README.md](README.md) (Prérequis, Installation)
- Les issues existantes (ouvertes et fermées) pour éviter les doublons

Pour des questions générales, ouvrez une issue avec le label `question`.

---

## Ouvrir une issue

Utilisez le formulaire d'issue de GitHub. Choisissez le template adapté :

- **Bug** : pour un comportement inattendu / erreur
- **Feature Request** : pour une nouvelle fonctionnalité

Titre clair et descriptif. Corps de l'issue :

- Description du problème ou du besoin
- Étapes pour reproduire (si bug)
- Comportement attendu vs. comportement actuel
- Environnement (OS, version, etc.) si pertinent

Ne pas oublier d'ajouter les labels appropriés (`bug`, `enhancement`, `documentation`) — les mainteneurs peuvent compléter.

---

## Workflow Git

Ce projet suit un workflow de branche feature isolée.

### Installation locale

```bash
git clone https://github.com/maximegrignon4-del/Repo.git
cd Repo
```

### Créer une branche

```bash
git checkout main
git pull origin main
git checkout -b <type>/<description-courte>
```

**Convention de nommage des branches** :

| Préfixe | Usage |
|---------|-------|
| `feat/` | nouvelle fonctionnalité |
| `fix/` | correction de bug |
| `docs/` | documentation |
| `refactor/` | refactoring (sans changement de comportement) |
| `test/` | ajout/changement de tests |
| `chore/` | maintenance, config, tooling |

Exemples : `feat/user-auth`, `fix/login-redirect`, `docs/contributing-guide`.

### Commiter

Voir [Conventions de commit](#conventions-de-commit) ci-dessous.

### Push & PR

```bash
git push -u origin <votre-branche>
# Puis ouvrir une PR sur GitHub (bouton « Compare & pull request » ou via CLI)
```

---

## Conventions de commit

Ce projet utilise **Conventional Commits** (https://www.conventionalcommits.org/).

### Format

```
<type>(<scope>): <description>

<corps optionnel>

<footer optionnel>
```

- **type** : `feat`, `fix`, `docs`, `style`, `refactor`, `perf`, `test`, `build`, `ci`, `chore`
- **scope** (optionnel) : contexte du changement, entre parenthèses (ex. `fix(auth)`, `docs(readme)`)
- **description** : phrase en minuscules, sans point final, max ~72 caractères
- Corps et footer optionnels (ex. `Closes #123` pour fermer une issue automatiquement)

### Exemples

```bash
feat(auth): ajouter endpoint de connexion JWT
fix(readme): corriger lien vers CONTRIBUTING.md
docs: ajouter guide de contribution
test(auth): ajouter tests de validation de token
```

---

## Processus de Pull Request

1. **Assurez-vous que main est à jour** avant de créer votre branche.
2. **Créez une branche feature** décrivant clairement le changement.
3. **Implémentez le changement** avec des commits atomiques et descriptifs.
4. **Testez localement** (voir section [Tests](#tests)).
5. **Ouvrez une PR** :
   - Titre au format Conventional Commits (ex. `feat: ajouter …`)
   - Corps de la PR : résumé du changement, motivation, approche, tests effectués, risques ou exclusions
   - Mentionnez l'issue liée : `Closes #123` (pour fermer automatiquement à la merge) ou `Refs #123`
   - Cibler la branche `main`
6. **Marquez la PR comme prête à review** une fois les CI passées.
7. **Répondez aux retours de review** (voir [Code Review](#code-review)).
8. **Attendre la merge** — un mainteneur reviewe et merge la PR (méthode de merge : squash par défaut).

### Corps de PR type

```markdown
## Résumé
- Ce que le PR fait (1-3 puces)

## Motivation
- Pourquoi ce changement est nécessaire

## Approche
- Décisions de design clés, alternatives considérées

## Tests
- [ ] Tests unitaires ajoutés / passant
- [ ] Tests manuels effectués (liste)

## Risques / Exclusions
- Dépendances, comportements non couverts, breaking changes si applicable

Closes #<N>
```

---

## Code Review

### Pour le contributeur

- Exigez une review avant merge (PR marquée comme prête)
- Répondez aux commentaires constructifs, même succinctement
- Si une review demande un changement substantiel, préférez un nouveau commit clair plutôt que de réécrire l'historique (sauf si squash est attendu)

### Pour le revieweur

- Reviewer le diff (pas seulement les lignes modifiées — lire le contexte)
- Vérifier les conventions de commit, le corps de PR, la trace vers l'issue
- Signaler les problèmes de clarté, de tests manquants, de style
- Approuver ou demander des changements — ne pas merge sans review explicite

### Critères de merge

- PR ciblant `main`
- CI passée (si workflows configurés)
- Au moins une review approuvée (ou mainteneur autorisé)
- Corps de PR rempli, issue liée clairement

---

## Tests

À ce stade le projet est minimal (README + CONTRIBUTING). Aucun test automatisé n'est requis pour les contributions documentation.

Pour les contributions code futures :

- Ajouter des tests unitaires pour les nouvelles fonctionnalités
- Assurer que les tests existants passent avant de soumettre
- Documenter les commandes de test dans le README si le projet grossit

---

## Contact & remerciements

- Pour les questions : ouvrez une issue avec le label `question`
- Pour les erreurs de ce guide : ouvrez une issue `documentation` ou proposez un PR

Merci de contribuer ! 🙏

---

*Dernière mise à jour : 2026-09-12 (ajout initial — issue #2)*
