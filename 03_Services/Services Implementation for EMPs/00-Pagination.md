# Pagination (explanation, definition) for EVSE Data


The PullEvseData service in OICP supports pagination to efficiently manage
large datasets. When requesting EVSE data, the following parameters are
available to implement pagination:

  1.  **pages:** This parameter allows you to specify which page for data retrieval within the dataset. It is particularly useful when fetching data in chunks or pages.

  2.  **size:** The limit parameter helps control the number of records returned per request. By adjusting this value, you can customize the size of each data page retrieved from the server. The maximum is 2000 elements per page.

 **Example Integration:**

To implement pagination in your PullEvseData service requests:

    
    
    curl --location 'https://service.hubject.com/api/oicp/evsepull/v23/providers/DE*ICE/data-records?size=2000&page=0' \
    --header 'X-HUBJECT-Client-Request-Origin: EXTERNAL' \
    --header 'Content-Type: application/json' \
    --data '{     
        "GeoCoordinatesResponseFormat": "Google",
        "ProviderID": {{providerID}},
        "OperatorIds":["OperatorID"]
    }'

In this example, the request is configured to start retrieving data from the
beginning (page: 0) and limit the response to 2000 records per page. Adjust
the Pages and Limit parameters as needed to navigate through the dataset
efficiently.

 **Note:** Proper pagination implementation enhances performance and ensures
that data retrieval is manageable for both the server and the client,
especially when dealing with extensive EVSE datasets.

 **Best Practice:**

Develop an automation script that iterates through all pages and sets the
default size to 2000.

