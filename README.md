# VHDL Process Sensitivity List Error

This repository demonstrates a common error in VHDL code: neglecting to include the reset signal in the sensitivity list of a process.  This can lead to unpredictable behavior and subtle bugs that are hard to track down.

The `bad_process.vhdl` file shows the erroneous code. The `good_process.vhdl` file provides a corrected version.

## Problem

The `bad_process.vhdl` example misses `reset` in the sensitivity list of the main process. Consequently, the `internal_data` signal isn't properly reset when `reset` is high. This will lead to unexpected values for `data_out` when the design is reset. 

## Solution

The `good_process.vhdl` file corrects the issue by adding `reset` to the sensitivity list. This ensures that the process is triggered when `reset` changes, allowing for proper resetting of `internal_data`. 

Always carefully review sensitivity lists to prevent such subtle and hard-to-debug problems.