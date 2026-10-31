# Semaine 1 : mise en place (phase 0)

**Objectif de la phase :** avoir les outils prêts et une première idée de ce que l'IA sait faire.

## Séance 1 : 31/10/2026

### Ce que j'ai fait
- Assisté (via un ami) à une table ronde avec une personne du conseil en IA, sujet : les agents IA. Idées retenues :
  - il faut apprendre à **manager** l'IA, pas seulement lui confier ce que je sais déjà faire ;
  - les développeurs deviennent les **architectes** du code produit par l'IA ;
  - méthodes à connaître : Agentic SDLC, SDD (Spec-Driven Development), TDD (Test-Driven Development) ;
  - connaître les **maths** derrière les modèles est important.
- Construit un plan d'apprentissage sur 16 semaines (voir le [README](../README.md)).
- Installé **Claude Code** dans le terminal et ajouté `~/.local/bin` au PATH.
- Appris les bases du terminal : `cd`, `ls`, `pwd`, `mkdir`.
- Créé mon compte **GitHub** et ajouté ma clé SSH pour pouvoir pousser sans mot de passe.
- Créé ce dépôt et fait mon premier `git push`.
- Lu l'article [Building effective agents](../notes/building-effective-agents.md) d'Anthropic.

### Ce que l'IA a bien fait
- Quand `ssh -T git@github.com` a été refusé, Claude Code a lancé `ssh -vT` pour voir le détail. Résultat : ma clé est bien envoyée, c'est GitHub qui la refuse. Le problème vient donc de mon compte GitHub, pas de mon Mac.
- Il m'a donné l'**empreinte** (fingerprint) de ma clé pour que je la compare à celle enregistrée sur GitHub.
- L'IA a bien réussi à se connecter à mon terminal, mon dossier github et à VSC.
- Les questions posées sont intéressantes : quand je lui demande quelque chose, il fait un effort pour bien orienté ma requete. Par exemple, il a de lui même demandé s'il fallait ajouter une branche différente à partir d'un prompt large. 
### Où l'IA s'est trompée (et comment je l'ai vu)
- Limite plutôt qu'erreur : l'IA ne peut pas voir mon compte GitHub (le CLI `gh` n'est pas installé), alors elle m'a donné une liste de vérifications au lieu de la réponse.

### Ce que j'ai appris
- Claude Code peut s'utiliser avec un **abonnement** ; la **clé API** sert à coder ses propres agents (je la créerai en semaine 8).
- Une clé API ne doit **jamais** finir dans un dépôt : elle va dans un `.env`, lui-même listé dans le `.gitignore`.
- Une clé SSH a une partie publique (`.pub`, à donner à GitHub) et une partie privée (qui ne quitte jamais mon Mac). Une passphrase protège la clé privée.
- `ssh -T git@github.com` sert à tester la connexion SSH à GitHub. Si ça marche, on voit `Hi <pseudo>!`. Sinon, on voit `Permission denied (publickey)`.
- `ssh -vT` (mode verbeux) montre quelle clé est proposée et si elle est refusée.
- GitHub distingue les clés **d'authentification** (pour se connecter et pousser) des clés **de signature** (pour signer les commits).
- Ce qu'est un workflow et un agent, et la différence entre les deux. 

### Prochaine étape
- Régler la clé SSH : `ssh -T git@github.com` répond encore `Permission denied`.
- Créer un abonnement Claude si besoin.
- Semaine 2 : l'expérience « avant / après » sur 5 exercices simples, chronométrés avec et sans IA.
