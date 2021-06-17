# SHIM KVX Models #

This repository contains the Software-Hardware Interface For Multi-Many-Core (SHIM) model files for the kvx architecture.  
SHIM is an IEEE standard available for download at this
[page](https://standards.ieee.org/standard/2804-2019.html).  
Its main goal is to allow tool developers to fully understand and exploit a
given architecture in order to generate efficient code for it.


The models in this repository use the XML schema from the second version of SHIM
and its associated SHIM Editor for writing and visualization.  
A guide on how to use the tools is available [here](https://github.com/openshim/shim2/tree/master/docs).

## Structure ##

├── `kv3`: contains the kv3 models (third generation of kvx processors, also
known as Coolidge).

├── `shim`: submodule containing the XML schema and editors from the first SHIM
version. Kept for historical reasons.

└── `shim2`: submodule containing the XML schema and editors from the second
SHIM version. This should be used to exploit the models available in the other
directories.

## Roadmap ##

The only available model for now is the `kv3/coolidge-base-model.xml`  
Future work points:

1. The base model is accurate on all SHIM sections except the Communication and
   ContentionGroups. Both of these need work, discussion and benchmarks to
   properly provide the right abstraction and performance numbers.
2. The performance of memory accesses either to the Clusters' local memory
   (SMEM) or to the chip global memory (DDR) reflect the hardware behavior. They
   could be improved mainly for DDR by distinguishing read and write accesses.
3. Not all the Cluster Master components such as DMA, DSU, etc. are described in
   the ComponentSet.
