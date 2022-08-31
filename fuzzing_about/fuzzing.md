# What is Fuzzing or Fuzz Testing?

Fuzzing, commonly referred to as fuzz testing, is a method for identifying any design or security 
issues in an application by supplying unexpected, erroneous, or invalid information as inputs to the 
target system. With the aid of automated testing tools, fuzzing is done by injecting random values 
into various system or web application inputs and monitoring the response. Malformed inputs are 
injected into the target system and it is monitored for any unusual behavior, such as crashes, 
memory leaks, information leakage, or other security issues. Fuzzing aims to detect known, unknown,
and zero-day vulnerabilities.

> Software Fuzzing is the process of repeatedly executing software with inputs designed to be 
> syntactically or semantically malformed to isolate bugs and vulnerabilities.
> 
Prof. Barton Miller from the University of Wisconsin made the initial discovery of the fuzzing 
technology in the 1980s. During a storm, Miller saw substantial signal interference while 
accessing a UNIX system over a dial-up network. The tampering eventually caused a collision.
Miller later had his students reenact his experiment by simulating his experience with a fuzz
generator and hammering UNIX systems with noise to see whether they would crash. From then on
forward, fuzzing has developed into a well-acclaimed method for assessing the reliability of
software and applications.

> From: Barton Miller  
> Sent: Wednesday, February 16, 2005 4:39 AM  
> To: Shawn Hernan  
> Subject: Re: origins of the term "fuzz"
> 
> Thanks for the note. As far as I know, I coined the term.
> 
> The original work was inspired by being logged on to a modem during a storm with lots of line noise. And the line noise was generating junk characters that seemingly was causing programs to crash. The noise suggested the term "fuzz".
> 
> --bart miller

Fuzzing is widely recognized within both industry and the Department of Defense (DoD) as a valuable
technique for improving software security, robustness, and safety, and has become an integral
part of some of the best-known secure Software Development Life Cycle (SDLC) frameworks.

This testing methodology can be combined with other established testing methods, including static
analysis, dynamic analysis, symbolic execution, and the use of formal methods for verification of
software correctness, security, and reliability. The primary objective of fuzzing is to find faults and
exploitable security flaws in the target application that are outside the purview of manual human
testing and even targeted automated test cases.

# Benefits of Software Fuzzing

The practice of software fuzzing possesses many unique features that make it especially
attractive for identifying defects and exploitable vulnerabilities.

- There are no false positives. A bug is a bug.
- Fuzzing easily identifies the exact input or sequence of steps needed to reproduce the
defect.
- Fuzzing can be performed directly on delivered software. Even when source code isn’t
provided, fuzzing can always be done.
- Software fuzzers can be integrated as a part of a Continuous Integration/Continuous
Deployment (CI/CD) development or Software Assurance pipeline to provide cyber test
coverage over the full life cycle.
- Once integrated, fuzz testing serves as a low-effort testing methodology and is ideal for
general-purpose regression testing.

# How is Fuzzing Performed?

Before software can be fuzzed, special “glue” software called a fuzzing harness must be
constructed to allow the fuzzer to drive the inputs to the application. The harness is typically
written in the same language supported by the fuzzer. With the fuzzing harness in place, the
target software then must be executed in an environment that mirrors a realistic deployment.
For software targeting embedded microprocessors, this can be performed on general compute
hardware with the use of emulation tools such as QEMU, Unicorn, and Ghidra.

Careful consideration must also be given to the fuzzer or fuzzers used to perform testing. No
single fuzzer outperforms another since various fuzzers possess different capabilities and
produce varying results even on the same binary. While commercial fuzzers are available, many
open source fuzzers also exist for a variety of languages and are mature enough to integrate
into DevSecOps pipelines. Examples include afl++, libfuzzer, honggfuzz, gofuzz, atheris, and
cargo-fuzz.
