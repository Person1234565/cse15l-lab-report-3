# Researching Commands (grep)  
## Option 1: -r  
  
This option makes grep search the specified directory recursively, meaning every file in the directory will be searched regardless of how nested they are.  
  
Example 1:   
```
[cs15lwi23ama@ieng6-201]:skill-demo1-data:422$ grep -r "bathhouses" written_2/
written_2/travel_guides/berlitz1/HistoryJapan.txt:        segregated in the public bathhouses, with naked government spies to
written_2/travel_guides/berlitz1/WhereToJapan.txt:        small traditional inns (ryokan) and bathhouses are now dwarfed by
```  
  
In this example, while the input directory was written_2/, because of the -r option, the command searched through each subdirectory to find matches for the string. Without the -r option, the command would simply search written_2/ itself, which would have outputted nothing.   
  
Example 2:  
```
[cs15lwi23ama@ieng6-201]:skill-demo1-data:445$ grep -r "great wall" written_2/
written_2/travel_guides/berlitz1/WhereToIbiza.txt:        •The tunnel through the great wall leads to a classic
written_2/travel_guides/berlitz1/WhereToIbiza.txt:        gateway through the great wall, where you’ll find yourself in the
```  
  
In this example, the command is again searching through subdirectories that weren't directly under written_2/ to find matches for the specified string. This is due to the -r option, which tells the command to search each subdirectory recursively. 

This option is extremely useful because you no longer have to use the find command to list all the subdirectories before running grep if you wished to search all the files in a directory. With this option, you simply add -r and it will recursively search for the string you want in all the files from a directory regardless of how the files are nested.   
  
Source: https://man7.org/linux/man-pages/man1/grep.1.html    
  
## Option 2: -v  
  
This option makes grep list the lines that do not contain the specified string.    
  
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
  
In this example, grep is only outputting the lines from the file that don't contain the string "The." Without the -v option, the command would print out all the lines that contain "The."  
  
Example 2:   
```
[cs15lwi23ama@ieng6-201]:skill-demo1-data:459$ grep -v "a" written_2/non-fiction/OUP/Castro/chZ.txt




Zoot Suit





```
  
In this example, grep is only outputting the lines that don't contain the string "a." Without the -v option, this command would print out all the lines that contain "a."  

This option can be useful in situations where you want to find lines in a file that don't contain a sequence of characters. For example, when going through a CSV file, you might want to only find the rows that don't include a certain value, which you can accomplish with grep and the option -v.    
  
Source: https://man7.org/linux/man-pages/man1/grep.1.html  

## Option 3: -i  
  
This option makes grep ignore case when searching for the specified string, meaning it returns the lines that contain the string while treating uppercase and lowercase letters as the same.   
  
Example 1:   
```
[cs15lwi23ama@ieng6-201]:skill-demo1-data:489$ grep -i "PTAS" written_2/travel_guides/berlitz1/HandRIbiza.txt
        ✪less than 5,000 ptas.
        ✪✪5,000–8,000 ptas.
        ✪✪✪more than 8,000 ptas.

```
  
In this example, grep is searching for "PTAS" in the specified file, and due to the -i option, grep outputs occurrences of "ptas" even though it doesn't exactly match the specified string. Without the -i option, nothing would be outputted as there are no occurrences of "PTAS" exactly in the file.   
  
Example 2:   
```
[cs15lwi23ama@ieng6-201]:skill-demo1-data:488$ grep -i "perhaps" written_2/travel_guides/berlitz2/Amsterdam-Intro.txt
Perhaps the most widely publicized acts of tolerance in recent history have been in the areas of sex and drugs. Amsterdammers looked at feasible and practical responses to the issues, and decriminalized some aspects of both. This does not make the city one huge den of iniquity and these areas are still controlled and regulated; in fact, you could visit Amsterdam and be quite unaware of these activities. There’s just a recognition here that provided no harm comes to you or others around you, then you should be free, as an adult, to make your own choices.

```
  
In this exampe, grep searches for occurrences of "perhaps," and with the -i option, it outputs an occurrence of "Perhaps" because it has the same letters but different cases. Without -i, nothing would be outputted as there are no occurrences of exactly "perhaps" in the file.   
  
This option is extremely useful as there are many cases where the string you are searching for is not case sensitive. With this option, you can avoid manually running grep for different versions of the same word and instead run one grep command that searches for occurrences of the string while ignoring case.   
  
Source: https://man7.org/linux/man-pages/man1/grep.1.html  
  
## Option 4: -x  
  
This option makes grep only output lines that exactly match the specified string, meaning a full line must match with the specified string to be outputted.   
  
Example 1:   
```
[cs15lwi23ama@ieng6-201]:skill-demo1-data:500$ grep -x  "The Bahamas" written_2/travel_guides/berlitz2/Bahamas-Intro.txt

```
  
In this example, the grep command outputs nothing as there are no lines that exactly match "The Bahamas." The string might still be inside the file, but there are no occurrences where the string is its own line in the file.   
  
Example 2:   
```
[cs15lwi23ama@ieng6-201]:skill-demo1-data:501$ grep -x  "The Bahamas and the Bahamians" written_2/travel_guides/berlitz2/Bahamas-Intro.txt
The Bahamas and the Bahamians

```

In this example, the grep command outputs the line that matches exactly with the specified string. From this, you can conclude that there is a line in the file that consists of exactly the specified string. 

This option can be useful when trying to filter for specific lines while avoiding finding other occurrences of the string. For example, you could try to find a chapter title using the -x option so that only the line with the chapter title is shown and not any other occurrences of the chapter title in the text.    
  
Source: https://man7.org/linux/man-pages/man1/grep.1.html  
