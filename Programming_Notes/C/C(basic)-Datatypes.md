Date: 2025-03-30
Main: [[Basics]]
Sub: [[DataTypes]] 
Taal/Editor: [[VisualStudioCode]],[[C]]
Desc: Er zijn verschillende manieren om variabelen te declareren. Hierin vertel ik meer over de basis manieren om variabelen te kunnen declareren. 

C is een taal die zeer gedreven is in optimalisatie, Hierdoor zijn er ook heel veel verschillende datatypes die allemaal hun eigen "use cases" hebben.
### 1. **Integer (`int`)**

Een geheel getal zonder decimalen. De int heeft een bit groote van 32.  


```
`#include <stdio.h> 
int main() 
{     
int leeftijd = 25;    
printf("Leeftijd: %d\n", leeftijd);     
return 0; 
}`
```

### 2. **Floating Point (`float`)**

Een decimaal getal met enkele precisie (minder nauwkeurig dan `double`).

```
`#include <stdio.h>  
int main() 
{     
float temperatuur = 36.5;     
printf("Temperatuur: %.1f\n", temperatuur);     
return 0; 
}`
```

### 3. **Double Precision (`double`)**

Een decimaal getal met dubbele precisie (nauwkeuriger dan `float`).

```
`#include <stdio.h>  
int main() 
{     
double pi = 3.14159265359;     
printf("Pi: %.10lf\n", pi);     
return 0; 
}`
```

### 4. **Character (`char`)**

Een enkel karakter, altijd tussen enkele aanhalingstekens `' '`.

```
`#include <stdio.h>  
int main() 
{     char eersteLetter = 'A';     
printf("Eerste letter: %c\n", eersteLetter);     
return 0; 
}`
```

### 5. **Boolean (`_Bool`)**

C heeft geen ingebouwd `bool` type zoals in andere talen, maar `_Bool` kan worden gebruikt.

```
`#include <stdio.h> 
#include <stdbool.h> // Voor betere leesbaarheid  
int main() 
{     
_Bool isWaar = 1; // 1 = true, 0 = false     
printf("Is het waar? %d\n", isWaar);     
return 0; 
}`
```

Met `<stdbool.h>` kun je ook `bool`, `true` en `false` gebruiken:

```
`#include <stdio.h> 
#include <stdbool.h>  
int main() 
{     
bool isGroot = true;     
printf("Is groot: %d\n", isGroot);     
return 0; 
}`
```

### 6. **Short Integer (`short`)**

Een korter (kleiner bereik) geheel getal.

```
`#include <stdio.h>  
int main() 
{     
short kleinGetal = 32767; // Maximale waarde voor short (afhankelijk van het systeem)     
printf("Klein getal: %d\n", kleinGetal);     
return 0; 
}`
```

### 7. **Long Integer (`long`)**

Een groter geheel getal.

```
`#include <stdio.h>  
int main() {     
long grootGetal = 1234567890;     
printf("Groot getal: %ld\n", grootGetal);     
return 0; 
}`
```

### 8. **Long Long Integer (`long long`)**

Een nog groter geheel getal.

```
`#include <stdio.h>  
int main() 
{     long long zeerGrootGetal = 9223372036854775807;     
printf("Zeer groot getal: %lld\n", zeerGrootGetal);     
return 0; 
}`
```

### 9. **Unsigned Variabelen**

Voor positieve getallen kun je `unsigned` gebruiken, waardoor het bereik verdubbelt.

```
`#include <stdio.h>  
int main() 
{     
unsigned int positief = 4294967295; // Grootste waarde voor unsigned int     printf("Positief getal: %u\n", positief);     
return 0; 
}`
```

Dit zijn al de basis datatypes die veel gebruikt worden voor variabelen. De uitgebreidere datatypes komen aanbod in mijn volgende note. Deze datatypes hebben dan ook meer uitleg nodig dan deze datatypes.

Volgende note: ...