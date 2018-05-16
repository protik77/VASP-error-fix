# VASP-error-fix
Typical VASP errors encountered and fix associated with them.
Usually encountered and fixed with v5.4.4.


## Error: `forrtl: severe (71): integer divide by zero`

Solution: Usually it is faced with `LSORBIT = .TRUE.` with `PREC = Normal`. Usually setting `PREC = Accurate` resolves the issue.

**Caveat:** For GW calculations, `PREC = Accurate` increases the memory requirement by manifold.

## Error: `scaLAPACK: Routine ZPOTRF ZTRTRI failed!` 

Solution: Usually the solution is to change `ALGO` tag to something else.
But if this happens during many bands step of single shot GW (G0W0),
then changing `ALGO` is not possible as for this step exact
diagonalization is needed. The solution is to change
`ALGO` from `Exact` to `Damped`. According to 
[VASP documentation](https://cms.mpi.univie.ac.at/vasp/vasp/ALGO_tag.html),
`Damped` also does exact diagonalization.

