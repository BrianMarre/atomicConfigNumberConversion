# Description
Library for converting between atomic config numbers and shell occupation number vector representations of atomic state super configurations.

# Installation
```bash
git clone git@github.com:ComputationalRadiationPhysics/SCFlyTools.git

cd SCFlyTools

pip install .

alternatively pip install -e . to install in edit mode
```

# Usage
usage example:
```python
import atomicConfigNumebrConversion as conv

# atomicConfigNumber -> occupationNumberVector
## Carbon, Z = 6
atomicNumber = 6
numberTrackedLevels = 10
atomicConfigNumber = 11

## result: np.array((2,3,0,0,0,0,0,0,0,0))
print(conv.getLevelVector(atomicConfigNumber, atomicNumber, numberTrackedLevels))

# occupationNumberVector -> atomicConfigNumber

## Argon, Z=18
atomicNumber = 18
occupationNumberVector = np.array((2,1,1,0,0,0,0,1,0,0))
## result: 352973
print(conv.testGetConfigNumber(occupationNumberVector, atomicNumber))

# atomicConfigNumber -> chargeState

# Argon, Z=18
atomicNumber = 18
atomicConfigNumber = 352973
numberTrackedLevels = 10

## result: 12
print(conv.getChargeState(atomicConfigNumber, atomicNumber, numberTrackedLevels))
```
