# Orca 

    module avail orca/

[Orca](https://orcaforum.kofo.mpg.de/app.php/portal) is a general purpose tool for quantum chemistry with specific emphasis on spectroscopic properties of open-shell molecules. 

Orca features a wide variety of standard quantum chemical methods ranging from semiempirical methods to DFT to single- and multireference correlated ab initio methods. It can also treat environmental and relativistic effects. 

## Usage

### License

To use the application you first need to accept its licence:

- [Orca version 3.0.1](https://signup.e-infra.cz/fed/registrar/?vo=meta&group=lic_orca)
- [Orca version 4.x.x and above](https://signup.e-infra.cz/fed/registrar/?vo=meta&group=lic_orca40)

### Notes

**Docs**

User reference manuals (as pdf files) are placed in `/cvmfs/software.metacentrum.cz/spack1/software/orca/`.

**Path specification**

You should always run the Orca program with it's full path because it's finding the program parts according to the run path. 

Example:

    $(which orca) input

or directly

    /software/orca-3.0.1/bin/orca in.inp
    /software/orca/4.2.1/orca in.inp

Newer versions of Orca (> `5.0`) are prepared using the Spack package manager and the directory structure is different

    # example for module orca/5.0.1-intel-19.0.4-bnofsgq
    /cvmfs/software.metacentrum.cz/spack1/software/orca/linux-debian10-x86_64/5.0.1-intel-bnofsg/bin/orca in.inp

**OpenMPI computing**

Don't try to run `mpirun -np $NCPUs orca`. ORCA will take care of it if you have the [!PAL keyword](https://www.orcasoftware.de/tutorials_orca/first_steps/parallel.html) set.

**Usage with NAMD**

[NAMD](../../software/sw-list/namd.md) uses Orca application for some computation. However due to different installation methods usually both programs use different OpenMPI to run. 

In Orca-4.2.1 module is created a wrapper for `orca` binary to avoid OpenMPI mismatch problems. Now should be sufficient to put the path to this orca wrapper to NAMD configuration file and avoid of running `module add orca/4.2.1` in your PBS script. For documentation purposes, the wrapper is this:

```
#!/bin/bash
eval $(env |sed -n '/^OMPI/s/^\([^=]*\).*/unset \1;/p')
module add orca/4.2.0
exec /software/orca/4.2.1/orca "$@"
```
