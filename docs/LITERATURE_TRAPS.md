# Literature traps

Ways a literature record misleads a reader. Used by extraction prompts and by auditors. The variant
section lists kinds expected from the variant-reporting literature; the pilot confirms, removes or
adds kinds, and a reader who meets a kind not listed records it as `NEW TYPE:`.

## Disease attribution

| Kind | Example |
|---|---|
| Acquired phenocopy under the inherited name | An autoantibody disease filed under the inherited gene's disease term |
| Subtype misattribution | A record for one subtype attached to the parent disease or another subtype |
| Identifier mis-expansion | A trial-condition string such as "Fed" (fed-state bioequivalence) expanded to an unrelated rare disease |
| Same variant, different disease names | One variant reported under a clinical name in one paper and a gene-based name in another |

## Variant reporting

| Kind | What to check |
|---|---|
| Legacy names | ΔF508 is p.Phe508del in CFTR; a legacy name must be normalized before comparison |
| Legacy numbering | Numbering that omits the initiator methionine (haemoglobin S is β6 in legacy numbering and p.Glu7Val in HGVS) |
| Non-MANE transcript | The same variant has a different c. position on another transcript |
| Protein-only notation | One p. change can come from more than one c. change |
| Genome build | Genomic coordinates on GRCh37 and GRCh38 differ |
| Incomplete genotype | A compound-heterozygous patient whose paper discusses one variant |
| Prediction reported as function | In silico prediction presented alongside, or in place of, a functional study |
| Non-segregating or incidental finding | A variant found in a cohort without segregation, or reported as incidental |
| Supplement-only tables | The variant list sits in a supplement that may not be open access |
| Repeated reporting | The same family or cohort described in several papers |

## Therapy records

Relevant to V6.

| Kind | Example |
|---|---|
| Procedure drug | Conditioning before transplant or gene therapy, graft immunosuppression |
| Probe substrate | A drug given only to measure an interaction, tagged with the sponsor's disease |
| Placebo or comparator arm | A placebo recorded as an indication |
| Given to every arm | A background drug both arms receive |
| Healthy volunteers | A phase 1 study registered under the intended indication |
| Different molecule studied | A precursor or analogue of the named drug |
| One label, several indications | A single product label producing records for conditions it does not authorise |

## Evidence counting

- A review is not a primary report; trace it to the paper it cites.
- A citation of a trial number may be there to say that no such trial exists.
- A record existing in a database is not evidence of what the record claims; read it.
