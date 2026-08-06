[README.md](https://github.com/user-attachments/files/30790251/README.md)

# NGS Panel Lookup

A single-page reference tool for checking which targeted NGS panel covers a given gene, and with what type of analysis.

Type a gene symbol and the tool shows, for each panel, whether the gene is included and how it is interrogated: hotspot, full coding region, copy number, fusion or LOH.

## Panels included

| Panel | Manufacturer | Genes |
|---|---|---|
| Oncomine Precision Assay GX (OPA) | Thermo Fisher Scientific | 50 |
| Oncomine Comprehensive Assay v3 GX (OCA) | Thermo Fisher Scientific | 161 |
| Oncomine Childhood Cancer Research Assay | Thermo Fisher Scientific | 200 |
| OncoDEEP | OncoDNA | 638 |

## Notes

- Gene content reflects manufacturer specifications as of the version date shown in the footer of the tool. Panel composition changes between assay versions — check against the current specification sheet before relying on it for a case.
- OncoDEEP is a capture-based exonic assay: all genes are covered for SNV/INDEL, CNV and LOH. Fusions are detected only when the rearrangement falls within captured exonic regions. It additionally reports HRD, TMB and MSI.
- Promoter and other non-coding regions are generally not covered by exon-based designs. Where a promoter variant is clinically relevant, confirm coverage with the molecular laboratory.
- No targeted panel provides a genome-wide methylation class or chromosomal copy number profile.

## Use

The tool is a single self-contained HTML file with no external dependencies. It can be opened directly from disk or served as a static page. No data is transmitted or stored.

## Disclaimer

This is an internal reference aid. It does not replace the manufacturer's specification sheet or the report issued by the molecular pathology laboratory.

