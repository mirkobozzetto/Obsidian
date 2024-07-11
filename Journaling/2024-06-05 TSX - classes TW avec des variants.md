#tailwind #typescript #react

Pour créer un composant React TypeScript qui utilise Tailwind CSS avec des classes dynamiques basées sur des variantes, voici comment tu peux structurer ton code :

1. Définir un type ou une interface pour les variantes.
2. Utiliser une fonction pour générer les classes Tailwind en fonction de la variante passée.
3. Créer un composant qui prend la variante en props et applique les classes appropriées.

```tsx
type Variant = 'primary' | 'secondary' | 'tertiary';

const getVariantClasses = (variant: Variant): string => {
    switch (variant) {
        case 'primary':
            return 'bg-blue-500 text-white hover:bg-blue-700';
        case 'secondary':
            return 'bg-gray-500 text-white hover:bg-gray-700';
        case 'tertiary':
            return 'bg-green-500 text-white hover:bg-green-700';
        default:
            return '';
    }
};

type ButtonProps = {
    variant: Variant;
    children: React.ReactNode;
};

const Button = ({ variant, children }: ButtonProps) => {
    const classes = `py-2 px-4 rounded ${getVariantClasses(variant)}`;
    return <button className={classes}>{children}</button>;
};

export default Button;
```

ou avec #clsx ça permet de faire des choses plus complexes en terme d'interactivité

```tsx
import clsx from 'clsx';

type Variant = 'primary' | 'secondary' | 'tertiary';

const getVariantClasses = (variant: Variant): string => {
    switch (variant) {
        case 'primary':
            return 'bg-blue-500 text-white hover:bg-blue-700';
        case 'secondary':
            return 'bg-gray-500 text-white hover:bg-gray-700';
        case 'tertiary':
            return 'bg-green-500 text-white hover:bg-green-700';
        default:
            return '';
    }
};

type ButtonProps = {
    variant: Variant;
    children: React.ReactNode;
    disabled?: boolean;
    active?: boolean;
};

const Button = ({ variant, children, disabled = false, active = false }: ButtonProps) => {
    const baseClasses = 'py-2 px-4 rounded transition-all duration-300';
    const classes = clsx(
        baseClasses,
        getVariantClasses(variant),
        {
            'opacity-50 cursor-not-allowed': disabled,
            'border-2 border-blue-700': active,
        }
    );

    return <button className={classes} disabled={disabled}>{children}</button>;
};

export default Button;

```

### Exemples d'utilisation

```tsx
import Button from './Button';

const App = () => (
    <div className="space-y-4">
        <Button variant="primary">Primary Button</Button>
        <Button variant="secondary" disabled>Secondary Button (Disabled)</Button>
        <Button variant="tertiary" active>Tertiary Button (Active)</Button>
        <Button variant="primary">
            <span className="font-bold">Nested Content</span>
        </Button>
        <Button variant="secondary" active>
            <div>
                <p className="text-sm">Multiple Lines</p>
                <p>Of Content</p>
            </div>
        </Button>
    </div>
);

export default App;

```

### Explications

- `children`: Peut contenir du texte, des éléments HTML ou des composants React imbriqués.
- `variant: Variant`: Utilisé pour inférer le type des variantes directement dans `ButtonProps`.
- `disabled` et `active`: Optionnels pour permettre une flexibilité d'utilisation.