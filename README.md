# AI voice assistant insurance underwriter

[![Twitter Follow](https://img.shields.io/twitter/follow/Norest?style=social)]([https://twitter.com/mattshumer_](https://twitter.com/Norest))

Nobody enjoys buying life insurance, especially when the underwriting process requires form after form to be manually filled out. Would the process be less painful if customers had the option to complete underwriting by voice via a conversation with an AI voice assistant?  

Try taking a short risk assessment yourself! Below are the steps to run it completely in Google colab and have it call your direct number!  

Disclaimer: I'm not sponsored by any of the API providers mentioned below.
Relevant [Vapi docs](https://docs.vapi.ai/outbound_call_python)

## Steps

1. Register @ [twilio](https://www.twilio.com/en-us) to get a free trial number
2. Register @ [Vapi](https://vapi.ai/) for free - you get $10 free credits too.
3. In Vapi, under [Dashboard > Phone Numbers](https://dashboard.vapi.ai/phone-numbers), import the free trial number. After importing, you'll see a UUID (xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx). You'll need this later.
   
![image](https://github.com/DesmondChoy/ai_underwriter/assets/46787018/255fc959-6053-4349-ae1a-e16ec4027cb1)

Twilio Account SID and Auth Token can be obtained [here](https://console.twilio.com/us1/account/keys-credentials/api-keys).  

4. In Google Colab secrets, input the following:
* VAPI_API: Obtained [here](https://dashboard.vapi.ai/account).
* TWILIO_NUM: UUID obtained in Step 3.
* CUST_NUM: Your mobile number, along with country code.
5. Run the notebook!  
If you're running into geo-permissions errors after running the notebook, [set your country to low-risk](https://console.twilio.com/us1/develop/voice/settings/geo-permissions?frameUrl=%2Fconsole%2Fvoice%2Fcalls%2Fgeo-permissions%3Fx-target-region%3Dus1&currentFrameUrl=%2Fconsole%2Fvoice%2Fcalls%2Fgeo-permissions%2Flow-risk%3F__override_layout__%3Dembed%26x-target-region%3Dus1%26bifrost%3Dtrue) in twilio.

In my notebook, I opted to run mixtral by Groq. Vapi supports plug-and-play with a wide range of models including GPT4, Claude 3 Opus, etc. You just need to add your API keys. There's also a staggering amount of customization in terms of assistant voices, behaviour, etc.


## License

This project is licensed under the [MIT License](LICENSE).
