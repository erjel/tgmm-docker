# tgmm-docker

[![](https://images.microbadger.com/badges/version/nclack/tgmm:latest.svg)](https://cloud.docker.com/repository/docker/nclack/tgmm "Docker Hub")

Automated DockerHub builds for the TGMM (Tracking with Gaussian Mixture Models) software developed in the [Keller lab](https://www.janelia.org/lab/keller-lab).

`docker run -rm -it nclack/tgmm:latest`

## About

This Dockerfile builds TGMM for environments based on nvidia/cuda containers. Build products are installed to `/opt/tgmm`.

A multi-stage docker build is used.  By default grabbing the image will not download the build environment, but if you'd like you can target the 'builder' stage.

For more information see the references below.

## Autobuild and this repository

1. Any tags on this repository build corresponding tagged docker images.
2. Different branches here correspond with Dockerfiles based on different nvidia/cuda containers.

## Contents of docker container
```
tgmm/
|-- bin
|   |-- GentleBoost_PrecRecallCurve
|   |-- ProcessStack
|   |-- ProcessStack_woGPU
|   |-- TGMM
|   |-- classifierBackgroundTracks.txt
|   |-- classifierCellDivision.txt
|   |-- classifierCellDivisionWithTemporalWindow.txt
|   |-- trainCellDivision
|   `-- trainCellDivisionWithTemporalWindow
|-- doc
|   `-- quickstart.txt
|-- lib
|   |-- libHierarchicalSegmentationPBC.a
|   |-- libMedianFilter2D_CUDAlib.a
|   |-- libTemporalLogicalRules.a
|   |-- libTemporalLogicalRules_woCUDA.a
|   |-- libellipticalHaarFeatures.a
|   `-- libtrainCellDivisionWithTemporalWindowLib.a
`-- test
    |-- MedianFilter2D
    `-- WatershedWithPersistanceAgglomeration_Test

4 directories, 18 files
```
## References

[TGMM Repository](https://bitbucket.org/fernandoamat/tgmm-paper)

McDole K, Guignard L, Amat F, Berger A, Malandain G, Royer LA, Turaga SC, Branson K, Keller PJ
Cell. 2018 Oct 10;175(3):859-876. doi: [10.1016/j.cell.2018.09.031](http://doi.org/10.1016/j.cell.2018.09.031)

Amat F, Höckendorf B, Wan Y, Lemon WC, McDole K, Keller PJ
Nature Protocols. 2015 Oct 2;10(11):1679-96. doi: [10.1038/nprot.2015.111](http://doi.org/10.1038/nprot.2015.111)

Amat F, Lemon W, Mossing DP, McDole K, Wan Y, Branson K, Myers EW, Keller PJ.
Nature Methods. 2014 Jul 20;11(9):951-8. doi: [10.1038/nmeth.3036](http://doi.org/10.1038/nmeth.3036)
