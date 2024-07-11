Tag:  #daily #NextJs 

# Next Themes

`next-themes` est un package conçu pour simplifier la gestion des thèmes dans une application Next.js, notamment en supportant le basculement entre thèmes clair et sombre, et en permettant de respecter les préférences de thèmes des utilisateurs.

### Fonctionnement de `next-themes`

- **ThemeProvider** : `next-themes` fournit un composant `ThemeProvider` que tu utilises pour englober ton application ou une partie de celle-ci. Ce composant stocke le thème actuel dans le contexte de l'application, permettant ainsi à tous les composants enfants d'accéder au thème actuel et de réagir aux changements.
- **Attribut `class`** : Quand tu passes `attribute="class"` à `ThemeProvider`, cela indique à `next-themes` de gérer les thèmes en ajoutant ou en retirant des classes CSS au niveau de l'élément `<body>` de ta page. Cela permet une commutation de thème efficace et évite le flash de style non désiré lors du chargement de la page.
- **Préférences système** : Par défaut, `next-themes` détecte et respecte les préférences de thème du système de l'utilisateur. Si l'utilisateur a une préférence pour un thème sombre ou clair au niveau du système, `next-themes` appliquera cette préférence automatiquement.
- **Stockage persistant** : Lorsqu'un utilisateur choisit un thème, ce choix est persisté (par défaut dans `localStorage`), de sorte que le thème sélectionné reste actif lors des visites ultérieures.

### Interdépendance avec le `ThemeProvider` dans une app Next.js

Dans le code que tu as fourni, le `ThemeProvider` de `next-themes` est utilisé pour englober les enfants (`children`) passés au composant `Provider`. Cela signifie que tous les composants enfant auront accès au thème actuel et pourront se mettre à jour en conséquence lors d'un changement de thème. 

Dans une application Next.js utilisant le routing (`next/router`), cela garantit que peu importe la route visitée, les préférences de thème de l'utilisateur sont respectées et appliquées uniformément sur toutes les pages. Le basculement de thème sera cohérent et fluide lors de la navigation à travers différentes routes de l'application.

### Conclusion

Utiliser `next-themes` avec `ThemeProvider` offre une solution élégante et efficace pour gérer les thèmes dans une application Next.js, en assurant une expérience utilisateur cohérente et respectueuse de leurs préférences, tout en simplifiant la gestion des thèmes pour les développeurs.

```tsx
import React, { useEffect, useState } from "react";
import { useTheme } from "next-themes";

const ThemeSwitch = () => {
  const { theme, setTheme } = useTheme();
  const [mounted, setMounted] = useState(false);

  useEffect(() => {
    setMounted(true);
  }, []);

  if (!mounted) {
    return null;
  }

  return (
    <button onClick={() => setTheme(theme === "dark" ? "light" : "dark")}>
      {theme === "dark" ? "Light" : "Dark"}
    </button>
  );
};

export default ThemeSwitch;

```

```tsx
"use client";

import React from "react";
import { ThemeProvider } from "next-themes";

interface ProviderProps {
children: React.ReactNode;
}

export const Provider = ({ children }: ProviderProps) => {

return <ThemeProvider attribute="class">{children}</ThemeProvider>;

};
```