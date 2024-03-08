[[Javascript]]

```jaavscript
const PREPARATION_MINUTES_PER_LAYER = 2; //constante local
export const EXPECTED_MINUTES_IN_OVEN = 40; //constante exportable

export function remainingMinutesInOven(actualMinutesInOven) {
  return EXPECTED_MINUTES_IN_OVEN-actualMinutesInOven;
}

export function preparationTimeInMinutes(numberOfLayers) {
  return numberOfLayers * 2;
}

export function totalTimeInMinutes(numberOfLayers, actualMinutesInOven) {
  return actualMinutesInOven + preparationTimeInMinutes(numberOfLayers);
}
```
