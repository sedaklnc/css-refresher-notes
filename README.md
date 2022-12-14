# :mushroom: css-refresher-notes :mushroom:
This is a quick refresher of CSS concepts. 



|Content No | Content|
|----|-------------|
|1  | [Selectors](https://github.com/sedaklnc/css-refresher-notes#selectors)|
|2   | [Selectors-Pseudo-Class](https://github.com/sedaklnc/css-refresher-notes#selectors-pseudo-class)|
|3| [Css-Pseudo-Elements](https://github.com/sedaklnc/css-refresher-notes#css-psuedo-elements)|
|4   | [Width](https://github.com/sedaklnc/css-refresher-notes#width)|
|5   | [Height](https://github.com/sedaklnc/css-refresher-notes#height)|
|6  | [Border](https://github.com/sedaklnc/css-refresher-notes#border)|
|7  | [Padding](https://github.com/sedaklnc/css-refresher-notes#padding)|
|8 | [Padding-Individual-Sides](https://github.com/sedaklnc/css-refresher-notes#padding---individual-sides)|
|9 | [Margin](https://github.com/sedaklnc/css-refresher-notes#margin-baby_chick)|
|10 | [Background-Repeat](https://github.com/sedaklnc/css-refresher-notes#background-repeat--shell)|
|11| [Text-Align](https://github.com/sedaklnc/css-refresher-notes#text-align-alien)|




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
## WIDTH 
> The width CSS property sets an element's width

| Name | Description | 
| :---         |     :---:      |
| auto |  The browser will calculate and select a width for the specified element. |
| % | Defines the width as a percentage of the containing block's width.  |
| inherit|  Inherits this property from its parent element|
| initial| 	Sets this property to its default value.|

```ruby
<style>
  
    div#bir{
        background-color: black;
        width: 80%;
    }
    div#iki{
        background-color: red;
        width: inherit;
    }
    div#uc{
        background-color: blue;
        width: inherit;
    }
    div#dort{
        background-color: yellow;
        width: inherit;
    }
  
</style>

<body>         
    <div id="bir">
        <div id="iki">
            <div id="uc">
                <div id="dort">zz</div>
            </div>
        </div>
    </div>
</body>
```
> The output of the above code is the picture below.
![image](https://user-images.githubusercontent.com/63013903/192121291-b7d101e3-a819-46fc-ae94-3ad89b5f8a2a.png)

## HEIGHT 
> Sets the height of html elements.Content is important

| Name | Description | 
| :---         |     :---:      |
| auto |  The browser will calculate and select a width for the specified element. |
| % | Defines the width as a percentage of the containing block's height.  |
| inherit|  Inherits this property from its parent element|
| initial| 	Sets this property to its default value.|

```ruby
<style> 
  div#main-value{
    background-color: aqua;
    height: 100px;
  }

  div#temp-value{
    height: 25px;
  }
  div#one{
    background-color: brown;
    height: inherit;
  }
  div#two{
    background-color: yellow;
    height: inherit;
  }
</style>

<body>         
      <div id="main-value">
        <div id="temp-value">
            <div id="one">CSS</div>
            <div id="two">LECTURES</div>
        </div>
      </div>
```
output is : an intermediate element is used to avoid the height of the inherited height main element.
![image](https://user-images.githubusercontent.com/63013903/192312546-4a090748-2c1f-44f6-850b-74c8814bcad7.png)

## BORDER 
> The border shorthand CSS property sets an element's border. Syntax= line-width || line-style|| color. we have to indicate style parameters. but the other parameters if we dont indicate it will set the default value.

| ParamterOne| ParameterTwo| ParameterThree | 
| :---         |     :---:      | :---:  |
| :boom: Length| :boom: Style| :boom:  Color | 
|  Length|  none |color |
| Initial| hidden | |
| Inherit| solid| |
| Thin|  double| |
| |  dashed| |
| |  dotted| |
| |  groove| |
| |  ridge| |
| |  inset| |
| |  outset| |

```ruby
<style> 
  #one{
    border: 2px none red;
  }
  #two{
    border: 2px hidden red;
  }
  #three{
    border: 2px solid red;
  }
  #four{
    border: 2px double red;
  }
  #five{
    border: 2px dashed red;
  }
  #six{
    border: 2px dotted red
  }
  #seven{
    border: 2px groove red;
  }
  #eight{
    border: ridge red;

  }
  #nine{
    border: 2px inset red;
  }
  #ten {
    border: 2px outset red
  }
</style>

<body>         
      <p id="one">This is NONE!</p>
      <p id="two">This is HIDDEN!</p>
      <p id="three">This is SOLID!</p>
      <p id="four">This is DOUBLE!</p>
      <p id="five">This is DASHED!</p>
      <p id="six">This is DOTTED!</p>
      <p id="seven">This is GROOVE!</p>
      <p id="eight">This is RIDGE!</p>
      <p id="nine">This is Inset!!</p>
      <p id="ten">This is OUTSET!!</p>
</body>
``` 
Let's get to know the style parameters
![image](https://user-images.githubusercontent.com/63013903/193265805-528b91c6-1bd8-41cc-a634-d36456b8632b.png)

## PADDING

Padding is used to create space around an element's content, inside of any defined borders

| Paramter| Description|
| :---         |     :---:      | 
|  Length|  The size of the padding as a fixed value. |
| %|  The size of the padding as a percentage| 
| Initial| Returns the inital value | 
| Inherit| set to the computed value of the parent element| 

lets give an example
![image](https://user-images.githubusercontent.com/63013903/193410821-5726d782-e038-4dfc-8266-b95f419da8a1.png)

If you want to see an image like above we need to do some calculations. Lets start with html code
```ruby
<body>             
  <div id="one">
    <div id="two">
      Topic is Padding
    </div>
  </div>
</body>
``` 
lets continue with child's style 
```ruby
 div#two{
    width: 108px;
    height: 18px;
    border: 1px solid red;
    padding: 10px;
  }
  ```
 > Output is 
 
![image](https://user-images.githubusercontent.com/63013903/193411086-7397f66e-85d6-45eb-8f4d-f8632ccf9be4.png)

okey lets cont with calculation. What will be the parent value which id is one.

WIDTH = child width + shild border-left + child border-right + padding = 108 + 10 + 1+1 = 130

HEIGHT = child height + child border-top + child border-bottom + child padding + 18 + 1+1 +10 + 30

RESULT WILL BE 

```ruby 
 div#one{
    width: 130px;
    height: 40px;
    border: 1px solid blue;
    padding:30px; 
  }
  ```
  ![image](https://user-images.githubusercontent.com/63013903/193411345-2e44280c-7d46-4880-ae27-983bb5f0dbe4.png)
  
  
  ## Padding - Individual Sides
    The padding-top: CSS property sets the height of the padding area on the top of an element.
  
    The padding-bottom: CSS property sets the height of the padding area on the bottom of an element.
  
    The padding-right: CSS property sets the width of the padding area on the right of an element.

    The padding-left: CSS property sets the width of the padding area to the left of an element.
    
  LETS DO IT  :bird:

```ruby
<body>             
  <p id="top">Padding-top</div>
  <p id="left">Padding-left</div>
  <p id="bottom">Padding-bottom</div>
  <p id="right">Padding-right</div>
</body>
```

HTML part is done and lets see CSS part

```ruby
p#top{
    width: 79px;
    height: 18px;
    border:1px solid red;
    padding-top: 25px;
  }
  p#right{
    width: 88px;
    height: 18px;
    border:1px solid red;
    padding-right: 25px;
  }
  p#bottom{
    width: 104px;
    height: 18px;
    border:1px solid red;
    padding-bottom: 25px;
  }
  p#left{
    width: 80px;
    height: 18px;
    border:1px solid red;
    padding-left: 25px;
  }
  ```
  what will be the output :eyes:
  
  ![image](https://user-images.githubusercontent.com/63013903/193413261-06165911-ede7-4760-a801-855d66fd41ae.png)

## MARGIN :baby_chick:

The margin CSS shorthand property sets the margin area on all four sides of an element

| Paramter| Description|
| :---         |     :---:      | 
|  Length|  The size of the margin as a fixed value. |
| %|  The size of the margin as a percentage| 
| Initial| Returns the inital value | 
| Inherit| set to the computed value of the parent element|
| Auto| set to the computed value of the parent element|

> lets understand better :whale2:

```ruby
<style>
  div{  
    border:5px solid red;
    background-color: red;  
  }  
</style>

<body>             
  <div></div> 
</body>
```

When we write like this code the output will be 
![image](https://user-images.githubusercontent.com/63013903/193416110-9621860c-5d16-4cf2-ae15-60091fe534e8.png)

okey as you can see line has space with right to left and top size because of body's margin.If we rewrite code like this

```ruby
<style>
  body{
    margin: 0px;
  }
  div{  
    border:5px solid red;
    background-color: red;  
  }  
</style>

<body>             
  <div></div> 
</body>
```

> yup its okey right now. So when we write menubar or footer firstly reset the margin
![image](https://user-images.githubusercontent.com/63013903/193416237-2b4dc924-8963-45ee-91e0-a588c85852aa.png)

## Background-repeat  :shell:

| Paramter| Description|
| :---         |     :---:      | 
|  repeat|   tile the image in both directions. This is the default value|
| Space|   tile the image in both directions. Never crop the image unless a single image is too large to fit. If multiple images can fit, space them out evently images always touching the edges| 
| Round|tile the image in both directions. Never crop the image unless a single image is too large to fit. | 
| no-repeat|don???t tile, just show the image once|
| repeat-x|tile the image horizontally|
| repeat-y| tile the image vertically| 
| initial| returns initial value|
| inherit| set to the computed value of the parent element|

> Lets understand with an example. 

```ruby
<body>
    <h2>THIS IS REPEAT</h2><p id="one"></p>
    <h2>THIS IS Space</h2><p id="two"></p>
    <h2>THIS IS Round</h2><p id="three"></p>
    <h2>THIS IS no-REPEAT</h2><p id="four"></p>
    <h2>THIS IS REPEAT-x</h2><p id="five"></p>
    <h2>THIS IS REPEAT-y</h2><p id="six"></p>
</body> 
```

HTML PART IS DONE 

CSS PART IS STARTED

```ruby
    p#one{
        width:800px;
        height:300px;
        border: 5px solid orangered;
        background-image: url('photo.jpg');
        background-repeat: repeat;
        color: brown;
        font-size: 60px;
        font-weight: bolder;
    }
    p#two{
        width:800px
        ;
        height:300px;
        border: 5px solid orangered;
        background-image: url('photo.jpg');
        background-repeat: space;
    }
    p#three{
        width:800px
        ;
        height:300px;
        border: 5px solid orangered;
        background-image: url('photo.jpg');
        background-repeat: round;
    }
    p#four{
        width:800px
        ;
        height:300px;
        border: 5px solid orangered;
        background-image: url('photo.jpg');
        background-repeat: no-repeat;
    }
    p#five{
        width:800px;
        height:300px;
        border: 5px solid orangered;
        background-image: url('photo.jpg');
        background-repeat: repeat-x;
    }
    p#six{
        width:800px;
        height:300px;
        border: 5px solid orangered;
        background-image: url('photo.jpg');
        background-repeat: repeat-y;
    }
```
CSS PART IS DONE..

output will be like below  :jack_o_lantern:

![image](https://user-images.githubusercontent.com/63013903/193453516-7a13ad47-11a9-4d7e-9ec3-ab82399d6339.png)
![image](https://user-images.githubusercontent.com/63013903/193453544-d7c3e02e-5f79-418d-a0e8-684881d9d4f0.png)

## Text-align :alien:

The text-align property is specified in one of the following ways

| Paramter| Description|
| :---         |     :---:      | 
|  left| The inline contents are aligned to the left edge of the line box|
| right| The inline contents are aligned to the right edge of the line box| 
| justify|The inline contents are justified|
| center| The inline contents are centered within the line box|

Lets give an example 

![image](https://user-images.githubusercontent.com/63013903/194069750-146579df-f48b-478f-8762-420190562a54.png)

Okey as you can see above the last one and the fourth one both of them are justify. But justify But justify is not clear for small text.Lets code it 

```ruby
<style>
    div#center{
        width: 750px;
        height: auto;
        border: 2px solid red;
        text-align:center;
    }
    div#right{
        width: 750px;
        height: auto;
        border: 2px solid red;
        text-align:right;
    }
    div#left{
        width: 750px;
        height: auto;
        border: 2px solid red;
        text-align:left;
    }
    div#justify{
        width: 750px;
        height: auto;
        border: 2px solid red;
        text-align:justify;
    }
    div#justifyBetter{
        width: 750px;
        height: auto;
        border: 2px solid red;
        text-align:center;
    }
</style>
<body>
    <div id="center">TEXT ALIGN CENTER</div><br>
    <div id="right">TEXT ALIGN RIGHT</div><br>
    <div id="left">TEXT ALIGN LEFT</div><br>
    <div id="justify">TEXT ALIGN JUSTIFY</div><br>
    <div id="justifyBetter">Lorem ipsum dolor sit amet consectetur adipisicing elit. Cupiditate hic dolorum doloremque nostrum maiores quaerat iste optio odit voluptates nesciunt expedita sint debitis ex eveniet repellendus quod, asperiores, totam magnam?
    </div>
</body>
```

