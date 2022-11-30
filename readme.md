# SceneEngine

This projects aim is to create a lightweight TUI engine based on the concept of scenes.

## Design (Scenes?)

What is this `concept of scenes`?

A scene is something like a website - it usually has a title, content, maybe some hyperlinks to other websites, and also a way to browse and interact with it all.

### Title

A title isn't `absolutely necessary`, however it helps having the user know *where* they are.

### Content

The content is *most likely some text*, for example it could be a game main menu.

It would probably best work with containers for it, something like a `header`, `body`, `footer` - something similar to what you have in html.

These containers could also have some styling options like indenting content or organising content to lists or tables.

### Input

At the time of writing this I anticipate two types/modes of input:

- `choose an option` - in this case you input a number, character, or word corresponding to an option from a list, for example:

  ```
  [L]oad Game
  [N]ew Game
  [O]ptions
  [Q]uit
  ```

  Options: `L`, `N`, `O`, `Q`
  
  Example input: `N`->`Enter`

  ```
  1. Lorem ipsum dolor sit amet.
  2. Litwo ojczyzno moja ty jesteś jak zdrowie.
  3. [...]
  ```

  Options: `1`, `2`, `3`

  Example input: `2`->`Enter`


- `text input` - in this case you simply type something and the program does something with the inputted string, example use case: naming a character

There is another type of input that I would like to have implemented - `on key down/up/press` - its where you simply can press arrows or other keys and the program instantly can react to it without having a need to press enter, however I would need to research how it works in C# and if it even works and that would take some time, and I am unsure how much.

As a sidenote - input options might be inheritable from parents to allow for global options for example like a pause menu in games (resume, options, save, load, quit), or like a hamburger menu in applications with options like `file`, `view`, `settings`

### Interactivity

When choosing an option, a scene executes its action corresponding to the chosen option. An action could for example simply change value of some variables or enter another scene (change the current scene to this other scene).


## Scene Attributes

Here is a list of scene attributes that alter how scene behaves with explanations what they do:

`string` `OptionName` - name of the scene as an option

`string` `OptionDescription` - description of the scene as an option //TODO: different description types? ie AlwaysShown, Hideable (in settings for example)?

`string` `title` - title of the scene

`TODO` `content` - object tree defining the content of the scene

`byte` `inputType` - how should the input be handled, available options:

 - `0` - `choose an option`
 - `1` - `text input`
 - `2` - maaaaybe `on key down/up/press`??

`TODO` `optionList` - if inputType=0; inputs-options key-value list 

`bool` `isPersistent` - whether a scene should persist after entering and then exiting from a child scene

`bool` `isPopup` - whether a parent scene should persist after exiting from the current scene

