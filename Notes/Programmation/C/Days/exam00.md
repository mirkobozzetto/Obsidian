Assignment name  : only_a
Expected files   : only_a.c
Allowed functions: write
Write a program that displays a 'a' character on the standard output.

```c
#include <unistd.h>

int main(void)
{
    write(1, "a", 1);
    return (0);
}
```

--------------------------------------------------------------------------------
Assignment name  : ft_countdown
Expected files   : ft_countdown.c
Allowed functions: write
Write a program that displays all digits in descending order, followed by a
newline.

Example:
$> ./ft_countdown | cat -e
9876543210$
$>
```c
#include <unistd.h>

int main(void)
{
    write(1, "9876543210\n", 11);
    return (0);
}

```

---------------------------------------------------------------
Assignment name  : maff_alpha
Expected files   : maff_alpha.c
Allowed functions: write
Write a program that displays the alphabet, with even letters in uppercase, and
odd letters in lowercase, followed by a newline.

Example:

$> ./maff_alpha | cat -e
aBcDeFgHiJkLmNoPqRsTuVwXyZ$

```c
#include <unistd.h>

int main(void)
{
    write(1, "aBcDeFgHiJkLmNoPqRsTuVwXyZ\n", 27);
    return (0);
}

```

---------------------------------------------------------------
Assignment name  : maff_revalpha
Expected files   : maff_revalpha.c
Allowed functions: write

Write a program that displays the alphabet in reverse, with even letters in
uppercase, and odd letters in lowercase, followed by a newline.

Example:

$> ./maff_revalpha | cat -e
zYxWvUtSrQpOnMlKjIhGfEdCbA$

```c
#include <unistd.h>

int main(void)
{
    write(1, "zYxWvUtSrQpOnMlKjIhGfEdCbA\n", 27);
    return (0);
}

```

--------------------------------------------------------------------------------

Assignment name  : hello
Expected files   : hello.c
Allowed functions: write


Write a program that displays "Hello World!" followed by a \n.

Example:

$>./hello
Hello World!
$>./hello | cat -e
Hello World!$
$>

```c
#include <unistd.h>

int main(void)
{
    write(1, "Hello World!\n", 13);
    return (0);
}

```

--------------------------------------------------------------------------------
Assignment name  : ft_swap
Expected files   : ft_swap.c
Allowed functions: 

Write a function that swaps the contents of two integers the adresses of which
are passed as parameters.

Your function must be declared as follows:

void	ft_swap(int *a, int *b);

```c
void	ft_swap(int *a, int *b)
{
    int tmp;

    tmp = *a;
    *a = *b;
    *b = tmp;
}

```

--------------------------------------------------------------------------------

Assignment name  : ft_strcmp
Expected files   : ft_strcmp.c
Allowed functions: 

Reproduce the behavior of the function strcmp (man strcmp).

Your function must be declared as follows:

int    ft_strcmp(char *s1, char *s2);

```c
int	ft_strcmp(char *s1, char *s2)
{
    while ((*s1 == *s2) && *s1 && *s2)
    {
        s1++;
        s2++;
    }
    return ((unsigned char)*s1 - (unsigned char)*s2);
}

```

--------------------------------------------------------------------------------
Assignment name  : ft_strrev
Expected files   : ft_strrev.c
Allowed functions: 

Write a function that reverses (in-place) a string.

It must return its parameter.

Your function must be declared as follows:

char    *ft_strrev(char *str);

```c
char    *ft_strrev(char *str)
{
    int     i;
    int     len;
    char    temp;

    len = 0;
    while (str[len])
        len++;
    i = 0;
    while (i < len / 2)
    {
        temp = str[i];
        str[i] = str[len - i - 1];
        str[len - i - 1] = temp;
        i++;
    }
    return (str);
}

```

--------------------------------------------------------------------------------
Assignment name  : ft_atoi
Expected files   : ft_atoi.c
Allowed functions: None

Write a function that converts the string argument str to an integer (type int)
and returns it.

It works much like the standard [[atoi]](const char *str) function, see the man.

Your function must be declared as follows:

int	ft_atoi(const char *str);

```c
int	ft_atoi(const char *str)
{
    int i;
    int sign;
    long res;

    i = 0;
    sign = 1;
    res = 0;
    while ((str[i] >= 9 && str[i] <= 13) || str[i] == 32)
        i++;
    if (str[i] == '-' || str[i] == '+')
    {
        if (str[i] == '-')
            sign = -1;
        i++;
    }
    while (str[i] >= '0' && str[i] <= '9')
    {
        res = (res * 10) + (str[i] - '0');
        i++;
    }
    return ((int)(res * sign));
}

```
Les valeurs 9, 13 et 32 correspondent aux codes ASCII pour certains caractères blancs (whitespace characters) dans une chaîne de caractères. Ces caractères sont souvent ignorés lors de l'analyse de textes ou de nombres.

Voici ce à quoi ces valeurs correspondent :

- 9 : caractère de tabulation horizontale ('\t')
- 13 : caractère de retour à la ligne ('\r')
- 32 : espace (' ')

La condition `str[i] >= 9 && str[i] <= 13` vérifie donc si le caractère est un caractère blanc. Cette partie de la fonction `ft_atoi` ignore tous les caractères blancs au début de la chaîne de caractères.

--------------------------------------------------------------------------------
