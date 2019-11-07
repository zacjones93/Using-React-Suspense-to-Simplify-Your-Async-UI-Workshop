## useTransition for improved loading states

Showing a spinner on the specific area that is loading would be a better UX than just waiting to load

`why would you have multiple transition hooks in a component?`
  If you have multiple components that suspend, you'll want control on how that transition happens

`what does the timeoutMs mean?`
  the timeoutMs will set the time you wait until the fallback is shown
  how long are we going to reference the isPending state before showing the fallback

`how it works with useEffect?`
  with useEffect you show the loading state immediately
  Suspense useTransition gives you a mechanism to let you control how long you show stale data

you can also set the busyDelayMs which will tell React that if data isn't loaded at 300Ms, show the placeholder for the busyMinDurationMs (say 500ms → will show the fallback for atleast 200Ms

We want to give the user some indication that work is happening and we want to control how soon react shows the fallback

this lets you control the fallback at the place the data is being loaded

Everything under the closest suspense boundary will be suspended - even if you have multiple components in one boundary

I see people putting suspense boundaries anywhere they want this finegrain control

`the question is whether the idea is one suspending component for each React.Suspence?`

If the user does something that starts a suspense, react will warn you that that is happening and suggest you useTransition so that the user will know that something is happening
