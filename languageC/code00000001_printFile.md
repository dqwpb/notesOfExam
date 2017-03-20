# 一個基本的讀檔程式

`main.c`

```c
#include <stdlib.h>
#include <stdio.h>

int line = 0, page = 0;

void do_heading(char *filename);

int main(int argv, char *argc[]) {
    char buffer[256];
    FILE *fp;

    if (argv < 2) {
        fprintf(stderr, "\nProper Usage is: ");
        fprintf(stderr, "\n\nprint_it filename.ext\n");
        return(1);
    }

    if ( (fp = fopen(argc[1], "r")) == NULL ) {
        fprintf(stderr, "Error opening file, %s!", argc[1]);
        return(1);
    }

    page = 0;
    line = 1;
    do_heading(argc[1]);

    while ( fgets(buffer, 256, fp) != NULL ) {
        if (line % 55 == 0) {
            do_heading(argc[1]);
        }
        fprintf(stdout, "%4d:\t%s", line++, buffer);
    }

    fprintf(stdout, "\f");
    fclose(fp);

    return 0;
}

void do_heading(char *filename) {
    page++;
    if (page > 1) {
        fprintf(stdout, "\f");
    }
    fprintf(stdout, "Page: %d, %s\n\n", page, filename);
}
```

`alice59.txt`

```txt
ALICE'S ADVENTURES IN WONDERLAND

                          Lewis Carroll

               THE MILLENNIUM FULCRUM EDITION 3.0




                            CHAPTER I

                      Down the Rabbit-Hole


  Alice was beginning to get very tired of sitting by her sister
on the bank, and of having nothing to do:  once or twice she had
peeped into the book her sister was reading, but it had no
pictures or conversations in it, `and what is the use of a book,'
thought Alice `without pictures or conversation?'

  So she was considering in her own mind (as well as she could,
for the hot day made her feel very sleepy and stupid), whether
the pleasure of making a daisy-chain would be worth the trouble
of getting up and picking the daisies, when suddenly a White
Rabbit with pink eyes ran close by her.

  There was nothing so VERY remarkable in that; nor did Alice
think it so VERY much out of the way to hear the Rabbit say to
itself, `Oh dear!  Oh dear!  I shall be late!'  (when she thought
it over afterwards, it occurred to her that she ought to have
wondered at this, but at the time it all seemed quite natural);
but when the Rabbit actually TOOK A WATCH OUT OF ITS WAISTCOAT-
POCKET, and looked at it, and then hurried on, Alice started to
her feet, for it flashed across her mind that she had never
before seen a rabbit with either a waistcoat-pocket, or a watch to
take out of it, and burning with curiosity, she ran across the
field after it, and fortunately was just in time to see it pop
down a large rabbit-hole under the hedge.

  In another moment down went Alice after it, never once
considering how in the world she was to get out again.

  The rabbit-hole went straight on like a tunnel for some way,
and then dipped suddenly down, so suddenly that Alice had not a
moment to think about stopping herself before she found herself
falling down a very deep well.

  Either the well was very deep, or she fell very slowly, for she
had plenty of time as she went down to look about her and to
wonder what was going to happen next.  First, she tried to look
down and make out what she was coming to, but it was too dark to
see anything; then she looked at the sides of the well, and
noticed that they were filled with cupboards and book-shelves;
here and there she saw maps and pictures hung upon pegs.  She
took down a jar from one of the shelves as she passed; it was
labelled `ORANGE MARMALADE', but to her great disappointment it
was empty:  she did not like to drop the jar for fear of killing
somebody, so managed to put it into one of the cupboards as she
fell past it.
```

`.\main.out alice59.txt`

```txt
Page: 1, alice59.txt

   1:   ALICE'S ADVENTURES IN WONDERLAND
   2:
   3:                             Lewis Carroll
   4:
   5:                  THE MILLENNIUM FULCRUM EDITION 3.0
   6:
   7:
   8:
   9:
  10:                               CHAPTER I
  11:
  12:                         Down the Rabbit-Hole
  13:
  14:
  15:     Alice was beginning to get very tired of sitting by her sister
  16:   on the bank, and of having nothing to do:  once or twice she had
  17:   peeped into the book her sister was reading, but it had no
  18:   pictures or conversations in it, `and what is the use of a book,'
  19:   thought Alice `without pictures or conversation?'
  20:
  21:     So she was considering in her own mind (as well as she could,
  22:   for the hot day made her feel very sleepy and stupid), whether
  23:   the pleasure of making a daisy-chain would be worth the trouble
  24:   of getting up and picking the daisies, when suddenly a White
  25:   Rabbit with pink eyes ran close by her.
  26:
  27:     There was nothing so VERY remarkable in that; nor did Alice
  28:   think it so VERY much out of the way to hear the Rabbit say to
  29:   itself, `Oh dear!  Oh dear!  I shall be late!'  (when she thought
  30:   it over afterwards, it occurred to her that she ought to have
  31:   wondered at this, but at the time it all seemed quite natural);
  32:   but when the Rabbit actually TOOK A WATCH OUT OF ITS WAISTCOAT-
  33:   POCKET, and looked at it, and then hurried on, Alice started to
  34:   her feet, for it flashed across her mind that she had never
  35:   before seen a rabbit with either a waistcoat-pocket, or a watch to
  36:   take out of it, and burning with curiosity, she ran across the
  37:   field after it, and fortunately was just in time to see it pop
  38:   down a large rabbit-hole under the hedge.
  39:
  40:     In another moment down went Alice after it, never once
  41:   considering how in the world she was to get out again.
  42:
  43:     The rabbit-hole went straight on like a tunnel for some way,
  44:   and then dipped suddenly down, so suddenly that Alice had not a
  45:   moment to think about stopping herself before she found herself
  46:   falling down a very deep well.
  47:
  48:     Either the well was very deep, or she fell very slowly, for she
  49:   had plenty of time as she went down to look about her and to
  50:   wonder what was going to happen next.  First, she tried to look
  51:   down and make out what she was coming to, but it was too dark to
  52:   see anything; then she looked at the sides of the well, and
  53:   noticed that they were filled with cupboards and book-shelves;
  54:   here and there she saw maps and pictures hung upon pegs.  She

Page: 2, alice59.txt

  55:   took down a jar from one of the shelves as she passed; it was
  56:   labelled `ORANGE MARMALADE', but to her great disappointment it
  57:   was empty:  she did not like to drop the jar for fear of killing
  58:   somebody, so managed to put it into one of the cupboards as she
  59:   fell past it.
```
