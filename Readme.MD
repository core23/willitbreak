# BC break table for php
 
The following tables will give you a short overview which changes are allowed in your code or if they result in a BC break.
 
## Modification on classes
 
| type           | add method | remove method  | add method stub | remove method stub | make abstract | remove abstract | make final | remove final | add interface | remove interface |
|----------------|------------|----------------|-----------------|--------------------|---------------|-----------------|------------|--------------|---------------|------------------|
| class          | ok         | BREAK          | -               | -                  | BREAK         | -               | BREAK      | ok           | ok            | ok               |
| abstract class | ok         | BREAK          | BREAK           | BREAK              | -             | ok              | -          | -            | depends*1     | ok               |
| final class    | ok         | BREAK          | -               | -                  | -             | -               | -          | ok           | ok            | ok               |
| interface      | BREAK      | -              | BREAK           | ok                 | -             | -               | -          | -            | BREAK         | ok               |
| trait          | BREAK      | BREAK          | BREAK           | ok                 | -             | -               | -          | -            | -             | -                |
 
Adding / Removing methods for private methods are always alowed.
 
## Modification on methods
 
### Normal class
 
| method type     | make final | remove final | increase visibility | decrease visiblity | add parameter | add optional parameter | remove parameter | remove optional parameter | change signature |
|-----------------|------------|--------------|---------------------|--------------------|---------------|------------------------|------------------|---------------------------|------------------|
| final public    | -          | ok           | -                   | BREAK              | BREAK         | ok                     | BREAK            | BREAK                     | BREAK            |
| final protected | -          | ok           | ok                  | BREAK              | BREAK         | ok                     | BREAK            | BREAK                     | BREAK            |
| public          | BREAK      | ok           | -                   | BREAK              | BREAK         | BREAK                  | BREAK            | BREAK                     | BREAK            |
| protected       | BREAK      | ok           | BREAK               | BREAK              | BREAK         | BREAK                  | BREAK            | BREAK                     | BREAK            |
| private         | -          | -            | ok                  | -                  | ok            | ok                     | ok               | ok                        | ok               |
 
### Abstract class
 
| method type        | make abstract | remove abstract | make final | remove final | increase visibility | decrease visiblity | add parameter | add optional parameter | remove parameter | remove optional parameter | change signature |
|--------------------|---------------|-----------------|------------|--------------|---------------------|--------------------|---------------|------------------------|------------------|---------------------------|------------------|
| final public       | -             | -               | -          | ok           | -                   | BREAK              | BREAK         | ok                     | BREAK            | BREAK                     | BREAK            |
| final protected    | -             | -               | -          | ok           | ok                  | BREAK              | BREAK         | ok                     | BREAK            | BREAK                     | BREAK            |
| abstract public    | -             | depends*1       | -          | -            | BREAK               | BREAK              | BREAK         | ok                     | BREAK            | BREAK                     | BREAK            |
| abstract protected | -             | depends*1       | -          | -            | BREAK               | BREAK              | BREAK         | ok                     | BREAK            | BREAK                     | BREAK            |
| public             | BREAK         | -               | BREAK      | -            | -                   | BREAK              | BREAK         | BREAK                  | BREAK            | BREAK                     | BREAK            |
| protected          | BREAK         | -               | BREAK      | -            | BREAK               | BREAK              | BREAK         | BREAK                  | BREAK            | BREAK                     | BREAK            |
| private            | -             | -               | -          | -            | ok                  | -                  | ok            | ok                     | ok               | ok                        | ok               |
 
### Final class
 
| method type | increase visibility | decrease visiblity | add parameter | add optional parameter | remove parameter | remove optional parameter | change signature |
|-------------|---------------------|--------------------|---------------|------------------------|------------------|---------------------------|------------------|
| public      | -                   | BREAK              | BREAK         | ok                     | BREAK            | BREAK                     | BREAK            |
| protected   | ok                  | ok                 | ok            | ok                     | ok               | ok                        | ok               |
| private     | ok                  | -                  | ok            | ok                     | ok               | ok                        | ok               |
 
### Interface
 
| method type | add parameter | add optional parameter | remove parameter | remove optional parameter | change signature |
|-------------|---------------|------------------------|------------------|---------------------------|------------------|
| public      | BREAK         | BREAK                  | BREAK            | BREAK                     | BREAK            |
 
 
### Trait
 
| method type        | make abstract | remove abstract | increase visibility | decrease visiblity | add parameter | add optional parameter | remove parameter | remove optional parameter | change signature |
|--------------------|---------------|-----------------|---------------------|--------------------|---------------|------------------------|------------------|---------------------------|------------------|
| abstract public    | -             |                 | -                   |                    |               |                        |                  |                           |                  |
| abstract protected | -             |                 |                     |                    |               |                        |                  |                           |                  |
| public             |               | -               | -                   |                    |               |                        |                  |                           |                  |
| protected          |               | -               |                     |                    |               |                        |                  |                           |                  |
| private            | -             | -               |                     | -                  | ok            | ok                     | ok               | ok                        | ok               |
 
The `final` keyword has no impact to traits, because you can't extend a trait.
 
*1 ok, if you implement all methods
 
