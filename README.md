# chrono

A extremely simple timing, header-only library for C. This is simply a nicer
wrapper over the function `clock_gettime`.

# Usage

```
#include "chrono.h"

int main(void)
{
    chrono tm;
    chrono_start(&tm);

    // Perform heavy lifting
    int s = 0;
    for (int i = 0; i < 10000; ++i) {
        if (i % 3) {
            s += i;
        }
    }

    chrono_end(&tm);
    printf("%f\n", chrono_get_nsec(&tm));
}
```
