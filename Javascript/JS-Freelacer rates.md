[[Javascript]]

```javascript
export function dayRate(ratePerHour) {
  return ratePerHour * 8;
}

export function daysInBudget(budget, ratePerHour) {
  return Math.floor(budget / dayRate(ratePerHour));
}

export function priceWithMonthlyDiscount(ratePerHour, numDays, discount) {
  const dRate = dayRate(ratePerHour);
  const numMonths = Math.floor(numDays / 22);
  const daysRemaining = numDays % 22;
  const totalDiscount = discount * dRate * 22 * numMonths;
  return Math.ceil(numMonths * 22 * dRate + daysRemaining * dRate - totalDiscount);
}
```
