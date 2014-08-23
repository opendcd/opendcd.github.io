OpenDcd - An Open Source WFST based Speech Recognition Decoder
=================

OpenDcd is a collection or tools for speech recognition decoding, cascade construction,
model conversion and results post-processing. The toolkit makes used of [OpenFst](http://openfst.org/) for representing and manipulating the models. The toolkit was developed by members of [Yandex](http://yandex.com/). It is distributed as an open source project with an Apache Licence. For more information see the [main documentation site](https://github.com/opendcd/opendcd.github.io/wiki)


Quick Installation Guide
-------------------------

````bash
    git clone https://github.com/opendcd/opendcd.git
````

````bash
    cd src/bin
    make
````

See egs directory for an example showing how to convert a Kaldi WSJ setup

Brief Overview
---------------

The first release includes the following features:

  - Standalone lightweight decoder core
  - Kaldi file format compatible
  - Cascade construction and experimental pipeline built around Unix make
  - Post-processing tools

Decoder:

  - Customizable transition model for custom user and transition models
  - Direct decoding on different weight semiring
  - On-the-fly decoding using lookahead composition
  - Lattice generation 
  - Switchable STL implementations. Use different implementations such EASTL or RDESTL, or mix optimized containers such as Google sparse hash.

Cascde construction:

  - Experimental framework built around Gnu make
  
Results post-processing:

  - ``farfilter`` Apply the command to every in FST in the FAR archive
  - ``latticetofar`` Convert Kaldi Table to OpenFst FAR archive
  - ``fartolattice`` Convert an OpenFst FAR archive to Kaldi Table

Kaldi Interoperability:

  - Write results in Kaldi *Lattice* table format

More Information

  - Ongoing introdcution slides can be found [here](https://dl.dropboxusercontent.com/u/321851/opendcd.pdf). These are updated frequently. 
