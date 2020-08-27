Todays post is really based on a subject I deal with at each deployment. Of course there are many scripts on the net to take care of all your Lync deployment needs, so whats different about my script?

Usually Lync is deployed in a phased manner, my script allows the administrator to enable just the bits needed for each phase of the deployment. By simply commenting out the parts that are not needed you can deploy each phase of the Lync deployment at your own pace.

Because of this approach, you can re-use the script and input CSV file and simply run just the steps you want for each phase.

So what does the script do?

Using a reference CSV input file the script does the following:

Counts the number of users that will be processed based on the data in the input CSV
Checks to see if the user is valid in AD
Checks to see if the user is already enabled for Lync, id not then enable and move to next step
Enable User for Enterprise Voice and add the Line URI
Assign Client Policy to the user
Assign Conferencing Policy to the user
Assign Dial Plan to the user
Assign Voice Policy to the user
Assign External Access Policy to the user
Assign Mobility Policy to the user
Update the AddressBook
NOTE

If any of the steps fails then the failure is written to a log file
The input CSV and the log file paths are defined in the beginning of the script and will need to be edited to match your environment
It is important to match the CSV file format as the column headers are used to match the variables in the script
