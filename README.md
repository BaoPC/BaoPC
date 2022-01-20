int myStrlen(char s[])
{
    int n = 0;
    while (s[n] != '\0') ++n;
    return n;
}
void myStrcpy(char s2[], char s1[])
{
    int i = 0;
    for (int j = 0; i <= myStrlen(s1); i++, j++)
        s2[j] = s1[i];
}
void trim(char s[])
{
    int i = 0;
    while (s[i] == ' ')
        i++;
    if (i != 0)
        myStrcpy(s, s + i);
    i = myStrlen(s,0) - 1;
    while (s[i] == ' ' && i >= 0)
        i--;
    s[i + 1] = '\0';
}
void deletespace(char s[])
{
    char a[MAX];
    int n = 0;
    for (int i = 0; i <myStrlen(s,0); ++i)
    {
        if (s[i] != ' ')
        {
            a[n] = s[i];
            n++;
        }
        else if (s[i] == ' ' && s[i + 1] != ' ')
        {
            a[n] = s[i];
            n++;
        }
    }
    a[n] = '\0';
    myStrcpy(s, a);
}
