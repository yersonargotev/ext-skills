# Rank profile discovery matches before strict install semantics

Harness catalog discovery will treat multiple selected catalog profiles as a ranked discovery query: plugins matching all selected profiles appear before partial matches, instead of hiding partial matches. If Harness later supports installing from catalog profiles directly, that installation flow must use stricter semantics so it does not install loosely related plugins by surprise.
