# Researching Commands (grep)  
## Option 1: -r  
  
This option makes grep search the specified directory recursively, meaning every file in the directory will be searched regardless of how nested they are.  
  
Example 1:   
```
[cs15lwi23ama@ieng6-201]:skill-demo1-data:422$ grep -r "bathhouses" written_2/
written_2/travel_guides/berlitz1/HistoryJapan.txt:        segregated in the public bathhouses, with naked government spies to
written_2/travel_guides/berlitz1/WhereToJapan.txt:        small traditional inns (ryokan) and bathhouses are now dwarfed by
```

Example 2:  
```
[cs15lwi23ama@ieng6-201]:skill-demo1-data:445$ grep -r "great wall" written_2/
written_2/travel_guides/berlitz1/WhereToIbiza.txt:        •The tunnel through the great wall leads to a classic
written_2/travel_guides/berlitz1/WhereToIbiza.txt:        gateway through the great wall, where you’ll find yourself in the
```  

Source: https://man7.org/linux/man-pages/man1/grep.1.html    
  
## Option 2: -v  
  
Example 1:   
```
[cs15lwi23ama@ieng6-201]:skill-demo1-data:454$ grep -v "The" written_2/travel_guides/berlitz1/HandRIbiza.txt





        Recommended Hotels
        local restaurants, and should convince you that not everything on the
        island comes with chips (french fries).
        offfical government rating system.
        As a basic guide, the symbols we use indicate what you can
        expect to pay for a three-course meal for two, excluding wine, tax and
        tip. Drinks will add considerably to the final bill.
        ✪less than 5,000 ptas.
        ✪✪5,000–8,000 ptas.
        ✪✪✪more than 8,000 ptas.




```

  
Example 2:   
```

```

  
Source: https://man7.org/linux/man-pages/man1/grep.1.html  

## Option 3: -i  
  
Example 1:   
```

```
  
Example 2:   
```

```

  
Source: https://man7.org/linux/man-pages/man1/grep.1.html  
  
## Option 4: -x  
  
Example 1:   
```

```
  
Example 2:   
```

```

  
Source: https://man7.org/linux/man-pages/man1/grep.1.html  
