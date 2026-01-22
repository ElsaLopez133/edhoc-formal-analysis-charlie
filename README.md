This repository contains the models for the formal analysis of the Lake Remote Attestation over EDHOC protocol.
The version under verification is draft 03 (https://datatracker.ietf.org/doc/draft-ietf-lake-ra/).

This work builds on prior formal analyses of the LAKE EDHOC protocol, in particular the results reported in the paper `A comprehensive, formal and automated analysis of the EDHOC protocol`- Charlie Jacomme, Elise Klein, Steve Kremer, Maïwenn Racouchot, USENIX'23,  https://hal.inria.fr/hal-03810102/.

## 📌 Goals

The model enables the formal verification of:

- Authentication
- Attestation
- Authentication and attestation

# Prerequisite

The case-studies are based on the Sapic+ protocol platform, which allows from a single input file to export to Tamarin, Proverif and Deepsec.

- Tamarin Prover ≥ 1.9.0
- ProVerif ≥ 2.04
- Python 3 (for automation script)
- Optional: Graphviz (for ProVerif attack graphs)

# High Level Description

In `model`, you will find two `.spthy` files, the tamarin and Sapic+ input format, that correspond to the protocol:
 * `lake-edhoc-ra.spthy` -> the model with 4 authentication methods under the latest version of the draft-ietf-lake-ra (version -03)
 * `lake-edhoc-ra-fix.spthy`  -> the model with proposed fix to mitigate the found attack.
 
 These two files share the same headers, in `Headers.splib`, and the security lemmas, in `LakeProperties.splib`. Moreover, they contain multiple options for advanced threat models that can be enabled or disabled with flags, specified to tamarin on the command line using the "-D" option. More details can be found under /models repo.
 

## 📚 References

- [Remote attestation over EDHOC Draft](https://www.ietf.org/archive/id/draft-ietf-lake-ra-03.html)
- [EDHOC IETF Draft](https://datatracker.ietf.org/doc/html/draft-ietf-lake-edhoc)

## Acknolwdegments

This repository follows https://github.com/charlie-j/edhoc-formal-analysis/tree/master
