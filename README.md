[README.md](https://github.com/user-attachments/files/31695307/README.md)
# NGS Panel Lookup

A single-page reference tool for checking which targeted NGS panel covers a given gene, and with what type of analysis.

Type a gene symbol and the tool shows, for each panel, whether the gene is included and how it is interrogated: hotspot, full coding region, targeted exons, copy number, fusion or LOH. Panels that cover the gene are listed first; those that don't are collapsed into a single card underneath.

The tool has two faces, switched from the toggle in the header:

- **Solid tumour** — six panels
- **Haematology** — four panels

Each face searches only its own panels. Whatever is in the search box is kept and re-run when switching faces, so the same gene can be checked on both sides in one step.

## Panels included

### Solid tumour

Listed smallest first.

| Panel | Manufacturer | Genes |
|---|---|---|
| Ion AmpliSeq Colon and Lung Research Panel v2 | Thermo Fisher Scientific | 22 |
| Oncomine HRR Pathway Predesigned Panel | Thermo Fisher Scientific | 28 |
| Oncomine Precision Assay GX (OPA) | Thermo Fisher Scientific | 58 |
| Oncomine Comprehensive Assay v3 GX (OCA) | Thermo Fisher Scientific | 161 |
| Oncomine Childhood Cancer Research Assay | Thermo Fisher Scientific | 200 |
| OncoDEEP | OncoDNA | 638 |

### Haematology

| Panel | Manufacturer | Genes |
|---|---|---|
| Chronic Lymphocytic Leukaemia Solution | Sophia Genetics | 21 |
| Ion AmpliSeq Lymphoid Panel v2 | Thermo Fisher Scientific | 60 |
| Oncomine Myeloid Assay GX v2 | Thermo Fisher Scientific | 70 |
| Oncomine Childhood Cancer Research Assay | Thermo Fisher Scientific | 200 |

## Searching several genes at once

Press Enter, or click a suggestion, to turn a gene into a chip. Chips accumulate, so several genes can be compared side by side; each has an **×** to remove it, and Backspace on an empty box removes the last one.

With two or more genes, every panel card breaks down gene by gene, showing what each one covers and marking the rest as *not covered*. Within each card the covered genes are listed first, so the card reads top-down from what the panel does to what it misses. Two further cues make partial coverage visible at a glance:

- The coloured bar on the left of the card is proportional — the covered fraction keeps the panel's colour, the remainder turns grey.
- A small counter next to the panel name reads, for example, *2 of 3*. Panels covering every gene have a full bar and no counter.

## Requiring an analysis type

Clicking a gene chip opens a row of alteration types — hotspot, full coding, targeted exons, CNV, fusion, LOH — and selecting one or more sets a requirement for that gene alone. The requirement appears on the chip, and only panels meeting every requirement are listed; the rest move to the card at the bottom. Genes left without a requirement do not constrain the result.

Requirements are per gene because different genes are often needed in different ways. Asking for a CNV in one gene and a hotspot in another is a single question with one answer: which panel does both. The options offered match the alteration types present on the active face.

## Sort order

With more than one matching panel, a **Sort by** control appears above the results:

- **Recommended** (default) — panels covering the most requested genes first; where coverage is equal, the smaller panel comes first, since a narrower panel that answers the question is usually the cheaper choice.
- **Panel name** — alphabetical.

The choice persists across searches.

## Spike-in panel additions

Some panels have supplementary content added to the base design. Where a searched gene depends on such an addition, its analysis-type tag carries a small asterisk. Hover over it, or tap it on a touch screen, to see what the asterisk means for that gene:

- *Only in the spike-in version* — the gene is not part of the base panel and is covered solely through the supplementary content.
- *Expanded coverage in the spike-in version* — the gene is in the base panel, but the supplementary content extends the regions interrogated.

The asterisk sits on the tag of the gene it applies to, so in a multi-gene search it is always clear which gene is affected.

OPA currently carries eight spike-in genes (RB1, TERT, KEAP1, FOXL2, H3F3A, SMARCA4, STK11, POLE) and five with expanded coverage (FGFR2, FGFR3, HRAS, KRAS, PIK3CA). Confirm with the molecular laboratory that the spike-in content is in use before relying on it for a case.

## Targeted exon coverage

Some panels cover selected exons rather than whole genes. These carry a dashed **Targeted exons** tag — hover over it, or tap it on a touch screen, to see exactly which exons are covered for the gene searched. The same applies to the CNV tag in the CLL panel, where the cytogenetic locus is shown.

This matters: a variant falling outside the covered exons will not be detected, even though the gene appears in the panel.

## Gene synonyms

Where a gene is listed under a legacy symbol in one panel and its current symbol in another, both are searchable and resolve to the current symbol. Typing a legacy symbol shows it in the suggestions with an arrow to the current name.

## Notes

- The TERT spike-in on OPA is listed by the supplier as promoter coverage. Confirm the exact region with the molecular laboratory.
- Gene content reflects manufacturer specifications as of the version date shown in the footer of the tool. Panel composition changes between assay versions — check against the current specification sheet before relying on it for a case.
- OncoDEEP is a capture-based exonic assay: all genes are covered for SNV/INDEL, CNV and LOH. Fusions are detected only when the rearrangement falls within captured exonic regions. It additionally reports HRD, TMB and MSI.
- HRR, Colon and Lung v2 and Lymphoid v2 detect SNV/INDEL only. The CLL panel adds CNVs at defined loci. Myeloid GX v2 covers 17 genes across the full coding region, 28 at hotspots only, and screens a further set for known fusions.
- Promoter and other non-coding regions are generally not covered by exon-based designs. Where a promoter variant is clinically relevant, confirm coverage with the molecular laboratory.
- No targeted panel provides a genome-wide methylation class or chromosomal copy number profile.
- Panel size is used as a proxy for cost in the recommended sort order. Actual pricing depends on the contract with each supplier and is not reflected here.

## Use

The tool is a single self-contained HTML file with no external dependencies. It can be opened directly from disk or served as a static page. No data is transmitted or stored.

## Disclaimer

This is an internal reference aid. It does not replace the manufacturer's specification sheet or the report issued by the molecular pathology laboratory.
