Time to Pause Blog

Project Set Up 

Created Mind Map on Ludic App for ideas of funcitonality of the blog as well as some additional add on features that I woudl like to have if I have sufficient time at the end of the project to implement. 

Setting Up Django Workspace

I used the Django Blog Cheat Sheet from the 'I Think Therefore I Blog' course content in order to set up my workspace for use with Django and supporting libraries. 
I installed the relevant libraries required which were Django, Gunicorn, Psycopg2, DJ Database URL, Cloudinary and URL Lib 3. 
I created my app using the command python3 manage.py startapp "timetopause"
I migrated these changes and then I ran the server to test was my workspace working using the relevant commands.
I added my app name to the ALLOWED_HOSTS list in the settings.py file.
Next, I used ElephantSQL to create an extrernal database to support my app. I have an account already with Elephant SQL so I logged into my account. I selected the 'Create New Instance Button' at the top right hand corner of the screen. From here I entered my app name, selected a plan on which I would like this datebase to run and I clicked on the 'Select Region' button at the bottom of the screen. On this page I checked that the region already selected was correct for me and once I had that confirmed I clicked on the 'Review' button at the end of the page. I reviewed the details of my database here and once I was happy with that I selected the button "Create Instance".
Once I had this database connected I was returned to my dashboard, from here I clicked on the app I had just created which brought me to my app details. I copied the URL name here. 
I now logged onto my Heorku account and navigated to the dashboard here. I selected the "New" button on the top right hand corner of the screen and selected "Create New App" from the list of options. From here I entered a name for my app and selected the correct region. I selected "Create App" from here.
Once I had the app created and was returned to the homepage I selected the app I had just created and then clicked on the "Settings" tab from the app homepage. From here I selected to "Reveal Congif Vars". Here I added a Config Var with the Key of DATABASE_URL and the value of the URL name I had copied from the database I had created in Elephant SQL. I selcted "Add" when both fields had been entered.
Back in my Gitpod workspace for the app I created an env.py file in the top level directory. Here I imported os and added the database url and created a secret key for the project.
I once again returned to Heorku and clicked into the Settings tab of my project and again revealed config vars and added a new Key of SECRET_KEY and a value of the secret key that I created for the project.
In Gitpod I opened my settings.py file and using code imported os and dj database url. Here I also changed the code for the SECRET_KEY and set it to get the secret key value from where it was set. I also commented out the old code for the DATABASE value and added in code to point to my new database url that was specified.
I saved all files and in the termnial I made migrations using the code python3 manage.py migrate.
I have an account set up with Cloudinary also. This site is used to host images and media from the app to ensure they are always available. I logged into my Cloudinary account and from the dashboard I copied the API Environment Variable. 
I added this to my env.py file as a separate line of code to point directly to my Cloudinary URL.
I once again returned to my app created on Heroku and clicked on the Settings tab and revealed config vars. From here I added a key of CLOUDINARY_URL and the value of the API Environment Variable I copied from Cloudinary and I added this.