# Comprendre l'Intelligence Artificielle — Édition 2026

**Architecture, limites et gouvernance des systèmes génératifs**

Manuel de formation technique et conceptuelle pour les professionnels des données qui souhaitent comprendre, construire et auditer des systèmes d'IA générative en production.

---

## 🔗 Accès

👉 **[Lire le manuel en ligne]([https://wontolla00.github.io/Comprendre_lIA_v3.html](https://github.com/wontolla00/Comprendre_la_IA)/)**

Le manuel est une page web interactive lisible directement dans le navigateur. Sans installation, sans inscription.

---

## 📖 À qui s'adresse ce manuel

- Ingénieurs et architectes de données souhaitant transitionner vers les systèmes d'IA
- Architectes de solutions qui conçoivent des systèmes RAG en production
- Responsables de gouvernance et de conformité réglementaire (AI Act, NIST, ISO 42001)
- Professionnels du QA et de la validation des systèmes génératifs
- Formateurs et responsables de la montée en compétences techniques en IA

**Niveau d'entrée :** expérience préalable avec les données (SQL, Python, pipelines, qualité de la donnée). Ce n'est pas un manuel pour grands débutants en technologie.

---

## 📚 Structure : 5 modules + fondamentaux + référence

Le manuel suit une progression délibérée : il part de ce que le lecteur sait déjà (les données) et construit vers ce qui est nouveau (l'IA générative).

| Module | Titre | Contenu principal |
|--------|-------|-------------------|
| **Module 0** | Le pont | Comment fonctionne un LLM · Tokenisation et non-déterminisme · Hallucinations · Traçabilité |
| **Module 1** | Le pont (avancé) | Pipeline ETL → RAG · Embeddings et espace vectoriel · Qualité de la donnée → évaluation probabiliste · Traçabilité en IA |
| **Module 2** | Fondamentaux propres à l'IA | LLMs de l'intérieur · Recherche vectorielle avancée (BM25, re-ranking, GraphRAG, ColBERT) · Diagnostic RAG · Ingénierie des prompts · Modèles de raisonnement · Agents IA et entropie accumulée |
| **Module 3** | Construire en production | Systèmes critiques · Architecture hybride (patron sandwich) · Validation et QA · Supervision humaine · MLOps pour RAG · Écosystème réglementaire mondial (AI Act, NIST AI RMF, ISO 42001) |
| **Module 4** | Rôle et carrière | Quatre rôles émergents · Rôles de risque IA (CAIRO, Red Team AI, AI Ethics Specialist) · Plan de transition de 6 mois · Comment démontrer une compétence réelle |
| **Module 5** | Référence et approfondissement | Conséquences épistémologiques de l'IA · Concepts originaux de l'auteur |

**Annexes incluses :**
- **Annexe A** — Guide des coûts et de la latence d'inférence (2026) : prix par fournisseur, formule de coût mensuel, coût des architectures avancées (GraphRAG, re-ranking, tool loops, contexte long)
- **Annexe B** — Auto-évaluation par module : questions avec critères d'évaluation, sans réponses modèles fermées
- **Annexe C** — Références techniques commentées : 14 ressources organisées en 5 sections (retrieval, GraphRAG, chunking avancé, raisonnement, tool use)
- **Glossaire** — 66 termes de l'écosystème IA avec renvois croisés et distinction entre terminologie standard et concepts originaux de l'auteur (★)

---

## 🧩 Contenu technique couvert

### Architectures de retrieval
- RAG standard, hybride (BM25 + vectoriel + RRF) et contextuel
- Re-ranking : cross-encoders open-weight (BGE-Reranker-v2-m3, Jina Reranker v3, Cohere) et interaction tardive (ColBERT)
- GraphRAG : pipeline opérationnel complet (extraction d'entités, construction du graphe, détection de communautés, requête hybride) avec coûts par étape
- Chunking contextuel : sémantique, préfixage avec contexte synthétique, compression contextuelle

### Modèles et embeddings
- Architecture Transformer, attention Q/K/V, tokenisation
- Sélection du modèle d'embedding (MTEB, multilingue, domaine spécifique)
- Modèles de raisonnement natif : o1, o3, Gemini 2.0 Flash Thinking, Claude 3.7 Sonnet, DeepSeek R1
- RLHF, DPO, RLAIF, RLVR, GRPO : paradigmes d'alignement et leurs implications

### Production et opérations
- Patron sandwich : le LLM propose, le code décide
- Circuit breaker, fallback déterministe, versionnage des index et des corpus
- Évaluation continue : RAGAS, DeepEval, golden dataset, LLM-as-judge
- MLOps : CI/CD pour systèmes RAG, prompt caching, surveillance de la dégradation silencieuse

### Tool use et agents
- Tool use comme capacité du modèle vs. architecture du système
- Sécurité dans les outils : allowlist, validation de schéma, injection par sortie d'outil, HITL pour les actions irréversibles
- Entropie accumulée dans les architectures multi-agents : pourquoi la fiabilité se multiplie à la baisse
- Frameworks : LangGraph, LangChain, comparatif custom vs. framework

### Gouvernance et risque
- Classification par niveaux de risque : AI Act (UE), NIST AI RMF (États-Unis), ISO/IEC 42001 (international)
- Métriques de risque avec outils : hallucinations (RAGAS, LangSmith), biais (IBM AI Fairness 360, Fairlearn), sécurité adversariale (Garak, PyRIT), confidentialité (Presidio), dégradation (Arize, WhyLabs)
- Proxies discriminatoires : détection technique en production
- Plan d'action en trois horizons pour la conformité AI Act

---

## ✨ Ce qui distingue ce manuel des autres ressources

**Honnêteté sur les limites.** Chaque technique comporte une section explicite « quand ne pas l'utiliser ». L'entropie accumulée dans les agents, la dégradation silencieuse du contexte long, le risque de sur-ingénierie dans GraphRAG — sont nommés et quantifiés, pas cachés.

**Progression depuis les données, pas depuis l'IA.** Chaque nouveau concept s'ancre dans son équivalent en données : ETL → RAG, qualité de la donnée → évaluation probabiliste, lignage des données → traçabilité des modèles, gouvernance des données → AI Act. Le lecteur data arrive avec plus de 60 % des compétences nécessaires.

**Caducité déclarée.** Les prix des modèles, benchmarks et seuils portent une note explicite de vérification. Un manuel qui ne déclare pas sa caducité ment par omission.

**Dialogues conceptuels.** Blocs Q&A pour les doutes récurrents que les manuels ignorent habituellement : le token change-t-il avec le contexte ? Le « contexte » est-il le prompt ou le corpus d'entraînement ? Pourquoi RAG n'« enseigne »-t-il pas de nouvelles choses au modèle ?

**Métriques avec seuils opérationnels.** Pas « mesurez la faithfulness » mais « Hit Rate@5 > 0,85 avant la production ; si c'est en dessous, le problème est dans le retrieval, pas dans le LLM. »

---

## 📋 Contenu pédagogique inclus

- **83 tableaux** de référence avec comparatifs, seuils et critères de décision
- **66 infobulles** avec définitions contextuelles
- **6 laboratoires d'erreurs** — systèmes qui ont échoué en production : chunking incorrect, dégradation silencieuse, injection de prompt, entropie accumulée dans les agents, biais non détecté, sandwich cassé
- **12 dialogues conceptuels** (format Q&A) pour les doutes architecturaux fréquents
- **Auto-évaluation par module** avec questions factuelles et de critère
- **Questions sans réponse correcte** — scénarios de décision qui entraînent le jugement, pas la connaissance déclarative

---

## 🛠️ Pour suivre les exercices pratiques

- Python de base et SQL
- Optionnel pour le plan de 6 mois : Ollama (local, gratuit), Groq free tier, ou clé API OpenAI/Anthropic

---

## 🌐 Versions disponibles

| Version | Langue | URL |
|---------|--------|-----|
| Édition 2026 | Français | *(lien à venir)* |
| Edición 2026 | Español | [wontolla00.github.io/Comprendre_la_IA](https://wontolla00.github.io/Comprendre_la_IA/) |

---

## 📄 Licence et attribution

Libre accès pour la formation, la révision et l'amélioration continue.

Les termes marqués **★** dans le glossaire sont des concepts originaux de l'auteur (entropie architecturale, bridge score, indice de diversité cognitive de Shannon, néoténie informationnelle) et ne font pas partie de la terminologie standard du secteur.

**Auteur :** David Escudero de Félix  
**Version :** 2026  
**Dépôt :** [github.com/wontolla00/Comprender_la_IA](https://github.com/wontolla00/Comprender_la_IA)

---

*Si vous trouvez des erreurs, des sections obsolètes ou des améliorations à apporter, ouvrez une issue ou soumettez une pull request. Le manuel se met à jour à la même fréquence que le domaine évolue — ce qui, en 2026, est rapide.*
