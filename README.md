# eTM_finder
eTM_finder: a tool to predict eTMs (endogenous target mimics) of miRNAs in plants

This program is aim to predict target mimics in plants. It can be worked with Perl.
There are two steps to do for predicting:
a. If your sequences are RNAs
1) transform your fasta sequences to the ones we needed.
>usage: "perl transform_seq_2_need_S1.pl your_seq.fasta we_needed_seq.fasta";

2) find the eTMs of your miRNAs
>usage: "perl eTM_Finder(+)_S2.pl we_needed_seq.fasta your_miRNAs.fasta resut.txt";


b. If your sequences are DNAs(we don't know their direction of transcription)
1) transform your fasta sequences to the ones we needed.
>usage: "perl transform_seq_2_need_S1.pl your_seq.fasta plus_seq.fasta minus_seq.fasta";

2) find the eTMs of your miRNAs
>usage: "perl eTM_Finder(+)_S2.pl plus_seq.fasta your_miRNAs.fasta resut_plus.txt","perl eTM_Finder(+)_S2.pl minus_seq.fasta your_miRNAs.fasta resut_minus.txt";

result file would like this
>\>Chr1_37186146_37186795	62..85(+)	GCTGAAAGCTTGGGGAGGCAGCAG	>osa-miR444a-3p.1#osa-miR444d.1	CGTCGTTCGAAC---TCCGTCGTT	0
>\>Chr1_37186146_37187317	62..85(+)	GCTGAAAGCTTGGGGAGGCAGCAG	>osa-miR444a-3p.1#osa-miR444d.1	CGTCGTTCGAAC---TCCGTCGTT	0
>\>Chr2_15891727_15891997	1..23(+)	CAGGTGGTCGGCGGCGGCGACGA	>osa-miR5809	CGACACCAGC-G--GCCGCTGCT	0
>\>Chr4_25008800_25009129	118..141(+)	CATCAATGCTTAGCAATTCAATAC	>osa-miR397b	GTAGTTGCGA--CG-TGAGTTATT	2 G
>\>Chr5_21509938_21510235	120..143(+)	TCCCCGCGCGCGAACTCGGCGAGG	>osa-miR1848	ACGTGCGCGCGC---GGCCGCTCC	0
>\>Chr7_23991731_23991987	140..162(+)	GCGGTGGTGGACGTGGGCGACGA	>osa-miR5809	CGACACCAGC-G--GCCGCTGCT	0

explanation:
>for the first line, the '>Chr1_37186146_37186795' means the title of your input sequence;
 										the '62..85' means the location of eTM in your input seq, '(+)' means the strand is '+';
 										the 'GCTGAAAGCTTGGGGAGGCAGCAG' is the eTM binding sequence;
 										the '>osa-miR444a-3p.1#osa-miR444d.1	CGTCGTTCGAAC---TCCGTCGTT' means the miRNA and its binding state.
 										like this:
 										eTM seq 5' GCTGAAAGCTTGGGGAGGCAGCAG 3'
 										           ::o:o:::::::   ::::::::.
 									miRNA seq 3' CGTCGTTCGAAC---TCCGTCGTT 5' 
