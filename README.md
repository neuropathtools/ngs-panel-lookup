[README (1).md](https://github.com/user-attachments/files/30830048/README.1.md)
# NGS Panel Lookup

A single-page reference tool for checking which targeted NGS panel covers a given gene, and with what type of analysis.

Type a gene symbol and the tool shows, for each panel, whether the gene is included and how it is interrogated: hotspot, full coding region, targeted exons, copy number, fusion or LOH. Panels that do cover the gene are listed first; those that don't are collapsed into a single line underneath.

The tool has two faces, switched from the toggle in the header:

- **Solid tumour** — six panels
- **Haematology** — three panels

Each face searches only its own panels.

## Panels included

### Solid tumour

| Panel | Manufacturer | Genes |
|---|---|---|
| Oncomine Precision Assay GX (OPA) | Thermo Fisher Scientific | 50 |
| Oncomine Comprehensive Assay v3 GX (OCA) | Thermo Fisher Scientific | 161 |
| Oncomine Childhood Cancer Research Assay | Thermo Fisher Scientific | 200 |
| OncoDEEP | OncoDNA | 638 |
| Oncomine HRR Pathway Predesigned Panel | Thermo Fisher Scientific | 28 |
| Ion AmpliSeq Colon and Lung Research Panel v2 | Thermo Fisher Scientific | 22 |

### Haematology

| Panel | Manufacturer | Genes |
|---|---|---|
| Ion AmpliSeq Lymphoid Panel v2 | Thermo Fisher Scientific | 60 |
| Chronic Lymphocytic Leukaemia Solution | Sophia Genetics | 21 |
| Oncomine Childhood Cancer Research Assay | Thermo Fisher Scientific | 200 |

## Targeted exon coverage

Some panels cover selected exons rather than whole genes. These carry a dashed **Targeted exons** tag — hover over it, or tap it on a touch screen, to see exactly which exons are covered for the gene you searched. The same applies to the CNV tag in the CLL panel, where the cytogenetic locus is shown.

This matters: a variant falling outside the covered exons will not be detected, even though the gene appears in the panel.

## Gene synonyms

Where a gene is listed under a legacy symbol in one panel and its current symbol in another, both are searchable and resolve to the current symbol. Typing a legacy symbol shows it in the suggestions with an arrow to the current name.

## Notes

- Gene content reflects manufacturer specifications as of the version date shown in the footer of the tool. Panel composition changes between assay versions — check against the current specification sheet before relying on it for a case.
- OncoDEEP is a capture-based exonic assay: all genes are covered for SNV/INDEL, CNV and LOH. Fusions are detected only when the rearrangement falls within captured exonic regions. It additionally reports HRD, TMB and MSI.
- HRR, Colon and Lung v2, Lymphoid v2 detect SNV/INDEL only. The CLL panel adds CNVs at defined loci.
- Promoter and other non-coding regions are generally not covered by exon-based designs. Where a promoter variant is clinically relevant, confirm coverage with the molecular laboratory.
- No targeted panel provides a genome-wide methylation class or chromosomal copy number profile.

## Use

The tool is a single self-contained HTML file with no external dependencies. It can be opened directly from disk or served as a static page. No data is transmitted or stored.

## Disclaimer

This is an internal reference aid. It does not replace the manufacturer's specification sheet or the report issued by the molecular pathology laboratory.
