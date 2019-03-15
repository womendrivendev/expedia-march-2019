# BODY AND SOUL

http://www.bodyandsoulcharity.org/

We work with 5,500-plus of the most vulnerable children and families in the UK today. We were established in 1996 to formalise the work of our founder, who had spent several years running groups for women and children, primarily refugees, who had experienced the full panoply of trauma in the past – rape, torture, trafficking etc – and continued to live with grave existential uncertainties in the present – homelessness or unstable housing, destitution and a continuing vulnerability to domestic violence and sexual abuse.


## About

Here are some questions to help you get going...

- This project is for BODY & SOUL caseworkers and organizers

- They are having issues with organizing and accessing their user data

- Their user data is currently stored on an Access DB hosted locally (on-premises, we are not sure of exact hosting setup)

- We have set up a Google account for BODY&SOUL (bodyandsoul.wdd@gmail.com)

- We have set up a Google Cloud hosted MySQL DB (owned by aforementioned Google account)

- We have set up a Google Data Studio view for Caseworkers to view data visualizations


## Links

Stick a link to the project repository here, if applicable.

Feel free to share your project in any other forms of communication, such as blog posts, articles, drawings, photography, posts on social media etc.

## Acknowledgement

Cite any tools or sources of information you've used within the project.



## Connecting to the MySQL DB

- Get your google account added to the google cloud instance owned by bodyandsoul.wdd. 
- Go to google cloud console (google cloud > console)
- On the left side hamburger menu, go to SQL > the DB should be there & up and running
- To connect to the DB, you need a client running on a VM! So you need to first log onto a VM
- To do this, go to “Compute Engine” in the hamburger menu
- Find the VM “test-instance-1” and scroll right -- find the triangle dropdown next to “SSH”
- In the dropdown, select “view gcloud command” > then within the popup, select “Run in Cloud Shell”. This will open a browser based shell that will start SSHing into the VM
- When you first log on, you will be prompted for SSH key info. Just hit enter to both questions. Give it a minute. You should now be on a command line for the VM!
- Connect to the mysql DB using a command line mysql client
“mysql --host=35.242.134.197   --user=root --password=$root_password”
- If successful, this should have now dropped you into a mysql prompt. You can type things like: 
- use members;
- SELECT * FROM DEMOGRAPHICS AS DEMOGRAPHICS JOIN PERSONAL_DETAILS AS DETAILS ON DEMOGRAPHICS.MEMBER_ID = DETAILS.MEMBER_ID;
- If the connection wasn’t successful, you can try again (sometimes the connection times out -- this is just a transient error)	


## Exporting Data from Spreadsheets and Into DB
- Create the table (using mysql commands) for your data on the MySQL DB
- The # of columns on your spreadsheet should match the # of columns on your MySQL DB table -- the column names don’t matter, the order DOES
- On your spreadsheet, select Export or Save As... and choose the options that says ".csv" > This will export your data in a CSV format
- In your Google Cloud Console, select "Storage" from the leftside hamburger menu
- There should be a "Bucket" with name "body-and-soul"
- Select "Upload files" or drag and drop to upload the CSV file you downloaded earlier
- Now your data is in the bucket on Cloud! Next you need to import it into the Database that lives on the cloud
- From the hamburger menu on the leftside in the Cloud console, got to "SQL"
- click into the "body-and-soul" MySQL DB instance
- There is a "Import" symbol at the top. Click this.
- Click on "Browse" next to the Cloud Storage File" to select the previously uploaded CSV file
- Select the CSV file and hit "Select"
- It should auto-detect htat it is a CSV file rather than a SQL file > manually select if it didn't
- Choose the "members" database
- Specify the name of the table you created in step 1
- Hit "import"
- You should be able to see the data reflecting now! See "Connecting to the MySQL DB" for instructions on connecting to DB and running a "SELECT" in order to see the rows you imported
- The column headings sometimes get mistakenly imported as a row! You may need to clean this up by running:
- e.g.) DELETE FROM ACE_QUESTIONS WHERE MEMBER_ID = 0;

 ## Logging into Data Studio to View Dashboard

 ## Adding new queries to Data Studio

 ## Google Forms Integration


## Contributors

Last, but not least, names of the proud contributors please!

| Name | GitHub | Twitter | LinkedIn | Other |
| :--- | :--- | :--- | :--- | :--- |
| Nina Nduwayo | nn250 | - | https://www.linkedin.com/in/ninanadia/ | - |
| Emma Matsubara | matsoob | - | https://www.linkedin.com/in/emma-matsubara-094003b6/ | - |
| Jennifer N | jennlew | @jen_onl | https://www.linkedin.com/in/jennlewedum/ | - | 
| Yanan Liu | - | - | - | - | 
| Kara de la Marck | - | - | - | - | 
| Frankie | - | - | - | - | 
| Holly Smith | - | - | - | - | 
| Kara de la Marck | - | - | - | - | 
