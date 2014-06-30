OpenDcd - An Open Source WFST based Speech Recognition Decoder
=================


OpenDcd is a collection or tools for speech recognition decoding, cascade construction,
model conversion and results post-processing.

````bash
  git clone https://github.com/opendcd/opendcd.git
````

The first release includes the following features:

  - Standalone lightweight decoder core
  - Kaldi drop-in replacement decoder
  - Cascade construction and experimental pipeline built around Unix make
  - Post-processing tools


Decoder:
  - Direct decoding on different weight semiring
  - Lattice generation 


Cascde construction:
  - Experimental framework built around Gnu make
  
Results post-processing:

  - ``farfilter``
  - ``latticetofar``
  - ``fartolattice``
  
##Authors

 - Paul R. Dixon
 - Josef Novak
