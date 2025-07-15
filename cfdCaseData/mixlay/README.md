## Planar (2D) Spatially-Developing Mixing Layer
Simulation case for Nek5000.  

Note: 
   * Temperature field is included, but transport properties are constant. 

### Nek5000:
Download:
git clone --recursive https://github.com/KTH-Nek5000/KTH_Framework

### How to compile the case:
  1. `cd ../compile/`
  2. In `makenek`, assign the correct version and path to Nek5000 at `mver` and `SOURCE_ROOT`, respectively. Also set the correct compilers to `FC` and `CC`.
     * Note: `makenek` is designed to work for both V.17 (`17.0.4`) and V.19 (`19.0.1`) of Nek5000.
     * Note: If you compile a case with V.19, the following three lines will be automatically added at the end of `SIZE`:

          `c automatically added by makenek`<br/>
          `integer lelr`<br/>
          `parameter (lelr=lelt) ! max number of local elements per restart file`<br/>
       Therefore, remove these lines manually, if you want to recompile using V.17.

  3. In `SIZE`:
     * Set the number of GLL points per elemen per direction at `lx1` (adjust `lxd` accordingly).
     * Set the number of elements at `lelg`. This number can be read from the first line, second column of `../run/mixlay.re2`.
     * Set the min and max number of processors, respectively at `lpmin` and `lpmax`.
  4. Compile the case by `./compile_script --all`.
     * For removing compiled files, `./compile_script --clean`

### Run the case:
  1. `cd ../run/`
  2. Set appropriate runtime controllers at `mixlay.par`
  3. Choose the number of processors
  4. Run the case by `bash runBash_local.bash` or an appropriate script. 

Note: If using a high Re number, to avoid the numerical instabilities you can start from a lower Re-number to let the initial data leave the domain. Then you can restart the simulation increasing the Re-number. 
