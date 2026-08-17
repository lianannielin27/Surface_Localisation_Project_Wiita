# Surface Localisation Project (Wiita Lab)

## Revising old IsExtracellular code
purpose: testing IsExtracellular script from Rucha's old repo: https://github.com/Rucha1796/IsExtracellular/blob/main/README.md to see if still working/has correct output
<br> still specifically for PTMs but made the following edits/debugs so is locally compatible:
#### updates:
- Removed from google.colab import files (Colab-only import, doesn't exist locally)
- Removed the files.download(updated_file_path) call at the end
- Changed file paths from /content/... (Colab's default directory) to local relative paths (e.g., 'data/test_peptide.tsv')
- Updated get_protein_sequence: https://www.uniprot.org/uniprot/{id}.fasta → https://rest.uniprot.org/uniprotkb/{id}.fasta
- Updated get_extracellular_domains: https://www.uniprot.org/uniprot/{id}.txt → https://rest.uniprot.org/uniprotkb/{id}.txt

#### bug fixes:
- added paranthesis around df_peptide['Assigned Modifications'].str.strip() != '' as it was being ignored from the &
- added .strip() into find_position_in_protein preventatively
