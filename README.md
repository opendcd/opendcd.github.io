OpenDcd - An Open Source WFST based Speech Recognition Decoder
=================

OpenDcd a lightweight and portable WFST based speech decoding toolkit written in C++. OpenDcd provides a set of tools for decoding, cascade construction and hypothesis post- processing. The focus of the toolkit is to provide a foundation for research into new decoding methods that can be deployed. Through the use of C++ templates the core decoder can be configured and extended in many ways. For example selecting different on-the-fly composition or lattice generation strategies. The core engine has detailed profiling, logging and analysis methods that make it highly for deployement in production systems. The toolkit makes used of [OpenFst](http://openfst.org/) for representing and manipulating the models. It is distributed as an open source project with an Apache Licence. 

For more information see the [main documentation site](https://github.com/opendcd/opendcd.github.io/wiki), and the tutorial for installing the OpenDcd and decoding using the Librispeech corpus and models from kaldi-asr.og.


Quick Installation Guide
-------------------------

````bash
    git clone https://github.com/opendcd/opendcd.git
````

````bash
    cd src/bin
    make
````

Kaldi Conversion Quick Start
-------------------------------

For Kaldi model converion and decoding a working Kaldi installation and 
set of acoustic and language models and features from generated from a Kaldi egs/s5 
script are required. The following example is based on the output of Kaldi WSJ training run.

Graph construction, the scripts directory contains 
The Kaldi language directory, we re-use the existing Kaldi lexicon and LM.

````bash
    cd $OPENDCD/scripts
    export KALDI_ROOT=/home/opendcd/tools/kaldi-trunk
    ./makeclevel.sh \
    $KALDI_ROOT/egs/wsj/s5/data/lang_test_bg_5k \
    $KALDI_ROOT/egs/wsj/s5/exp/tri2a \
    $KALDI_ROOT/egs/wsj/s5/exp/ocd_tri2a \
    $KALDI_ROOT
````


See egs directory contains example script for showing how to convert a Kaldi WSJ setup

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
  - [More information](https://github.com/opendcd/opendcd.github.io/wiki/Kaldi-Interoperability) on optionally building against Kaldi 

More Information
  - A [getting start guide](https://github.com/opendcd/opendcd.github.io/wiki/EC2-Installation-Walkthrough) for running OpenDcd on Ec2 using the Librispeech models
  - Ongoing introdutory slides can be found [here](https://dl.dropboxusercontent.com/u/321851/opendcd.pdf). These are updated infrequently. 
