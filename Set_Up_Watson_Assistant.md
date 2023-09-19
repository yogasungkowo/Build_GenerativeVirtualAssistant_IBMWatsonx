# Setup Watson Assistant From IBM Cloud

* Open this [link](https://cloud.ibm.com/), login to your IBM Cloud Account, and search "**Watson Assistant**" then select "**Watson Assistant**"
* After that, you can select country to Dallas-US, plan lite, and check "**i have read and aggree to the license aggreement**" and then click "**Create**"
* and after your Watson Assistant Service created you can see in the search bar is would be like this :
  
![Screenshot (10)](https://github.com/yogasungkowo/Build_Generative_Virtual_Assistant_With_IBM_WatsonX_Watson_Assistant/assets/93362737/ff24f974-38ee-4065-8361-82b5d7fd0630)

* Click on the "**Watson Assistant-(random character, for me is Watson Assistant-aa, it would be different per user)**"
* Click "**Launch**"
* After launch the Watson Assistant service, you will see the following:

![Screenshot (13)](https://github.com/yogasungkowo/Build_Generative_Virtual_Assistant_With_IBM_WatsonX_Watson_Assistant/assets/93362737/19bd6ddb-3bac-404f-a08d-51eff16a76e5)

# Setup Extension WatsonX On Watson Assistant

Before we take action to setup our virtual agent, we must create integration between WatsonX Generated AI and Watson Assistant to make the virtual assistant work like chat GPT
* Click menu on top left corner, and select "**Integration**"
* Scroll Down and choose "**Build Custom Extension**"
* Before we move forward we need copy our WatsonX API KEY
* Back to WatsonX and open our project assets and click the following :

![Screenshot (14)](https://github.com/yogasungkowo/Build_Generative_Virtual_Assistant_With_IBM_WatsonX_Watson_Assistant/assets/93362737/5383a72a-3cbd-4597-a5eb-cd872ebdac19)

* Click "**Create**"
* Fill in the name and description as desired
* And then click "**Create**"
* Copy API Key / Download, and back to Watson Assistant
* Click "**Next**"
* Fill in Extension Name and Extension Description then click next
* Download this [JSON](https://github.com/watson-developer-cloud/assistant-toolkit/blob/master/integrations/extensions/starter-kits/language-model-watsonx/watsonx-openapi.json) file
* And then drag or drop the file to the following :

![Screenshot (15)](https://github.com/yogasungkowo/Build_Generative_Virtual_Assistant_With_IBM_WatsonX_Watson_Assistant/assets/93362737/5707ecff-8613-42b2-892d-ae7f69c3b792)

* Click "**Next**"
* Click "**Finish**"
* Scroll Down again to extension menu and click "**Add**" to integration we just created
* Click "**Next**"
* Authentication Type select "**Oauth 2.0**"
* Paste API Key from WatsonX, that we copied before to "**Api Key Form**"
* Click "**Next**"
* And click "**Finish**"

# Setup Action On Watson Assistant

After we successfully integrated WatsonX and Watson Assistant, next step is testing
* Open menu on left top corner and select "**Action**"
* Click "**New Action**"
* Define Customer say for start the coversation, e.g. "hello"

![Screenshot (17)](https://github.com/yogasungkowo/Build_Generative_Virtual_Assistant_With_IBM_WatsonX_Watson_Assistant/assets/93362737/e2861da5-ab64-49dd-bd65-8decf8ad456b)

* I start to asking user to ask everything they want to ask, and select customer response to "**Free Text**"

![Screenshot (18)](https://github.com/yogasungkowo/Build_Generative_Virtual_Assistant_With_IBM_WatsonX_Watson_Assistant/assets/93362737/71e1f0fe-a98a-4746-a5a1-00e839120754)

## Import WatsonX To Watson Assistant

* Select "**New Step**"
* In menu "_And Then_" select "**Use an Extension**"
* Choose an extension and select the extension we create before
* Select "_Operation_" to "**Generation**"
* For Parameters we can insert the following from WatsonX Prompt Lab via View Code, below is the instruction to read the code and fill parameters

![Screenshot (19)](https://github.com/yogasungkowo/Build_Generative_Virtual_Assistant_With_IBM_WatsonX_Watson_Assistant/assets/93362737/bde11225-3b2c-4909-bf36-90fe4f3b7080)

* For input parameter select "**Action Variables**" and select "**step 1**"
* After we set the extension, time to making variable that will call the extension
* Click "**New Step**"
* Change "**Is taken to** to "**With conditions**"

https://github.com/yogasungkowo/Build_Generative_Virtual_Assistant_With_IBM_WatsonX_Watson_Assistant/assets/93362737/2eec23cd-ea8c-4ad1-b695-ac985763db34

* Click "**Set Variable Values**"
* Click "**Set New Value**", "**New Session Variable**", insert the variable name, this time e.g result, and variable type select "**Free Text**"
* In "variable to" form Select "**Expression**" and insert this code
```
${step_472_result_1.body.results}[0].generated_text
```

https://github.com/yogasungkowo/Build_Generative_Virtual_Assistant_With_IBM_WatsonX_Watson_Assistant/assets/93362737/3d2a9ebb-b655-495b-b03f-03926c26269d

* After the setup finally done we can tested it, click "**preview**" in right bottom corner

https://github.com/yogasungkowo/Build_Generative_Virtual_Assistant_With_IBM_WatsonX_Watson_Assistant/assets/93362737/83ee4409-5d7f-479f-832f-fc2cd4429f6a

# Making Halo Barca Generative Virtual Assistan

After do some test integration between watsonx and watson assistant, we can move forward onto next topic. That's making our Generative Virtual Assistant for Halo Barca website
* Open your Watson Assistant and create new action same as previosly explained
* Create customer first say, in this step I define the customer input in the form of the alphabet a to z, and the word "Barca"
* After that we define assistant say, i define with this sentence:
```
Welcome to the Halo Barca's virtual assistant . A website that covers news related to the FC Barcelona football club. How can we help you? 🔵🔴
```
* Im define customer response in options type, and there 3 options i made
  * **About Us** : to inform users general information about the website.
  * **Many Things About Barca** : to make user enter the generative ai session on the virtual assistant then users can interact to it like asking to Chat GPT (We will configure this on the next step)
  * **Info Classement** : to tell the users about the latest football league standing that can be accessed to Halo Barca football table page
* After that choose _And then_ to **Continue to next step**
* Im insert the image to making the assistant more looking good

![Screenshot (43)](https://github.com/yogasungkowo/Build_Generative_Virtual_Assistant_With_IBM_WatsonX_Watson_Assistant/assets/93362737/79c47a0e-2daf-4f37-828e-9ed31329cc38)

* Create new step
* On the new step, we making the response if users choosing **About Us**
* Click _Is taken_ and set it into **With conditions**
* On if menu set it into **Action step variable > step 1 > is > About us**
* After that we define assistant say, i defining assistant say like below:
```
Halo Barca is a website that discusses all things related to FC Barcelona, ranging from player updates, match score history, and other exciting news about El Blaugrana!!🔴🔵
```
* Im select customer response to options with 2 options
  * **Back to main** : the response to took back customers into the virtual assistant main menu
  * **Many Things About Barca** : the respone to take customers into chatbot menu, that customers can ask everything about Fc Barcelona
> noted, options **Many Things About Barca** it's the important options that we can take the customers into chatbot with this options

https://github.com/yogasungkowo/Build_Generative_Virtual_Assistant_With_IBM_WatsonX_Watson_Assistant/assets/93362737/ab85fde5-199d-44e2-8b38-ce3f1818e077

* Click new step, now we make the response if customer select **Info Classement** in main menu
* Set _Is taken_ to **With conditions**
* On if menu select **Action Step Variable and choose step 1 > is > Info Classement**
* Define the assistant say, i defined it with :
```
To see about classement info, you can check this
! 🔵🔴
```
* I making "this" word into link, that customers or users can access into it
* Define customer response with options
  * **Back to main** : the response to took back customers into the virtual assistant main menu
  * **Many Things About Barca** : the respone to take customers into chatbot menu, that customers can ask everything about Fc Barcelona

https://github.com/yogasungkowo/Build_Generative_Virtual_Assistant_With_IBM_WatsonX_Watson_Assistant/assets/93362737/039e415d-cd66-4697-84d1-c3783590bf3f



  




