# Dynamic workbook rules in Copilot for Excel

A small expense-review exercise from Stringfest Analytics. All data and explanatory notes are fictional.

## Follow along

1. Open `dynamic-rules-expense-review.xlsx` in Excel with Copilot workbook editing available. Work in a copy.
2. On `Expenses`, inspect the prepared table and notes. Variance is Actual minus Budget; positive values are overruns.
3. Leave `Control!B2` at 1000. Read the formula and its displayed instruction in `.Rules!A5`. Keep `.Rules` visible.
4. Open Copilot and run the prompt in `prompt.txt`. Check the review against the source table and notes.
5. Change `Control!B2` to 2500. Confirm `.Rules!A5` now says $2,500. Run the exact same prompt again.

At $1,000, Travel and Software qualify, totaling $4,200 in overruns. At $2,500, Travel alone qualifies, with a $3,000 overrun. The total overrun across all three categories remains $4,600. The threshold includes equality.

Changing the input recalculates the rule. It does not itself ask Copilot to rewrite the review. The generated review reflects the prompt that produced it.

The dynamic rule is already included for inspection:

```excel
="Discuss expense categories where Actual minus Budget is at least $"&TEXT(Control!B2,"#,##0")&"."
```

## References

- [Microsoft: Workbook rules](https://support.microsoft.com/en-us/excel/copilot/copilot-in-excel-rules)
- [Excel Off The Grid: .Rules video](https://www.youtube.com/watch?v=_szIu3Sg0Xw&t=482s)
- [Stringfest: Personalization versus workbook rules](https://stringfestanalytics.com/how-to-understand-personalization-versus-rules-in-copilot-for-excel/)

Copilot availability and behavior depend on your account, Excel surface, model, and rollout. Inspect the resulting categories, amounts, and explanations.
