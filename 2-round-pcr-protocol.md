# ILLUMINA PROTOCOLS
-----
-----
![image_broken][image] 

## PRIMERS:

### Adaptor-bound primers (for first PCR round): 
A  (Illumina adaptor) +  PRIMER (ITS(fungal) or 16S(bacterial))

Adaptor-bound primer examples:
```python 
							Adaptor	                              Primer
ITS1f-Next   	TCGTCGGCAGCGTCAGATGTGTATAAGAGACAG           CTTGGTCATTTAGAGGAAGTAA	
                                                            
ITS2-Next		GTCTCGTGGGCTCGGAGATGTGTATAAGAGACAG          GCTGCGTTCTTCATCGATGC
```

### Index primers (for second PCR round):
For use with any product that has illumina adaptors as above.

Index primer examples:
```python
 Name 										   		 Barcode     
i5_A501 		AATGATACGGCGACCACCGAGATCTACA  		CATCGTACG  		TCGTCGGCAGCGTC
i7_A701			CAAGCAGAAGACGGCATACGAGAT      		AACTCTCGG  		TCTCGTGGGCTCGG
```

---------------
---------------

## 2-STAGE PCR AND LIBRARY PREP:
 - Always use the correct primer pairs with an A and B adaptor.  
 - Use Hi Fidelity Hot Start Taq, and keep everything on ice to prevent bad primer-dimers from forming.

In the first round of PCR we will use amplicon-specific primers that also include the Illumina adapters.
These will be the same for every sample so they can be added together to the master mix.  Since we will be using the product of 22 cycles of PCR as a starting template for round 2, create your reaction conditions to pause after 22 cycles, at which point you can pull out a small amount of product for round 2, but then resume the reaction so you can do a gel check after 8 more cycles.  

To download a super convenient master mix calculator designed for this protocol, [click this link.][calculator]

If you like doing it the hard way, here are the reaction ingredients...
### 1st Round (22 cycles)

| `Reagent`       |`Final Conc`     |`1 x`    |
| -------------  | ------------- | :----- |
| **5X Buffer**      | 1X            | 5 µL   |
| **GC Enhancer**    | 10%           | 2.5 µL |
| **dNTPs [10mM]**   | 0.2 mM        | 0.5 µL   |
| **BSA [10mg/mL]** | 0.2 mM        | 0.25 µL  |
| **F Primer [10µM]**| 0.04µM        | 0.1 µL |
| **R Primer [10µM]**| 0.04µM        | 0.01 µL  |
| **Q5 Polymerase**  | 0.25 Units    | 0.125 µL|
| **Template**       | ---           | 1.4 µL|
|**Water**           | --- | 15.025 µL

-----

**Fungi Round 1**

 - 98 °C for 2 min, (98 °C for 15s | 52°C for 15s | 72 °C for 20s) x 22 cycles
 - PAUSE -> remove 1.4µL of into tubes containing 12.6µl water; cover plate and resume for 8-16 more cycles for a test gel.
 - If the gel is successful, then the diluted PCR product from 22 cycles is added to round 2.

**Bacteria Round 1**

 - 98 °C 2 min, (98 °C for 15s | 55°C for 15s | 72 °C for 20s) x 22
 - PAUSE -> remove 1.4µL of into tubes containing 12.6µl water; cover plate and resume for 8-16 more cycles for a test gel.
 - If the gel is successful, then the diluted PCR product from 22 cycles is added to round 2.
-------------------

### Second round (22 *more* cycles)

 - Same protocol for Bacteria and Fungi
 - Pipette 1 µL of the appropriate i5/i7 **index primers** from the pre-filled plates into a new clean plate
 - Keep track of which primer plate you use.  The current plate maps can be [downloaded here].  
 
Pipette 22.9µL of round-2 master mix into each well and gently mix with the 1µL of index primers.  Finally, add 2.8 µL of the diluted amplicon from round 1 (the 22-cycle amplicon).

The round-2 master mix reagents are also calculated on [that spreadsheet] from above, but here they are:

| `Reagent`       								|`Final Conc`     |`1 x`      	|
| -------------  								| -------------   | :----- 		|
| **5X Buffer**      							| 1X              | 5 µL   		|
| **GC Enhancer**    							| 10%             | 2.5 µL 		|
| **dNTPs [10mM]**   							| 0.2 mM          | 0.5 µL   	|
| **BSA [10mg/mL]** 							| 0.2 mM          | 0.25 µL  	|
| **Q5 Polymerase**  							| 0.25 Units      | 0.125 µL	|
| **Water**          							| ---             | 15.025 µL	|
| **Template**       							| ---             | 2.8 µL		|
| **Primers** *unique pair for each sample*		| ---             | 1 µL		|

----

**Fungi or Bacteria Round 2**

 - 98 °C for 2 min, (98 °C for 15s | 60°C for 15s | 72 °C  for 30s) x 22
 - 72 °C for 2 min | 4 °C hold
 
**Check on gel for product:**
 - Fungal ITS should be ~400 bp
 - Bacterial 16S (V4) should be ~450 bp
 - Keep in mind that you now have some rather long adapter and primer sequences flanking to your amplicons as well so don't be too worried if your bands are larger than this
--------------
-----------------

## CLEAN UP YOUR PRODUCTS

If you have significant primer dimers in your amplification you will probably want to reduce these before normalization or they could be over-represented in your normalized product. 

Use AMpureXP beads (we will use a home-brewed version of this: see MagNA composition in the SPRI-Bead note in the lab's "Protocols" folder). Or [click here to download directly].
Determine the ratio of beads to use to use to exclude all fragments shorter than PCR product.  You can practice with different concentrations of beads on 100 bp ladder: see figure S5 in the SPRI bead note for inspiration (probably about ~0.8X will be about right). For example if using 0.8Xreaction with a sample volume of 50ul, the volume of MagNA per reaction to add will be: .8x50ul = 40ul of MagNA.

1.	Make sure the beads are at room temp.
2.	Shake beads to Resuspend any settled particules.
3.	Add beads to PCR reaction, mix up and down x10.
4.	Incubate at room temp for 5min.
5.	Place plate on magnetic plate for 2mins. Wait for the solution to clear.
6.	Aspirate the clear solution and discard.
7.	Add 200ul of fresh 70% ethanol to each well.
8.	Incubate for 30secs @ room temp.
9.	Aspirate the ethanol.
10.	Repeat the ethanol step.
11.	Dry for 15min @ room temp (longer if necessary until no visible ethanol).
12.	Remove the plate from the magnet.
13.	Add 40ul of 0.1x TE and mix up and down x10.
14.	Place plate on the magnet for 1min.
15.	Transfer the eluant to a new 96 well plate.

--------
--------

## Normalization of samples using SequalPrep Normalization Plates

- Be sure to perform this step in the post-pcr area of the lab.
- Be careful not to scrape the sides of the wells in the normalization plate, as the DNA-binding coating is adhered to the inner surface of the wells.
- You can follow this link if you want to view the complete [normalization plate user manual].

This kit is designed to eliminate the tedious step of quantification and equalization of each of your samples before pooling.  It works by binding a *fixed amount* of DNA to the sides of the wells. After binding is completed you may remove the excess amplicon solution and store it at -20°C for up to 30 days to perform additional purifications at a later time.

See the user manual for detailed instructions, but the general workflow is as follows:
1. Transfer cleaned-up PCR product into the Normalization Plate along with an equivalent amount of binding buffer.
2. Wait for one hour.
3. Carefully avoiding the walls of the plate with your pipette tip, remove the amplicon/buffer mixture and save in a clean 96-well plate for later use.
4. Add 50 µL Wash Buffer to the wells, pipette up and down a few times to wash, and aspirate from the wells. Try to remove as mush wash buffer as possible.
5. Add 20 µL Elution Buffer to each well. *Do not use water for elution.* Seal the plate with foil, vortex and spin down.
6. Incubate at room temp for 5 minutes
7. Transfer and pool the DNA as desired.

-----------
-----------


*More coming soon...*

- BioAnalyzer prep and analysis
- Sample Submission
- Troubleshooting



[calculator]:[https://github.com/gzahn/Protocols/raw/master/2-Round_PCR_Calculator.xlsx]
[downloaded here]:[https://github.com/gzahn/Protocols/raw/master/i5-i7_Index_Primer_Maps_Oct-25-2015.xlsx]
[that spreadsheet]:[https://github.com/gzahn/Protocols/raw/master/2-Round_PCR_Calculator.xlsx]
[click here to download directly]:[https://github.com/gzahn/Protocols/raw/master/SPRI-Bead.pdf]
[image]:[http://vignette1.wikia.nocookie.net/villains/images/6/67/Pennywise_Evil_Grin.jpg/revision/latest?cb=20130511222536]
[normalization plate user manual]:[https://tools.thermofisher.com/content/sfs/manuals/sequalprep_platekit_man.pdf]
