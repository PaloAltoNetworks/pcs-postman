# This Collection Runner example is to archive Active Compute events

For all examples here, it is assumed you are using the existing **Postman environment** from [the main repo](https://github.com/PaloAltoNetworks/pcs-postman).

## Setup

1. Within the Bulk Archive Compute Incidents collection find the **POST Login Generate Token** request.
2. Enter a valid `ACCESS_KEY` and `SECRET_KEY` value in the `Body` tab.
3. Submit the request to generate your JWT token.
4. Create the list of Incident IDs to archive by using the **GET List Active Incidents** request.

| **_id**                  |
|--------------------------|
| 6299af31b714e5bfd23728df |
| 6299ae7804891ec0812b4fd1 |
| 604aa3b4bfbb730c0e3bf98b |

## Steps to iterate the CSV using the Collection Runner

- Click the main Collection folder on the left sidebar.
- Click the **Run Collection** option for the Collection.
- Ensure the **Environment** **Prisma Cloud** is selected from the dropdown in the upper right.
- In the **Functional** tab, select the `Run manually` radio button.
- In the **Run configuration** section, click the **Data** `Select File` button.
- Find the CSV file you created from the Active Incident List and click `Open`.
- Click the `Preview` button to double-check the format and content.
- Click the `Run...` button.

## That should be it!

You should see the Collection Runner "Run Results"


## Troubleshooting

| Error            | Did you check?                                                                                                                                                                                                                                                                                 |
|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| POST Error       | Make sure you imported the **Prisma Cloud Postman Environment**, and you set the correct [API endpoint](https://github.com/PaloAltoNetworks/pcs-postman#instructions-on-how-to-setup-the-postman-collections-and-environments-relating-to-prisma-cloud-including-compute-console-api-requests) |
| 400 Bad Request  | If you are getting 200s for the Login POST and List Incidents GET, and only a 400 for the actual Archive Incident POST, check your CSV format                                                                                                                                                  |
| 401 Unauthorized | Make sure you set the proper Access/Secret key in the Body of the Login request                                                                                                                                                                                                                |

_As always, if anything is incorrect or needs to be updated, please submit a PR and we will take a look._