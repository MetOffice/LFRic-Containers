# Introduction to LFRIC

## LFRic and PSyclone: A quick overview

`LFRic` is the new weather and climate modelling system being developed by the
UK Met Office to replace the existing Unified Model (UM) in preparation for
exascale computing in the 2020s. `LFRic` uses the GungHo dynamical core and runs
on a semi-structured cubed-sphere mesh.

The design of the supporting infrastructure follows object-oriented principles
to facilitate modularity and the use of external libraries. One of the guiding
design principles, imposed to promote performance portability, is
“separation of concerns” between the science code and parallel code. An
application called `PSyclone`, developed at the STFC Hartree Centre, can generate
the parallel code enabling deployment of a single source science code onto
different machine architectures.

`PSyclone` is a domain-specific compiler and source-to-source translator developed
for use in finite element, finite volume and finite difference codes. Using the
information from a supported API, `PSyclone` generates code exploiting different
parallel programming models.

More detailed information about `LFRic` and further references can be found in
[*Introduction to LFRic*](https://github.com/eth-cscs/ContainerHackathon/blob/master/LFRIC/LFRicIntro.md) section.

## LFRic repository and wiki

The `LFRic` repository and the associated wiki are hosted at the Met Office
Science Repository Service [(MOSRS)](https://code.metoffice.gov.uk/trac/home).
The code is BSD-licensed, however browsing the
[`LFRic` wiki](https://code.metoffice.gov.uk/trac/lfric/wiki) and
[code repository](https://code.metoffice.gov.uk/trac/lfric/browser) requires
login access to MOSRS. Please contact the `LFRic` team manager,
[Steve Mullerworth](mailto:steve.mullerworth@metoffice.gov.uk), to be granted
access to the repository.

Once the access has been granted the `LFRic` trunk can be checked out using
[Subversion](https://subversion.apache.org/) or
[FCM](https://metomi.github.io/fcm/doc/) version control systems. `SVN` is
recommended for checking out the code for runs only as it is easier to install.

### LFRic code structure

The `LFRic` trunk 
[(revision 25065, September 2020)](https://code.metoffice.gov.uk/trac/lfric/browser/LFRic/trunk?rev=25065)
is structured as follows:

* `bin` - `Rose` executables;

* `extra` - Utilities (e.g.job submission scripts);

* `gungho` - Gungho dynamical core (one of the main science applications);

* `infrastructure` - `LFRic` infrastructure supporting science applications;

* `jules` - Interface to the MO [JULES land surface model](https://www.metoffice.gov.uk/research/approach/collaboration/jwcrp/jules);

* `lfric_atm` - `LFRic` atmospheric model (Gungho dynamical core, UM Physics,
                JULES and SOCRATES);

* `mesh_tools` - Mesh generation tools;

* `miniapps` - "Standalone" science and infrastructure applications (e.g.
                Gravity Wave application);

* `socrates` - Interface to the MO radiative transfer ("Suite Of Community
               RAdiative Transfer codes") model;

* `um_physics` - Interface to the MO UM Physics parameterisation schemes.

## References and links

* Adams SV, Ford RW, Hambley M, Hobson JM, Kavcic I, Maynard CM, Melvin T,
  Mueller EH, Mullerworth S, Porter AR, Rezny M, Shipway BJ and Wong R (2019):
  [LFRic: Meeting the challenges of scalability and performance portability in
  Weather and Climate models.](https://doi.org/10.1016/j.jpdc.2019.02.007) Journal of Parallel and Distributed Computing.
* [Met Office LFRic modelling approach](https://www.metoffice.gov.uk/research/approach/modelling-systems/lfric)
* [Met Office research news, May 2019](https://www.metoffice.gov.uk/research/news/2019/gungho-and-lfric)
