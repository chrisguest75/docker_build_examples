# Example 1b - Mv, Rm, Sh
** Not working!! **
Building a simple container with mv, rm, sh.  Probably missing libs. 

## Script to follow
Demonstrate removing files

```sh 
docker build -t scratchtest .
docker run -it --entrypoint=/bin/sh scratchtest
```
