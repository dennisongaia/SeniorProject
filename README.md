The memory management system used by FreeNOS is virtual memory paging. Virtual memory paging is a technique used by operating systems to allow processes to use more memory than physically available in the system. In virtual memory paging, the operating system creates a virtual address space for each process, which is mapped to physical memory. When a process tries to access memory that is not currently in physical memory, the operating system will swap the required memory pages from the hard drive into physical memory. We can infer that this is the memory management system used because of the Range struct that  includes a virtual address field, which suggests that FreeNOS uses virtual memory to manage memory access.

![Screen Shot 2023-05-05 at 3 27 27 PM](https://user-images.githubusercontent.com/77359793/236580969-99535bf0-f26d-4587-91f4-cfce1be28e90.png)

The Memory namespace defines memory access flags and a Range struct for representing memory ranges with various access permissions. The clearBSS() function and MemoryBlock class provide utilities for working with memory blocks, such as clearing them to a specified value.

![Screen Shot 2023-05-05 at 3 27 38 PM](https://user-images.githubusercontent.com/77359793/236580993-784aaf11-226f-4615-88d7-b1e172a59a8d.png)

The memory management is implemented using virtual memory mapping. The MemoryMap class defines the virtual memory layout of the system by dividing the virtual address space into different regions, each with its own access permissions and corresponding physical memory ranges. Virtual memory paging allows processes to use more memory than physically available, while memory mapping allows processes to access files and devices as if they were in memory. The MemoryMap class has a set of predefined regions that include kernel and user data, heap, stack, and private and shared memory regions. Each region is represented by a Memory::Range object, which specifies the virtual and physical address range and the access permissions of the memory region.

![Screen Shot 2023-05-05 at 3 27 00 PM](https://user-images.githubusercontent.com/77359793/236581054-966abc9e-694a-487c-a87b-ccc92050342c.png)

The memory management system used by FreeNOS has advantages over other memory management systems because it is efficient and flexible. The virtual memory paging technique used by FreeNOS allows physical memory to be allocated only when required by a process. Additionally, FreeNOS is very flexible because its page size can be changed depending on the requirements of the system. Despite these advantages, this memory management system has quite a bit of overhead because the OS has to manage the mapping of virtual memory to physical memory. 

Overall, the virtual memory paging technique used by FreeNOS is very efficient and flexible, but due to these advantages it also has the disadvantage of a large overhead. 
