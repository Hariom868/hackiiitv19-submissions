    #include <stdio.h>
    void main ()
    {

        int number[20]={145,156,225,259,245,136,45,98,157,250,224,298,201,120,165,85,147,258,248,159};

        int i, j, a, n;
        n=20;

        for (i = 0; i < n; ++i)
        {
            for (j = i + 1; j < n; ++j)
            {
                if (number[i] < number[j])
                {
                    a = number[i];
                    number[i] = number[j];
                    number[j] = a;
                }
            } 
        }

        printf("The container arranged in descending order of their current capacity of garbage are given below\n");

        for (i = 0; i < n; ++i)
        {
            printf("%d\n", number[i]);
        }
    }
