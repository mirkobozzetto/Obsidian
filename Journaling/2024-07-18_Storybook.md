# Storybook - Design System

## Paynovate - Design System

Inside the Paynovate Design System, we have a Storybook that allows us to test our components in isolation.
This is a great way to test our components and see how they look in different states.

## Structure

You can display Button component for example in different states, such as hover, active, disabled, etc.

Inside this component you can find this kingfd of porps:

```tsx
type ButtonProps = {
	children: React.ReactNode | string;
	variant?: ButtonVariant;
	size?: ButtonSize;
	className?: string;
	onClick?: () => void;
	type?: 'submit' | 'button' | 'reset';
	disabled?: boolean;
	loading?: boolean;
	rounded?: boolean;
};
```

- Objectif de Storybook :
    - Storybook est un outil de développement pour créer, tester et documenter des composants UI de manière isolée.
- Structure d'un fichier story :
    - Un fichier `.stories.tsx` contient la configuration et les exemples d'utilisation d'un composant.
    - Il définit des métadonnées (meta) et plusieurs "stories" qui montrent différentes variations du composant.
- Métadonnées (meta) :
    - Définissent des informations globales pour toutes les stories d'un composant, comme le titre, les paramètres de mise en page, et les tags.
- Stories individuelles :
    - Chaque story est une fonction ou un objet qui montre une utilisation spécifique du composant.
    - Elles peuvent démontrer différentes props, états, ou configurations du composant.
- Rendu personnalisé :
    - Les stories peuvent utiliser une fonction `render` pour créer des mises en page complexes ou montrer plusieurs variations côte à côte.
- Interactivité :
    - Storybook permet de modifier les props en temps réel, facilitant les tests et l'exploration du composant.
- Documentation automatique :
    - Storybook peut générer automatiquement de la documentation basée sur les props et les commentaires du composant.
- Cas d'utilisation :
    - Démonstration de variantes (ex: différents styles de boutons)
    - Illustration de différentes tailles
    - Présentation d'états spéciaux (désactivé, chargement, etc.)
- Avantages pour le développement :
    - Facilite la collaboration entre designers et développeurs
    - Sert de référence visuelle et fonctionnelle pour l'utilisation des composants
    - Permet des tests visuels rapides et la détection précoce de problèmes
- Integration avec le composant :
    - Les stories utilisent directement le composant, assurant que la documentation reste à jour avec le code.
- Flexibilité :
    - Storybook s'adapte à différents frameworks et peut être personnalisé selon les besoins du projet.


