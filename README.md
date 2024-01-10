# google-sheet-api
Makes a Google Sheet Into a Public GET API (for reading and writing)

The example we use is a simple one column sheet which can be read in json output and written to append to the last line.



# Steps

1. Create Google Sheet
- Create the column and add data. (for example - "Users" as the header, "Bob" as first row (A2) and "Jason" as second row (A3)
- Name the sheet (for example "Sheet1"). If you change this, you will need to change the value also in your API request path= (see step 5 below)
2. Create Apps Script
- In Google Sheet Top Menu, Click on Extensions -> App Script
- Edit the Code.gs file and copy paste this repository Code.gs. Make sure to edit row 70 "Users" with the name of header of your column A ->       rowData.push(e.parameter['Users'] || '');
- Set a "project title" name and click on "Deploy" -> "New Deployment"
3. Set Permissions of Apps Script and Publish
Make sure to deploy as "Web app" and copy the Web App URL: https://script.google.com/macros/s/xxxxxxxxxxxxxx/exec (make sure to replace the x's with your ID)
4. Using the Api and Testing
Take the "Web App URL" and Use it in the Following Way:
a. Read the Sheet
- Add to the end of the "Web App URL" ?path=Sheet1&action=read
b. Write to the Sheet (Add a new row)
- Add to the end of the "Web App URL" ?path=Sheet1&action=write&Users=[name]
5. Start Using It. Enjoy!

