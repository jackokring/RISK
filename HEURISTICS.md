1. Assumption: integer multiply is by constant (data structure indexing) traded against float multiply is by variable (DSP).
	* a fast integer pair multiply is not required and no const float multiply is needed before float load and float variable pair multiply.
2. All rounded float maths is integer.
  * what really is missed?
3. The stalling of writes on an SMP core which wants the serial transfered memory segment (64 kB) gives up the task to efficency of process on localized CPU core not needing the transfer.
  * The processing follows the data, and the code is moved toward the data.

