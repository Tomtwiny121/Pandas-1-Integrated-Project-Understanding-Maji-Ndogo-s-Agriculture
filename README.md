# Pandas-1-Maji-Ndogo-Code-Challenge


Integrated Project: Understanding Maji Ndogo's Agriculture
© ExploreAI Academy

In this coding challenge, we will apply all of the skills we learned in Pandas.

⚠️ Note that this code challenge is graded and will contribute to your overall marks for this module. Submit this notebook for grading. Note that the names of the functions are different in this notebook. Transfer the code in your notebook to this submission notebook.

Instructions
Do not add or remove cells in this notebook. Do not edit or remove the ### START FUNCTION or ### END FUNCTION comments. Do not add any code outside of the functions you are required to edit. Doing any of this will lead to a mark of 0%!

Answer the questions according to the specifications provided.

Use the given cell in each question to see if your function matches the expected outputs.

Do not hard-code answers to the questions.

The use of StackOverflow, Google, and other online tools is permitted. However, copying a fellow student's code is not permissible and is considered a breach of the Honour code. Doing this will result in a mark of 0%.

Introduction
Hey there, I'm glad you're on board for the Maji Ndogo project AGAIN! Let me walk you through what we're up against and how we'll tackle it.

As you know, we're in an ambitious project aimed at automating farming in Maji Ndogo, a place with diverse and challenging agricultural landscapes. Before we dive into the 'how' of farming, we need to figure out the 'where' and 'what'. It's not just about deploying technology; it's about making informed decisions on where to plant specific crops, considering factors like rainfall, soil type, climate, and many others.

Our analysis is the groundwork for this entire automation project. We have an array of variables like soil fertility, climate conditions, and geographical data. By understanding these elements, we can recommend the best locations for different crops. It's a bit like solving a complex puzzle – each piece of data is crucial to seeing the bigger picture.

We'll start by importing our dataset into a DataFrame. It is currently in an SQLite database, and split into tables. Unlike Power BI or SQL, data analysis in Python happens in a single table. So we will have to brush off those dusty SQL skills to get the data imported. Expect a bit of a mess in the data – it's part of the challenge. We need to clean it up and maybe reshape it to make sense of it. It's like sorting out the tools and materials we need and getting rid of what we don't.

Here's where the real fun begins. We'll dive deep into the data, looking for patterns, and correlations. Each clue in the data leads us closer to understanding the best farming practices for Maji Ndogo. I'll be relying on your skills and insights. We'll be working through these steps together, discussing our findings and strategies.

Let's gear up and get ready to make a real difference in Maji Ndogo. Ready to get started? Let's dive into our data and see what stories it has to tell us.

Sanaa.

Data Dictionary
Geographic features

Field_ID: A unique identifier for each field (BigInt).

Elevation: The elevation of the field above sea level in meters (Float).

Latitude: Geographical latitude of the field in degrees (Float).

Longitude: Geographical longitude of the field in degrees (Float).

Location: Province the field is in (Text).

Slope: The slope of the land in the field (Float).

Weather features

Field_ID: Corresponding field identifier (BigInt).

Rainfall: Amount of rainfall in the area in mm (Float).

Min_temperature_C: Average minimum temperature recorded in Celsius (Float).

Max_temperature_C: Average maximum temperature recorded in Celsius (Float).

Ave_temps: Average temperature in Celsius (Float).

Soil and crop features

Field_ID: Corresponding field identifier (BigInt).

Soil_fertility: A measure of soil fertility where 0 is infertile soil, and 1 is very fertile soil (Float).

Soil_type: Type of soil present in the field (Text).

pH: pH level of the soil, which is a measure of how acidic/basic the soil is (Float).

Farm management features

Field_ID: Corresponding field identifier (BigInt).

Pollution_level: Level of pollution in the area where 0 is unpolluted and 1 is very polluted (Float).

Plot_size: Size of the plot in the field (Ha) (Float).

Chosen_crop: Type of crop chosen for cultivation (Text).

Annual_yield: Annual yield from the field (Float). This is the total output of the field. The field size and type of crop will affect the Annual Yield.

Standard_yield: Standardized yield expected from the field, normalized per crop (Float). This is independent of field size, or crop type. Multiplying this number by the field size, and average crop yield will give the Annual_Yield.

Average yield (tons/Ha) per crop type:

Coffee: 1.5

Wheat: 3

Rice: 4.5

Maize: 5.5

Tea: 1.2

Potato: 20

Banana: 30

Cassava: 13

Alright, let's walk through the process of importing our SQL data from multiple tables into a single DataFrame. This is a crucial step as it sets the foundation for all our subsequent analyses.

We're dealing with an SQLite database, Maji_Ndogo_farm_survey.db, which contains multiple tables. We'll need to join these tables on a common key to create a comprehensive dataset for our analysis. The common key in our case is Field_ID.
