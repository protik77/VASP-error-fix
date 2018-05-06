# VASP-error-fix
Typical VASP errors encountered and fix associated with them.
Usually encountered and fixed with v5.4.4.


## Error: forrtl: severe (71): integer divide by zero

* Solution: Usually it is faced with `LSORBIT = .TRUE.` with `PREC = Normal`. Usually setting `PREC = Accurate` resolves the issue.