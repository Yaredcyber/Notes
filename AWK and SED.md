- **AWK**  is a Linux command used for filter special words from some data .
- **Example**  we create some file name is called my data and it has bellow data.
```my dat 
name age grade sex bank
kalid 18 ten male cbe
yonas 17 ten male awash
rosa 16 ten female abissinya
```
- **Use of AWK**
- separate data using space 
-  To display content of file `awk '{print $0}' filename ` when change 0 in to 1 that filter first spaced words. 
- To filter first raw of data we use `awk '/name/{ print $0'} filename`  
```output
name 
kalid 
yonas
rosa
```
- To print in  Number row `awk '{print NR,$0}' filename`
```output
1 name age grade sex bank
2 kalid 18 ten male cbe
3 yonas 17 ten male awash
4 rosa 16 ten female abissinya
```
- To filter only one row `awk 'NR==2,{print NR,$0}' filename` 
```output
2 kalid 18 ten male cbe
```
- To filter rows in range  `awk 'NR==1,NR==3{print NR,$0}' filename`
```output
1 name age grade sex bank
2 kalid 18 ten male cbe
3 yonas 17 ten male awash
```
- **SED** it is also Linux command used for find and replace some data 
- *syntax* :- `sed 's/FIND/REPLACE/' filename`
- For example we has mydata.txt based on data we can exercise 
- To change sex in to gender `sed 's/sex/gender/ mydata.txt`
```output
name age grade gender bank
kalid 18 ten male cbe
yonas 17 ten male awash
rosa 16 ten female abissinya
```
- same to AWK file output does not save you can redirect save the file 
- To change all /repeated data we use after / use g `sed 's/hello/hi/g'mydata.txt`
- Which means `g` global 
- SED have power to delete words in file 
-  syntax `sed '/filtered_word /d' filename`
-  Example `sed '/male/d' mydata.txt`
```output
name age grade sex bank
```
- Used to give space b/n rows use `sed G mydata.txt`
- Example `sed G mydata.txt`
```output
kalid 18 ten male cbe

yonas 17 ten male awash

rosa 16 ten female abissinya

```
