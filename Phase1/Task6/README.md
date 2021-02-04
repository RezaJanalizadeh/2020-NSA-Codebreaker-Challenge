# 2020 <a href="https://codebreaker.ltsnet.net" target="_top">NSA Codebreaker Challenge</a>
<!--![Codebreaker Challenge 2020 Solutions Thumbnail](Images/nsalogo.svg)-->
<p align="center">
  <img src="https://www.nsa.gov/Portals/70/images/about/cryptologic-heritage/center-cryptologic-history/insignia/nsa-insignia-lg.png"width="40%" height="40%">
</p>

| Task 6 - What's On the Drive? - (Computer Forensics, Command Line, Encryption Tools) | Points: 10 |
|:------------------------------------------------------------------------------------ | ---------: |

>Satellite imaging of the location you identified shows a camouflaged building within the jungle. The recon team spotted multiple armed individuals as well as drones being used for surveillance. Due to this heightened security presence, the team was unable to determine whether or not the journalist is being held inside the compound. Leadership is reluctant to raid the compound without proof that the journalist is there.

>The recon team has brought back a signal collected near the compound. They suspect it is a security camera video feed, likely encoded with a systematic Hamming code. The code may be extended and/or padded as well. We've used BPSK demodulation on the raw signal to generate a sequence of half precision floating point values. The floats are stored as IEEE 754 binary16 values in little-endian byte order within the attached file. Each float is a sample of the signal with 1 sample per encoded bit. You should be able to interpret this to recover the encoded bit stream, then determine the Hamming code used. Your goal for this task is to help us reproduce the original video to provide proof that the journalist is alive and being held at this compound.

>Downloads:

* [Collected Signal (signal.ham)](./Files/home.zip)

**Solution:**