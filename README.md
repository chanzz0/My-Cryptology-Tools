# My-Cryptology-Tools

![GitHub License](https://img.shields.io/github/license/chanzz0/My-Cryptology-Tools?logo=github) ![GitHub repo size](https://img.shields.io/github/repo-size/chanzz0/My-Cryptology-Tools) ![GitHub last commit (by committer)](https://img.shields.io/github/last-commit/chanzz0/My-Cryptology-Tools)

[![C/C++ CI](https://github.com/chanzz0/My-Cryptology-Tools/actions/workflows/c-cpp.yml/badge.svg)](https://github.com/chanzz0/My-Cryptology-Tools/actions/workflows/c-cpp.yml)

Crypto++: free C++ Class Library of Cryptographic Schemes
Version 8.9 - October 1, 2023

Crypto++ Library is a free C++ class library of cryptographic schemes.
Currently the library contains the following algorithms:

                   algorithm type  name

 authenticated encryption schemes  GCM, CCM, EAX, ChaCha20Poly1305 and
                                   XChaCha20Poly1305

        high speed stream ciphers  ChaCha (8/12/20), ChaCha (IETF), Panama, Salsa20,
                                   Sosemanuk, XSalsa20, XChaCha20
    
           AES and AES candidates  AES (Rijndael), RC6, MARS, Twofish, Serpent,
                                   CAST-256
    
                                   ARIA, Blowfish, Camellia, CHAM, HIGHT, IDEA,
                                   Kalyna (128/256/512), LEA, SEED, RC5, SHACAL-2,
              other block ciphers  SIMON (64/128), Skipjack, SPECK (64/128),
                                   Simeck, SM4, Threefish (256/512/1024),
                                   Triple-DES (DES-EDE2 and DES-EDE3), TEA, XTEA

  block cipher modes of operation  ECB, CBC, CBC ciphertext stealing (CTS),
                                   CFB, OFB, counter mode (CTR), XTS

     message authentication codes  BLAKE2s, BLAKE2b, CMAC, CBC-MAC, DMAC, GMAC, HMAC,
                                   Poly1305, Poly1305 (IETF), SipHash, Two-Track-MAC,
                                   VMAC
    
                                   BLAKE2s, BLAKE2b, Keccack (F1600), LSH (256/512),
                   hash functions  SHA-1, SHA-2 (224/256/384/512), SHA-3 (224/256),
                                   SHA-3 (384/512), SHAKE (128/256), SipHash, SM3, Tiger,
                                   RIPEMD (128/160/256/320), WHIRLPOOL
    
                                   RSA, DSA, Deterministic DSA, ElGamal,
          public-key cryptography  Nyberg-Rueppel (NR), Rabin-Williams (RW), LUC,
                                   LUCELG, EC-based German Digital Signature (ECGDSA),
                                   DLIES (variants of DHAES), ESIGN

   padding schemes for public-key  PKCS#1 v2.0, OAEP, PSS, PSSR, IEEE P1363
                          systems  EMSA2 and EMSA5

                                   Diffie-Hellman (DH), Unified Diffie-Hellman (DH2),
            key agreement schemes  Menezes-Qu-Vanstone (MQV), Hashed MQV (HMQV),
                                   Fully Hashed MQV (FHMQV), LUCDIF, XTR-DH
    
      elliptic curve cryptography  ECDSA, Deterministic ECDSA, ed25519, ECNR, ECIES,
                                   ECDH, ECMQV, x25519
    
          insecure or obsolescent  MD2, MD4, MD5, Panama Hash, DES, ARC4, SEAL
algorithms retained for backwards  3.0, WAKE-OFB, DESX (DES-XEX3), RC2,
     compatibility and historical  SAFER, 3-WAY, GOST, SHARK, CAST-128, Square
                            value

Other features include:

  * pseudo random number generators (PRNG): ANSI X9.17 appendix C, RandomPool,
    DARN, VIA Padlock, RDRAND, RDSEED, NIST Hash and HMAC DRBGs
  * password based key derivation functions: PBKDF1 and PBKDF2 from PKCS #5,
    PBKDF from PKCS #12 appendix B, HKDF from RFC 5869, Scrypt from RFC 7914
  * Shamir's secret sharing scheme and Rabin's information dispersal algorithm
    (IDA)
  * fast multi-precision integer (bignum) and polynomial operations
  * finite field arithmetics, including GF(p) and GF(2^n)
  * prime number generation and verification
  * useful non-cryptographic algorithms
      + DEFLATE (RFC 1951) compression/decompression with gzip (RFC 1952) and
        zlib (RFC 1950) format support
      + Hex, base-32, base-64, URL safe base-64 encoding and decoding
      + 32-bit CRC, CRC-C and Adler32 checksum
  * class wrappers for these platform and operating system features (optional):
      + high resolution timers on Windows, Unix, and Mac OS
      + /dev/random, /dev/urandom, /dev/srandom
      + Microsoft's CryptGenRandom or BCryptGenRandom on Windows
  * A high level interface for most of the above, using a filter/pipeline
    metaphor
  * benchmarks and validation testing
  * x86, x64 (x86-64), x32 (ILP32), ARM-32, Aarch32, Aarch64 and Power8
    in-core code for the commonly used algorithms
      + run-time CPU feature detection and code selection
      + supports GCC-style and MSVC-style inline assembly, and MASM for x64
      + x86, x64 (x86-64), x32 provides MMX, SSE2, and SSE4 implementations
      + ARM-32, Aarch32 and Aarch64 provides NEON, ASIMD and ARMv8 implementations
      + Power8 provides in-core AES using NX Crypto Acceleration

The Crypto++ library was originally written by Wei Dai. The library is now
maintained by several team members and the community. You are welcome to use it
for any purpose without paying anyone, but see License.txt for the fine print.

The following compilers are supported for this release. Please visit
http://www.cryptopp.com the most up to date build instructions and porting notes.

  * Visual Studio 2003 - 2022
  * GCC 3.3 - 13.1
  * Apple Clang 4.3 - 12.0
  * LLVM Clang 2.9 - 14.0
  * C++ Builder 2015
  * Intel C++ Compiler 9 - 16.0
  * Sun Studio 12u1 - 12.7
  * IBM XL C/C++ 10.0 - 14.0

*** Important Usage Notes ***

1. If a constructor for A takes a pointer to an object B (except primitive
types such as int and char), then A owns B and will delete B at A's
destruction.  If a constructor for A takes a reference to an object B,
then the caller retains ownership of B and should not destroy it until
A no longer needs it.

2. Crypto++ is thread safe at the class level. This means you can use
Crypto++ safely in a multithreaded application, but you must provide
synchronization when multiple threads access a common Crypto++ object.

*** MSVC-Specific Information ***

To compile Crypto++ with MSVC, open "cryptest.sln" (for MSVC 2003 - 2015)
and build one or more of the following projects:

cryptest Non-DLL-Import Configuration - This builds the full static library
  along with a full test driver.
cryptest DLL-Import Configuration - This builds a static library containing
  only algorithms not in the DLL, along with a full test driver that uses
  both the DLL and the static library.
cryptdll - This builds the DLL. Please note that if you wish to use Crypto++
  as a FIPS validated module, you must use a pre-built DLL that has undergone
  the FIPS validation process instead of building your own.
dlltest - This builds a sample application that only uses the DLL.

The DLL used to provide FIPS validated cryptography. The library was moved
to the CMVP's [Historical Validation List](http://csrc.nist.gov/groups/STM/cmvp/documents/140-1/140val-historical.htm).
The library and the DLL are no longer considered
validated. You should no longer use the DLL.

To use the Crypto++ DLL in your application, #include "dll.h" before including
any other Crypto++ header files, and place the DLL in the same directory as
your .exe file. dll.h includes the line #pragma comment(lib, "cryptopp")
so you don't have to explicitly list the import library in your project
settings. To use a static library form of Crypto++, make the "cryptlib"
project a dependency of your application project, or specify it as
an additional library to link with in your project settings.
In either case you should check the compiler options to
make sure that the library and your application are using the same C++
run-time libraries and calling conventions.

*** DLL Memory Management ***

Because it's possible for the Crypto++ DLL to delete objects allocated
by the calling application, they must use the same C++ memory heap. Three
methods are provided to achieve this.
1.  The calling application can tell Crypto++ what heap to use. This method
    is required when the calling application uses a non-standard heap.
2.  Crypto++ can tell the calling application what heap to use. This method
    is required when the calling application uses a statically linked C++ Run
    Time Library. (Method 1 does not work in this case because the Crypto++ DLL
    is initialized before the calling application's heap is initialized.)
3.  Crypto++ can automatically use the heap provided by the calling application's
    dynamically linked C++ Run Time Library. The calling application must
    make sure that the dynamically linked C++ Run Time Library is initialized
    before Crypto++ is loaded. (At this time it is not clear if it is possible
    to control the order in which DLLs are initialized on Windows 9x machines,
    so it might be best to avoid using this method.)

When Crypto++ attaches to a new process, it searches all modules loaded
into the process space for exported functions "GetNewAndDeleteForCryptoPP"
and "SetNewAndDeleteFromCryptoPP". If one of these functions is found,
Crypto++ uses methods 1 or 2, respectively, by calling the function.
Otherwise, method 3 is used.

*** Linux and Unix-like Specific Information ***

A makefile is included for you to compile Crypto++ with GCC and compatibles.
Make sure you are using GNU Make and GNU ld. The make process will produce
two files, libcryptopp.a and cryptest.exe. Run "cryptest.exe v" for the
validation suite and "cryptest.exe tv all" for additional test vectors.

The makefile uses '-DNDEBUG -g2 -O2' CXXFLAGS by default. If you use an
alternate build system, like Autotools or CMake, then ensure the build system
includes '-DNDEBUG' for production or release builds. The Crypto++ library uses
asserts for debugging and diagnostics during development; it does not
rely on them to crash a program at runtime.

If an assert triggers in production software, then unprotected sensitive
information could be egressed from the program to the filesystem or the
platform's error reporting program, like Apport on Ubuntu or CrashReporter
on Apple.

The makefile orders object files to help remediate problems associated with
C++ static initialization order. The library does not use custom linker scripts.
If you use an alternate build system, like Autotools or CMake, and collect source
files into a list, then ensure these three are at the head of the list: 'cryptlib.cpp
cpu.cpp integer.cpp <other sources>'. They should be linked in the same order:
'cryptlib.o cpu.o integer.o <other objects>'.

If your linker supports initialization attributes, like init_priority, then you can
define CRYPTOPP_INIT_PRIORITY to control object initialization order. Set it to a
value like 250. User programs can use CRYPTOPP_USER_PRIORITY to avoid conflicts with
library values. Initialization attributes are more reliable than object file ordering,
but its not ubiquitously supported by linkers.

The makefile links to the static version of the Crypto++ library to avoid binary
planting and other LD_PRELOAD tricks. You should use the static version of the
library in your programs to help avoid unwanted redirections.

*** Side Channel Attacks ***

Crypto++ attempts to resist side channel attacks using various remediations.
The remediations are applied as a best effort but are probably incomplete. They
are incomplete due to cpu speculation bugs like Spectre, Meltdown, Foreshadow.
The attacks target both cpu caches and internal buffers. Intel generally refers
to internal buffer attacks as "Microarchitectural Data Sampling" (MDS).

The library uses hardware instructions when possible for block ciphers, hashes
and other operations. The hardware acceleration remediates some timing
attacks. The library also uses cache-aware algorithms and access patterns
to minimize leakage cache evictions.

Elliptic curves over binary fields are believed to leak information. The task is a
work in progress. We don't believe binary fields are used in production, so we feel it
is a low risk at the moment.

Crypto++ does not engage Specter remediations at this time. The GCC options
for Specter are -mfunction-return=thunk and -mindirect-branch=thunk, and the
library uses them during testing. If you want the Specter workarounds then add
the GCC options to your CXXFLAGS when building the library.

To help resist attacks you should disable hyperthreading on cpus. If you
suspect or find an information leak then please report it.

*** Documentation and Support ***

Crypto++ is documented through inline comments in header files, which are
processed through Doxygen to produce an HTML reference manual. You can find
a link to the manual from http://www.cryptopp.com. Also at that site is
the Crypto++ FAQ, which you should browse through before attempting to
use this library, because it will likely answer many of questions that
may come up. Finally, the site provides the wiki which has many topics
and code examples.

If you run into any problems, please try the Crypto++ mailing list.
The subscription information and the list archive are available on
http://www.cryptopp.com.

*** Source Code and Contributing ***

The source code and its planned changes are available at the following locations.

  * The Crypto++ GitHub repository allows you to view the latest (unreleased)
    Crypto++ source code via the Linux kernel's git beginning around June 2015.
    Its also serves as an incubator to nurture and grow the library.
  * The former Crypto++ SourceForge repository allows you to view the Crypto++
    source code via Apache's subversion until about July 2015. At that time,
    SourceForge had infrastructure problems and a cutover to GutHub was performed.
  * The Roadmap on the wiki provides the general direction the library is heading.
    It includes planned features and releases, and even some wishlist items.

Contributions of all types are welcomed. Contributions include the following.

  * Bug finding and fixes
  * Features and enhancements
  * Test scripts and test cases
  * Branch and release testing
  * Documentation and updates

If you think you have found a bug in the library, then you should discuss it on the
Users mailing list. Discussing it will help bring the issue to the attention of folks
who can help resolve the issue. If you want to contribute a bug fix to the library,
then make a Pull Request or make a Diff available somewhere. Also see Bug Reports on
the wiki.

Features and enhancements are welcomed additions to the library. This category tends
to be time consuming because algorithms and their test cases need to be reviewed and
merged. Please be mindful of the test cases, and attempt to procure them from an
independent source.

The library cherishes test scripts and test cases. They ensure the library is fit and
they help uncover issues with the library before users experience them. If you have
some time, then write some test cases, especially the ones that are intended to break
things.

Branch and release testing is your chance to ensure Master (and planned merges) meets
your expectations and perform as expected. If you have a few spare cycles, then please
test Master on your favorite platform. We need more testing on MinGW, Windows Phone,
Windows Store, Solaris 10 (and below), and modern iOS and OS X (including TV and
Watch builds).

Documentation and updates includes both the inline source code annotations using
Doxygen, and the online information provided in the wiki. The wiki is more verbose and
usually provides more contextual information than the API reference. Besides testing,
documentation is one of the highest returns on investment.

Originally written by Wei Dai, maintained by the Crypto++ Project