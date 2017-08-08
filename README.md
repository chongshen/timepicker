# Custom Control in Dynamics 365: Time Picker (Time-only Field)

In the system pre-defined data types of Dynamics CRM, two formats are available for "Date and Time": Date Only, Date and Time. Where is time-only? This can be a really common scenario. For example, client may want to create reoccurring appointments that happens everyday.

One simple, no-code solution is to create an option set. But what if the client wants the time to be specific to minutes? You'll have to create 24*60=1440 labels for the option set. Scrolling through all 1440 labels will be a terrible UX. Not a good idea.

# Solution: time picker
Just like the system pre-defined date and time field, the user will first pick a time, and then edit the time value input if the minute is not exactly at HH:00 or HH:30.

I have created a web resource to serve as a time picker that work exactly like this.

# How does it work
This custom control works as both an input area and a selection list.
DEMO: https://www.youtube.com/watch?v=VKyzNjsDTXs

# How to use
1. Create a Single Line of Text field. (e.g., new_StartTime) This will be used to store the actual time input.
2. Insert the HTML web resource to your form.
3. Change the following two lines, replace new_StartTime with your field name:

window.parent.Xrm.Page.getAttribute("new_StartTime").setValue(timeselected.text);
window.parent.Xrm.Page.getAttribute("new_StartTime").setValue(inputvalue);


08/08/2017 Update: Now with Javascript input validation.
