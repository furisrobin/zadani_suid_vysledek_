Byla využita chyba PATH hijacking u SUID programu /usr/bin/syscheck, který spouštěl příkaz "date" bez celé cesty.
Vytvořil jsem vlastní skript se stejným názvem a nastavil PATH tak, aby se spustil můj místo originálního.
UID je skutečný uživatel, ale EUID určuje oprávnění programu; u SUID je EUID root.
Díky tomu se můj skript spustil s právy root a mohl jsem přečíst chráněný soubor.
Ochrana je používat celé cesty k programům a omezit používání SUID.
