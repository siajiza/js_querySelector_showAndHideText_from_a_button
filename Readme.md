# **QuerySelector**

    The Document method querySelector() returns the first Element within the document that matches
     the specified selector, or group of selectors of CSS. If no matches are found, null is returned.

**SYNTAX**

    const matches = document.querySelector(".element");     
    
    //take in count de point before the element´s name ".widget"

**On Console**

    > div.widget.mainHeading.showElement

click and open
    
    >...[]
    >classList: DOMTokenList(3)
        0: "widget"
        1: "mainHeading"
        2: "showElement"
        length: 3
        value: "widget mainHeading showElement"
    >...[]


**HOW WORKS _"querySelectorAll"_ IN OUR EXAMPLE CODE**

**Behavior**

    We are looking for on this example to show or hide the Main Title and the subtitle. 

    To find down that we´re gonna build a button where we´ll click on it and make this two actions; show and hide text are intertactives.

    We part first, from three language code locations;

    -html
    -css 
    -js

    Each one are going to contribute with part of the code 
    to create interact between them.

_To find this interact, we need to call with specific class and id names inside of each element, regardless of whether it is html or css. And from javascript we call this elements to the action._

**CSS**

Two different behaviors from each "onclick":

        .hideElement {
          visibility: hidden;
        }
    
        .showElement {
          display: block;
        }


**HTML**

We must build a two parts:

1. First part

On the main "div" element wich contains the other child elements, where are the interactives title and subtitle, will find the class and inside of it will have the two specific words we´re gonna use on javascript to call the actión  from CSS.

In this case, this especific word will be **"showElement"** and **"widget"**.


    <div class="widget mainHeading showElement">
        <div class="mainHeading">
          <h1>Hi there</h1>
        </div>
    
        <div class="subHeading">
          My Amazing subheading...
        </div>
    </div>

2. Second part

The button must be "onclick=contentToggle()", and this toggle function will be used on Javascript funtion to find the interaction.

    <button onclick="contentToggle()">Toggle Content</button>
<button onclick="">Toggle Content</button>

**JAVASCRIPT**

In this first step we build a variable that call the element where we´re gonna build the interaction, in this case the main "div".

    const widget = document.querySelector('.widget');

On the second step, we´re gonna build the function on how is gonna show or hide the text. "onclick".    

    function contentToggle() {

On the third step, we´re gonna code through javascript to get the behavior from style´s CSS.

    if (widget.classList.contains('showElement')) {
                widget.classList.remove('showElement');
                widget.classList.add('hideElement');
            } else {
                widget.classList.remove('hideElement');
                widget.classList.add('showElement');
            }
        };

