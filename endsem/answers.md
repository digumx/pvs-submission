# Part 2:

 The proofs for both the lemma are marked in the `.pvs` file.

# Part 3:
## Question 1:

A representation of the proof using hoare logic given in the midsem is in the `hoar_logic_proofs.pvs` file. The program is slowly built using a series of program definitions. Then, the various invariants are expressed as a list of assertions. Using these, we write down the list of triples to be used in the proof. Finally, we express the hoare proof itself as a series of `preProof` objects, each dependent on the previous for definition. The correctness of the proof is expressed as using the return of the `Proof?` function on the constructed `preProof`.

## Question 2:

The proof is saved under the default proof name, `<lemma_name>-1`.

## Question 3:

The proof is saved as `Hoare_Completeness-2` and marked as active.

# Part 4:
## Question 1:

Excercise 3 is redone using verification conditions at the end of the `hoare_vcgen.pvs` file. The program was rewritten as `slow_div: annotatedProgram`, annotating the while loop with the invariant `x = r + y*z`. Then, the required pre-conditions and post-conditions is stated as `precond` and `postcond`. `precond` is always true, and `postcond` represents the condition when `x = r + y*z /\ r < y` holds. Using these, the correctness of the algorithm could be represented by the lemma `slow_div_correct`, which is of the form `triple_valid(...)`. 

Proving this lemma was done in three steps. Firstly, I showed that the `precond` is indeed obtained as the "straight-line" precondition from `postcond` for the given program. Then I applied `vc_pre` to obtain an goal of the form `vc(slow_div)`. Finally, I proved this goal by automatically expanding, splitting and rewriting using `(grind)`.

## Question 2:

The proof of `vc_pre` is marked and saved as `vc_pre-1`.

