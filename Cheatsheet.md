# GIT

## Commands related to a remote repository:

- git clone git@github.com:USER-NAME/REPOSITORY-NAME.git
- use cd for going into repository
- git push or git push origin main (Both accomplish the same goal in this context)

## Commands related to the workflow:

- git add .
- git commit -m "A message describing what you have done to make this snapshot different"

# Commands related to checking status or log history

- git status
- git log

**The basic Git syntax is program | action | destination.**

For example,

- git add . is read as git | add | ., where the period represents everything in the current directory;
- git commit -m "message" is read as git | commit -m | "message"; and
- git status is read as git | status | (no destination).

## Branch creation

- You can make new branches by using the command git branch *branch_name*. You can then change to your new branch using git checkout *branch_name*. 
- You can also create a new branch and change to it in a single command by using the -b flag with checkout, in the form git checkout -b *branch_name*.
- You can see all of your current branches using git branch with no other arguments.

Merges are done by using the command git merge *branch_name* which will take the changes you’ve committed in branch_name 
and add them to the branch that you’re currently on.

When you don’t need a branch anymore it can be deleted using git branch -d *branch_name* if the branch has already been merged 
into main or with git branch -D *branch_name* if it hasn’t. You will usually want to delete branches when you’re done with them, 
otherwise they can pile up and make it more difficult to find the branch you’re looking for when you need it.

To make the branch accessible in remote GitHub to share the branch or any other thing, use git push origin *branch name*

# HTML

**What if we want to use the image in the other page?**
We would first have to go up one level out of the pages directory into its parent directory so we could then access the images directory.

## Form in HTML

Forms are one of the most critical parts of your site. They are your user’s gateway into your backend – the user provides data in a form, and you do stuff with it.

- The form element accepts two essential attributes; the first is the action attribute which takes a URL value that tells the form where it should send its data to be processed.
- The second is the method attribute which tells the browser which HTTP request method it should use to submit the form. The GET and POST request methods are the two you will find yourself using the most.
- We use GET when we want to retrieve something from a server. For example, Google uses a GET request when you search as it gets the search results.
- POST is used when we want to change something on the server, for example, when a user makes an account or makes a payment on a website.

### Form Controls

To start collecting user data, we need to use form control elements. These are all the elements users will interact with on the form, such as text boxes, dropdowns, checkboxes and buttons. 

- The **input** element is the most versatile of all the form control elements. It accepts a type attribute which tells the browser what type of data it should expect and how it should render the input element.

- An input on its own isn’t very useful since the user will not know what kind of data they are supposed to provide. Instead, we can give our inputs a label to inform users what type of data they are expected to enter.

To create a label, we use the label element. The text we want displayed in the label will go between its opening and closing tags:

```html
<form action="example.com/path" method="post">
  <label for="firstName"*First Name:*/label>
  <input type="text" id="firstName">
</form>
```

Labels accept a for attribute, which associates it with a particular input. The input we want to associate with a label needs an id attribute with the same value as the label’s for attribute.

To guide users on what to enter in form elements, we can include placeholder text in input fields.

This is done by adding a placeholder attribute to an input. The value will be the placeholder text we want to display in the input:

```html
<label for="first_name"*First Name:</label>
<input type="text" id="first_name" placeholder="Bob...">
```

Use placeholder text to demonstrate how text should be entered and formatted.

The name attribute serves as a reference to the data inputted into a form control after submitting it. You can think of it as a variable name for the input. Form input should always have a name attribute; otherwise, it will be ignored when the form is submitted.

```html
<label for="first_name"*First Name:</label>
<input type="text" id="first_name" name="first_name">
```

#### The Types of input are:

- Email Input
- Password Input
- Number Input
- Date Input
- Text Input
- File Input
- Radio Input
- Checkbox or Toggle Switch Input
- Telephone Number Input
- Search Input
- URL Input
- Slider Input
- Color Input

The **text area** element provides an input box that can accept text that spans multiple lines like user comments and reviews. It can also be resized by clicking and dragging the bottom right corner to make it bigger or smaller.
Unlike input elements, Textarea elements do have a closing tag. This allows you to wrap some initial content you want the text area to display.
Text area elements accept a couple of unique attributes that other form controls do not. These are the rows and cols attributes. They allow you to control the initial height(rows) and width(cols) of the text area.

### Selection Elements

There are Three selection elements:

- #### Select Dropdown: 

The select element renders a dropdown list where users can select an option. Syntactically, select elements have similar markup to unordered lists. The select element wraps option elements which are the options that can be selected.
To create a select dropdown, we use the *select* element. Any options we want to display within the select element are defined using *option* elements
We may also split the list of options into groups using the *optgroup* element. The optgroup element takes a label attribute which the browser uses as the label for each group:

``` html
<select name="fashion">
  <optgroup label="Clothing">
    <option value="t_shirt">T-Shirts</option>
    <option value="sweater">Sweaters</option>
    <option value="coats">Coats</option>
  </optgroup>
  <optgroup label="Foot Wear">
    <option value="sneakers">Sneakers</option>
    <option value="boots">Boots</option>
    <option value="sandals">Sandals</option>
  </optgroup>
</select>
```

We can set one of the options to be the default selected element when the browser first renders the form by giving one of the options the selected attribute

- #### Radio Buttons  

- #### Checkboxes

*This two can be created using Input tag with type atrributes has either Radio or checkbox.*

### Organising Elements

Using the correct inputs for the data we want users to enter goes a long way towards making our forms user friendly. However, in larger forms, users can easily get overwhelmed and discouraged if there are many inputs to fill in.
Luckily, HTML provides a couple of elements that make it easy to organize forms into sections that are visually distinct and manageable to digest.

#### Fieldset Element

The fieldset element is a container element that allows us to group related form inputs into one logical unit.
To create a fieldset, we use the *fieldset* element. Whatever form inputs we want to group together go within the opening and closing fieldset tags:

```html
<fieldset>
  <label for="first_name">First Name</label>
  <input type="text" id="first_name" name="first_name">

  <label for="last_name">Last Name</label>
  <input type="text" id="last_name" name="last_name">
</fieldset>
```

##### Legend

The legend element is used to give field sets a heading or caption so the user can see what a grouping of inputs is for.
To create a legend, we use the *legend* element with the text we want to display within its opening and closing tags. A legend should always come right after an opening fieldset tag:

```html
<fieldset>
  <legend>Contact Details</legend>

  <label for="name">Name:</label>
  <input type="text" id="name" name="name">

  <label for="phone_number">Phone Number:</label>
  <input type="tel" id="phone_number" name="phone_number">

  <label for="email">Email:</label>
  <input type="email" id="email" name="email">
</fieldset>
```

```html
<fieldset>
  <legend>Delivery Details</legend>

  <label for="street_address">Street Address:</label>
  <input type="text" id="street_address" name="street_address">

  <label for="city">City:</label>
  <input type="text" id="city" name="city">

  <label for="zip_code">Zip Code:</label>
  <input type="text" id="zip_code" name="zip_code">
</fieldset>
```

A common use-case for these elements is using a fieldset to group radio buttons and using a legend to communicate to the user what each of the options is ultimately for:

```html
<fieldset>
  <legend>What would you like to drink?</legend>

  <div>
    <input type="radio" name="drink" id="coffee" value="coffee">
    <label for="coffee">Coffee</label>
  </div>

  <div>
    <input type="radio" name="drink" id="tea" value="tea">
    <label for="tea">Tea</label>
  </div>

  <div>
    <input type="radio" name="drink" id="soda" value="soda">
    <label for="soda">Soda</label>
  </div>

</fieldset>
```

### Autocomplete box

- You can provide suggested, automatically-completed values for form widgets using the *datalist* element with child *option* elements to specify the values to display. The *datalist* needs to be given an id.
- The data list is then bound to an *input* element (e.g. a text or email input type) using the list attribute, the value of which is the id of the data list to bind.
- Once a data list is affiliated with a form widget, its options are used to auto-complete text entered by the user; typically, this is presented to the user as a drop-down box listing possible matches for what they've typed into the input.

Basic example
Let's look at an example.

```html
<label for="myFruit">What's your favorite fruit?</label>
<input type="text" name="myFruit" id="myFruit" list="mySuggestion">
<datalist id="mySuggestion">
  <option>Apple</option>
  <option>Banana</option>
  <option>Blackberry</option>
  <option>Blueberry</option>
  <option>Lemon</option>
  <option>Lychee</option>
  <option>Peach</option>
  <option>Pear</option>
</datalist>
```

### Form Validation

One of the most significant features of HTML5 form controls is the ability to validate most user data without relying on JavaScript. This is done by using validation attributes on form elements. We've seen many of these earlier in the course, but to recap:

- *required*: Specifies whether a form field needs to be filled in before the form can be submitted.
- *minlength* and maxlength: Specifies the minimum and maximum length of textual data (strings)
- *min and max*: Specifies the minimum and maximum values of numerical input types
- *type*: Specifies whether the data needs to be a number, an email address, or some other specific preset type.
- *pattern*: Specifies a regular expression that defines a pattern the entered data needs to follow.

If the data entered in a form field follows all of the rules specified by the above attributes, it is considered valid. If not, it is considered invalid.

**When an element is valid, the following things are true:**

- The element matches the :valid CSS pseudo-class, which lets you apply a specific style to valid elements.
- If the user tries to send the data, the browser will submit the form, provided there is nothing else stopping it from doing so (e.g., JavaScript).

**When an element is invalid, the following things are true:**

- The element matches the :invalid CSS pseudo-class, and sometimes other UI pseudo-classes (e.g., :out-of-range) depending on the error, which lets you apply a specific style to invalid elements.
- If the user tries to send the data, the browser will block the form and display an error message.

# CSS

To go to the parent directory we need to use two dots in the relative filepath like this: ../
When we create a CSS declaration, we can target specific elements using selectors.

## id

We can target elements based on their id, using the syntax #id

## class | attribute | pseudo-class

- We can target elements based on their class, using the syntax .class
This level also includes attribute selectors that target HTML attributes, like [checked] and [href="https://wattenberger.com"]
This level also includes pseudo-selectors, like :hover and :first-of-type

The *universal selector (*)* and combinators (+, *, ~, _, ||) have no effect on specificity

A *descendant combinator* will only cause elements that match the last selector to be selected if they also have an ancestor (parent, grandparent, etc) that matches the previous selector.

So something like .ancestor .child would select an element with the class child if it has an ancestor with the class ancestor. Another way to think of it is child will only be selected if it is nested inside of ancestor.
give Space when you are using this.

Everything in CSS has a box around it, and understanding these boxes is key to being able to create layouts with CSS, or to align items with other items.
here are multiple ways to manipulate the size of these boxes, and the space between them, using margin, padding, and border.

- padding increases the space between the edge of a box and the content inside of it; 
- margin increases the space between a box and any others that sit next to it; 
- and border adds space (even if it’s only a pixel or two) between the margin and the padding. Be sure to study the diagrams carefully.

In *Box model* the total height = padding(top + bottom) + defined height; similarly for total width= border(top + bottom) + defined width.
If you don't want your padding and border adding up your total, use box-sizing:border-box which makes it to only consider the defined height and width.

To inspect the box model, Use Chrome Dev Tools.

Most of the elements that you have learned about so far are block elements. In other words, their default style is display: block. By default, block elements will appear on the page stacked atop each other, each new element starting on a new line.
Inline elements, however, do not start on a new line. They appear in line with whatever elements they are placed beside. A clear example of an inline element is a link, or *a* tag. If you stick one of these in the middle of a paragraph of text, it will behave like a part of the paragraph. 

**Div** is a block-level element by default. It is commonly used as a container element to group other elements. Divs allows us to divide the page into different blocks and apply styling to those blocks.
Two commonly used block elements are: *p* and *div*.
The *p* element defines a paragraph in an HTML document.
The *div* element defines a division or a section in an HTML document.

An inline element does not start on a new line.
An inline element only takes up as much width as necessary.
Span is an inline-level element by default. It is commonly used to group text content and inline HTML elements so we can apply styling to them.
An inline element cannot contain a block-level element!

display: inline-block brought a new way to create side by side boxes that collapse and wrap properly depending on the available space in the containing element. It makes layouts that were previously accomplished with floats easier to create. No need to clear floats anymore.
Compared to display: inline, the major difference is that inline-block allows to set a width and height on the element. Also, with display: inline, top and bottom margins & paddings are not respected, and with display: inline-block they are.
Now, the difference between display: inline-block and display: block is that, with display: block, a line break happens after the element, so a block element doesn’t sit next to other elements.

**Flexbox** is a way to arrange items into rows or columns, where those items will flex (i.e. grow or shrink) based on some simple rules that you can define.
A flex container is any element that has display: flex on it. A flex item is any element that lives directly inside of a flex container.
This method of creating and nesting multiple flex containers and items is the primary way we will be building up complex layouts. The next image was achieved using only flexbox to arrange, size, and place the various elements. Flexbox is a very powerful tool.

Shorthand properties are CSS properties that let you set the values of multiple other CSS properties simultaneously. Using a shorthand property, you can write more concise (and often more readable) stylesheets, saving time and energy.

when we changed the flex-direction to column, flex-basis refers to height instead of width.

Adding flex: 1 to .item makes each of the items grow to fill the available space, but what if we wanted them to stay the same width, but distribute themselves differently inside the container? We can do this by
Remove flex: 1 from .item and add justify-content: space-between in parent flex container.

justify-content aligns vertically and align-items aligns horizontally. The most common behavior, however, is the default, i.e. justify-content aligns items horizontally (because the main axis defaults to horizontal), and align-items aligns them vertically.

One more very useful feature of flex is the gap property. Setting gap on a flex container simply adds a specified space between flex items, very similar to adding a margin to the items themselves. gap is a very new property so it doesn’t show up in very many resources yet, but it works reliably in all modern browsers, so it is safe to use and is very handy!

An **animation** lets an element gradually change from one style to another.
You can change as many CSS properties you want, as many times as you want.
To use CSS animation, you must first specify some keyframes for the animation.
Keyframes hold what styles the element will have at certain times.
When you specify CSS styles inside the @keyframes rule, the animation will gradually change from the current style to the new style at certain times.
To get an animation to work, you must bind the animation to an element.
The animation-duration property defines how long an animation should take to complete. If the animation-duration property is not specified, no animation will occur, because the default value is 0s (0 seconds). 
We can use from and to for defining the transition, we can also use percent. By using percent, you can add as many style changes as you like.