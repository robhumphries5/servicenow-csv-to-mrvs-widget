# servicenow-csv-to-mrvs-widget
A ServiceNow Portal Widget which allows the user to enter data in to a multi-row variable set from a local csv file

## Functionality
The update set in this repository provides a widget which can be used to accept csv files from the user and pushes the data in to a selected multi-row variable set.

| Step | Image |
| ----------- | ----------- |
| Downloads a template CSV file (if configured) |![image](https://user-images.githubusercontent.com/20129129/159959062-51725820-2151-46a3-91ed-d421f2a93418.png)|
| Update the data and saves locally|![image](https://user-images.githubusercontent.com/20129129/159959355-cba387ef-19d8-4c78-80b6-651d994f365b.png)|
| Click the widget button on the catalog item|![image](https://user-images.githubusercontent.com/20129129/159957801-7efae73d-9a1c-4a05-9746-0dceec52c76a.png)|
| Select the local .csv file to upload|![image](https://user-images.githubusercontent.com/20129129/159957816-bc18e1b6-2ad6-4b27-a084-ffff00d78c12.png)|
| The multi-row variable set is updated with the data from the csv file automatically|![image](https://user-images.githubusercontent.com/20129129/159957829-f48b089d-13d8-4bc8-922f-e5f26c2e2b9f.png)|

 

## Implementation
1. Create your target multi-row variable set and add it to the Catalog Item you want the functionality available on.
2. Optional - Create a template csv file with column names matching the variable names in your target multi-row variable set
3. Optional - Save the template as an attachment in your instance and record the link to download it.
4. Download the update set in this repository
5. Import and commit the update to your instance
6. On the Catalog Item you want the functionality available on, create a catalog variable of type "Custom"
7. On the catalog variable set the "Widget" field to "Load CSV Data to MRVS"
8. On the catalog variable set the default value to contain the options configuration. Example below. Remove any comments before saving.
```
{
button_text:"Import CSV Data", //the text to show on the button
icon:"upload", //the glyphicon to show on the button
level:"primary", // bootstrap class of the button. exclude "btn-"
target:"", // [mandatory] the name of the multi-row variable set that you want the csv data imported to
csv_template_link:"", // [optional] a link to template csv file the user can download to fill in and upload with their data. 
csv_template_text:""//[optional] text that will form the link to the template file
}
```

## Options explanation
![image](https://user-images.githubusercontent.com/20129129/159954751-46d8a523-79a8-4b0d-830e-bae24310544f.png)

