#### Pourquoi ne pas utiliser useEffect pour fetch des données

#useEffect #React #useSWR #ReactQuery

1. **Complexité du State Management**
    - `useEffect` nécessite la gestion des états de chargement et d'erreur.
    - Cela augmente la quantité de code et complique la base de code.

2. **Absence de Cache**
    - `useEffect` ne fournit pas de mise en cache intégrée.
    - Utiliser `useSWR` ou `ReactQuery` permet de bénéficier d'un cache automatique.

#### Avantages de `useSWR` pour le fetch de données

1. **Moins de Code**
    - `useSWR` simplifie la gestion du chargement et des erreurs.
    - Exemple :
      ```jsx
      import useSWR from "swr";

      const fetcher = (...args) => fetch(...args).then(res => res.json());

      const Header = () => {
        const { data, error } = useSWR('https://catfact.ninja/fact', fetcher);

        if (error) return <div>failed to load</div>;
        if (!data) return <div>loading...</div>;

        return <div>Header Fact : {data.fact}</div>;
      }

      const Hero = () => {
        const { data, error } = useSWR('https://catfact.ninja/fact', fetcher);

        if (error) return <div>failed to load</div>;
        if (!data) return <div>loading...</div>;

        return <div>Hero Fact : {data.fact}</div>;
      }

      export default function App() {
        return (
          <div>
            <Header />
            <hr/>
            <Hero />
          </div>
        )
      }
      ```

2. **Cache Automatique**
    - La même URL API retourne les mêmes données, économisant des appels API.

#### Inconvénients de `useEffect`

1. **Code Verbeux et Redondant**
    - Chaque composant utilisant `useEffect` pour fetch les données crée du code redondant.
    - Exemple :
      ```jsx
      import { useEffect, useState } from "react";

      const fetcher = (...args) => fetch(...args).then(res => res.json());

      const Header = () => {
        const [data, setData] = useState(null);
        const [loading, setLoading] = useState(true);
        const [error, setError] = useState(null);

        useEffect(() => {
          fetch('https://catfact.ninja/fact')
            .then(res => res.json())
            .then(setData)
            .catch(setError)
            .finally(() => setLoading(false));
        }, []);

        if (error) return <div>failed to load</div>;
        if (loading) return <div>loading...</div>;

        return <div>Header Fact : {data.fact}</div>;
      }

      const Hero = () => {
        const [data, setData] = useState(null);
        const [loading, setLoading] = useState(true);
        const [error, setError] = useState(null);

        useEffect(() => {
          fetch('https://catfact.ninja/fact')
            .then(res => res.json())
            .then(setData)
            .catch(setError)
            .finally(() => setLoading(false));
        }, []);
      }
      ```

2. **Pas de Cleanup Automatique**
    - Nécessité d'utiliser `AbortController` pour annuler les requêtes.
    - Exemple :
      ```jsx
      useEffect(() => {
        const controller = new AbortController();

        fetch('https://catfact.ninja/fact', { signal: controller.signal })
          .then(res => res.json())
          .then(setData)
          .catch(setError)
          .finally(() => setLoading(false));

        return () => {
          controller.abort();
        };
      }, []);
      ```

#### Recommandations de Bibliothèques

1. **useSWR**
    - Idéal pour les petits projets.

2. **ReactQuery**
    - Recommandé pour les grands projets.

#### Futur du fetch de données avec React

- **use hook**
  - À venir dans React 19.
  - Promet une approche plus simplifiée pour le fetch de données.
  - Détails supplémentaires à venir lors de la sortie stable.

---

Ces notes peuvent être ajoutées à votre système de prise de notes Obsidian pour référence rapide.