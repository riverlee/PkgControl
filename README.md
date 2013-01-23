Table of Content
================
* [Overview](#overview)
* [Configure] (#configure)
  * [.bash_profile]  (#profile)
  * [.bashrc] (#bashrc)
* [Usage] (#usage)
  * [List all packages] (#listall)
  * [List latest packages] (#latest)
  * [List current used packages] (#current)
  * [Change a  package to another version] (#change)
  * [Reset packages to the latest versions] (#reset)
  * [Search a package] (#search)
 

<a name="overview"/>

Overview
----------------------
PkgControl is a set of perl and shell scripts for package control between different versions.


<a name="configure"/>

Configure
----------------------
Suppose you are currently using **bash** as your default shell (The default shell on accre). Here are the two steps to do.

* Modify .bash_profile
* Modify .bashrc

<a name="profile"/>

### .bash_profile

At your home directory, add the following lines at the **end** of your **.bash_profile** file (create it if not exists)

```bash
if [ -f ~/.bashrc ]; then
    . ~/.bashrc
fi

```

<a name="bashrc"/>

### .bashrc

Then add the following lines at the **end** of your **.bashrc** file (create it if not exists)

```bash
export PATH=/scratch/cqs/lij17/softwares:$PATH
source /scratch/cqs/lij17/softwares/cqspkgs.sh
cqspkgs -reset

```



<a name="usage"/>
Usage
----------------------

```bash
#This output all the packages together with the help
cqspkgs
```
Details for each parameters are here

```bash
Usage: cqspkgs [-d DIR] [-s key ] [-listall ] [-current] [-latest]  [-reset ] [-c name] [-v version] [-h|-help]

cqspkg manipulates the software between versions for cqs users
================================================================
-d DIR      Change the default package configure directory to DIR.
-s key      Search softwares with your searching key
-c name     Change the software with provided name and version (need to provide version by -v)
-v version  Provide the software version
-listall    List all avialable softwares
-current    List current softwares used in your $PATH
-latest     List the latest softwares
-reset      Set the softwares to the latest version
-h|-help    display this help page

```

<a name="listall"/>

### List all packages

```bash
cqspkgs -listall
```

Output

```
All avaialbe softwares
Name                  Version     Base                                                          Description
====================================================================================================
bowtie                V0.12.9     /scratch/cqs/lij17/softwares/bin/bowtie-0.12.9                ultrafast, memory-efficient short read aligner
bowtie2               V2.0.5      /scratch/cqs/lij17/softwares/bin/bowtie2-2.0.5                ultrafast and memory-efficient tool for aligning sequencing reads to long reference sequences
bwa                   V0.6.2      /scratch/cqs/lij17/softwares/bin/bwa-0.6.2                    Burrows-Wheeler Aligner (BWA)
cufflinks             V2.0.2      /scratch/cqs/lij17/softwares/bin/cufflinks-2.0.2.Linux_x86_64  Cufflinks assembles transcripts, estimates their abundances, etc.
fastQC                V0.10.1     /scratch/cqs/lij17/softwares/bin/FastQC                       A quality control application for high throughput sequence data
plink                 V1.07       /scratch/cqs/lij17/softwares/bin/plink-1.07-x86_64            a free, open-source whole genome association analysis toolset
samtools              V0.1.18     /scratch/cqs/lij17/softwares/bin/samtools-0.1.18              SAM Tools provide various utilities for manipulating alignments in the SAM format  
tophat                V2.0.6      /scratch/cqs/lij17/softwares/bin/tophat-2.0.6.Linux_x86_64    Fast splice junction mapper for RNA-Seq reads
tophat                V1.3.1      /scratch/cqs/lij17/softwares/bin/tophat-1.3.1.Linux_x86_64    Fast splice junction mapper for RNA-Seq reads
vcftools              V0.1.10     /scratch/cqs/lij17/softwares/bin/vcftools_0.1.10              a program package designed for working with VCF files

```

<a name="latest"/>

### List latest packages

```bash
cqspkgs -lastest
```

Output

```
All the lastest softwares
Name                  Version     Base                                                          Description
====================================================================================================
bowtie                V0.12.9     /scratch/cqs/lij17/softwares/bin/bowtie-0.12.9                ultrafast, memory-efficient short read aligner
bowtie2               V2.0.5      /scratch/cqs/lij17/softwares/bin/bowtie2-2.0.5                ultrafast and memory-efficient tool for aligning sequencing reads to long reference sequences
bwa                   V0.6.2      /scratch/cqs/lij17/softwares/bin/bwa-0.6.2                    Burrows-Wheeler Aligner (BWA)
cufflinks             V2.0.2      /scratch/cqs/lij17/softwares/bin/cufflinks-2.0.2.Linux_x86_64  Cufflinks assembles transcripts, estimates their abundances, etc.
fastQC                V0.10.1     /scratch/cqs/lij17/softwares/bin/FastQC                       A quality control application for high throughput sequence data
plink                 V1.07       /scratch/cqs/lij17/softwares/bin/plink-1.07-x86_64            a free, open-source whole genome association analysis toolset
samtools              V0.1.18     /scratch/cqs/lij17/softwares/bin/samtools-0.1.18              SAM Tools provide various utilities for manipulating alignments in the SAM format  
tophat                V2.0.6      /scratch/cqs/lij17/softwares/bin/tophat-2.0.6.Linux_x86_64    Fast splice junction mapper for RNA-Seq reads
vcftools              V0.1.10     /scratch/cqs/lij17/softwares/bin/vcftools_0.1.10              a program package designed for working with VCF files
```

<a name="current"/>

### List current used packages

```bash
cqspkgs -current
```

Output

```
All the current used softwares
Name                  Version     Base                                                          Description
====================================================================================================
bowtie                V0.12.9     /scratch/cqs/lij17/softwares/bin/bowtie-0.12.9                ultrafast, memory-efficient short read aligner
bowtie2               V2.0.5      /scratch/cqs/lij17/softwares/bin/bowtie2-2.0.5                ultrafast and memory-efficient tool for aligning sequencing reads to long reference sequences
bwa                   V0.6.2      /scratch/cqs/lij17/softwares/bin/bwa-0.6.2                    Burrows-Wheeler Aligner (BWA)
cufflinks             V2.0.2      /scratch/cqs/lij17/softwares/bin/cufflinks-2.0.2.Linux_x86_64  Cufflinks assembles transcripts, estimates their abundances, etc.
fastQC                V0.10.1     /scratch/cqs/lij17/softwares/bin/FastQC                       A quality control application for high throughput sequence data
plink                 V1.07       /scratch/cqs/lij17/softwares/bin/plink-1.07-x86_64            a free, open-source whole genome association analysis toolset
samtools              V0.1.18     /scratch/cqs/lij17/softwares/bin/samtools-0.1.18              SAM Tools provide various utilities for manipulating alignments in the SAM format  
tophat                V2.0.6      /scratch/cqs/lij17/softwares/bin/tophat-2.0.6.Linux_x86_64    Fast splice junction mapper for RNA-Seq reads
vcftools              V0.1.10     /scratch/cqs/lij17/softwares/bin/vcftools_0.1.10              a program package designed for working with VCF files

```

<a name="change"/>

### Change a pacakge to another version

```bash
cqspkgs -c tophat -v V1.3.1

#See which tophat you are current using
which tophat
#Or by
cqspkgs -current
````

<a name="reset"/>

### Reset packages to latest versions

```bash
cqspkgs -reset
#see all the current used packages
cqspkgs -current
```


<a name="search"/>

### Search packages

```bash
cqspkgs -s tophat
```

Output

```
All avaialbe softwares with searching key 'tophat' 
Name                  Version     Base                                                          Description
====================================================================================================
tophat                V2.0.6      /scratch/cqs/lij17/softwares/bin/tophat-2.0.6.Linux_x86_64    Fast splice junction mapper for RNA-Seq reads
tophat                V1.3.1      /scratch/cqs/lij17/softwares/bin/tophat-1.3.1.Linux_x86_64    Fast splice junction mapper for RNA-Seq reads
```




