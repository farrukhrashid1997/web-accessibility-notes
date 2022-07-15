# web-accessibility-notes
WCAG -  Web Content Accessibility Guidelines


The web accessibility has three main topics:  
- Focus
- Semantics
- Styling

# Focus
- WCAG states that all page functionality is available using the keyboard. 
- Keys imp for focus:  
  - Tab moves the focus forward
  - Shift + Tab moves the focus backward
  - Use up and down arrow keys to navigate within a component
- Generally there is no need of focus on something when the user doesnt have to interact with it or input something in it. 
- When using CSS to change the order of elements on the screen, ensure the tabbing isnt of random order. 
- 1.3.2 - Meaning Sequence of the tabbing
- A tab index of -1 would take the element out of the taborder, and only focusable through the focus method. 
- A tab index of 0 will place the tab in the natural tab order.
- A tab index of more than zero is discouraged as its an anti pattern and jumbles up the order of the tabs. 
- Typically, we should only add tabindex attributes to interactive elements. 
- But there is a caveat of adding focus to text elements:
  - Imagine a web page(SPA) which has three navigation elements. Lets name them fir, sec and thir. 
  - Now when you click on the first element, the section that opens, has a link, 
  - You want to go to that link using the tab key. 
  - But in this case, it would go to sec. 
  - So to prevent that, auto focus the first header element in that section of fir. 
  - Programatically, I will give a tabindex of -1 to the header of fir, and then call .focus on it.

- Similar to this example, now if there is a navbar, a user might want to (someone with motor rotatory issue) navigate to the links directly. This we can do using Skip Links. Basically add a href at the top which will be visible once you press tab. If clicked, it takes you to the main content. 

- ARIA design patterns stock lists various kinds of elements and their keyboard behaviour, a guideline.   
- Check out roving focus in order to manage focus of various elements like radio buttons etc. 
- Another scenario which comes up is, imagine if you have a drawer on your page which has nav elements. When you press tab, it will navigate through all the elements, but it wont be visible to you. 
- To track down which element is active use the document.activeElement in your console. 
- Learning keyboard traps within a modal, and also when to prevent a keyboard trap. (Its a guidelines in WCAG)


# Semantics
- 
