## Simple Data-fetching

if there is data - you render data

if there's error - you throw it

if theres a promise - you throw it

react will suspend everything 'under' the promise

Suspense doesn't catch the promise. React catches the promise and then finds the closest Suspense component in the tree and resolves the promise there.

Can you explain the why behind Suspense?

 - look at prereqs, Dans talk gives the why

Keep modules pure - no side effects by just loading the module

`Is there a reason to call fetchPokemon outside of the component instead of inside useEffect?`
  promise is created in useEffect so we wouldn't have access to the promise to throw it.
  theres no way to stop rendering because it's already rendered

createResource is defined outside of react and then you call `read` in react that will return an Error, Promise, or the data.

`Can you pass params to your createResource?`
  you can. and read from props as well.
  reason Kent wouldn't recommend this is that pokemonInfo has to render before request is made. So all the files in your project needs to load as well as all others before that need to load. (when passing params into c

You want to avoid states that are invalid

define `status` so you can key off of this instead of the actual thing returned
