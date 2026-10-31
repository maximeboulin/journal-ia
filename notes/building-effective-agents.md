# Fiche de lecture : Building effective agents

- **Source :** [anthropic.com/engineering/building-effective-agents](https://www.anthropic.com/engineering/building-effective-agents)
- **Auteurs :** Erik Schluntz et Barry Zhang (Anthropic), 19 décembre 2024
- **Lu le :** 31/10/2026

## Workflow ou agent ?

- **Workflow :** le LLM et les outils suivent des étapes **fixées à l'avance par le code**.
- **Agent :** le LLM **décide lui-même** des étapes et des outils à utiliser, en boucle, jusqu'à finir la tâche.

Le message principal : **commencer par la solution la plus simple**. Un seul appel bien prompté suffit souvent. On n'ajoute de la complexité (workflow, puis agent) que si elle améliore vraiment le résultat.

## La brique de base : le LLM augmenté

Un LLM auquel on ajoute des **outils**, de la **recherche** (retrieval) et de la **mémoire**.

## Les 5 patterns de workflow

| Pattern | En une phrase | Exemple |
|---|---|---|
| **Prompt chaining** | Découper une tâche en étapes successives, chaque appel traitant la sortie du précédent. | Écrire le plan d'un article, vérifier le plan, puis rédiger l'article. |
| **Routing** | Classer l'entrée, puis l'envoyer vers le traitement spécialisé adapté. | Un support client qui envoie les questions de remboursement, les questions techniques et les questions générales vers des prompts différents. |
| **Parallelization** | Lancer plusieurs appels en même temps (sous-tâches indépendantes, ou plusieurs avis à comparer). | Plusieurs appels relisent le même code pour chercher des failles, puis on compare leurs avis (vote). |
| **Orchestrator-workers** | Un LLM central découpe la tâche à la volée et délègue à des « workers ». | Un agent de code qui choisit quels fichiers modifier selon la demande, puis confie chaque fichier à un worker. |
| **Evaluator-optimizer** | Un LLM produit, un autre évalue et donne un retour, et on boucle jusqu'à ce que ce soit bon. | Traduire un texte, faire critiquer la traduction par un second appel, et corriger jusqu'à ce qu'elle soit bonne. |

## Les 3 principes

1. **Simplicité** dans la conception.
2. **Transparence** : montrer les étapes de planification de l'agent.
3. **Des outils bien conçus** : les documenter et les tester aussi soigneusement qu'un prompt.

## Mon avis

- ✍️ *Ce qui m'a surpris :*
- ✍️ *Ce que je n'ai pas compris (à revoir en semaine 11) :*
- ✍️ *Une idée d'agent que j'aimerais construire :*
