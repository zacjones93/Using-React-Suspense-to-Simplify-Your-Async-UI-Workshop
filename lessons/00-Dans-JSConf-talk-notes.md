# Dans Beyond React Talk

Computing Power - CPU

creating nodes

re-rendering

Network Speed - IO

data fetching

code splitting

## CPU - Time Slicing

You're going to get stutter in react when your re-renders affect large portions of your tree.

You bump into this problem where no particular component is slow but you have so many features that they all are

**You could debounce**

but you are decreasing ux

**Async is the way to go**

lets your UI stay interactive while you mount component trees.

We've built a generic way to ensure that *high-priority updates* like user input don't get blocked by rendering *low-priority updates*.

'Time Slicing'

- react doesn't clock the thread while rendering
- feels synchronous if the device is fast
- feels responsive if the device is slow
- only the final rendered state is displayed
- same declaritive component model

**Git as a metaphor**

React works as if you are on a git branch vs only working in master

if working only in master - you have to deal with an issue immediately before finishing the feature. if on the branch, you deal with the issue, rebase the feature and can continue as normal and merge everything together when all is finished.

## IO - Supsense

introduces suspense that lets you set a placeholder if the latency on any request is taking a while. The UI is still interactive while the fetching is going on.

If you send out multiple requests - you can control what gets rendered when.
If you need all the data - it will display a fallback until all the data is present.

if you only care about one piece of data, it will wait until that data is present and render - if other data is still loading you can show a spinner for that data.

You can use this with for code splitting

"We've built a generic way for components to *suspend rendering* while they load *asynchronous data*.

- Pause any state update until the data is ready
- add async data to any component without 'plumbining'
- on a fast network, render after the whole tree is ready
- on a slow network, precisely control the loading states
- There's both a high-level and a low-level API

The problem is about scheduling

solution: async rendering

- Adapt to user's device and netowrk
- fast interactions feel instant
- slower interactions feel responsive

This will still be the react you know - Declarative Component development
