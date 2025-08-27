
Precision, Recall, FPR, FNR:
Precision = TP / (TP + FP), FPR = FP / (TP + FP), FPR + Precision = 1
Recall = TP / (TP + FN), FNR = FN / (TP + FN), FNR + Recall = 1
F-score = 2 * (Precision * Recall) / (Precision + Recall)

Soundness & Completeness:
Now let’s look at effectiveness. As we saw in the divide-by-zero examples, a dynamic analysis may miss errors, as it inspects only a finite number of runs, whereas the program may contain an unbounded number of paths, some of which are not covered by those runs. We say that a dynamic analysis is inherently “unsound”: in other words, it may produce false negatives. On the other hand, it is possible to design a static analysis that does not miss errors, but such an analysis may report spurious errors. We say that a static analysis is inherently “incomplete”: in other words, it may produce false positives.
Soundness: FPR = 0, Precision = 1
Completeness: FNR = 0, Recall = 1


Who needs software analysis: 
Compiler, Software quality tools, IDEs


Dynamic Analysis:
array bounding checking: Purify; 
memory leak detection: Valgrind; 
datarace detection: Eraser;
finding likely invariants: Daikon;

Static Analysis:
Suspicious error patterns: 



