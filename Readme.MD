# BC break table for php

The following tables will give you a short overview if changes in the following parts are allowed or if they result in a BC break.


## Modification on classes

|                | add method* | remove method* | make abstract | remove abstract | make final | remove final | add interface | remove interface |
|----------------|-------------|----------------|---------------|-----------------|------------|--------------|---------------|------------------|
| class          |             |                |               |                 |            |              |               |                  |
| abstract class |             |                |               |                 |            |              |               |                  |
| final class    |             |                |               |                 |            |              |               |                  |
| interface      |             |                |               |                 |            |              |               |                  |
| trait          |             |                |               |                 |            |              |               |                  |

* only public or protected methods. Private methods will never result in a BC break.

## Modification on methods

### Normal class

|           |  make abstract | remove abstract | make final | remove final | increase visibility | decrease visiblity | add parameter | add optional parameter | remove parameter | remove optional parameter | change signature |
|-----------|----------------|-----------------|------------|--------------|---------------------|--------------------|---------------|------------------------|------------------|---------------------------|------------------|
| public    |                |                 |            |              |                     |                    |               |                        |                  |                           |                  |
| protected |                |                 |            |              |                     |                    |               |                        |                  |                           |                  |
| private   |                |                 |            |              |                     |                    |               |                        |                  |                           |                  |

### Abstract class

|           |  make abstract | remove abstract | make final | remove final | increase visibility | decrease visiblity | add parameter | add optional parameter | remove parameter | remove optional parameter | change signature |
|-----------|----------------|-----------------|------------|--------------|---------------------|--------------------|---------------|------------------------|------------------|---------------------------|------------------|
| public    |                |                 |            |              |                     |                    |               |                        |                  |                           |                  |
| protected |                |                 |            |              |                     |                    |               |                        |                  |                           |                  |
| private   |                |                 |            |              |                     |                    |               |                        |                  |                           |                  |

### Final class

|           |  make abstract | remove abstract | make final | remove final | increase visibility | decrease visiblity | add parameter | add optional parameter | remove parameter | remove optional parameter | change signature |
|-----------|----------------|-----------------|------------|--------------|---------------------|--------------------|---------------|------------------------|------------------|---------------------------|------------------|
| public    |                |                 |            |              |                     |                    |               |                        |                  |                           |                  |
| protected |                |                 |            |              |                     |                    |               |                        |                  |                           |                  |
| private   |                |                 |            |              |                     |                    |               |                        |                  |                           |                  |

### Interface

|           |  make abstract | remove abstract | make final | remove final | increase visibility | decrease visiblity | add parameter | add optional parameter | remove parameter | remove optional parameter | change signature |
|-----------|----------------|-----------------|------------|--------------|---------------------|--------------------|---------------|------------------------|------------------|---------------------------|------------------|
| public    |                |                 |            |              |                     |                    |               |                        |                  |                           |                  |
| protected |                |                 |            |              |                     |                    |               |                        |                  |                           |                  |
| private   |                |                 |            |              |                     |                    |               |                        |                  |                           |                  |


### Trait

|           |  make abstract | remove abstract | make final | remove final | increase visibility | decrease visiblity | add parameter | add optional parameter | remove parameter | remove optional parameter | change signature |
|-----------|----------------|-----------------|------------|--------------|---------------------|--------------------|---------------|------------------------|------------------|---------------------------|------------------|
| public    |                |                 |            |              |                     |                    |               |                        |                  |                           |                  |
| protected |                |                 |            |              |                     |                    |               |                        |                  |                           |                  |
| private   |                |                 |            |              |                     |                    |               |                        |                  |                           |                  |

