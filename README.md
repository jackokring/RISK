# The Odius Public Domain Origins of RISK
A hot off `.gsheet` to `.ods` (format export allowed) of the version 1 specification of RISK.

## Pin Out
Just using a pin for pin Z80 style layout would work fine. It would leave `/HALT` as an output which was not used for indicating system halt as no such state exists in the RISK design. I mean technically very few designs actually use the `/M1` pin either, and as an instruction pipeline fetch might not let `/M1` go high between instruction starts, it makes more sense for `/M1` to indicate all program fetch including `PC` indirect immediate operands (`/ROM`) so that an easy memory split becomes possible for simpler systems.

So `/HALT` as a `/C` (not carry, low on carry) is potentially more useful. Keeping `/RFSH` is useful for some contexts, although exactly how possible a refresh fetch is in a pipelined processor is debatable (if there is no instruction cache), especially if the processor is in `BUSACK`, and the fact that most newish Z80 systems use static RAM. In a way automatic `/WAIT` insertion to trigger a `/RFSH` would be ideal for some. But would such projects be new or in need of an actual Z80 for retro maintainance? It's likely best as a procesor status word to configure refresh if required.

| Pin	| Old	| New	|
|  18	| /HALT	| /C	|
|	 27	| /M1	| /ROM	|
|  28	| /RFSH	| ---	|
