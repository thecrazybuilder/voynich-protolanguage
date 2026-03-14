# Voynich Manuscript — Computational Italian Decipherment

A statistical approach to deciphering Beinecke MS 408 using hill climbing optimization, consonant skeleton matching, and folio-level vocabulary analysis.

## What this is

This project uses computational methods to test whether the Voynich Manuscript encodes Italian text. It is NOT a claimed solution. It is a statistical analysis with both positive and negative results, honestly reported.

## Key results

**Strongest finding:** The EVA word `shol` maps to Italian *miele* (honey), confirmed by two independent methods (hill climbing optimization AND consonant skeleton matching against LJS 419 cipher patterns). Honey appears 187 times across the manuscript, consistent with its central role in medieval Italian pharmacy.

**Hill climbing results:** Optimizing EVA-to-Italian character mappings via simulated annealing (1M iterations, 8 random restarts) produces 9 exact Italian word matches from 608 decoded words:

| EVA | Italian | English | Count |
|-----|---------|---------|-------|
| chedy | vino | wine | 69x |
| daiin | della | of the | 54x |
| shol | miele | honey | 7x |
| cthory | storeo | storax resin | 3x |

The same method against Hebrew produces only 1 exact match. Italian signal is 9x stronger.

**Negative result:** The f9v viola page test failed. No rare/unique word on folio 9v (confidently identified as *Viola tricolor*) has a consonant skeleton matching "viola." The word `chol` (skeleton `vl`) appears on f9v but occurs 397 times across 151 pages, ruling it out as a plant name.

## Consonant mapping

| EVA | Italian | Confidence |
|-----|---------|------------|
| sh | m | Very high (two methods) |
| ch | v | Very high (hill climbing) |
| l | l | Very high (stable) |
| t | s | High |
| k | r | High |
| d | n | High |
| q | p | High |

The vowel encoding is context-dependent (not monoalphabetic), consistent with the Naibbe cipher framework (Greshko 2025).

## Files

- `voynich_research.html` — Full research document (all 7 phases)
- `voynich_analysis.html` — Interactive statistical dashboard
- `voynich_decoder.html` — Three-method decipherment toolkit
- `voynich_f9v_words.json` — Folio 9v vocabulary analysis data
- `voynich_best_mapping.json` — Current best character mapping
- `voynich_forum_post.md` — Draft post for voynich.ninja forum

## Methods used

1. Frequency substitution (baseline)
2. Hill climbing with simulated annealing (1M iterations)
3. Compound token retokenization (76 tokens)
4. LJS 419 consonant skeleton matching
5. Constraint-based vowel deduction
6. Folio-level vocabulary analysis (voynichese.com data)

## Caveats

- Hill climbing always finds SOME matches. The 9x Italian-over-Hebrew advantage is meaningful but not conclusive.
- Gaskell & Bowern (2022) showed human gibberish can replicate Voynichese statistics.
- The f9v negative result is an honest finding that weakens one specific identification.
- This is a high school research project, not peer-reviewed scholarship.

## References

- Greshko, M.A. (2025). The Naibbe cipher. *Cryptologia*.
- Gaskell, D.E. & Bowern, C.L. (2022). Gibberish after all? *CEUR Workshop Proceedings*.
- Davis, L.F. (2020). Five scribes identification study.
- Bowern, C. & Lindemann, M. (2021). *Annual Review of Linguistics*.
- Petersen, J.K. Voynich Portal botanical identifications.
- Sherwood, E. Voynich botanical plant identifications.

## Data sources

- Takahashi EVA transcription via Landini-Stolfi Interlinear file
- Voynichese.com XML dataset (folio-level word frequencies)
- Yale Digital Collections (manuscript scans)

---

*Built by a high school student trying to crack a 600-year-old mystery. Feedback welcome.*
