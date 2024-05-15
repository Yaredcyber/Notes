### C format specifier
- **Integer variable** It can also  hold negative and posetive integer specified by `%d`
```c
int num = 10;
printf("%d",num);
```
- **character** they use / hold only single characters specified by`%c`
``` c
char spell = 'B' ; // only hold single character
print("%c",spell);
```
- **Floats/** they can hold decimals in the form of point specified by `%f`
``` c
float num = 1.3; //  It can chnage whole number to integer
printf("%f,num);
```
- **Double** It is same to float but it can hold 8biyte data to specify format use `%lf`
``` c 
double num = 20.4;
printf("%lf",num); // The double format specifire is %lf
```
- **Multiple character** it can hold more than single characters ; specifier `%s`
``` c
char car[] = "BMW";
printf("%s",car);
```
- **Boolean** used for specify true or false  / yes or no / on or off we use specify format `%d`
```c // boolean 
#include <stdbool.h>
int main(){
bool say = true;
printf("%d",true);
// or
printf("%d",20>10);// output = 1 it is true 

return 0;
}
```
- **Sizeof()** This function specified by `lu` format 
``` c 
int x = 30 ;
printf("The sie of 30 is %lu ",sizeof(x));
```
- **Pointers** is a memory address of the data stored  using hexadecimal format  to specified by  `%p`
``` c
int age = 17;
int *my_age = &age;
printf("My age is %d \n",age); // output -->My age is  17
printf("My age pointer is %p \n",my_age) //output--> My age in pointer is 0061FF14 
```
