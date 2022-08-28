# How Long Should I Fuzz?

Technically speaking, there is no “done” when it comes to fuzzing. This gives rise to the question of when to stop fuzzing from a release
planning perspective. With “[Coverage Guided Fuzzing](https://safecode.org/blog/focus-on-fuzzing-a-closer-look-at-coverage-guided-fuzzing/)” you could
technically stop when there is sufficient coverage of your software. At a minimum, you want to make sure all untrusted interfaces and untrusted inputs
have been sufficiently fuzzed prior to a release. 

The simple approach of fuzzing after feature-complete, typically within the validation phase, applies to the traditional waterfall or spiral
development methodology. However, what about fuzzing in an Agile or a DevOps development model?
