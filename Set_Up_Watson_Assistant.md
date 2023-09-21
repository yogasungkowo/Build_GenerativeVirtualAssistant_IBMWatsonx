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

# Making Halo Barca Generative Virtual Assistant

After do some test integration between watsonx and watson assistant, we can move forward onto next topic. That's making our Generative Virtual Assistant for Halo Barca website
> For this project im making 2 action on Watson Assistant, first for general assistant and another one is for call watsonx extension.

## Creating action for call watsonx extension

* Open watson assitant, click menu on the top left, and select **Action**
* After that click **New Action**
* Give the action name whenever you want, in this i'll give that **Chatbot**
* setup watsonx extension like step that already describe
* In the end part i'll making it **end step**, so the extension will stop after generated the answer that users ask

![Screenshot (61)](https://github.com/yogasungkowo/Build_Generative_Virtual_Assistant_With_IBM_WatsonX_Watson_Assistant/assets/93362737/61dc3c67-13b1-403e-a88d-18717d049743)
> I don't know why in the step extension call it give me red indicator, i think it's error but after trying it, it run correctly and dont have any error or bugs.

## Creating action for general assistant

* Open watson assistant, and create **New action**
* Give the name of the action, i'll giving it **_Halo Barca Generative Virtual Assistant_**
* First part it'll be customer say, i want them say **_Barca_** and then Assistant start the program
* In first step we want customer to give their name, so the assistant can say customer name like **_Hi, Yoga_**
* Fill the assistant say :
```
Hi, can you give me your name first ? 🔵🔴
```
* In **Customer Response** i make it **Free Text**, _And then_ **Continue to next step**

![making it so guudd](https://github.com/yogasungkowo/Build_Generative_Virtual_Assistant_With_IBM_WatsonX_Watson_Assistant/assets/93362737/78774eee-070b-441c-9778-19abbfc0784b)

* Create new step, and in step we making variabel that will saving name from user in step 1
* Click **Set variable values**
* **Set new value**, **New session value**, and give it the name like e.g **_name_** set type is **Free Text**
* After that, select variable **set to action step** and choose step 1,
* set _And then_ to **Continue to next step**

![Screenshot (61)](https://github.com/yogasungkowo/Build_Generative_Virtual_Assistant_With_IBM_WatsonX_Watson_Assistant/assets/93362737/a580f9c3-bcdd-4522-88d4-ce56a793d54f)

* In step 3, i'll making the welcoming text for the user. Including beauty image to representative Fc Barcelona
* i fill assistant say with welcoming text, followed by _**name**_ variable we just created before
```
Hi ${name}, Welcome to the Halo Barca's virtual assistant . A website that covers news related to the FC Barcelona football club. How can we help you? 🔵🔴  
```
* In customer response i giving 3 options
  * **About Us**                  : To tell customer detail information about the website Halo Barca
  * **Info classement**           : To tell customer if they want to see football league table 
  * **Many Things About Barca**   : To direct customer to chatbot menu, so they can asking all about Fc Barcelona with Watsonx Generative AI
* set _And then_ to **Continue to next step**

![Screenshot (63)](https://github.com/yogasungkowo/Build_Generative_Virtual_Assistant_With_IBM_WatsonX_Watson_Assistant/assets/93362737/bb07ea65-8a14-43f7-a9d2-a2665989e5f5)

* In step 4, is a response to customer if they choose **About us** in step 3
* Set _Is taken_ to **With Conditions**
* In condition menu select **Action Step Variable** and choose step 3, **To** select **About us**
* And we set assistant say
```
Halo Barca is a website that discusses all things related to FC Barcelona, ranging from player updates, match score history, and other exciting news about El Blaugrana!!🔴🔵
```
* In customer response i make options again
  * **Back to main**                : To redirect customer to main menu
  * **Many Things About Barca**     : To direct customer to chatbot menu, so they can asking all about Fc Barcelona with Watsonx Generative AI
* set _And then_ to **Continue to next step**

![Screenshot (64)](https://github.com/yogasungkowo/Build_GenerativeVirtualAssistant_IBMWatsonx/assets/93362737/50950062-8880-4369-a940-766ec72a52fd)

* In step 5, is a response if customer choose **Info classement** in step 3
* set _Is taken_ to **With conditions**
* In condition menu select **Action Step Variable** and choose step 3, **To** select **Info classement**
* set assistant say
```
To see about classement info, you can check this! 🔵🔴
```
* Setting word "this" to clickable link direct to [Halo Barca](https://haloobarca.blogspot.com/)
* Same with step 5, im making customer response to options with same argument
* set _And then_ to **Continue to next step**

![image](https://github.com/yogasungkowo/Build_GenerativeVirtualAssistant_IBMWatsonx/assets/93362737/16bca473-9785-4832-ad9f-cc1882d012d9)

* In step 6 we setting the response for customer if they choose back to main, in every step
* Set _Is taken_ to **With Conditions**
* In condition menu set is to **If any of this is true**
* Chose step 4 and step 5 **is Back to main**
* We skip the assistant say, and customer response
* Set _And then_ to **request previous step**, we choose step 3, which step provides the main menu.

https://github.com/yogasungkowo/Build_GenerativeVirtualAssistant_IBMWatsonx/assets/93362737/32d0ea24-6dfa-413e-80ee-4aa7bff23db2

* We move to step 7, which is step called _Chatbot__ action
* In step 7, skip customers say and customer response, we focus on the _And then_ menu.
* Set _And then_ to **Go to sub action**
* In the sub-action menu choose **Chatbot** Action we, had did before, and apply

https://github.com/yogasungkowo/Build_GenerativeVirtualAssistant_IBMWatsonx/assets/93362737/9f8458a6-7734-40d1-873e-fb1fb40c448f

* Next in step 8, which is step to set variable to call the sub action
* In _Is taken_ set to **Without Conditions**
* Click **Set variable values**
* If you dont have session variable yet, you can create **new session variable** give it name and set type to **Free Text**
> except variable **name** we created for calling customer name, dont use this variable to call sub action
* Set variable _To_ to **expression** type '$' and chose **Chatbot(step 7)** choose the step in the sub action
* Next to the expression we type give it "[0].generated_text" _you will see the result in the end_
* After done setup variable, we fill customer say with variable we just created
* And customer response with options
  * **Ask again**        : To direct customers to ask again with the chatbot
  * **Back to main**     : To redirect customer to main menu
* Set _And then_ to **Continue to next step**

https://github.com/yogasungkowo/Build_GenerativeVirtualAssistant_IBMWatsonx/assets/93362737/5b0df704-02ea-4641-9304-b3d31b5964dc

* In step 9, we're making the response if select **Back to main** on step 8
* Set _Is taken_ to **With conditions**
* Choose action step variable, and chose step 8 **Back to main**
* Skip assistant say and customer response
* In _And then_ set into Re-ask Previous step(s), set re-ask to step 3

https://github.com/yogasungkowo/Build_GenerativeVirtualAssistant_IBMWatsonx/assets/93362737/e5fda7be-1959-4713-9f9a-a1274d768dab

* Next step (step 10) is the response if the customer chooses **Many things about barca** at every step
* Set _Is taken_ to **With conditions** in if menu set **If any of this is true**
* Choose step 5,4, and 3, and set into **Many things about barca**
* Skip **Assistant say** and customer response
* In _In then_ set into **Re-ask previous step(s)**, and choose step 7

https://github.com/yogasungkowo/Build_GenerativeVirtualAssistant_IBMWatsonx/assets/93362737/6c83c88e-4918-4304-a50f-ad96acf43b8f

* And the final step was step 11, which is step who response if customer choose **Ask again** on step 8
* Set _Is taken_ to **With conditions**
* Choose action step variable, and chose step 8 **Ask again**
* Skip assistant say and customer response
* In _And then_ set into Re-ask Previous step(s), set re-ask to step 7

https://github.com/yogasungkowo/Build_GenerativeVirtualAssistant_IBMWatsonx/assets/93362737/eb9a84c4-47c3-4ee0-9759-567b019eefe7

# Setup the watson assistant was done, and we need to try that

https://github.com/yogasungkowo/Build_GenerativeVirtualAssistant_IBMWatsonx/assets/93362737/d9112085-2fd8-4213-8620-03e15c3fa84c

### We had some error, but if we check in error details

![Runtime error](https://github.com/yogasungkowo/Build_GenerativeVirtualAssistant_IBMWatsonx/assets/93362737/b75090a5-2643-4440-ba5f-1ae3adceb3b0)

### The main reason why its have error is in _[0].generated_text_ on step 8 variable to. I'll try to make changes like remove "[0].generated_text", the assistant not give me the error again, but repeat questions asked by customers.

![Not error](https://github.com/yogasungkowo/Build_GenerativeVirtualAssistant_IBMWatsonx/assets/93362737/bdb8dc2d-bda4-44a8-8cd7-4f2844ddbfaf)

### After try some many ways, the final conclusion is I'll still enter "[0].generated text" in step 8, this is done because the error does not appear when in the virtual assistant display on the website.

https://github.com/yogasungkowo/Build_GenerativeVirtualAssistant_IBMWatsonx/assets/93362737/4603eca1-d675-46b2-aa9d-09658eb6669a

# The watson assistant setup was done.
