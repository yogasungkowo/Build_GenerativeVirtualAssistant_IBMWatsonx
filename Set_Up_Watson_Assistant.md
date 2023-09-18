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






  




