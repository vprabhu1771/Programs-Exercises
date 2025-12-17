```
https://stackoverflow.com/questions/4204666/how-to-list-files-in-a-directory-in-a-c-program
```

# c
```c
// Source - https://stackoverflow.com/a
// Posted by Jean-Bernard Jansen, modified by community. See post 'Timeline' for change history
// Retrieved 2025-12-13, License - CC BY-SA 4.0

/*
 * This program displays the names of all files in the current directory.
 */

#include <dirent.h> 
#include <stdio.h> 

int main(void) {
  DIR *d;
  struct dirent *dir;
  d = opendir(".");
  if (d) {
    while ((dir = readdir(d)) != NULL) {
      printf("%s\n", dir->d_name);
    }
    closedir(d);
  }
  return(0);
}
```