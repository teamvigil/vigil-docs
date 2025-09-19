# Architecture de Vigil

## Vue d'ensemble
Vigil est une application modulaire basée sur une architecture microservices légère.

### Composants Principaux
1.  **`vigil-backend`** (Ce dépôt) : API FastAPI cœur métier (collecte, IA, alertes).
2.  **`vigil-frontend`** : Interface Next.js/React.
3.  **`vigil-infra`** : Infrastructure as Code (Terraform, Docker Compose pour la prod).
4.  **PostgreSQL + pgvector** : Base de données principale et magasin vectoriel.

### Flow de données
1.  Les **Collecteurs** ingèrent des données de sources multiples.
2.  Le **Processeur IA** (SentenceTransformers) vectorise le texte.
3.  **PostgreSQL/pgvector** stocke et interroge les embeddings.
4.  L'**API** expose des endpoints de recherche et d'alerte.
5.  Le **Frontend** permet aux utilisateurs d'interagir avec le système.
