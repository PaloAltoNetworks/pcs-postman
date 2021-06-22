# This Collection Runner example is to add users from the input CSV

For all examples here, it is assumed you are using the existing **Postman environment** from [the main repo here](https://github.com/PaloAltoNetworks/pcs-postman)

## Setup

1. Within the attached Collection, go to the **Login Generate Token** POST request, and on the Body tab, enter a valid ACCESS and SECRET key to generate your JWT token. [More info can be found here if required](https://github.com/PaloAltoNetworks/pcs-postman#set-your-access-and-secret-key-in-the-username-and-password-fields-in-the-body-of-the-login-and-authenticate-requests)


1. Looking at the CSV of users, the input file needs to match the data like below:

(Note, there are a few other options and inputs you can pass, on the to-do list to update that here)


email | firstName | lastName | timeZone | accessKeysAllowed | defaultRoleId
------------ | ------------- | ------------- | ------------ | ------------- | -------------
user01@test.com | Test01 | User01 | GMT | false | role-id-from-ROLE-GET-request
user05@test.com | Test05 | User05 | America/New_York | true | role-id-from-ROLE-GET-request

### There is also one other field in the CSV you need more information for, the *roleId* field. 

This field directly correlates to the **Default Role** and **Assigned Role** these users will get added to during account creation. 

The easiest way to get these IDs is to run the included **List User Roles** GET request, see which Role you want to assign, and get the corresponding *roleId* from there. 

## Steps to iterate the CSV using the Collection Runner

1. After you have the above Collection imported and your Access/Secret key setup, click the main collection folder on the left, and then click the **"Run"** tab at the top-right of Postman.

* **Environment**

Choose the existing **Prisma Cloud** environmented imported for the [main repo](https://github.com/PaloAltoNetworks/pcs-postman/blob/main/Prisma%20Cloud.postman_environment.json)

* **Data**

Upload the completed CSV here, and you are then able to see the number of *Iterations* (basically the amount of users to be added) as well as view the *Preview* of what data Postman sees within your CSV. This is also where you should double-check the formatting of the CSV to make sure everything looks correct. 

## That should be it!

You should see the Collection Runner "Run Results" iterate through all of the rows of your CSV and add all the users. 

* Quick Troubleshooting

If getting any errors, check this:

Error | Did you check?
------------ | -------------
POST Error | Make sure you imported the Prisma Cloud Postman Environment, and you set the correct [API endpoint](https://github.com/PaloAltoNetworks/pcs-postman#instructions-on-how-to-setup-the-postman-collections-and-environments-relating-to-prisma-cloud-including-compute-console-api-requests)
400 Bad Request | If you are getting 200s for the Login POST and List Roles GET, and only a 400 for the actual Add User POST, check your CSV format
401 Unauthorized | Make sure you set the proper Access/Secret key in the /BODY of the Login request

As always, if anything is incorrect or needs updated, please submit a PR and will take a look. 