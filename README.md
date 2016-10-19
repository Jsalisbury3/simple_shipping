# Shipping Calculator
#### for help to figure out this code, make sure to email <a href="mailto:instructors@learningfuze.com" target="_blank">instructors@learningfuze.com</a>

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
    - Purpose: will allow the entry of the weight of the package
    - give it an ID of "weight_input" <a href="http://www.w3schools.com/tags/att_global_id.asp" target="_blank">info</a>
    - give it a placeholder of "weight of package in pounds" <a href="http://www.w3schools.com/tags/att_input_placeholder.asp" target="_blank">info</a>
  - button
    - label: calculate
    - give it an ID of "calculate_button"
  - create a div
    - give it an ID of "display_div"
    - purpose - display the shipping information of the package (the weight in ounces, the price of shipping, and the expected arrival date

### Functional Scope
- create the following functions: <a href="http://www.w3schools.com/js/js_functions.asp" target="_blank">info</a>
    - apply_event_handlers
      - name: apply_event_handlers
      - purpose: will add event handlers to all of the appropriate elements
      - see the comments inside the function for specifics
 
    - calculate_shipping
      - name: calculate_shipping
      - purpose: process the shipping time and weight, and return an object with the shipping time and weight
      - see the comments inside the function for specifics

          
    - display_shipping
      - name: display_shipping
      - purpose: update the shipping information inside the display div
      - see the comments inside the function for specifics

## After Coding Details

- Email the index.html file to instructors@learningfuze.com
