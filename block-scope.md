#ES6

##Block Scope Intro
Until ES6, JavaScript had two types of scope: function scope and global scope. Now it has block scope too.
Block scope means that a variable is accessible only within the block in which it is defined. A 'block' is defined by a pair of curly brackets ```{}```

Why do we want to be able to confine scope to a block?
Let's look at an example. Open buttonNodes.html in your text editor to read the code or follow along here. Open the html file in your browser to see it in action.


###The Problem
In the body of our html we have four buttons.

```
<button>button1</button>
<button>button2</button>
<button>button3</button>
<button>button4</button>
```

And our JavaScript is as follows:

```js
var buttonNodes = document.getElementsByTagName('button');
for (var i = 0; i < buttonNodes.length; i++){
  buttonNodes[i].addEventListener('click', function() {
    console.log('You clicked element number : ' + i)
  });
}
```

Turn and Talk(™) for a minute about what the developer might want to do here and what might actually happen. Or test it out yourself. Ok, not really I dunno how long I have to present.


No matter what button you click, it says you clicked element 4! Booooo!

###The solution
 Wouldn't it be nice if we could have a variable whose scope was confined to a single iteration of the for loop?
 Yes. Yes it would.
 Well now you can!!! Using the let keyword will confine a variable's scope to its block.
 Check out how we would fix the buttonNode code in ES6:

 ```js
 var buttonNodes = document.getElementsByTagName('button');
for (var i = 0; i < buttonNodes.length; i++) {
   let j = i;
   buttonNodes[i].addEventListener('click', function() {
      console.log('You clicked element #' + j);
   });
}
```

Here, j's scope is confined so that each element has the appropriate event handler. Now you can know which button you clicked. Yay!
One more important note about ```let```: Variables declared using let aren't hoisted. So if you try to reference it before it's let declaration, it's not gonna work, unless you wanted your variable to be equal to ReferenceError.

##const

Use const to define constants! Whaat? Who saw that coming? Variables defined with const follow the same scope rules as let in that they are block-scoped and are not hoisted. The difference is that const variables can't be redeclared.

Check out what I mean in this jsfiddle:  https://jsfiddle.net/mfournier91/urn7g18q/ and open your console so you can see what's happening.

You may have trouble using const in your browser. I did. My best buddy James in the whole world &hearts; told me to get a transpiler!
http://ccoenraets.github.io/es6-tutorial/setup-babel/
