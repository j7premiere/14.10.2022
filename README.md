### Task 7 kyu

[Task link](https://www.codewars.com/kata/566fc12495810954b1000030/)

Take an integer n (n >= 0) and a digit d (0 <= d <= 9) as an integer.

Square all numbers k (0 <= k <= n) between 0 and n.

Count the numbers of digits d used in the writing of all the k**2.

Call nb_dig (or nbDig or ...) the function taking n and d as parameters and returning this count.

### My solution

```Java

class CountDig
{
    public static int nbDig(int n, int d)
    {
        int c=0;

        for(int i=0;i<=n;i++)
        {
            int p=i*i;
            if ((p==0) && (d == 0)){ c++;}
            while(p!=0)
            {
                int l;
                l=p%10;
                if(l==d){
                    c++;
                }
                p=p/10;
            }

        }
        return c;
    }
}

```

### Favourite solution from code-wars

```Java

import java.util.stream.IntStream;

public class CountDig {

    public static int nbDig(int n, int d) {
        return (int) IntStream.rangeClosed(0, n)
                .flatMap(i -> String.valueOf(i * i).chars())
                .filter(i -> i == (char)(d + '0'))
                .count();
    }
}

```

The shortest solution at code-wars, it's very interesting.

# Have a nice day!