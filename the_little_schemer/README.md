# The Little Schemer Standard Advisory

Summary: Herein we detail details that are good to know about practicing The Little Schemer.

## Tips

- Use [DrRacket](https://www.racket-lang.org)
- Copy/paste this code into the DrRacket GUI top-level:


```
#lang scheme

(define atom?
  (lambda (x)
    (and (not (pair? x)) (not (null? x)))))

(define lat?
  (lambda (l)
    (cond
      ((null? l) #t)
      ((atom? (car l))(lat? (cdr l)))
      (else #f))))

(define member?
  (lambda (a lat)
    (cond
      ((null? lat) #f)
      (else (or (eq? (car lat) a)
                (member? a (cdr lat)))))))

(define add1
  (lambda (n)
    (+ n 1)))

(define sub1
  (lambda (n)
    (- n 1)))
```

- Your GUI should look like this at the start:

![Starting GUI should look like this](./starting_racket_gui)

# Study Group

I'm tentatively scheduling a Little Schemer study group to meet every Sunday starting 01/01/2023 around 6:30 PM EST. Study members can be on any chapter or material in the book. This time will be for chit-chat, mentoring, and possibly pair programming. Discuss questions & intuitions!

I'm making a directory for study notes, tips, etc. I'd appreciate it if everyone could submit a weekly log. Beginners, novices, experts... anybody! Every contribution is valuable, even if it's a rough estimate of how many pages you did & how long it took, or one or two lines of sample code. :)
