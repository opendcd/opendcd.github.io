OpenDcd - An Open Source WFST based Speech Recognition Decoder
=================


OpenDcd is a collection or tools for speech recognition decoding, cascade construction,
model conversion and results post-processing.

````bash
    git clone https://github.com/opendcd/opendcd.git
````

````bash
    cd src/bin
    make
````


The first release includes the following features:

  - Standalone lightweight decoder core
  - Kaldi drop-in replacement decoder
  - Cascade construction and experimental pipeline built around Unix make
  - Post-processing tools

Decoder:

  - Direct decoding on different weight semiring
  - On-the-fly decoding using lookahead composition
  - Lattice generation 
  - Switchable STL implementations. Use different implementations such EASTL or RDESTL, or mix optimized containers such as Google sparse hash.

Cascde construction:

  - Experimental framework built around Gnu make

Kaldi Compat
  
Results post-processing:

  - ``farfilter`` Apply the command to every in FST in the FAR archive
  - ``latticetofar`` Convert Kaldi Table to OpenFst FAR archive
  - ``fartolattice`` Convert an OpenFst FAR archive to Kaldi Table
  
##Authors

 - Paul R. Dixon
 - Josef Novak
