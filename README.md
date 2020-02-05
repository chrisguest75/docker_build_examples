# Docker Build Examples and Demos
A repository for showing examples of how containers are built and proving concepts that exist. 

The aim is to use examples to show how Docker behaves when building containers and to squash some assumptions. 

## Example 1 - Layers, Hiding and Squashing
Demonstrates how layers are stored, files are hidden and can be squashed.  
Steps [README.md](./01_layers_hiding/README.md)  

## Example 1b - Mv, Rm, Sh
** Not working!! **
Building a simple container with mv, rm, sh.  Probably missing libs.  
Steps [README.md](./01b_mv_cp_rm/README.md)  

## Example 2 - Kernel versions
Demonstrates how kernel versions are different for build and execution.  
Steps [README.md](./02_kernel_versions/README.md)  


## Example 3 - Buildargs 
Demonstrate how buildargs are stored in the image  
Steps [README.md](./03_buildargs_storage/README.md)  


## Example 4 - Docker Context 
Show a docker context issue (large files)  
Steps [README.md](./04_docker_context/README.md)  


## Example 5 - Root user 
Demonstrate root user  
Steps [README.md](./05_root_user/README.md)  


## Example 6 - Multistage small image size
Demonstrate multistage build small image size  
Steps [README.md](./06_multistage/README.md)  


## Example 7 - Buildkit
Demonstrate buildkit parallel building  
Steps [README.md](./07_buildkit/README.md)  


## Example 8 - Layer caching with arguments
Demonstrate layer caching.  
Steps [README.md](./08_caching_arguments/README.md)  


## Example 11 - Cmdline passthrough
Demonstrate passing through cmd line parameters in docker run 
Steps [README.md](./11_cmdline_passthrough/README.md)  


## Example 12 - Background processes
Demonstrate creating background processes  
Steps [README.md](./12_background_processes/README.md)  


## Example 13 - Users and permissions
Users and permissions  
Steps [README.md](./13_users_and_permissions/README.md)  


## Example 14 - OOM - Out of memory
Demonstrate an out of memory issue.  Includes sysdig...
Steps [README.md](./14_out_of_memory/README.md)  


## Example 15 - ENTRYPOINT and CMD
Demonstrate how ENTRYPOINT and CMD differ
Steps [README.md](./15_entrypoint_and_cmd/README.md)  


## Example 16 - Layer caching with non-deterministic executions
Demonstrate how layer caching works with non-determinstic commands.
Steps [README.md](./16_cache_fails/README.md)  


## Example 17 - Microscanner
Demonstrate how to use Microscanner to detect vulnerabilities.
Steps [README.md](./17_microscanner/README.md)  


## Example 18 - Hadolint
Demonstrate hadolint
Steps [README.md](./18_hadolint/README.md) 


## Example 19 - Locking versions with APT
Demonstrate an apt locking technique
Steps [README.md](./19_apt_locking/README.md) 


## Example 20 - Building a rootfs image
Demonstrates building a root image  
Steps [README.md](./20_build_root/README.md) 





## Example 23 - Building bash5 for Unbuntu 16.04
Demonstrates building bash 5 on an ubuntu image. 
Steps [README.md](./23_bash5_ubuntu/README.md) 


# README.md


## TODO
1. Show patching a container to fix an issue reported by GCR
1. Show how multistage builds work for testing
1. Cache invalidation - package managers 
1. Ordering of layers
1. Secrets
1. onbuild
1. read only containers
1. Signing builds
1. entrypoint versus cmd
1. Docker in docker kaniko. 
1. Build software using qemu and copy it in. 
1. Build something for arm and for x86 and support both inside a single container. 
1. Unpack the filesystem flattened.  Filesystem view in a single container.
1. Start a cgroup manually using an unpacked container.
1. Injecting another container into a container. 
1. Snaps??
1. Showing the process tree for docker
1. Demo using cache-from.....  Use a timed layer.
1. Cron in a container. 
1. memory restrictions and how they manifest. 
1. Can I use a cgroup command inside a container?
1. Docker users. 
1. Demonstrate an Out of memory issue  
1. Binding to different networks localhost vs 127.0.0.1 or 0.0.0.0
1. Here docs and string during building images.. https://gist.github.com/abn/a16e9d799312fb492861

