# petitions_analysis
 An analysis of text data from petitions between 2015 and 2025 using LDA topic modeling. LDA topic modelling was used as it handles large amounts of data well, works best with minimal preprocessing and has been used for similar projects on petitions data.

The code consists of 7 files labelled with the action completed. To extract the petition and signature data, first:
1. Download petitions metadata from https://petition.parliament.uk/
2. Run 1_petitions_data_ingestion.ipynb which uses the metadata to index and ensure all petition information is extracted.

After extraction, files are cleaned and processed using 2_petitions_data_cleaning_exploration.ipynb and 3_petitions_data_preprocessing.ipynb.
Models have been tested and examined in 4_petitions_data_model_evaluation.ipynb and a final model chosen.

After model has been chosen, data is extracted with 5_petitions_data_model.ipynb. This is done by assigning a probability to each petition and topic using the seletced model, merging with either the constituency data or region data and then running through years, regions and constituencies to calculate the topic weighting by multiplying signature counts by probability for each petition and topic with probability higher than 0.5.

Visuals are created based on the data extracted in 6_petitions_data_visualisation.ipynb and 7_petitions_interactive_visuals.ipynb. 

There are still errors in topic assignment and some lack of coherence within some topics. Further experimentation with entropy and different kinds of topic modelling techniques would be useful. I have used Cv coherence predominantly to evaluate results.

## Contents
1. Installation and running instructions
2. How to use
3. Testing

## Installation and running instructions
Create a virtual environment and activate it. Download the requirements.txt and move to the directory being used. Use the command below to install required packages:

pip install -r requirements.txt
Once the requirements have been installed, follow the files in number order.

## How to use
These files can be used for future analysis and further analysis. The model parameters may need altering to fit the data better. 

Interactive visuals have been created and can be seen in the results folder along with a dashboard that was made using quarto. Alter the chosen topics and visuals as fit.

## Testing
There is some testing in the 6_petitions_data_model file where the model is applied on a larger set of data and so data quality is checked and validated. There are also some tests to ensure the calculation of signatures by region and constituency is correct. I am working on further systematic testing.
