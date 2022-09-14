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

