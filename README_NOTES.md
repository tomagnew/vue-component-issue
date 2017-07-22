I have an issue which I am trying to resolve as either a bug or (hopefully) my misunderstanding of the Vue.js component system.

I want to author a reusable Vue.js component for others to use in their applications.

I want my component to be consumable by either:

 a) using the established build system used in the Vue-cli, i.e.  
  import myCoolComponent from 'my-cool-component'  
  
or
 
 b) by simply dropping a script into their html page and using the component from a global object.

For the purposes of demonstrating my issue, I have stripped the example down to the minimal code necessary to show the problem.

Thus far, my component compiles and works perfectly in the typical Webpack build workflow with no complaints from Vue.

It also works fine if all code is declared in the browser.

The issue is when I use Webpack to build the precompiled version of the component and then drop that script into the browser.

The component functions correctly but the console gives the Vue warning that props are being mutated directly on the component.

I understand the whole "don't mutate props directly" theory and agree with the reasoning behind it.

However, in my example I am not (to my knowlege) mutating the components props directly. I am only changing the state on the Parent, which should then propagate down to the child component props.

So my question is, am I doing something wrong and actually manipulating the childs props directly when I use the precompiled component this way, or is this simply a warning that I have to live with, or is this a real bug?



