# nf-core/fetchngs: Changelog

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/)
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [[1.10.1](https://github.com/nf-core/fetchngs/releases/tag/1.10.1)] - 2023-10-08

### Credits

Special thanks to the following for their contributions to the release:

- [Adam Talbot](https://github.com/adamrtalbot)
- [Harshil Patel](https://github.com/drpatelh)
- [Maxime Garcia](https://github.com/maxulysse)
- [Rob Syme](https://github.com/robsyme)

Thank you to everyone else that has contributed by reporting bugs, enhancements or in any other way, shape or form.

### Enhancements & fixes

- [#173](https://github.com/nf-core/fetchngs/issues/173) - Add compatibility for sralite files
- [PR #205](https://github.com/nf-core/fetchngs/pull/205) - Rename all local modules, workflows and remove `public_aws_ecr profile`
- [PR #206](https://github.com/nf-core/fetchngs/pull/206) - CI improvments and code cleanup
- [PR #208](https://github.com/nf-core/fetchngs/pull/208) - Template update with nf-core/tools 2.10

### Software dependencies

| Dependency  | Old version | New version |
| ----------- | ----------- | ----------- |
| `sra-tools` | 2.11.0      | 3.0.8       |

> **NB:** Dependency has been **updated** if both old and new version information is present.
>
> **NB:** Dependency has been **added** if just the new version information is present.
>
> **NB:** Dependency has been **removed** if new version information isn't present.

## [[1.10.0](https://github.com/nf-core/fetchngs/releases/tag/1.10.0)] - 2023-05-16

### Credits

Special thanks to the following for their contributions to the release:

- [Adam Talbot](https://github.com/adamrtalbot)
- [Esha Joshi](https://github.com/ejseqera)
- [Maxime Garcia](https://github.com/maxulysse)
- [Moritz E. Beber](https://github.com/Midnighter)
- [Rob Syme](https://github.com/robsyme)
- [sirclockalot](https://github.com/sirclockalot)

Thank you to everyone else that has contributed by reporting bugs, enhancements or in any other way, shape or form.

### Enhancements & fixes

- [#85](https://github.com/nf-core/fetchngs/issues/85) - Not able to fetch metadata for ERR ids associated with ArrayExpress
- [#104](https://github.com/nf-core/fetchngs/issues/104) - Add support back in for [GEO IDs](https://www.ncbi.nlm.nih.gov/geo) (removed in v1.7)
- [#129](https://github.com/nf-core/fetchngs/issues/129) - Pipeline is working with SRA run ids but failing with corresponding Biosample ids
- [#138](https://github.com/nf-core/fetchngs/issues/138) - Add support for downloading protected dbGAP data using a JWT file
- [#144](https://github.com/nf-core/fetchngs/issues/144) - Add support to download 10X Genomics data
- [PR #140](https://github.com/nf-core/fetchngs/pull/140) - Bumped modules version to allow for sratools download of sralite format files
- [PR #147](https://github.com/nf-core/fetchngs/pull/147) - Updated pipeline template to [nf-core/tools 2.8](https://github.com/nf-core/tools/releases/tag/2.8)
- [PR #148](https://github.com/nf-core/fetchngs/pull/148) - Fix default metadata fields for ENA API v2.0
- [PR #150](https://github.com/nf-core/fetchngs/pull/150) - Add infrastructure and CI for multi-cloud full-sized tests run via Nextflow Tower
- [PR #157](https://github.com/nf-core/fetchngs/pull/157) - Add `public_aws_ecr.config` to source mulled containers when using `public.ecr.aws` Docker Biocontainer registry

### Software dependencies

| Dependency      | Old version | New version |
| --------------- | ----------- | ----------- |
| `synapseclient` | 2.6.0       | 2.7.1       |

> **NB:** Dependency has been **updated** if both old and new version information is present.
>
> **NB:** Dependency has been **added** if just the new version information is present.
>
> **NB:** Dependency has been **removed** if new version information isn't present.

## [[1.9](https://github.com/nf-core/fetchngs/releases/tag/1.9)] - 2022-12-21

### Enhancements & fixes

- Bumped minimum Nextflow version from `21.10.3` -> `22.10.1`
- Updated pipeline template to [nf-core/tools 2.7.2](https://github.com/nf-core/tools/releases/tag/2.7.2)
- Added support for generating nf-core/atacseq compatible samplesheets
- Added `--nf_core_rnaseq_strandedness` parameter to specify value for `strandedness` entry added to samplesheet created when using `--nf_core_pipeline rnaseq`. The default is `auto` which can be used with nf-core/rnaseq v3.10 onwards to auto-detect strandedness during the pipeline execution.

## [[1.8](https://github.com/nf-core/fetchngs/releases/tag/1.8)] - 2022-11-08

### Enhancements & fixes

- [#111](https://github.com/nf-core/fetchngs/issues/111) - Change input mimetype to csv
- [#114](https://github.com/nf-core/fetchngs/issues/114) - Final samplesheet is not created when `--skip_fastq_download` is provided
- [#118](https://github.com/nf-core/fetchngs/issues/118) - Allow input pattern validation for csv/tsv/txt
- [#119](https://github.com/nf-core/fetchngs/issues/119) - `--force_sratools_download` results in different fastq names compared to FTP download
- [#121](https://github.com/nf-core/fetchngs/issues/121) - Add `tower.yml` to render samplesheet as Report in Tower
- Fetch `SRR` and `DRR` metadata from ENA API instead of NCBI API to bypass frequent breaking changes
- Updated pipeline template to [nf-core/tools 2.6](https://github.com/nf-core/tools/releases/tag/2.6)

## [[1.7](https://github.com/nf-core/fetchngs/releases/tag/1.7)] - 2022-07-01

### :warning: Major enhancements

Support for GEO ids has been dropped in this release due to breaking changes introduced in the NCBI API. For more detailed information please see [this PR](https://github.com/nf-core/fetchngs/pull/102).

As a workaround, if you have a GEO accession you can directly download a text file containing the appropriate SRA ids to pass to the pipeline:

- Search for your GEO accession on [GEO](https://www.ncbi.nlm.nih.gov/geo)
- Click `SRA Run Selector` at the bottom of the GEO accession page
- Select the desired samples in the `SRA Run Selector` and then download the `Accession List`

This downloads a text file called `SRR_Acc_List.txt` that can be directly provided to the pipeline e.g. `--input SRR_Acc_List.txt`.

### Enhancements & fixes

- [#97](https://github.com/nf-core/fetchngs/pull/97) - Add support for generating nf-core/taxprofiler compatible samplesheets.
- [#99](https://github.com/nf-core/fetchngs/issues/99) - SRA_IDS_TO_RUNINFO fails due to bad request
- Add `enum` field for `--nf_core_pipeline` to parameter schema so only accept supported pipelines are accepted

## [[1.6](https://github.com/nf-core/fetchngs/releases/tag/1.6)] - 2022-05-17

- [#57](https://github.com/nf-core/fetchngs/pull/57) - fetchngs fails if FTP is blocked
- [#89](https://github.com/nf-core/fetchngs/pull/89) - Improve detection and usage of the NCBI user settings by using the standardized sra-tools modules from nf-core.
- [#93](https://github.com/nf-core/fetchngs/pull/93) - Adjust modules configuration to respect the `publish_dir_mode` parameter.
- [[nf-core/rnaseq#764](https://github.com/nf-core/rnaseq/issues/764)] - Test fails when using GCP due to missing tools in the basic biocontainer
- Updated pipeline template to [nf-core/tools 2.4.1](https://github.com/nf-core/tools/releases/tag/2.4.1)

### Software dependencies

| Dependency      | Old version | New version |
| --------------- | ----------- | ----------- |
| `synapseclient` | 2.4.0       | 2.6.0       |

## [[1.5](https://github.com/nf-core/fetchngs/releases/tag/1.5)] - 2021-12-01

- Finish porting the pipeline to the updated Nextflow DSL2 syntax adopted on nf-core/modules
  - Bump minimum Nextflow version from `21.04.0` -> `21.10.3`
  - Removed `--publish_dir_mode` as it is no longer required for the new syntax

### Enhancements & fixes

## [[1.4](https://github.com/nf-core/fetchngs/releases/tag/1.4)] - 2021-11-09

### Enhancements & fixes

- Convert pipeline to updated Nextflow DSL2 syntax for future adoption across nf-core
- Added a workflow to download FastQ files and to create samplesheets for ids from the [Synapse platform](https://www.synapse.org/) hosted by [Sage Bionetworks](https://sagebionetworks.org/).
- SRA identifiers not available for direct download via the ENA FTP will now be downloaded via [`sra-tools`](https://github.com/ncbi/sra-tools).
- Added `--force_sratools_download` parameter to preferentially download all FastQ files via `sra-tools` instead of ENA FTP.
- Correctly handle errors from SRA identifiers that do **not** return metadata, for example, due to being private.
- Retry an error in prefetch via bash script in order to allow it to resume interrupted downloads.
- Name output FastQ files by `{EXP_ACC}_{RUN_ACC}*fastq.gz` instead of `{EXP_ACC}_{T*}*fastq.gz` for run id provenance
- [[#46](https://github.com/nf-core/fetchngs/issues/46)] - Bug in sra_ids_to_runinfo.py
- Added support for [DDBJ ids](https://www.ddbj.nig.ac.jp/index-e.html). See examples below:

| `DDBJ`       |
| ------------ |
| PRJDB4176    |
| SAMD00114846 |
| DRA008156    |
| DRP004793    |
| DRR171822    |
| DRS090921    |
| DRX162434    |

## [[1.3](https://github.com/nf-core/fetchngs/releases/tag/1.3)] - 2021-09-15

### Enhancements & fixes

- Replaced Python `requests` with `urllib` to fetch ENA metadata

### Software dependencies

| Dependency | Old version | New version |
| ---------- | ----------- | ----------- |
| `python`   | 3.8.3       | 3.9.5       |

## [[1.2](https://github.com/nf-core/fetchngs/releases/tag/1.2)] - 2021-07-28

### Enhancements & fixes

- Updated pipeline template to [nf-core/tools 2.1](https://github.com/nf-core/tools/releases/tag/2.1)
- [[#26](https://github.com/nf-core/fetchngs/pull/26)] - Update broken EBI API URL

## [[1.1](https://github.com/nf-core/fetchngs/releases/tag/1.1)] - 2021-06-22

### Enhancements & fixes

- [[#12](https://github.com/nf-core/fetchngs/issues/12)] - Error when using singularity - /etc/resolv.conf doesn't exist in container
- Added `--sample_mapping_fields` parameter to create a separate `id_mappings.csv` and `multiqc_config.yml` with selected fields that can be used to rename samples in general and in [MultiQC](https://multiqc.info/docs/#bulk-sample-renaming)

## [[1.0](https://github.com/nf-core/fetchngs/releases/tag/1.0)] - 2021-06-08

Initial release of nf-core/fetchngs, created with the [nf-core](https://nf-co.re/) template.

## Pipeline summary

Via a single file of ids, provided one-per-line the pipeline performs the following steps:

1. Resolve database ids back to appropriate experiment-level ids and to be compatible with the [ENA API](https://ena-docs.readthedocs.io/en/latest/retrieval/programmatic-access.html)
2. Fetch extensive id metadata including direct download links to FastQ files via ENA API
3. Download FastQ files in parallel via `curl` and perform `md5sum` check
4. Collate id metadata and paths to FastQ files in a single samplesheet

## Supported database ids

Currently, the following types of example identifiers are supported:

| `SRA`        | `ENA`        | `GEO`      |
| ------------ | ------------ | ---------- |
| SRR11605097  | ERR4007730   | GSM4432381 |
| SRX8171613   | ERX4009132   | GSE147507  |
| SRS6531847   | ERS4399630   |            |
| SAMN14689442 | SAMEA6638373 |            |
| SRP256957    | ERP120836    |            |
| SRA1068758   | ERA2420837   |            |
| PRJNA625551  | PRJEB37513   |            |
