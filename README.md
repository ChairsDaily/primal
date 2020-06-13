## primal
High volume prime decompositions, rapid-fire sieving over huge number fields, and 
quick identification of primes. I guarentee this is the most advanced
open source Python number theory package that you can find online. Hours of 
solo work were poured into these modules and writing up the proofs/citing references
in `docs/`. 
```python
# load helper data
from primal.data import polynomials
from primal.data import small_primes
from primal.data import wheel_mod217_correctors

# import helper methods
from primal.helpers import best_rounds
from primal.helpers import wheel_mod217
from primal.helpers import digits
from primal import bitwise

from primal import PollardRhoMachine


# define a target number for some machine
N = 2382930812903821093803289380219382311818182738372198329292832903820381929191819821981910190190190190101110111

factorizer = PollardRhoMachine(
  rounds=best_rounds(digits(N)), 
  growth=polynomials['elipse'],
  failure=[factor_out_squares, continue],
  auxilary=[wheel_mod217, wheel_mod217_correctors],
  bitwise=bitwise)
```
