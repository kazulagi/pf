### plantFEM standard library (std)

In this section, we will use plantFEM for basic programming before we get into plant and soil simulations. First, let's write a Hello world program, a program that outputs text.


[![Hello, world!](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1XahUY6xCN0Jj045HMmL8teuMAdj-hmjZ?usp=sharing)


```fortran

! Activate the plantfem library.
use plantfem

! Disables implicit type declarations
implicit none

! Print "Hello, world" to the terminal
call print("Hello, world")

! End the program.
end

```

- output:

```shell

Hello, world

```

Next, let's output "hello hello hello hello hello". If we do the same thing as before, we can create a program that looks like this


```fortran

! Activate the plantfem library.
use plantfem

! Disables implicit type declarations
implicit none

! Print "Hello, world" to the terminal
call print("helo hello hello hello hello")

! End the program.
end

```


- output:

```shell

helo hello hello hello hello

```

In plantFEM, the string_ type can be used to process strings. If we write this example using the string_type, it will look like this.



[![Hello, world!](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1CTappBDBAVMNzjN1CX-Tj8DKzZ8OZbix?usp=sharing)

```fortran
use plantfem
implicit none

! Create a string-type variable named "word".
type(String_) :: word

word = "hello "

! Add "hello " in the end of the word.
word = word + "hello "

word = word + "hello "

word = word + "hello "

word = word + "hello "

call print(word)

end
```

- output:

```shell

helo hello hello hello hello

```


Here, the string "hello" is followed by one "hello" after another. Since this is a repetitive task, it can be written more simply by using a do loop.

```fortran

use plantfem
implicit none

! Create a string-type variable named "word"
type(String_) :: word

! This "i"  is defined as a 32-bit integer variable. 
integer(int32) :: i

! Input "hello " into the variable "word"
word = "hello "

! Repeat four times, where i is changes from 1 to 4
do i=1, 4
    word = word + "hello "
enddo

call print(word)

end

```

- output:

```shell

helo hello hello hello hello

```

