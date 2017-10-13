# Verifying multi-party authentication protocols

For my MSc thesis at Eindhoven University of Technology, I did some work on the verification of multi-party authentication protocols, using rank functions and the theorem prover [PVS](http://pvs.csl.sri.com/). This resulted in a published paper .

## Publications
* Master’s thesis [*Proving correctness of a multi-party authentication protocol with rank functions*](http://repository.tue.nl/631698)&nbsp;(2007)<br>
  ```tex
  @MASTERSTHESIS{verhoeven2007multiparty,
	author	= {R.H.A. Verhoeven},
	title	= {Proving correctness of a multi-party authentication protocol with rank functions},
	school	= {Eindhoven University of Technology},
	year	= {2007},
	url	= {http://repository.tue.nl/631698}
  }
  ```
* Article [*Verifying Multi-party Authentication Using Rank Functions and PVS*](http://link.springer.com/chapter/10.1007%2F978-3-642-01465-9_15?LI=true), with Francien Dechesne (2008)

## Accompanying PVS code
The PVS code is available for multiple versions of PVS. There are three theories.

| Theory | Description |
|--------|-------------|
|```csp_rules``` | [Neil Evans’ framework](http://dx.doi.org/10.1016/j.jlap.2004.09.005) for modelling CSP and Schneider’s Rank Theorem, updated from PVS version 3.1 and slightly extended |
|```nsl```*   | Analysis of the Needham-Schroeder-Lowe public key protocol using rank functions |
|```gnsl```*      | Analysis of Cremers and Mauw’s [Generalised Needham-Schroeder-Lowe public key protocol](http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.122.8106), using rank functions |

\* Requires the ```csp_rules``` theory as a library, for which the appropriate path must be set in the file ```dynetwork.pvs```.

## Running the ```gnsl``` theory

* Initial set up
  1. Install PVS
  2. Obtain a local copy of the appropriate versions of the ```gnsl``` and ```csp_rules``` theories (making sure to adjust the path to the latter in the former's file ```dynetwork.pvs```)
* Opening the theory
  1. Start PVS (this opens Emacs)
  2. Change the current context to the folder containing the ```gnsl``` theory with the command ```M‑x change‑context```
  3. Open the file ```gnsl.pvs```
* Working with the theory
  1. Perform any command on opened file (get PVS help with the command ```C‑x h```)
     * for proving the theory and its importchain, use the command ```M‑x pri```
     * for stepping through a proof, move the cursor onto a lemma and use the command ```M‑x step-proof``` (stepping through it with ```TAB 1``` or <code>ESC *n* TAB 1</code> for *n*&nbsp;steps)
