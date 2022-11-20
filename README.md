![pointfrip](https://raw.githubusercontent.com/pointfree-interpreter/pointfrip/main/images/pflogo.png) \
**pointfree interpreter with instance variables and classes, in lazarus**
#
![eye](https://raw.githubusercontent.com/pointfree-interpreter/pointfrip/main/images/eye.png)
![tahoma-fact](https://raw.githubusercontent.com/pointfree-interpreter/pointfrip/main/images/tahoma-fact.png)

**Combinator Language** like [FP](https://dl.acm.org/doi/pdf/10.1145/359576.359579) from John Backus

    ip ≡ (+ \) ° (* aa) ° trans ° ee
    eq0  ≡ id=0
    sub1 ≡ id-1
    fact ≡ eq0 → 1; id*fact°sub1

for example: generation of numbers with iota

    iota == [1]°((ispos°[0])->*(pred°[0]),([0],[1]),)°id,(),
    iota ° 10
    --> (1 ; 2 ; 3 ; 4 ; 5 ; 6 ; 7 ; 8 ; 9 ; 10 ;)

possibility to work with tables/instance-variables like in [trivia](https://esolangs.org/wiki/FP_trivia)

    (#beta & #alpha & #gamma & #delta & "US") ° (delta:="K") ° '("A" alpha "B" beta "C" gamma)
    --> "BACKUS"

defining classes and using objects

    constr == .. { list
                   [head] == head ° pop
                   [tail] == tail dip
                   [comma] == (top°[0]) obj [1],pop°[0]
                   [reverse] == reverse dip  // method
                 }
    --> ( )
    
    reverse ° (constr :: A;B;C;)             // reverse == [reverse] fn ...
    --> (constr :: C ; B ; A ;)

side-effects used in [installer.exe](https://github.com/pointfree-interpreter/pointfrip/tree/main/installer)

    ((#draco loadtext)°(draco:=corepath & "drache.pf") eff 'io)>>(it showinfo)>>(#draco run)>>()


[Example](https://github.com/pointfree-interpreter/pointfrip/blob/main/images/progopedia-drache.png) \
[Quickinfo.pdf](https://github.com/pointfree-interpreter/pointfrip/blob/main/examples/documents/quickinfo.pdf) \
[Reference.pdf](https://github.com/pointfree-interpreter/pointfrip/blob/main/examples/documents/reference.pdf) \
[Website](https://pointfree-interpreter.github.io/)

### [Getting Started ...](https://github.com/pointfree-interpreter/pointfrip/blob/main/Getting%20Started.md)

##
\
![heise Download](https://www.heise.de/software/icons/download_logo1.png)\
Virus checked with 40 virus scanners from heise.de:  [download](https://www.heise.de/download/product/fp-trivia)


##
### [Can you write any function in point-free notation?](https://www.reddit.com/r/haskell/comments/o4zyz5/can_you_write_any_function_in_pointfree_notation/)
![friedbrice](https://raw.githubusercontent.com/pointfree-interpreter/pointfrip/main/images/friedbrice24.png)


This is a Red and λ-Red language: [Closed applicative languages](http://dirkgerrits.com/publications/john-backus.pdf#section.8)

