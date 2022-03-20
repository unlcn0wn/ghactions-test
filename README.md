# Send a telegram notification when a commit is made to repository.

A repository that sends a notification to telegram channel - Nusfintech RPA when a commit is made to the repository.

## How to 

### Step 1:
Fork repository.

### Step 2:
Sign up and login to [IFFFT](https://ifttt.com).

Create an applet by clicking "Create" button on the top right.

For "IF This" -> Add Webhooks - Receive a web request   
- Input your Event Name


For "Then That" -> Add Telegram - Send message
- add Telegram account (First timers - prompt to connect telegram account to IFTTT [link](https://help.ifttt.com/hc/en-us/articles/360003121113-How-to-get-started-using-IFTTT-with-Telegram))
- Target chat - leave it as it is for now
- Input whatever message you want


### Step 3：
With telegram connected, you should have the IFTTT bot - @IFTTT in your telegram. 

Create a channel/group and add IFTTT bot as administrator. [-Guide-](https://help.ifttt.com/hc/en-us/articles/360003121113-How-to-get-started-using-IFTTT-with-Telegram)

Proceed to connect channel/group to IFTTT.
You may follow instructions from IFTTT bot or refer to above link to see how to connect channel/group.

### Step 4：
Go your applet in IFTTT and edit settings.
Change the target chat to the channel/group that you have created above.

### Step 5：
Go to [IFTTT Webhooks page]https://ifttt.com/maker_webhooks） and click on documentation to get your KEY.

Edit your code in line 39 of ghactions-test/.github/workflows/test1.yml.
On line 39, you may edit the values/messages to send specific messages to telegram.

Option 1:
- replace "${{ secrets.IFTTT_KEY }}" with your key

Option 2:
- In your repo, go to settings tab.
- Under Secrets>Actions, create a "New repository secret".
- Key in "IFTTT_KEY" as Name and your key as Value.

### Step 6:
Make commits and see notifications on your telegram channel/group!

## Notes
1. Channels/groups may take a few minutes to appear in IFTTT applets.
2. Webhook urls are case sensitive. Make sure to input the right event and key.
3. In your repo, go to Actions tab to see/monitor workflow
4. Use postman to check post request to IFTTT
