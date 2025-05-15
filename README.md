README
======

Quick-Look Plot for 4-Port Hybrid Coupler
-----------------------------------------

This Python script:

1.  loads six two-port Touchstone files (P1P2.s2p … P3P4.s2p),
2.  builds a 4-port S-parameter matrix, and
3.  draws four key graphs in one window:

    • dB(S11) – input return loss  
    • dB(S41) – isolation (port 4 → 1)  
    • dB(S21 / S31) – amplitude balance between the outputs  
    • Phase(S21 / S31) – phase error between the outputs


Files
-----

P1P2.s2p
P1P3.s2p
P1P4.s2p
P2P3.s2p
P2P4.s2p
P3P4.s2p

Place everything in the same directory before running.

Dependencies
------------

pip install scikit-rf matplotlib numpy


Running
-------

Change the name based on your file name:
python SCRIPTNAME.py


A 2 × 2 plot panel appears.  
Use the Matplotlib toolbar to save or zoom.


Modifying the script
--------------------

* To save the 4-port Touchstone:  
  add `dut4.write_touchstone('hybrid.s4p')` after the combiner line.

* To export the figure automatically:  
  add `plt.savefig('hybrid_panel.png', dpi=300)` just before `plt.show()`.

* To plot additional S-parameters, pull the desired column out of `S`
  (for example, `S22 = 20*np.log10(np.abs(S[:,1,1]))`) and add another
  subplot.


Version
-------

2025-05-14
