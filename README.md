# Surface Localisation Project (Wiita Lab)

## revising old IsExtracellular code
purpose: testing IsExtracellular script from Rucha's old repo: https://github.com/Rucha1796/IsExtracellular/blob/main/README.md to see if still working/has correct output
<br> still specifically for PTMs but made the following edits/debugs so is locally compatible:
#### updates:
- removed from google.colab import files (Colab-only import, doesn't exist locally)
- removed the files.download(updated_file_path) call at the end
- changed file paths from /content/... (Colab's default directory) to local relative paths (e.g., 'data/test_peptide.tsv')
- updated get_protein_sequence: https://www.uniprot.org/uniprot/{id}.fasta → https://rest.uniprot.org/uniprotkb/{id}.fasta
- Uupdated get_extracellular_domains: https://www.uniprot.org/uniprot/{id}.txt → https://rest.uniprot.org/uniprotkb/{id}.txt

#### bug fixes:
- added paranthesis around df_peptide['Assigned Modifications'].str.strip() != '' as it was being ignored from the &
- added .strip() into find_position_in_protein preventatively

## feature extraction
1. is extracellular? (in IsExtracellular)
2. Wollscheid surfaceome membership (in IsExtracellular)
3. KW-1003 cell membrane (in nat_comm_surface_database_1)
4. GO terms: 
