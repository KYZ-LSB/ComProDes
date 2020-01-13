This README file is for calculating the scores mentioned in Protein Sequence Fitness Function

For details about the scores please refer to

Kaushik, R. and Zhang K.Y. (2020). A Protein Sequence Fitness Function for Identifying Natural and Non-Natural Proteins

Details of Directories and Files:

(A) In the "./data" directory, there are three files with ".dat" extension.
	(a) CS-SCORE_REFERENCE.dat : This file as the CS-Score values for all the possible tripeptides (8000 triplets). 
					These values are used for calculation of CS-Score for an input protein sequence
							 	 and its identification as natural or non-natural proteins.
	(b) CSS-SCORE_REFERENCE.dat: This file as the CSS-Score values for all the possible tripeptides (8000 triplets) 
								 with all available combinations of secondary structural triplets. These values are 
								 used for calculation of CSS-Score for an input protein sequence and its identification
								 as natural or non-natural proteins.
	(c) PER_RES_CUTOFFS.dat :	This file contains the information about percentage number of proteins in reference 
								datasets scoring below a certain number residues scoring below the threshold values 
								of CS- and CSS-Scores. These values are used in quantifying the extent of mimicking 
								of an input protein as natural or non-natural protein.
(B) SEQUENCE_FITNESS.sh
		This is main shell script which perform all the calculations required for implementing the purposed method for
		identifying natural and non-natural proteins. The script is written in self-explanatory way and do not require any
		expertise for understanding. Also, the script can be easily followed for developing its equivalents in other programming
		or scripting language as per user's convenience. The script can be executed by providing the basename of input protein
		sequence.
		
			INPUTS : Directory name of the input protein sequence (e.g. ABC), the directory should have the protein sequence 
                                 and corresponding secondary structure in fasta format (e.g. ABC.fasta) as shown below:

				 >ABC:SEQ
				 KLNVRIRDSDQNKLQKALKKFIELARKSNGTITKTYTGTDLEIQITNIT
				 >ABC:SEC
				 CCCEEEECCCHHHHHHHHHHHHHHHHHCCCEEEEEEECCEEEEEEECCC

			OUTPUTS: The successful execution of script will generate two output files 
					i) *.SQSS (e.g. ABC.SQSS): This file contains the CS- (2nd column) and CSS-Scores (3rd Column)
								   for each tripeptide (1st column) in the input sequence.
								   e.g.
									KLN-CCC         26.08           10.83
									LNV-CCE         54.12           18.36
									NVR-CEE         16.58           4.00
									VRI-EEE         31.30           37.68
									RIR-EEE         25.10           5.58
                                   For CS-Score calculation, only sequence information is used while for 
								   CSS-Score calculation, sequence and secondary structural information is used.

					ii) *.DAT (e.g. ABC.DAT): This file have average CS-Score for input protein (2nd column), percentage number
								  of residues scoring below the CS-Score threshold (3rd column), average CSS-Score (4th column)
								  and the percentage number of residues scoring below the CSS-Score threshold (5th column).
								  Based on these values, the final prediction of input protein as natural or non-natural is done.  


In case of any query or suggestion, please contact

Dr. Kam Y. Zhang,
Laboratory for Structural Bioinformatics,
Biosystems Dynamics Researech Center,
RIKEN, Yokohama, Japan
Email: kamzhang@riken.jp

Or

Dr. Rahul Kaushik,
Laboratory for Structural Bioinformatics,
Biosystems Dynamics Researech Center,
RIKEN, Yokohama, Japan
Email: rahul.kaushik@riken.jp
