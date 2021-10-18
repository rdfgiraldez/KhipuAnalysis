# KhipuAnalysis
Exploratory Data Analysis of khipus from the Aschers' "Code of the Quipu: Databook", Pereyra's book "Quipus del Museo del Sitio Pachacamac" and Harvard's Khipu Database. 

"Lineplot with cord values" folder contains graphs depicting x=INVESTIGATOR_CORD_NUM (position on the primary cord), y=cord value

"sums" folder contains graphs depicting the total sum of all the cords on a khipu, arranged by archive.

analysis_all_khipus.ipynb is a Jupyter Notebook file that calls all khipu info into pandas dataframes for analysis.

analysis_single_khipu.ipynb is a Jupyter Notebook file that calls a single khipu into pandas dataframes for analysis.

Collca.db is a SQLite database created from KhipuDB_SQL, along with added information from Marcia and Robert Ascher's article "Numbers and Relations from Ancient Andean Quipus", which contains observations AS1-AS9. I have also corrected entries using published sources, such as the Aschers' "Code of the Quipu: Databook", Pereyra's book "Quipus del Museo del Sitio Pachacamac". As I am actively studying the khipus, I will continue to update collca.db as I come across discrepancies. Explanation of the tables is provided below.
The SQLite database does not require a server. To use, simply download the file and it can be opened with software such as DB Browser for SQLite (https://sqlitebrowser.org/).

"color boxes.png" file shows the RGB values of the different colors.

KDB key.xlsx is a spreadsheet that explains which table and column holds what data. The intent of the file is to facilitate creating meaningful queries. The same file as a Google Sheet can be accessed here: https://docs.google.com/spreadsheets/d/17HLTuk0MUDv9HWX-Fq8Mz2pfV_8IoVoH_WwUjIfDwsU/edit?usp=sharing

The folder KhipuDB_SQL was downloaded from khipukamayuq.fas.harvard.edu on Feb 4,2021. As the site is no longer active and the database is not posted elsewhere online, I share it here. If the owner of the database requests it to be taken down, I will. KhipuDB_SQL contains multiple files in MySQL format. An explanation of the tables is provided below.

Python scripts were developed in Jupyter Notebooks.




## Explanation of the tables in the database
Note: anything with "dc" in the title contains explanations of the abbreviations used in the database, like Ascher cord color OB is "moderate olive brown". I don't know the purpose of the tables labeled "flat" or "processed". If you have any additional insight to the tables, please leave a comment and I'll update the blog entry.
app_config_data  Creates a database named "collca", (the Quechua word for storehouse) and configures the database.
archive_dc   Notes for where each khipu archive was found.
ascher_canutito_color   Canutito is a small canuto (see image above), and refers to the khipu that have a woven textile attached to the primary cord, from which the pendant cords originate. This table contains color data for each canutito.
ascher_canuto_color   Contains color information for each canuto.
ascher_color_dc    Descriptions for the color names used in the database.
OB is ISCC number 95
To convert R_DEC, G_DEC, and B_DEC to standard RGB values, use the formula R = R_DEC * 255
ascher_cord_color   Colors of each cord. Gives the range, because maybe a cord changes color partway through. Provides the color name, but also separates each color code and the operators in between:
FULL_COLOR = "KB:W"
COLOR_CD_1 = "KB"
OPERATOR_1 = ":"
COLOR_CD_2 = "W"
attachment_dc   Explains what R, V, and H attachment types mean
beginning_dc   Explains the abbreviations used for the beginning of primary cords
canutito   Canutito data: start and end position, length, and notes
canuto_cord_flat   Canuto cord data
compare_seriation   I don't know the purpose of this table.
cord    Data for each pendant, subsidiary and top cord, as well as knots and markers. Has length, ordinal number, thickness, ply, fiber type, recto/verso attachment, and cord name.
cord_cluster  Contains the spacing and grouping of cords, example: "6.0 cm group of   5 pendant(s)       (1 - 5)        space of    1.0 cm"
cord_color_notes
cord_color_processed  Seems to be used by Carrie specifically. I don't know its purpose.
cord_flat   I don't know the purpose of this table. 
cord_notes
cord_processed  I don't know the purpose of this table.
cord_test   I don't know the purpose of this table.
cord_top_level_flat  I don't know the purpose of this table.
cord_type_dc   Contains no information
cord_value   Has the cord value and alternate cord value for cords. It does not have the cord value for all cords, only 293 of the 38,000 cords that have knots.
cord_value_components   I don't know the purpose of this table
cords_to_explore  Contains no data
fiber_dc  Explains the abbreviations for cord fiber types
grouping_class_dc  Explains the abbreviations for cord classification (K for knot, T for top cord)
khipu_blob_notes  Contains khipu notes. "Blob" is a data entry type in SQL that is not limited by characters.
khipu_defaults  Not sure of its purpose, seems like an early version of the primary_cord table
khipu_main   Khipu metadata. Museum name, provenance, etc.
khipu_notes   Contains khipu notes, but is not as complete as khipu_blob_notes
knot   Knot information such as direction (S or Z), type (single or long), value, number of turns
knot_cluster   Knot information such as start and end position, number of knots
knot_type_dc  Explains the abbreviations used for different knot types
pcord_colors_processed  I don't know the purpose of this table
pcord_notes  Notes for primary cords. Some, but not all, of these notes are also included in the primary_cord table.
pigmentation_dc   Explains the abbreviations used for pigmentation
primary_cord  Data regarding the thickness, ply, length, beginning and termination of primary cords
primary_cord_attach  Some khipu were found attached to others. This table describes those attachments.
primary_cord_processed   Appears to provide the sum values of all pendant cords on each khipu
regions_dc   Describes the North/South region of the provenances given in the database
routines   I don't know the purpose of this file. Does not contain any input data, nor does it create tables. Perhaps used for internal purposes.
structure_dc   Explains the abbreviations used for different structure types
termiantion_dc   Appears to be added by mistake
termination_dc  Explains the abbreviations used for different termination types
urton_khipu_type   Marks whether khipu falls into certain categories including seriated, banded, census, anomalous, etc.
x_canuto_color_flat   Contains data regarding canuto lengths, ordinal position, and colors used.
