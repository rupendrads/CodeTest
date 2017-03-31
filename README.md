# Parliamentary Digital Service

## Business Systems Development Code Test

Thanks for taking our code test! You'll find the instructions for what to create below. Please allow 3 hours for this test.

### Overview
------------
* Construct a responsive website to show business in the Main Chamber of the House of Commons
* List the business items by week and default to the current week
* Allow users to select the week they want to view
* List business items showing:
    * Start date & time
    * End date & time
    * The description of the item
* If a user clicks on an item then show more detail:
    * The category of the item
    * A list of the applicable Members if there are any. This is described in the Members collection of an event. For each Member use their ID property to call a separate service and show:
        * Party
        * MemberFrom
        * FullTitle

### Project structure
---------------------
A Visual Studio solution should be created. It should contain the following projects:
* MVC & WebApi project
    * MVC displays the required information
    * WebApi exposes API methods which should be called via AJAX to obtain the required information
* Services project
    * This should call the 2 remote services and combine the information into appropriate classes to return from the API
* Domain project
    * This should contain the classes returned from the Services project
* Unit test project
    * Tests for the service layer

### Urls
--------

#### Calendar

Help on the calendar feed can be found [here](http://service.calendar.parliament.uk/Help/Event)

To obtain the business items for a week use the following URL 
* http://service.calendar.parliament.uk/calendar/events/list.xml?startdate=2015-11-16&enddate=2015-11-20


#### Members names

Help on the members name service can be found here [here](http://data.parliament.uk/membersdataplatform/memberquery.aspx)

To obtain additional detail for a member using their ID use the URL 
* http://data.parliament.uk/membersdataplatform/services/mnis/members/query/id=579

### Hints
---------
* Using a framework like Angular will help with the frontend binding of information but jQuery can be used instead if preferred
* The service layer should do all the work of calling the services and returning the required information to the frontend. The service layer should combine the information from the two services. 
* In the XML returned from the Calendar feed you'll need to filter items on their `Type` and `House` to ensure you only get `Main Chamber` items in the `Commons`