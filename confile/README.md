# Configuration files

This folder contains the configuration files used for producing samples, to make it easy to reproduce previous simulations.

A list of available samples can be found here:


and contains the following information:

| Id | CoM Energy (TeV) | Process name | BIB | Generator (card) | Number of Events | Software version | Detector config | Location | Notes |
|----|------------------|--------------|-----|------------------|------------------|------------------|-----------------|----------|-------|

where (columns with trivial meaning omitted):
- `Id`: represents an unique number associated to the sample;
- `Process name` is a short description of the physics process (e.g. HH_bbbb, ...);
- `BIB` specifies if beam-induced background is fully included (`1`), partially included (e.g. `0.1` for 10% of expected BIB rate), or not included `0`;
- `Generator (card)` is a short name for the generator used followed by a link to this repository with the run card used (the link should be to a specific commit/version of the card);
- `Software version` is the software/detector version, as tagged in the repository and described in the https://confluence.infn.it/display/muoncollider/Releases+notes; if a custom version is used, please add "_custom" to the starting software version, add in the `Notes` what is special and add a link to the relevant code commit, if possible;
- `Detector config` is a short name for the simulation/reconstruction configuration with link to the corresponding tag or commit in this repository;


## Convention for configuration tags 

To help ensuring an homogeneous naming convention when making tags in this repository for configuration files used in production, we propose to use:

```
pc-[sw_ver]-[short_descr]-[version_major].[version_minor]
```

where:
- `pc` just stands for "production configuration", 
- `sw_ver` is the software/detector version, as tagged in the repository and described in the https://confluence.infn.it/display/muoncollider/Releases+notes; if a custom version is used, please add "_custom" to the starting software version, add in the `Notes` what is special and add a link to the commit of this repository containing the simulation/reconstruction configuration files used.
- `short_descr` is a short description of the configuration
- `version_major/minor` is just a versioning that might be useful for modifications

For example: `pc-v02_05_MC-baseline-1.0` or `pc-v02_05_MC-trkDLCuts-1.0` or `pc-v02_05_MC_custom-trkTightDLCuts-1.1` (the latter example implies that modification of the code in addition to config files are used)

## Folder structure
The `simulation` and `reconstruction` folders contain the relevant XML configuration files for the respective production step.

The `evtgen` folder contains the run card for the various processes, with sub-folders grouping similar processes, e.g. `higgs`, `pgun`, ... (as needed)



