# Business-Case-Example-using-TF1.14
You were given data from an audio book app. It relates to the audio version of books. Each customer in the database has made a purchase at least once. We want to create a ML algorithm based on our data that can predict if a customer will buy again from the audio book company? 
The data was gathered from the audiobook app. It represents 2 yrs of engagement. We've taken extra 6 months of data after the two year period,
to check if a customer converted or not.(this data included as Targets)

IMPORTANT METRICS FOR CONVERSION

 --> ID : It is like a name. No Information, we will skip it.
 
 --> Book Length : the overall book length is the sum of the length of purchases.
 
 --> Avg Book Length : the sum / #purchases. If someone has brought a single audio book, the average length and the overall length for this person may be equal.
                       therefore, Purchases = overall length / avg. length

 --> Price : the price variable is almost always a good predictor!
 
 --> Review : It is boolean. It shows if the customer left a review. (1 = left a review, 0 = didn't). 
              Our assumptions is that people will leave reviews are more likely to convert again.
 
 --> Review 10/10 : It measures the review of a customer from 1 to 10. Logically we'll only have a value for people who left a review by 
             examining the table. Most people leave no review as in most market places, that's bad for our dataset and bad in general.
                    We've decided to leave the reviews posted to the platform and substitude all missing values with the average review.
                     Avg = 8.91.
                     For our ML algorithm, 8.91 = status quo.
                     A review > 8.91 indicates above average "feelings".
                     A review < 8.91 indicates below average "feelings".
 
 --> Avg. Review 10/10 : Average review accross purchases. It Indicates the feelings towards the content on the medium or better the medium.                    
                         Eg. 2/10 = 0.2 (No Pleasant Experience) No buy again.
                         
 --> Minutes Listened : Total minutes listened is a measure of engagement.
 
 --> Completion : Total Minutes Listened / Total length og books. Assuming people don't re-listen to books. Both variables are self explanatory.
 
 --> Support Request : It is numerical. Shows the total number of support requests. Eg. Forgotten password to Assist. Its a measure of engagement.
                       More support a person need  == (more got fedup with the platform ) OR (likes so much that stumbles upon different issues.)
                       
 --> Last Visited minus Purchase date : Measure of engagement. Bigger difference = More likely to convert again.
                                                                      0          = Never access what he/she has brought.
                                                                      
 --> Targets : 1 , if a customer brought again in the last 6 months of data.
               0 , if a customer did not buy again.   
