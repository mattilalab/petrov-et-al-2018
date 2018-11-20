# Computational analysis of the evolutionarily conserved Missing In Metastasis / Metastasis Suppressor 1 gene predicts novel interactions, regulatory regions and transcriptional control

Petrov _et al_ 2018 (MANUSCRIPT)

Home-brewed shell scripts

These simple shell scripts were tested on Slackware GNU/Linux (http://www.slackware.com/). All prerequisites were installed from the scripts at SlackBuilds.org (http://slackbuilds.org).

## Prerequisites

You need the following:

1.  **RepeatMasker** (Screen DNA sequence for interspersed repeats)
    * Homepage: http://www.repeatmasker.org/
    * On SBo: http://slackbuilds.org/repository/14.2/academic/RepeatMasker/
2.  **BedTools** (A powerful toolset for genome arithmetic)
    * Homepage: http://bedtools.readthedocs.org/
    * On SBo: http://slackbuilds.org/repository/14.2/academic/bedtools/
3.  **MEME-suite** (Motif based sequence analysis tools)
    * Homepage: http://meme-suite.org/
    * On SBo: http://slackbuilds.org/repository/14.2/academic/meme-suite/
4.  **Motif databases** (Used by the MEME Suite)
    * Download: http://meme-suite.org/doc/download.html
    * Location: /var/lib/meme-suite/motif_databases

## Contents

Scripts are divided into two folders:

1.   **tfKnown**: This folder contains scripts that were used in our study (Petrov _et al_ 2018, MANUSCRIPT) to acquire data for transcription factor (TF) binding sequences. We used TFs reported for H. sapiens to also screen the corresponding genomic regions of other species.

2.   **tfUnknown**:

**Please note!**

This is work in progress. We are in the process of commenting our home-made scripts. We expect it to be ready till 23 November!
