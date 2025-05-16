# sat-qecc
A python-based SAT solver for finding the distance of a quantum error correcting code (limited to CSS codes).

The main file is a jupyter notebook release.ipynb. Just download ot and you're good to go!
For full functionality, you will need some additional packages:
- ldpc: https://github.com/quantumgizmos/ldpc/tree/main
- pysat: https://pysathq.github.io/
- drup (optional): https://fairlyaccountable.org/verified_rup/drup.html

Just run the first two code cells and you're ready to go!
Create your parity-check matrices HX and HZ as numpy arrays.
Let's assume you have an upper bound on the code distance (the tighter the better) of p.
- To find Z distance:
  ```
    find_weight(HX,HZ,p)
  ```
- To find X distance:
  ```
    find_weight(HZ,HZ,p,switch=True)
  ```
- To find the distance d=min(d_X,d_Z):
  ```
    find_weight(HX,HZ,p,both=True)
  ```

Note that proof verification is not extensively tested. I *think* I've understood how to convert between the proof that's output by the sat solver and the format required by the checker, but the documentation is somewhat sparse!
