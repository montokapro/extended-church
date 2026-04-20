This is a testing ground for extended-church notation, as well as the behavior of HVM2.

## Hypothesis

I believe that symmetric interaction nets can encode numbers like rationals and even complex numbers by extending church notation such that roots are represented by the construction combinator.

However, I have a lot to learn about interaction nets and the HVM evaluator before I can confidently assert this.

## Mapping

I've lifted the lambda mapping from. I hope I am applying this via HVM correctly!
https://zicklag.katharos.group/blog/interaction-nets-combinators-calculus/

```
// \x.M
@lamXofM = (@x @m)
// (M N)
@appMofN = mn & @m ~ (@n mn)
```

I then use church notation to guide me toward this mapping onto interaction nets.

```
// a = \log_b(c)
@logBofC = a & a ~ (@b @c)
// b = \sqrt[a](c) or (c^(1/a))
@rootAofC = b & @a ~ (b @c)
// c = b ^ a
@expBtoC = c & @a ~ (@b c)
```

## Tooling

```
cargo install hvm
```

## Evaluation

```
hvm run FILENAME.hvm
```
