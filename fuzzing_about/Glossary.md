# Glossary

Naming things is hard, so this page tries to reduce confusion around fuzzing-related terminology.

## Corpus

Or **test corpus**, or **fuzzing corpus**.<BR>

A set of [test inputs](#test-input). In most contexts, it refers to a set of minimal test inputs that generate maximal code coverage.

## Cross-pollination

The term is taken from botany, where one plant pollinates a plant of another variety.

In fuzzing, cross-pollination means using a corpus for one [fuzz target](#fuzz-target) to expand a [corpus](#corpus) for another fuzz target.
For example, if there are two libraries that process the same common data format, it is often benefitial to cross-pollinate their respective corpora.

## Dictionary

A file which specifies interesting tokens for a [fuzz target](#fuzz-target). Most [fuzzing engines](#fuzzing-engine) support dictionaries, and will adjust their mutation strategies to process these tokens together.

## Fuzz Target

Or **Target Function**, or **Fuzzing Target Function**, or **Fuzzing Entry Point**.<BR> A function to which we apply fuzzing. A [specific signature](http://libfuzzer.info#fuzz-target) is required for OSS-Fuzz.

Examples: [openssl](https://github.com/openssl/openssl/blob/master/fuzz/x509.c),
[re2](https://github.com/google/re2/blob/master/re2/fuzzing/re2_fuzzer.cc),
[SQLite](https://www.sqlite.org/src/artifact/ad79e867fb504338).

## Fuzzer

The most overloaded term and used in a variety of contexts, which makes it bad.

Sometimes, "Fuzzer" is referred to a [fuzz target](#fuzz-target), a [fuzzing engine](#fuzzing-engine), a [mutation engine](#mutation-engine), a [test generator](#test-generator) or a [fuzzer build](#fuzzer-build).

## Fuzzer Build

A build that contains all the fuzz targets for a given project, which is run with a specific fuzzing engine, in a specific build mode (e.g. with enabled/disabled assertions), and optionally combined with a sanitizer.

In [OSS-Fuzz](https://google.github.io/oss-fuzz/), it is also known as a [job type](https://google.github.io/oss-fuzz/reference/glossary/#job-type).

## Fuzzing Engine

A tool that tries to find interesting inputs for a [fuzz target](#fuzz-target) by executing it.

Examples: [libFuzzer](http://libfuzzer.info), [AFL](lcamtuf.coredump.cx/afl/), [honggfuzz](https://github.com/google/honggfuzz), etc.

See related terms [Mutation Engine](#mutation-engine) and [Test Generator](#test-generator).

## Mutation Engine

A tool that takes a set of testcases as input and creates their mutated versions.

It is just a generator and does not feed the mutations to [fuzz target](#fuzz-target).

Example: [radamsa](https://github.com/aoh/radamsa) (a generic test mutator).

## Reproducer

Or **Test Case**.<BR>

A [test input](#test-input) that can be used to reproduce a bug when processed by a fuzz target.

## [Sanitizer](https://github.com/google/sanitizers)

A [dynamic testing](https://en.wikipedia.org/wiki/Dynamic_testing) tool that can detect bugs during program execution.

Examples:
[ASan](http://clang.llvm.org/docs/AddressSanitizer.html),
[DFSan](http://clang.llvm.org/docs/DataFlowSanitizer.html),
[LSan](http://clang.llvm.org/docs/LeakSanitizer.html),
[MSan](http://clang.llvm.org/docs/MemorySanitizer.html),
[TSan](http://clang.llvm.org/docs/ThreadSanitizer.html),
[UBSan](http://clang.llvm.org/docs/UndefinedBehaviorSanitizer.html).

## Seed Corpus

A small initial [corpus](#corpus) prepared with the intent of providing initial coverage for fuzzing. Rather than being created by the fuzzers themselves, seed corpora are often prepared from existing test inputs or may be hand-crafted to provide interesting coverage. They are often checked into source alongside [fuzz targets](#fuzz-target).

## Test Generator

A tool that generates testcases from scratch according to some rules or grammar.

Examples:
[csmith](https://embed.cs.utah.edu/csmith/) (a test generator for C language),
[cross_fuzz](http://lcamtuf.coredump.cx/cross_fuzz/) (a cross-document DOM binding test generator).

## Test Input

A sequence of bytes that is used as input to a [fuzz target](#fuzz-target).

Typically, a test input is stored in a separate file.
