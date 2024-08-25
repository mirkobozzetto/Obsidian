
```c
// Inclut les fonctions de base du système d'exploitation
#include <unistd.h>

// Fonction pour écrire un seul caractère à l'écran
void  ft_putchar(char c)
{
    // Écrit le caractère c à l'écran
    write(1, &c, 1);
}

// Fonction pour convertir une chaîne de caractères en un entier
int ft_atoi(char *str)
{
    // Initialise les variables
    int i = 0;
    int num = 0;

    // Parcourt la chaîne de caractères tant qu'on y trouve des chiffres
    while (str[i] >= '0' && str[i] <= '9')
    {
        // Ajoute le chiffre courant à num, après avoir décalé num d'un ordre de grandeur
        num = num * 10 + (str[i] - '0');
        // Passe au caractère suivant
        i++;
    }
    // Renvoie le nombre obtenu
    return num;
}

// Fonction pour dessiner la première ligne du dessin
void  p_f_line(int hor)
{
    // Initialise le compteur
    int i = 0;
    // Dessine le premier caractère
    ft_putchar('/');
    // Dessine les caractères du milieu
    while (++i < hor - 1)
        ft_putchar('-');
    // Si nécessaire, dessine le dernier caractère
    if (hor > 1)
        ft_putchar('\\');
    // Passe à la ligne suivante
    ft_putchar('\n');
}

// Fonction pour dessiner les lignes du milieu du dessin
void  p_body(int hor, int ver)
{
    // Initialise le compteur pour les lignes verticales
    int i = 0;
    // Variable pour le compteur horizontal
    int j;

    // Boucle sur les lignes verticales
    while (++i < ver - 1)
    {
        // Réinitialise le compteur horizontal
        j = 0;
        // Dessine le premier caractère de la ligne
        ft_putchar('|');
        // Dessine les caractères du milieu de la ligne
        while (++j < hor - 1)
            ft_putchar(' ');
        // Si nécessaire, dessine le dernier caractère de la ligne
        if (hor > 1)
            ft_putchar('|');
        // Passe à la ligne suivante
        ft_putchar('\n');
    }
}

// Fonction pour dessiner la dernière ligne du dessin
void p_l_line(int hor)
{
    // Initialise le compteur
    int i = 0;
    // Dessine le premier caractère
    ft_putchar('\\');
    // Dessine les caractères du milieu
    while (++i < hor - 1)
        ft_putchar('-');
    // Si nécessaire, dessine le dernier caractère
    if (hor > 1)
        ft_putchar('/');
    // Passe à la ligne suivante
    ft_putchar('\n');
}

// Fonction pour dessiner tout le dessin
void  drw_pattern(int hor, int ver)
{
    // Si les dimensions sont invalides, termine la fonction
    if (hor <= 0 || ver <= 0)
        return;
        
    // Dessine la première ligne
    p_f_line(hor);
    
    // Si nécessaire, dessine les lignes du milieu
    if (ver > 1)
        p_body(hor, ver);
    // Si nécessaire, dessine la dernière ligne
    if (ver > 2)
        p_l_line(hor);
}

// Fonction principale du programme
int main(int argc, char **argv)
{
    // Si le nombre d'arguments est incorrect, affiche un message d'erreur et termine le programme avec un code d'erreur
    if (argc != 3)
    {
        // Affiche un message d'erreur
        write(1, "Erreur: deux arguments requis\n", 29);
        // Termine le programme avec un code d'erreur
        return 1;
    }

    // Convertit les arguments de chaînes de caractères en entiers
    int hor = ft_atoi(argv[1]);
    int ver = ft_atoi(argv[2]);

    // Dessine le motif avec les dimensions données
    drw_pattern(hor, ver);

    // Termine le programme avec succès
    return (0);
}
```

