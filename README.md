# Shipping Calculator

## Code Setup Details

#####1. Download the files
> Click on the green "clone or download" button on the top right of the github page
> Click on "download ZIP"
> Download the file to a folder on your computer
> Double click on it to expand it.
> Use an IDE (editor) to view/modify the file
- <a href="https://sublimetext.com/2" target="_blank">Sublime</a>
- <a href="https://atom.io/" target="_blank">Atom</a>
- <a href="https://www.visualstudio.com/free-developer-offers/" target="_blank">Visual Tools</a>

## Coding Instructions

### Layout Scope
>- Create a text input <a href="http://www.w3schools.com/tags/tag_input.asp" target="_blank">info</a>
    - Purpose: will hold the weight of the package to be shipped
    - give it an ID of "weight_input" <a href="http://www.w3schools.com/tags/att_global_id.asp" target="_blank">info</a>
    - give it a placeholder of "weight of package in pounds" <a href="" target="_blank">info</a>
  - button
    - label: calculate
    - give it an ID of "calculate_button"
  - create a div
    - give it an ID of "display_div"
    - purpose - display the shipping information of the package (the weight in ounces, the price of shipping, and the expected arrival date
  
<a href="https://github.com/Learning-Fuze/shipping_calculator/blob/master/design.png" target="_blank"><img src="https://github.com/Learning-Fuze/shipping_calculator/blob/master/design.png" height='300px'></a>

### Functional Scope
>- create the following global variable:
  - shipping_time
    - purpose: storage for what the current shipping time is
    - initial value: 5
- create the following functions:
    - apply_event_handlers
      - name: apply_event_handlers
      - purpose: will add event handlers to all of the appropriate elements
      - params: none
      - return: none
      - details:
        - add a keydown handler to the text input that calls "validate_keydown" 
        - add a click handler to the radio buttons (all of them) that calls "change_shipping_type"
        - add a click handler to the button that calls "display_shipping"
    - validate_keydown
      - name: apply_event_handlers
      - purpose: checks the incoming values.  If anything other than a number or period is pressed, it returns false.
      - param: event {object} the object that holds the details of the event
      - return: true if the key pressed is a number or the period key, false if it is not
      - hints:
        - look at the event, find the property that holds the ASCII number that corresponds to the letter you pressed
        - compare the values.  If they don't correspond to "0" through "9" or ".", return false.  Else return true if they do
      - extra knowledge: once you get it to work with keydown, what's the difference if you instead change the event to keypress
    - change_shipping_type
      - name: change_shipping_type
      - purpose: update the stored value for the shipping based on the clicked radio button
      - param: none
      - global: shipping_time
      - returns: none
      - hint: the radio button clicked will be the value you need.  So this should point to the right element.
    - calculate_shipping
      - name: calculate_shipping
      - purpose: process the shipping time and weight, and return an object with the shipping time and weight
      - param: weight, shipping_time
      - global: none
      - return: an object with the following properties and values:
        - arrival_date {string} the expected arrival time
        - weight {number} the weight (in ounces) of the package
        - cost {number} the cost (in dollars) of shipping the package
      - details:
        - should convert the weight (from pounds to ounces) 16 ounces to the pound.
        - calculate the shipping cost based on the following formula:
          - less than 20 ounces: 2 cents an ounce
          - greater than 2 pounds: 20 cents an ounce
          - between 20 ounces and 2 pounds: 10 cents an ounce
          - faster shipping acts as a multiplier
            - 5 day: 1x multiplier
            - 3 day: 1.5x multiplier
            - 2 day: 2x multiplier
        - calculate the arrival date based on the following:
          - the current date (use the Date object http://www.w3schools.com/jsref/jsref_obj_date.asp)
          - the shipping_time (in days), added on
          - if the current day is Sunday, add one day to the shipping (packages cannot be sent on Sunday)
          - if it would arrive on Sunday, add one day to the shipping (packages cannot arrive on Sunday)
          - Packages still move on Sunday (trains and planes don't stop moving on Sunday, so don't add 1 day for merely travelling on Sunday)
          - convert the date into a format similar to the following: June 3rd, 2016
  - create a jQuery document ready (load handler) function and call apply_event_handlers
          
    - display_shipping
      - name: display_shipping
      - purpose: call the calculate shipping function, and then display the results in the display div
      - param: none
      - global: shipping_time
      - return: none
      - hint: 
        - get the shipping details from the calculate_shipping function.  Pass in the appropriate information

## After Coding Details

##### 1. Save files to Git - Add all modified & created files
> Run below command in terminal tab

> `git add .`

##### 2. Package (group) all saved git files with a commit message

> Run below command in terminal tab

> `git commit -m "v0.1 - [Your Name]"`
> - [Your Name] should be replaced with your First & Last name

##### 3. Allow others to see your changes by uploading them to the Github website

> Run below command in terminal tab

> `git push origin v0.1`

##### 4. See if your feature fits with what everyone else was working on (Pull Request)

> ####Step 4.1 Open your shipping_calculator Repo in the browser
> - The link Should follow this format 'https://github.com/[your user name]/shipping_calculator`

> ####Step 4.2 Click Pull request tab to open the pull request list

> ####Step 4.3 Click "New Pull request" button

> ####Step 4.4 Comparing Changes
> During this step there are a hand full of highlighted things that need to be taken into consideration.

>##### NOTE: The image is for example puposes only, refer to the below text for what each value should actually be

>  1. `base fork: Learning-Fuze/shipping_calculator`
>  1. `base: C#_userName`
>    1. Here you will select the option that matches your username
>    1. If you can not locate an option that has your username, contact an instructor
>  1. `head fork: [your_user_name]/shipping_calculator`
>    1. Here you will select the option that matches your username / shipping_calculator
>    1. If you can not locate an option that has your username / shipping_calculator, contact an instructor
>  1. `compare: v0.1`
>    1. Here you will locate the branch name (or feature name) you created at the beginning of this version of the project
>  1. Github.com will let you know if the code can be merged automatically (without needing a manual merge)
>    1. If the text says something other than "able to merge". <b>Contact an instructor</b>
>    1. Sometimes a manual merge is necessary, it just has a couple more steps when completing the request (done by 
instructors at start)
>  1. Once we have verified #1 - #4 and noted #5, we click the "Create Pull request" button (#5 in the image above)

> ---

> ####Step 4.4 Add details into the pull request
> 1. Give the pull request a title, by default its the name of the last commit (package) message that was saved
>   1. If you set the commit message above you should get <b>v0.1 - [your first & last 
name]</b> already pre-populated in the Title field
>   1. If there is a different title pre-populated, change the title to match the correct format:
>      1. <b>v0.1 - [your first and last name]</b>
> 1. <b>Don't assign a user.</b> (An Instructor will select who this gets assigned too)
>   1. Further into the cohort we will have students learn to review pull requests
> 1. Click on "Create pull Request"

> <a href="https://github.com/Learning-Fuze/prototypes/blob/assets/assets/example/5.jpg?raw=true" target="_blank"><img src="https://github.com/Learning-Fuze/prototypes/blob/assets/assets/example/5.jpg?raw=true" width="800" /></a>
