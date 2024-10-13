# Table of algorithms

The notation is inspired by Haskell, but it is not consistent across the entire table.
All information is provided as is, please verify it yourself.

| Name           | Signature                  | Upper Bound | Family     | Aliases    | Comments |
| :---           | :---                       | :---        | :---       | :---       | :---     |
| copy if        | f int int [c] -> [c]       | O(n)        | copy       |            | various definitions exist with pointers, iterators, and integers |
| copy           |   [a]         -> [a]       | O(n)        | copy       |            | `copy        A := copy_if TRUE 0 (size A) A` |
| filter         | f [a]         -> [a]       | O(n)        | copy       | copy if    | `filter    F A   := copy_if F 0 (size A) A` |
| take           |   int [b]     -> [b]       | O(n)        | copy       |            | `take      i A := copy 0 i B`|
| take last      |   int [b]     -> [b]       | O(n)        | copy       |            | `take_last i A := copy (size B)-i (size B) B`       |
| drop           |   int [b]     -> [b]       | O(n)        | copy       |            | `drop      i A := copy i (size B) B`       |
| drop last      |   int [b]     -> [b]       | O(n)        | copy       |            | `drop_last i A := copy 0 (size B)-i B` |
| catenate       | f [a] [a]     -> [a]       | O(n)        | copy       |            | |
| map            | f [a]         -> [b]       | O(n)        | map        | transform  | |
| map (binary)   | f [a] [b]     -> [c]       | O(n)        | map        | transform  | `binary_map F A B := map F (zip A B)`|
| zip            |   [a] [b]     -> [(a,b)]   | O(n)        | map        |            | |
| reduce         | f  a  [b]     ->  a        | O(n)        | reduce     |            | args: binary op, accumulator init, sequence |
| fold left      | f  a  [b]     ->  a        | O(n)        | reduce     | accumulate | |
| fold right     | f  a  [b]     ->  a        | O(n)        | reduce     |            | `fold_right := fold_left (reverse B)` |
| fill           |    a          -> [a]       | O(n)        | scan       |            | |
| iota           |    a   a      -> [a]       | O(n)        | scan       |            | |
| inclusive scan | f  a  [b]     -> [a]       | O(n)        | scan       |            | |
| exclusive scan | f  a  [b]     -> [a]       | O(n)        | scan       |            | |
| find           | f [a]         -> int       | O(n)        | find       |            | |
| contains       | f [a]         -> bool      | O(n)        | find       |            | typically returns ptr instead of int, `contains F A   := (find F A) != (size A)` |
| mismatch       | f [a] [b]     -> (int,int) | O(n)        | find       |            | typically returns (ptr, ptr) instead of (int, int), `mismatch  F A B := find F (zip A B)` |
