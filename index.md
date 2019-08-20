---
layout: default
title: WAVM
lead: WAVM is a WebAssembly virtual machine, designed for use in non-web applications.
---
<div class="row">
  <div class="col-xs-12 col-md-6">
    <h3>Fast</h3>
    <p>WAVM uses <a href="https://llvm.org/">LLVM</a> to compile WebAssembly code to machine code with close to native performance. It can even beat native performance in some cases, thanks to the ability to generate machine code tuned for the exact CPU that is running the code.</p>
    <p>WAVM also leverages virtual memory and signal handlers to execute WebAssembly's bounds-checked memory accesses at the same cost as a native, unchecked memory access.</p>
  </div>
  <div class="col-xs-12 col-md-6">
    <h3>Safe</h3>
    <p>WAVM prevents WebAssembly code from accessing state outside of WebAssembly virtual machine*, or calling native code that you do not explicitly link with the WebAssembly module.</p>
    <p class="footnote">* WAVM <i>is</i> vulnerable to some side-channel attacks, such as Spectre variant 2. WAVM may add further mitigations for specific side-channel attacks, but it's impractical to guard against all such attacks. You should use another form of isolation, such as OS processes, to protect sensitive data from untrusted WebAssembly code.</p>
  </div>
</div>
<div class="row">
  <div class="col-xs-12 col-md-6">
    <h3>WebAssembly 1.0+</h3>
    <p>WAVM passes all tests in the WebAssembly reference <a href="https://github.com/WebAssembly/spec/tree/master/test/core">test suite</a>.</p>
    <p>WAVM also includes implementations of many proposed WebAssembly extensions:</p>
    <ul>
      <li><a href="https://github.com/WebAssembly/nontrapping-float-to-int-conversions">Non-trapping float-to-int conversions</a></li>
      <li><a href="https://github.com/WebAssembly/sign-extension-ops">Sign-extension instructions</a></li>
      <li><a href="https://github.com/WebAssembly/multi-value">Multiple results and block parameters</a></li>
      <li><a href="https://github.com/WebAssembly/reference-types">Reference types</a></li>
      <li><a href="https://github.com/webassembly/bulk-memory-operations">Bulk memory operations</a></li>
      <li><a href="https://github.com/WebAssembly/threads">Threads</a></li>
      <li><a href="https://github.com/WebAssembly/simd">128-bit SIMD</a></li>
      <li><a href="https://github.com/WebAssembly/exception-handling">Exception handling</a></li>
      <li><a href="https://github.com/WebAssembly/extended-name-section">Extended name section</a></li>
      <li><a href="https://github.com/WebAssembly/WASI">WASI</a></li>
    </ul>
  </div>
  <div class="col-xs-12 col-md-6">
    <h3>Portable</h3>
    <p>WAVM is tested on, and fully supports X86-64 Windows, MacOS, and Linux. It is designed to run on any POSIX-compatible system, but is not routinely tested on other systems.</p>
    <p>Supported for AArch64 is <a href="https://github.com/WAVM/WAVM/issues/76">planned</a>.</p>
    <p>WAVM is mostly written in portable C/C++, but has a small amount of X86-64 assembly code. It also uses a few of LLVM's X86-specific intrinsics for the WebAssembly SIMD extension. As a result, WAVM currently only supports X86-64, and adding support for other CPU architectures will require writing a small amount of architecture-specific code.</p>
    <p>WAVM's design also assumes 64-bit addresses, and so is not portable to 32-bit architectures.</p>
  </div>
</div>