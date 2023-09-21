# Setup Your Watson Machine Learning

First open this [link](https://cloud.ibm.com/) then create an IBM account and follow the steps. Then your account will look like this:

![yoi](https://github.com/yogasungkowo/Build_Generative_Virtual_Assistant_With_IBM_WatsonX_Watson_Assistant/assets/93362737/1e794eba-50ec-49b5-bb83-26a6a7cde252)

Type "**Watson Machine Learning**" into the search field, select Watson Machine Learning and your page will look like this:

![watson](https://github.com/yogasungkowo/Build_Generative_Virtual_Assistant_With_IBM_WatsonX_Watson_Assistant/assets/93362737/60f66f30-cebf-461f-a039-d6a0ab61f543)

Activate Watson Machine Learning.
Check "I have read and agree to the following license agreement" then select the plan you want to use (for starters I recommend using the lite plan, select location Dallas-US and click create.

Please note that Watson Machine Learning runs when IBM Cloud Pack For Data is installed in your IBM account, you can read the following link as a reference for [IBM Cloud Pack For Data setup](https://cloud.ibm.com/docs/cloud-pak-data?topic=cloud-pak-data-getting-started)

# Setup WatsonX
After activating Watson Machine Learning, WatsonX is ready to run.
Type in the IBM Cloud search field "**WatsonX**" and select
Later, you will be instructed to log in or register using your ibm cloud account, fill in according to the instructions, and your page should be like this:

![Screenshot (1)](https://github.com/yogasungkowo/Build_Generative_Virtual_Assistant_With_IBM_WatsonX_Watson_Assistant/assets/93362737/be6f3097-50fb-4985-8a4d-7d77725a8629)

Click "Get Started" because I have already used the service from IBM WatsonX so it says "launch" then the page should look like this:

![Screenshot (2)](https://github.com/yogasungkowo/Build_Generative_Virtual_Assistant_With_IBM_WatsonX_Watson_Assistant/assets/93362737/fbb374d9-7d37-46f6-a413-85d1b277a4cc)

Click the menu in the upper left corner and select "**Project, View All Project**" then follow the steps below:
* Create a new project by clicking "**New Project**"
* Select "**Create an empty project**"
* Enter your project name, then enter your project description (optional)
* Then click "**Create**"
* Your page should look like this:
  
![image](https://github.com/yogasungkowo/Build_Generative_Virtual_Assistant_With_IBM_WatsonX_Watson_Assistant/assets/93362737/6b2d2716-9eba-421e-b928-52162ac5e178)

* Click "**Assets**" and click "**New task**"
* Select "**Experimenting with foundation models and build prompts**"
* A notification will appear like this:

![Screenshot (4)](https://github.com/yogasungkowo/Build_Generative_Virtual_Assistant_With_IBM_WatsonX_Watson_Assistant/assets/93362737/8c9b0ab1-0378-4499-aea5-b3d36dead573)

* Click "**Associate Service**" and select "**Watson Machine Learnig**" and click "**Associate**"
* Return to the "**Assets**" menu and "**Create new task**" as above
* And your page will look like this:

![Screenshot (5)](https://github.com/yogasungkowo/Build_Generative_Virtual_Assistant_With_IBM_WatsonX_Watson_Assistant/assets/93362737/978906d0-c1ea-4f0b-b161-6364a68b7b85)

* Click on the menu I've rounded up and select "Question About an Article"

![Screenshot (6)](https://github.com/yogasungkowo/Build_Generative_Virtual_Assistant_With_IBM_WatsonX_Watson_Assistant/assets/93362737/aad1e018-e36d-4bff-9983-af9da0fced6f)

* Enter the following text into the "**Setup**" menu
```
Answer the following question using only information from the article. If there is no good answer in the article, say "Sorry, i cant get your answer. Because my foundation not updated yet😅".

Article: 
###
FC Barcelona, often referred to simply as Barcelona or Barça, is one of the most renowned and successful football clubs in the world. Here's a brief overview of the club's history and significant years:

Foundation (1899): FC Barcelona was founded on November 29, 1899, by a group of Swiss, English, and Catalan footballers led by Joan Gamper. The club's first president was Walter Wild.

Early Success (1910s - 1920s): Barcelona won its first Copa del Rey (Spanish Cup) in 1910. In the 1920s, they won several regional and national titles, solidifying their status in Spanish football.

Civil War and Franco Era (1930s - 1940s): During the Spanish Civil War and the subsequent dictatorship of Francisco Franco, the club faced numerous challenges. Its Catalan identity made it a symbol of resistance against Franco's regime.

Golden Era (late 1940s - 1950s): The 1940s and 1950s were marked by tremendous success for Barcelona. Players like Ladislao Kubala and Luis Suárez led the team to win numerous domestic and international titles.

Cruyff's Era (1970s - 1980s): Johan Cruyff's arrival as a player in the 1970s and later as a manager in the late 1980s had a profound impact on Barcelona. He implemented a playing style known as "Total Football" and won the club's first-ever European Cup (now UEFA Champions League) in 1992.

The Dream Team (1990s): Under Cruyff, Barcelona's "Dream Team" achieved great success, winning four consecutive La Liga titles from 1991 to 1994.

Modern Era (2000s - Present): In the 21st century, Barcelona reached the pinnacle of football success under managers like Pep Guardiola. The team won numerous domestic and international titles, including multiple UEFA Champions League titles and La Liga championships.

Lionel Messi Era: The club's most iconic player, Lionel Messi, made his debut for Barcelona in 2004. Messi became the club's all-time leading scorer and led the team to numerous victories.

Recent Challenges: In recent years, Barcelona has faced financial challenges, leading to the departure of Lionel Messi to Paris Saint-Germain in 2021. The club has been rebuilding its squad and finances.

FC Barcelona's history is rich with success, iconic players, and a commitment to a distinctive style of football known as "tiki-taka." The club has a passionate global fan base and remains a symbol of Catalan culture and identity.
###
```
* In the example field, enter as follows:
  
| Question                   | Answer                                                                                                                                |
|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------|
| What is FC Barcelona       | FC Barcelona, often referred to simply as Barcelona or Barça, is one of the most renowned and successful football clubs in the world. |
| When FC Barcelona was born | FC Barcelona was founded on November 29, 1899, by a group of Swiss, English, and Catalan footballers led by Joan Gamper.              |

![image](https://github.com/yogasungkowo/Build_Generative_Virtual_Assistant_With_IBM_WatsonX_Watson_Assistant/assets/93362737/3ffeee19-8787-4968-8e2c-486b7d4e34a2)

* Try prompt and make sure bot answer correctly
* Select the part that I highlighted:

![Screenshot (8)](https://github.com/yogasungkowo/Build_Generative_Virtual_Assistant_With_IBM_WatsonX_Watson_Assistant/assets/93362737/e20d3e67-c906-4a50-a32f-f9c1da92aabf)

* Make sure the options like the following:
  * Decoding Type: Greedy
  * Repetition Penalty : 1
  * Stop Sequences: (enter), and "." (period)
  * Min token: 0
  * Max tokens: 500
    
# After doing all the instructions correctly, the step for the setup of WatsonX has been completed





