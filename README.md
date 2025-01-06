# nosql-challenge

Mongo DB wsa used in a Jupyter notebook for this exercise, to analyse a database of restaurants in the UK.

MongoImport was first used in the CMD terminal to import the relevant data. The database was named 'uk_food' and assigned to the 'establishments' collection.

After initial sense-checking to make sure the data was imported and assigned correctly, a new restaurant, 'Penang Flavours' was added to the database. The insert.one function was used to do this. The find.one function was also used to double-check whether this was done correctly.

The next step was to delete any establishments in Dover and the delete-many function was used to do this. The count-documents function was also used to ensure the deletion was carried out successfully.

The update_many function was next used on all establishments to convert their Latitude/Longitude coordinates to decimal numbers. The same function was also used to the 'RatingValues' to integers.

In the next step, the count_documents function was used to query the establishments collection to count all restaurants with a hygiene score of 20. The result was also converted to a Pandas Dataframe for further analysis. The len(df) function was also used to idenify the total number of rows in the dataframe.

Next a query was created to filter the establishments in London with a RatingValue 4+, which amounted to a total of 35 restaurants.

The same exercise was repeated, but within the close vicinity of Penang Flavours, and with a RatingValue of 5. The top 5 establishments within this criteria were:

1) Ideal Sweets and Bakers
2) Nirala Sweets
3) World Shirdi Sai Baba Organisation (UK)
4) Springbok Newsagents
5) Kensington Dining Centre

A pipeline was created to match establishments with a hygiene score of 0 and group the matches by local authority. A total of 56 establishments were identified that fit this criteria. The establishments.aggregate function was used with the defined pipeline to obtain this result.

