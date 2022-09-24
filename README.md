# css-refresher-notes
This is a quick refresher of CSS concepts.

## Selectors ##


| Selectors | Example | Example Description |
| :---         |     :---:      |          ---: |
| *   | *   | selects all elements   |
| element     | p       | select all p elements |
| .class   | .number | selects all elements with class = 'number' |
| #id   | #userName   | select the element with id = 'userName'  |
| .classOne.classTwo     | .nameOne.nameTwo       | selects all elements with both nameOne and nameTwo within the class attributes      |
| element.class     | div.number       | select all div elements with class='intro'|
| element#id    | div#number       | select all div elements with id='number'|
| element,element  | div,p | selects all div and p elements |
| element>element     | div > p      | select all p elements where the parent is div element|
| [attribute]  | [name] | selects all elements with a name attribute |


> It selects all elements with the attr name is 'name' <
```ruby

<style>
    [name]{
        color:red }
</style>

<body>
    <h3 name="">This is title</h3>
    <div name="">CSS Notes</div>
    <div name="">HTML Notes</div>
    <div name="">JS Notes</div>
</body>
```
> Selects all div elements with name is html < 
```ruby
<style>
    div[name='html']{
        color:blue }
</style>

<body>
    <h3 name="title">This is title</h3>
    <div name="css">CSS Notes</div>
    <div name="html">HTML Notes</div>
    <div name="js">JS Notes</div>
</body>
```
> Selects all span elements inside ul elements and with attr name is css
```ruby
<style>
    ul span[name='css']{
        background-color: brown;
    }
</style>

<body>
    <div>
        <ul>
            <li> <span name="css">CSS</span></li>
            <li><span name="python">python</span></li>
            <li><span name="ruby">ruby</span></li>
            <li><span name="go">go</span></li>
        </ul>
    </div>
</body>
```
> Selects span elements inside ul and with a name attr. containing the word "title". i means it doesnt have case sensitive.(ruby and css will selected)
```ruby
<style>
    ul span[name ~= 'title'i ]{
        background-color: brown;
    }
</style>

<body>
    <div>
        <ul>
            <li> <span name="title">CSS </span></li>
            <li><span name="python">python</span></li>
            <li><span name="TiTle">ruby</span></li>
            <li><span name="go">go</span></li>
        </ul>
    </div>
</body>
```


## Selectors Pseudo Class ##


| Selectors | Example | Example Description |
| :---         |     :---:      |          ---: |
| :active | a:active   |Matches when an item is being activated by the user.|
| :hover     |   a:hover    | select links on mouse over|
| :link | a:link | represents an element that has not yet been visited |
| :visited | a:visited   | represents an element that has already visited |
| :focus  | a:focus       | generally triggered when the user clicks or taps on en element   |
| :target   | #a:target       | selects the current active #a element|
| :checked   |    s:checked   | selector represents any radio, checkboz, or option element that is checked or toggled|
| :disabled | input:disabled| An element is disabled if it cant be activated |
| :required| input:required | represents any input,select element that has the required attr set on it |

> :focus ->Makes the necessary style definitions when the specified html element is focused.Generally used in input elements.If u want to use with div elements you have to use with tabindex attr. (click tab and watch it)
```ruby
    <style>
        div:focus{
            background-color: red;
        }
    </style>
    
<body> 
    <div tabindex="1">HTML</div><br>
    <div tabindex="3">CSS</div><br>
    <div tabindex="2">JS</div><br>
    <div tabindex="4">PYTHON</div>
</body>
```
> :target CSS pseudo-class represents a unique element with an id matching the URL's fragment.
```ruby
 <style>
       :target{
        color: cadetblue;
        background-color: yellow;
       }
 </style> 
    
<body> 
    <div><a href='#ProgrammingLang'>Programming Languages</a></div>
    <div><a href='#MarkupLanguage'>Markup Languages</a></div>
    
    <ul id="ProgrammingLang">
        <li>HTML</li>
        <li>PYTHON</li>
        <li>C#</li>
        <li>C</li>
    </ul>

    <ul id="MarkupLanguage">
        <li>CSS</li>
        <li>HTML</li>
    </ul>
 </body>   
 ```
 > :not() Defines the style for all html elements except the specified html element.Firstly you have to create specific style for these elements.
 
 ```ruby
     <style>
        h3{
            background-color: red;
        }
       :not(h3){
        background-color: aquamarine;
       }
    </style>
</head>
<body> 
    <h2>This is Title</h2>
    <h3>This is content</h3>
    <h4>This is resources</h4>
</body>
```
> :checked : defines the style when the specified html element is selected. returns to normal when deselected. If you use checked attr it means checkbox is selected
```ruby
   <style>
        input:checked{
        width: 20px;
        height: 20px;
      }   
    </style>
</head>
<body>  
    <input type='checkbox'>Hobbies</input><br>
    <input type='checkbox'>Books</input><br>
    <input type='checkbox' checked="checked">Foods</input>
</body>
```
> an element is disabled if it can't be activated.
```ruby
<style>
    input:disabled{
    border: none;
    background-color: cornflowerblue;
        }  
    </style>
</head>
<body>  
    Member-no: <input type="text" value="12334" disabled>
</body>
```
> have to enter required info if elements have any required attr.
```ruby
<style>
    :required{
            width: 100px;
            border: 10px solid rosybrown;
        } 
    </style>
</head>
<body>  
        <form action="https://www.google.com.tr/search" method="get">
            Phone-num: <input name='q' type="text" required><br>
            <input type="submit" value="gonder">
        </form>
</body>
```
> When you write number between 10 and 20 the number color will be red the others will be default color
 ```ruby
     <style> 
        input:in-range{
            color: red;
        }
    </style>
</head>
<body>         
            <input type="number" min="10" max="20">
</body>
```
## CSS PSUEDO ELEMENTS 
A CSS pseudo-element is a keyword added to a selector that lets you style a specific part of the selected elements.

| Name | Description | 
| :---         |     :---:      |
| first-letter |  Defines a style to the first character of the specified html element |
| first-line |  Defines a style to the first line of the specified html element  |
| before |   Defines style by assigning content before the specified html element|
| after|  Can be used to insert some content after the content of an element.|
| selection|Matches the portion of an element that is selected by a user.|

> How to use ::first-letter -> First letters colors will change which are H and C 
```ruby
<style>

  p::first-letter{
    color: red;
  }
  div::first-letter{
    color: rgb(19, 195, 31);
  }
</style>

<body>        
    
    <p>CSS</p>
    <div>HTML</div>

</body>

```
> How to use ::first-line ? First-line is  responsive pseudo element when you make smaller the website first-line applied to the  first line again
```ruby
<style>
  
  ::first-line{
    color: cornflowerblue;
  }

</style>
<body>        
    
   <div> HTML is markup language.<br>HTML is skeleton of the web </div>
</body>
```
> ::before psuode element usage as you see below before the weather cond we will see -sun- charachter 
``` ruby

<style>  
    button::before{
    content: '\2600';
    color: red;
  }
</style>

<body>              
   <button> Weather condition</button>
</body>
```
>:: selection usage : when you select the div element's content color will be red

``` ruby
<style>
    ::selection{
    color: red;
  }
</style>

<body>         
   <div>Daisy is my favorite flower</div>
</body>
```
