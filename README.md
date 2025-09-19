# kladne-zaporne
#include <stdio.h>

int main(void) {
    int cislo;
    int vysledek;
    int znak;
    int pocetZnaku;

    do {
        printf("Zadej cele cislo :");
        vysledek = scanf("%d", &cislo);

        // Ověření, jestli byl zadán platný vstup
        if (vysledek != 1) {
            // Pokud není platný vstup, vyčistíme buffer a zjistíme počet znaků
            pocetZnaku = 0;
            while ((znak = getchar()) != '\n' && znak != EOF) {
                pocetZnaku++;
                printf("Neplatny vstup: znak '%c' (ASCII %d)\n", znak, znak);
            }
            printf("Ve vstupnim bufferu bylo nalezeno %d znaku.\n", pocetZnaku);
            printf("Nebyl zadán platný vstup! Zkuste to znovu.\n");
        } else {
            // Pokud byl zadán platný vstup
            printf("Bylo vypsano cislo %d.\n", cislo);

            // Zkontroluj hodnotu čísla
            if (cislo == 0) {
                printf("Cislo je nula. Program bude ukoncen.\n");
            } else if (cislo > 0) {
                printf("Cislo je kladne.\n");
            } else {
                printf("Cislo je zaporne.\n");
            }
        }

    } while (cislo != 0); // Program běží dokud není zadáno číslo 0

    return 0;
}
