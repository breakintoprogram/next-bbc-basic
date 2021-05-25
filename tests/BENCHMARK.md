# benchmarks

Tested using the [Rugg/Feldman (PCW) benchmarks](https://en.wikipedia.org/wiki/Rugg/Feldman_benchmarks#:~:text=This%20expanded%20set%20became%20known,many%20computer%20magazines%20and%20journals.)

NB:

- The BBC Micro CPU is a 6502
- The Spectrum is a Z80
- The Next is a Z80 running on an FPGA core

| # | Next (3.5Mhz)| Next  (28Mhz)| Spectrum (3.5Mhz) | BBC Micro (2Mhz) |
|---|-------------:|-------------:|------------------:|-----------------:|
| 1 |        1.12s |        0.16s |              4.4s |             0.8s |
| 2 |        4.48s |        0.66s |              8.2s |             3.1s |
| 3 |       14.12s |        2.08s |             20.0s |             8.1s |
| 4 |       15.34s |        2.30s |             19.2s |             8.7s |
| 5 |       16.48s |        2.64s |             23.1s |             9.0s |
| 6 |       24.06s |        3.56s |             53.4s |            13.9s |
| 7 |       35.44s |        5.12s |             77.6s |            21.1s |
| 8 |       40.41s |        6.10s |            239.1s |            49.9s |
