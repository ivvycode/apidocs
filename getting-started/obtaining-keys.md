# Obtaining Keys

For those who wish to develop a way to extract data from iVvy via programming means, whether to display on your website for for entering into a different system, you will need to generate an API Key. This is relatively simple to do, and can be achieved in only a couple of minutes.

Keys are defined as a pair of strings, the ‘key’ and the ‘secret’. Each request must be signed using a ‘secret’ key. There are generated from within the accounts ‘settings’ section of the website.

**To generate your API key**

1. Log into your iVvy account and click the Global Settings cog in the top right corner of the screen.
2.  On the left side of the screen in the menu, click **Applications** &gt; **API keys**
3. Click **Add Key** &gt; Give it a name so you know why it was generated and choose the user whose permissions match what you would like whoever is requesting the information can access, usually this will be the Super User so all information can be requested.
4. You will be provided a **Secret** and **Key**. Provide these to the developer requesting the information

**NOTE:** This secret cannot be looked up later. If you have forgotten/lost your secret you will need to generate a new key. 

