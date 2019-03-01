# Contact Form to Google Sheets

In order to send a contact form to Google Sheets we will need to set up the API within Google. We will need to be signed in and using the Google account which owns the sheet that we would like to use.

## Google Sheets API Setup

Go to:
[https://console.developers.google.com/apis/dashboard](https://console.developers.google.com/apis/dashboard)

Click the dropdown on the top left next to the Google APIs logo then click New Project.
Give your project a name and click create.
This will take you  back to the original page. Click the dropdown menu bar again and click on your projcet name. The project doesn't always show up immediately, you may need to hit F5 to refresh the page and have it show up. Select your new project.

On the left side of the screen click on Library.

Search for Sheets and click on the Google Sheets API.

Click Enable.

On the left side click Credentials.

Toward the top click on + Create Credential. On the next screen under 'Which API are you using?' make sure Google Sheets API is selected.

Under 'Where will you be calling the API from?' select 'Web Browser (JavaScript)' and then mark the 'User Data' radio button. Click the 'What credentials do I need?' button.

Under 'Create an OAuth 2.0 client ID' give your credential a name like 'Lead data' or whatever you like that is relevant. In the Authorized JavaScript origins field enter the name of the URL that will be using the API in a 'http://www.yourwebsite.com' form and then hit enter. Do the same for Authorized redirect URIs, using the same website link and hitting enter to add to the list. Click 'Create OAuth Client ID' button.

The next selection should show the email address that owns the sheet which you should be logged into. If it isn't listed make sure you are logged into it, or that you select it from the dropdown list. Product name can be whatever you want to be listed as the API. No one else will see this, so it isn't a big deal.

Once complete you will be given your **Client ID, save it to a text document for using it later. We will have several keys so it would be best to make a note of what each ID is**. Click done.

Next click the 'Create Credentials' blue button and select API Key. Copy and save your **API key for later** use as well.

You can choose to restrict the key so that only a certain website can access it. If you choose to restrict the key scroll down and then click HTTP Referrers and enter your site as *.yoursite.com/* and click Save.

## Testing the Google Sheets API

Open a new tab. Create a new google sheet or open an existing sheet. If creating a new sheet, enter some data into the fields. If the sheet already has data you can leave it as is.

On the left side of the Developers Google page click on Library on the left side again. Search for Google Sheets. Click Google Sheets API then click 'Try This API'. Scroll down to sheets.spreadsheets.values.get and click that option. In the spreadsheetId paste the ID of your spreadsheet in the URL - the nonsensical text between slashes - we will also need this Sheet ID for later, copy and paste to your text document.

Range is set to the name of the sheet, by default it is Sheet1. For valueRenderOption select FORMATTED_VALUE. Click the blue button that says 'Authorize and execute', deselect all selection except for FORMATTED_VALUE, click Authorize and execute, select your email and click allow. Scroll down to see the sheet data listed as JSON data. Testing should be sucessful so far.


