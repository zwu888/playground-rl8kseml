# Remove duplicates in a string

```C++ runnable
#include <iostream>
#include<cstring>

using namespace std;

void rem_dup(char* str)
{
    cout << *str << endl;
    if (!str)
        return;
    int end = 0;
    bool dup[256] = {false};
    for( int i = 0; str[i] !='\0'; i++)
    {
        cout << str[i] << endl;
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
    char* inp = new char[9];
    strcpy(inp, "aabbccdd\0");
    cout << strlen(inp) <<endl;
    //while (*inp != '\0')
    //    cout << *inp++ ;
    //cout << endl;
    rem_dup(inp);
    cout << "   ==" << inp << endl;
    while (*inp++ != '\0')
        cout << *inp ;
    cout << endl;
    
}
