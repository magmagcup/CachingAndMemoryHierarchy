# Caching and Memory Hierarchy

- Using [Docs to Markdown](https://gsuite.google.com/marketplace/app/docs_to_markdown/700168918607) to convert my [Caching and Memory Hierarchy](https://docs.google.com/document/d/1rRyiuy5fZceq-j0U3dBwTKfgawgnfybv3IB8qS3HnmY/edit?usp=sharing) from google doc text to markdown 

## Memory Hierarchy



*   Diagram represents a computer memory base on its response time and capacity (it can be distinct by other things ex. performance and controlling), the picture below shows the different levels of the memory hierarchy.


![alt_text](https://media.geeksforgeeks.org/wp-content/uploads/Untitled-drawing-4-4.png "image_tooltip")


<p style="text-align: right">
Memory Hierarchy Design, GeeksforGeeks</p>


*   The designing of the memory hierarchy is divided into two types
    *   External memory or Secondary memory
        *   Comprising of Magnetic Disk, Optical Disk, Magnetic Tape.
    *   Internal memory or Primary memory
        *   Comprising of Main Memory, Cache Memory & CPU registers, accessible by the processor. 
*   Characteristics of Memory Hierarchy
    *   Capacity
        *   The global volume of information that the memory can contain.
        *   Most upper(Registers) have the least capacity, the capacity increases as we move to the bottom level of the hierarchy (lower level have more capacity).  
    *   Access Time
        *   The time interval between the read and write requests and the availability of the data.
        *   Most upper(Registers) have the least access time, the access time increases as we move to the bottom level of the hierarchy (lower level need more access time).
    *   Performance
        *   In the past, the computer system was designed without Memory Hierarchy design, so the speed gap between the CPU registers and main memory is painfully slow. This results in a lower performance of the computer system so we make the enhancement in the form of Memory Hierarchy Design.
    *   Cost per bit
        *   Higher-level(Registers) is more expensive than the lower level.


## Memory Hierarchy Design



*   Registers
    *   Static RAM or SRAM in the processor of the computer used for holding the data word, typically 64 or 128 bits.
*   Cache Memory
    *   Hold chunk of data which frequently used from main memory.
    *   It can be found inside the processor however it can be another IC (integrated circuit) that is separated into levels but this rarely the case.
    *   A processor with a single-core will have two or more cached levels.
    *   Multi-core processors will have three, 2 levels for each core and one level is shared.
*   Main Memory
    *   The memory unit in the CPU, the main storage unit of the computer.
    *   Used for storing the data form operations of the computer.
    *   Made up of RAM and ROM
*   Magnetic Disks
    *   A storage device that uses a magnetization process to write, rewrite, and access data.
    *   Covered with a magnetic coat.
    *   Storing data in the form of tracks, spots, and sectors.
    *   E.g Hard disk and floppy disks.
*   Optical Disk
    *   A storage medium from which data is read and written by lasers.
    *   Support one of three recording types
        *   Read-only (CD and CD-ROM)
        *   Recordable (Write-once) (CD-R) 
        *   Re-recordable (rewritable) (CD-RW)
*   Magnetic Tape
    *   Magnetic recording with a slender magnetizable cover, plastic film.
    *   Mainly used to back up huge data


## Principle of locality (Locality of reference)



    *   The tendency of a processor to access the same set of memory locations repetitively over a short period of time.
    *   **Type of locality**
        *   Temporal locality
            *   If a particular memory location is referenced, it is likely to be referenced again soon.
        *   Spatial locality
            *   If a particular storage location is referenced, it is likely that other memory nearby will be referenced soon.
        *   Branch locality
            *   If there are only a few possible alternatives for the prospective part of the path in the spatial-temporal coordinate space.
            *   Loop has a simple structure or the possible outcome of a small system of conditional branching instructions is restricted to a small set of possibility
            *   Not a spatial locality because there are few possibilities that can be located far away from each other.
        *   Equidistant locality
            *   Halfway between the spatial locality and the branch locality.
            *   Consider a loop accessing locations in an equidistant pattern, a path in the spatial-temporal coordinate space is a dotted line.


## Spatial and temporal locality usage

	Memory hierarchy



*   Hardware optimization that takes benefits from the temporal locality and spatial locality.
*   Copy frequently used data and its neighbors from disk to main memory
*   Copy frequently used data and its neighbors from main memory to cache


## Caches



*   Fast and small memory that contains part of the data from the main memory.
*   Higher performance for the computer is possible via caching because of program locality


## Operation



*   Cache hit
    *   Data that the processor need is in the cache.
*   Cache miss
    *   Cold (compulsory) miss
        *   Accessing memory block for the first time.
    *   Conflict miss
        *   Occur when different addresses map to the same cache block.
    *   Capacity miss
        *   Occur when the amount of data referenced by a program exceeds cache capacity.


## Type of cache



*   Direct-mapped cache
    *   Memory location maps to one cache block.
*   Fully associative cache
    *   Memory location can be in any cache block.
    *   Needs to search all entries to determine cache hit or cache miss
*   N-way-set-associative cache
    *   Most common cache implementations.
    *   Memory addresses can be stored in any N block of the cache.


## Writing policies



*   Write-through
    *   Update to main memory in every cache write.
    *   Makes store instructions slow because it has to write to the main memory in every cache write.
*   Write-back
    *   Only write to the main memory when that memory in the cache got replaced or got removed.


## Calculate bit



*   Index bit
    *   X blocks = 2^n blocks. n is a number of bit for index
*   Offset bit
    *   X bytes in one block = 2^n bytes of data. n is a number of bit for offset
*   Tag bit
    *   X-bit address - Y offset bit - Z index bit = N bits for tag
*   Total cache capacity
    *   Number of blocks * bytes per block
*   Bits per row
    *   Block size (Bit) + tag bits + dirty bit
        *   Dirty bit
            *   Use to indicate that the corresponding block of memory has been modified or not.


## Example


<table>
  <tr>
   <td>Address size (Bits)
   </td>
   <td>Cache size
   </td>
   <td>Block size
   </td>
   <td>Tag bits
   </td>
   <td>Index bits
   </td>
   <td>Offset bits
   </td>
  </tr>
  <tr>
   <td>32
   </td>
   <td>32KiB (32768 B)
   </td>
   <td>16B
   </td>
   <td>17
   </td>
   <td>11
   </td>
   <td>4 (2^4) 
   </td>
  </tr>
</table>


Bits per row



*   (16 * 8) + 17 + 1 = 146


## Reference

[Memory hierarchy](https://en.wikipedia.org/wiki/Memory_hierarchy). Wikipedia. Retrieved 12 June 2020.

[Memory Hierarchy in Computer Architecture](https://www.elprocus.com/memory-hierarchy-in-computer-architecture/). Elprocus. Retrieved 13 June 2020.

[Memory Hierarchy Design and its Characteristics](https://www.geeksforgeeks.org/memory-hierarchy-design-and-its-characteristics/). Geeks for Geeks. Retrieved 13 June 2020.

[Optical disc](https://en.wikipedia.org/wiki/Optical_disc). Wikipedia. Retrieved 13 June 2020.

[What is Optical Disk?](https://www.webopedia.com/TERM/O/optical_disk.html). Webopedia. Retrieved 13 June 2020.

[Locality of reference](https://en.wikipedia.org/wiki/Locality_of_reference#:~:text=In%20computer%20science%2C%20locality%20of,a%20short%20period%20of%20time.&text=Locality%20is%20a%20type%20of%20predictable%20behavior%20that%20occurs%20in%20computer%20systems.). Wikipedia. Retrieved 13 June 2020.

[Cache (computing)](https://en.wikipedia.org/wiki/Cache_(computing)). Wikipedia. Retrieved 13 June 2020.

Victoria, Cherkasova. [What are 3 types of cache memory](https://www.student-circuit.com/learning/year3/embedded-systems/what-are-three-types-of-cache-memory/). Student Circuit. Retrieved 14 June 2020.

"Threads" by Paruj Ratanaworabhan