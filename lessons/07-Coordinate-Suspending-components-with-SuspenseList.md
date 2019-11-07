## Coordinate Suspending components with SuspenseList

SuspenseList give you control of loading a lot of data/suspended components on one page.

You want to load the latest message in a chat app first or the top post in a feed first and SuspenseList gives you control of that so that things don't just pop in however they want

<details>
<summary>list of args SuspenseList takes</summary>
The `SuspenseList` component has the following props:

- `revealOrder`: the order in which the suspending components are to render

- `{undefined}`: the default behavior: everything pops in when it's loaded (as

if you didn't wrap everything in a `SuspenseList`).

- `"forwards"`: Only show the component when all components before it have

finished suspending.

- `"backwards"`: Only show the component when all the components after it have

finished suspending.

- `"together"`: Don't show any of the components until they've all finished

loading

- `tail`: determines how to show the fallbacks for the suspending components

- `{undefined}`: the default behavior: show all fallbacks

- `"collapsed"`: Only show the fallback for the component that should be

rendered next (this will differ based on the `revealOrder` specified).

- `"hidden"`: Opposite of the default behavior: show none of the fallbacks

- `children`: other react elements which render `<React.Suspense />` components.

Note: `<React.Suspense />` components do not have to be direct children as in

the example above. You can wrap them in `<div />`s or other components if you

need.
</details>


tail prop

control the loading states - which you show

hidden will hide all loading states

collapse will show one fallback until all the dat comes through

This becomes very useful when you have a bunch of data that is loading async.

`How deeply nested is this control if you have nested suspense calls/components?`

`What have you found about testing Suspense?`
  Suspense is an implementation detail - if you were to test a Suspense component by itself, you would render it with the suspense.
  just like a regular async test but just with Suspense.

`Testing any different for React Hooks Testing Library?`
  You'd need to wrap in suspense

`How about Concurrent React and testing?`
  A global will be set depending on if you are using concurrent or not.

`Any libraries that are trying to support Suspense?`
  zeit's swr
  React Async
  React Query - good stuff

`Any Idea when this won't be experimental?`
  if hooks took 6 months to go from beta to stable
  React team is very vague about when it will come out.
  Sebastian said they've been working out the kinks and using this in production for a while

If you don't use concurrent mode, you won't be able to use `useTransition` . You're fallback will always show

`what's the perf benefits by just switching to concurrent mode?`
  watch dans talk - the demo shows the benefit
