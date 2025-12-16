# petitions_analysis
 An analysis of text data from petitions between 2015 and 2025 using LDA topic modeling.

The code consists of 7 files labelled with the action completed. To extract the petition and signature data, first:
1. Download petitions metadata from https://petition.parliament.uk/
2. Run 1_petitions_data_ingestion.ipynb which uses the metadata to index and ensure all petition information is extracted.

After extraction, files are cleaned and processed using 2_petitions_data_cleaning_exploration.ipynb and 3_petitions_data_preprocessing.ipynb.
Models have been tested and examined in 4_petitions_data_model_evaluation.ipynb and a final model chosen.

After model has been chosen, data is extracted with 5_petitions_data_model.ipynb. This is done by assigning a probability to each petition and topic using the seletced model, merging with either the constituency data or region data and then running through years, regions and constituencies to calculate the topic weighting by multiplying signature counts by probability for each petition and topic with probability higher than 0.5.

Visuals are created based on the data extracted in 6_petitions_data_visualisation.ipynb and 7_petitions_interactive_visuals.ipynb. 
