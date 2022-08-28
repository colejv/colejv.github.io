# Incorporate Fuzzing Into Your CI/CD Pipeline

Fuzzing should be incorporated into your existing CI/CD pipeline that builds, tests, and deploys your software. Adding fuzz tests in your CI/CD
pipeline will help ensure that any bugs introduced in that changeset are caught. Fuzz tests can run parallel to other tests, such as unit tests. 
This fuzzing step is not a gating factor for the pipeline since fuzzing is meant to run continuously and is unsuitable to be time-boxed. Please
note that even though fuzzing should not be a gated step within the CI/CD pipeline, it may be necessary to address some issues promptly. 

Some fuzzers, such as [libFuzzer](https://llvm.org/docs/LibFuzzer.html), stop when a bug is found and cannot continue until the bug is fixed. In these cases, it is essential to run the
fuzzer continually so that, as soon as the bug is fixed, the fuzzer can continue to run and traverse paths in the code that were previously
unexplored. By using this method in combination with [fuzzing frameworks](https://safecode.org/blog/focus-on-fuzzing-fuzzing-engines-and-services/) like [clusterfuzz](https://google.github.io/clusterfuzz/), a ticket created by the framework can be automatically
closed when the changeset fixes the problem. 

[OSS-Fuzz](https://github.com/google/oss-fuzz) is an example of an implementation of running a fuzzer this way. The target is constantly synced from the git repository through OSS-Fuzz
and new versions are uploaded to the storage bucket. OSS-Fuzz also includes Clusterfuzz, which monitors this bucket for new versions, downloads
them, and then fuzzes them when it finds them. A bug is automatically reported to the developers by email when an issue is created in the issue
tracker. 
