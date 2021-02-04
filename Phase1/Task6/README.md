# 2020 <a href="https://codebreaker.ltsnet.net" target="_top">NSA Codebreaker Challenge</a>
<!--![Codebreaker Challenge 2020 Solutions Thumbnail](Images/nsalogo.svg)-->
<p align="center">
  <img src="https://www.nsa.gov/Portals/70/images/about/cryptologic-heritage/center-cryptologic-history/insignia/nsa-insignia-lg.png"width="40%" height="40%">
</p>

| Task 6 - Proof of Life - (Signals Analysis)| Points: 1300 |
|:------------------------------------------ | -----------: |

>Satellite imaging of the location you identified shows a camouflaged building within the jungle. The recon team spotted multiple armed individuals as well as drones being used for surveillance. Due to this heightened security presence, the team was unable to determine whether or not the journalist is being held inside the compound. Leadership is reluctant to raid the compound without proof that the journalist is there.

>The recon team has brought back a signal collected near the compound. They suspect it is a security camera video feed, likely encoded with a systematic Hamming code. The code may be extended and/or padded as well. We've used BPSK demodulation on the raw signal to generate a sequence of half precision floating point values. The floats are stored as IEEE 754 binary16 values in little-endian byte order within the attached file. Each float is a sample of the signal with 1 sample per encoded bit. You should be able to interpret this to recover the encoded bit stream, then determine the Hamming code used. Your goal for this task is to help us reproduce the original video to provide proof that the journalist is alive and being held at this compound.

>Downloads:

* [Collected Signal (signal.ham)](./Files/signal.ham)

**Solution:**

>The size of the signal.ham file is 19198236 bytes or 153585888 bits. As inferred from the task description, each 16 bits in the file are in [IEEE 754 binary16](https://en.wikipedia.org/wiki/Half-precision_floating-point_format#IEEE_754_half-precision_binary_floating-point_format:_binary16) format, and denote the amplitude of the analog [BPSK](https://en.wikipedia.org/wiki/Phase-shift_keying#Binary_phase-shift_keying_(BPSK)) signal. Since the modulation process is BPSK, ideally (i.e., assuming no error affects the bits as they propagate through the communication channel) the signal amplitude should have two levels (e.g., A and -A), where one of the levels corresponds to a single bit of 1 and the other corresponds to a single bit of 0. Subsequently, the total number of (actual) transmitted bits is 9599118.

>Considering the fact that the bits are transmitted in frames, one infers that the total number of bits should be divisible by the frame size (i.e., number of bits in a frame). Using the MATLAB function `divisors(n)`, one can calculate the possible frame sizes for `n=9599118` to obtain `divisors(9599118) = 1, 2, 3, 6, 17, 34, 51, 102, 94109, 188218, 282327, 564654, 1599853, 3199706, 4799559, 9599118`.