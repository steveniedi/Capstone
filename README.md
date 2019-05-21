### Problem Statement

Most rescues use some sort of software platform for prospective adopters to apply for their dream dog. Depending on the software, the rescue organization can view the applications on the web or download them as a pdf file. They then read through every line to make sure it’s a good fit for the adopter and the dog.

THAT’S A LOT OF WORK!


### About the data

I gathered data from the petstablished account of In Our Hands Rescue. The Adoption Application Form was generated as an excel file with multiple tabs. I did some initial cleaning in excel before creating a dataframe in python. The application form consists of "fill in" questions and "multiple choice" questions. Initially, I split the dataframe into these 2 sections so that I could run NLP on the text data. Because of poor model performance, I took a closer look at the answers and worked on feature engineering.

---

#### Feature Engineering

After exploring the "fill in" answer data, I selected questions that had consistence yes / no answers and questions that I could heap into "buckets." For example, one question asks applicants to fill out their vet's information. I created a list of words associated with answers from people who had a vet such as 'dr', 'st', 'clinic', 'ASPCA', etc.

---

#### Data Dictionary

| Column | Description |
| --- | --- |
| rent_own | Do you own or rent? |
| breed_rstrc | Does your landlord or home insurance place any breed or weight restrictions on the animals you are allowed to have? |
| yard | Do you have a yard? |
| screens | Do you have screens in your windows? |
| household_agree | Are all the members of your household in agreement about adopting a dog? |
| pub_housing | Do you live in public housing (NYCHA, projects, section 8)? |
| energy | What energy level would work with your lifestyle? |
| previous_animals | Are your pets up to date on their vaccinations and monthly preventatives (flea/tick and heartworm)? |
| spay_neuter | Are your current cats/dogs spayed or neutered and have your past cats/dogs been spayed or neutered |
| vet | Please provide the name and phone number for your most recent or current veterinarian (even if you don't have the animals anymore). What name are the records listed under? Please note that some vets require your permission to release information to us; please call your vet now and give them permission as this will help expedite the application process!|
| home_alone | On a regular day, how many hours will the dog be left alone? |
| how_soon | How soon do you want to adopt a pup? |
| pet_return | Have you ever had to give up a pet? If so, why and where did the pet go? |
| training_hardships | Are you willing to work through unexpected hardships with your pet and hire a trainer if need be? i.e. housetraining, separation anxiety, fear, socialization, acclimation to other animals, etc? |
| accepted | 1 if the applicant was accepted, 0 for rejected |


### Modeling

I tested out a few different models on the data including Logistic Regression, Random Forest, AdaBoost and XGBoost. Each model handled the data well. The model that had the least variance and highest score was XGBoost.