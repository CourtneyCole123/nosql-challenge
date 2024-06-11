# Part 1: Database and Jupyter Notebook Set Up 📒 #

- Include the mongoimport command text you used to import establishments.json in a markdown cell at the beginning of your Jupyter notebook file

  <pre> Note: this was removed as a requirement per instructor. </pre>

- The mongoimport command text correctly drops any existing establishments collection before importing establishments.json into MongoDB

  <pre> Note: this was removed as a requirement per instructor. </pre>

- The database is named uk_food and the collection is named establishments

   <pre> Note: this was removed as a requirement per instructor. </pre>

- Correctly imports PyMongo and Pretty Print

  ![image](https://github.com/CourtneyCole123/nosql-challenge/assets/162069113/158f6565-d419-4fc3-a573-da79092fb606)

- An instance of the Mongo Client is created

  ![image](https://github.com/CourtneyCole123/nosql-challenge/assets/162069113/dc63d1f3-c1d1-4021-89c4-4be815c2b9cb)
 
- Lists the databases you have in Mongo, which includes uk_food

  ![image](https://github.com/CourtneyCole123/nosql-challenge/assets/162069113/be5a4e94-7471-4699-b2bf-116f69c97669)

- Lists the collection(s) in the uk_food database, which includes establishments in the output

  ![image](https://github.com/CourtneyCole123/nosql-challenge/assets/162069113/2ac96d44-0af0-4728-8f48-3e638b235482)

- Uses find_one() and pprint to display one document in the establishments collection

  ![image](https://github.com/CourtneyCole123/nosql-challenge/assets/162069113/473bc53b-994b-4cc6-9f80-1c8e2ebf4b43)

- The establishments collection is assigned to a variable

  ![image](https://github.com/CourtneyCole123/nosql-challenge/assets/162069113/8d7e9832-cef5-41ae-882d-1aec8b67afd9)

# Part 2: Update the Database ⬆️ #

- The supplied data for the "Penang Flavours" restaurant is correctly inserted into the establishments collection

  ![image](https://github.com/CourtneyCole123/nosql-challenge/assets/162069113/3bdea236-e1d3-4e27-aa52-a44081d09d60)

  ![image](https://github.com/CourtneyCole123/nosql-challenge/assets/162069113/a03b21dd-ce1f-4a7d-a6d2-003eaab4ac60)

- A query is performed to find the BusinessTypeID for "Restaurant/Cafe/Canteen" and returns only the BusinessTypeID and BusinessType fields

  ![image](https://github.com/CourtneyCole123/nosql-challenge/assets/162069113/c65b55e8-cba8-434e-b24a-1980bcf2e29b)

- The "Penang Flavours" document is updated with the correct value for BusinessTypeID

  ![image](https://github.com/CourtneyCole123/nosql-challenge/assets/162069113/5d5a1e55-400a-4531-803a-afdbeb30c95d)

- A query is correctly performed to delete all the documents in the collection where "Dover Local Authority" is the value for LocalAuthorityName

  ![image](https://github.com/CourtneyCole123/nosql-challenge/assets/162069113/12329eb1-eed1-4032-9597-c2c7ab2b6b31)

- A count_documents() check is performed before and after the removal of the Dover documents to ensure the documents were removed

  ![image](https://github.com/CourtneyCole123/nosql-challenge/assets/162069113/7cd047af-7f90-45e4-bee6-559412ad273d)

- An update_many() query is performed to convert the latitude and longitude fields from strings to decimal numbers and RatingValue to integers

  ![image](https://github.com/CourtneyCole123/nosql-challenge/assets/162069113/8245eb05-7d71-42a8-ab0b-d4bb931bfb21)

# Part 3: Exploratory Analysis 📈 #

- Question 1: Which establishments have a hygiene score equal to 20?

  - A query is correctly performed to find the establishments with a hygiene score of 20

   ![image](https://github.com/CourtneyCole123/nosql-challenge/assets/162069113/99a5394e-234d-476f-b1ce-34ff22a88b1e)

  - count_documents() is used to list the correct number of documents (answer: 41)
 
    ![image](https://github.com/CourtneyCole123/nosql-challenge/assets/162069113/f4430304-374a-41ba-9d14-acba3dfcc01f)

  - The first result is printed using pprint
 
    ![image](https://github.com/CourtneyCole123/nosql-challenge/assets/162069113/7e437d65-e086-41f9-90da-ea7e174cb6ae)

  - The results are converted to a Pandas DataFrame and displays the first 10 rows
 
    ![image](https://github.com/CourtneyCole123/nosql-challenge/assets/162069113/3e534cf3-009e-4944-9213-dccd43e64549)

- Question 2: Which establishments in London have a RatingValue greater than or equal to 4?

  - A query is correctly performed to find the establishments in London with a RatingValue greater than or equal to 4
 
      - The query uses the $regex operator to locate the London establishments
 
        ![image](https://github.com/CourtneyCole123/nosql-challenge/assets/162069113/40aee348-42c8-4538-b08d-75e68db82862)

  - count_documents() is used to list the correct number of documents (answer: 33)
 
    ![image](https://github.com/CourtneyCole123/nosql-challenge/assets/162069113/9e7f8fc1-a62a-40e7-87be-764a9b959d80)

  - The first result is printed using pprint
 
    ![image](https://github.com/CourtneyCole123/nosql-challenge/assets/162069113/54e478f0-d9ad-45d0-ba7f-61e0d0515503)

  - The results are converted to a Pandas DataFrame and displays the first 10 rows
 
    ![image](https://github.com/CourtneyCole123/nosql-challenge/assets/162069113/97bd72a1-27dd-48bd-ac11-270a7c67f13d)

- Question 3: What are the top 5 establishments with a RatingValue of 5, sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours"?

  - A query is correctly performed to find the establishments within 0.01 degree of the "Penang Flavours" restaurant
 
      - The query also limits the results to establishments with a RatingValue of 5
      
      - The query uses the sort() method in PyMongo to sort in ascending order on the hygiene score
      
      - The query uses the limit() method in PyMongo to limit the results to 5
      
      - All five results are printed using pprint
 
      ![image](https://github.com/CourtneyCole123/nosql-challenge/assets/162069113/1461b2d3-56a8-4596-9970-bced5152a9d9)

  - The results are converted to a Pandas DataFrame and displayed
 
    ![image](https://github.com/CourtneyCole123/nosql-challenge/assets/162069113/f846271e-4eb7-4d8a-bb77-367b0703b63d)

- Question 4: How many establishments in each Local Authority area have a hygiene score of 0? Sort the results from highest to lowest, and print out the top ten local authority areas.

  - An aggregation pipeline is built to include a match query, group, and sort
      
      - The match query matches documents with a hygiene score of 0

        - The group step of the pipeline is grouped on LocalAuthorityName and counts the number of documents

        - The sort step of the pipeline sorts the count of the documents in descending order

        - The aggregation pipeline is correctly sent to the aggregate() method

        - The results from the aggregation query is cast as a list and then saved to a variable

        - The first ten results are printed using pprint
       
          ![image](https://github.com/CourtneyCole123/nosql-challenge/assets/162069113/61889cf1-f7f0-47bf-a296-7f8f86239dd3)

  - The results are converted to a Pandas DataFrame and displays the first 10 rows
    
    ![image](https://github.com/CourtneyCole123/nosql-challenge/assets/162069113/7cc90741-ac7f-4203-82d7-7148ec1a06a9)
