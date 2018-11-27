# Remove duplicates in a string

```C++ runnable
#include <iostream>

using namespace std;

void rem_dup(char* str)
{
    if (!str)
        return;
    int end = 0;
    bool dup[256] = {false};
    for( int i = 0; str[i] !='\0'; i++)
    {
        if (dup[(int)str[i]])
            continue;
        else
        {
            dup[(int)str[i]] = true;
            str[end++] = str[i];
        }
     }
     str[end]='\0';
}

int main()
{
    char* inp = "aabbccdd";
    while (*inp++ != '\0')
        cout << *inp ;
    cout << endl;
    rem_dup(inp);
    while (*inp++ != '\0')
        cout << *inp ;
    cout << endl;
    
}
