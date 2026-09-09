# Item validity filter — trap kinds

A disease–drug pair can carry a clinical record without the drug ever having been given as
treatment of that disease. Joining identifiers cannot tell the difference; reading the record can.
This catalogue lists the kinds found so far. It is used before adjudication
([`docs/ITEM_CONSTRUCTION.md`](../docs/ITEM_CONSTRUCTION.md) §6) and during it
([`docs/ADJUDICATION.md`](../docs/ADJUDICATION.md) §4).

The list is not exhaustive. New kinds kept appearing in the last batches read when it was
compiled; a reader who meets one not listed here records it as `NEW TYPE:` in `notes`, and the
catalogue is extended with the next version. Finding a new kind is a normal result.

## A. Right disease, but the drug's role is not treatment

| Kind | What it looks like | Example |
|---|---|---|
| Conditioning before transplant or gene therapy; graft immunosuppression; GvHD prophylaxis | Alkylating agents and immunosuppressants attached to lysosomal, haematological or immunodeficiency diseases | One bone-marrow-transplant protocol produced busulfan and cyclophosphamide records across six different lysosomal diseases. The transplant is the treatment; the drugs are tools |
| Probe substrate in a drug-interaction study | A pharmacokinetic probe (midazolam for CYP3A4, itraconazole as inhibitor, celecoxib for CYP2C9) or a pharmacodynamic probe tagged with the sponsor's disease | One interaction study in healthy volunteers turned seven probe drugs into sickle-cell "indication" records |
| Premedication and toxicity rescue | Antipyretic or antihistamine before infusion; leucovorin with pyrimethamine; mesna with cyclophosphamide; seizure cover during conditioning | No endpoint of its own |
| Placebo or comparator arm | Sodium chloride and similar recorded as an indication | |
| Healthy volunteers under a disease tag | A phase-1 study registered under the intended indication while enrolling only healthy adults | Check the enrolled population, not the condition field |
| Given to every arm | A background drug both arms receive | A skin cleanser recorded for cystic fibrosis because both arms of an inhaled-antibiotic trial used it; the same trial supports a genuine record for the study drug |
| Imaging tracer, contrast agent, diagnostic reagent | | |

## B. The disease attachment itself is wrong

| Kind | What it looks like | Example |
|---|---|---|
| Identifier mis-expansion | A trial-condition string expanded to an unrelated rare disease | The string `"Fed"` (fed-state bioequivalence) expanded to *Fish-Eye Disease*, producing phase-1 records for antihistamines and antipsychotics |
| Acquired phenocopy under the inherited name | An autoantibody disease filed under the inherited gene's term | Acquired haemophilia A under `hemophilia A` |
| Subtype misattribution | A parent-disease record standing for a subtype the authorisation does not cover | A phase-4 flag on one Gaucher subtype where the authorisation covers another |

## C. The drug was not in the trial, or a different molecule was

| Kind | Example |
|---|---|
| Cited trial does not contain the drug | A cystic fibrosis record citing a trial whose only interventions were glutathione and saline |
| Precursor or analogue was studied | Niacinamide records citing nicotinamide-riboside trials |
| Class record standing in for one molecule | A cannabinoid-class entry whose Huntington record cites a THC + cannabidiol study in which that molecule was never given |
| Aggregator error | A drug-indication table recording an approval that exists nowhere else — treat a single-source claim with suspicion regardless of the source |

## D. Trial withdrawn after enrolling zero participants

The record exists; nobody received the drug.

## E. One label producing several indications

A single product label can generate separate records for each condition it mentions, only one of
which is authorised. Read the authorisation, not the mention count.

## Source-side notes that matter for every kind

- Synonym and trade-name fields in aggregated drug indexes are contaminated: a synonym search returns analogues. Identify by the primary name field.
- Records may sit on a salt or on the parent molecule. Follow the parent link both ways before concluding a drug has no record.
- A drug's approval can appear in a description field that the indication tables lack, and the same field can carry claims that are wrong. Read it; corroborate it.
- Orphan-designation *withdrawn* or *expired* does not mean development stopped.
