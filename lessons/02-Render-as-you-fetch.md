## Render as you fetch

you don't need to wait for the data to load to load images and such. You can load it all at once.

render as you fetch is twice as fast.

we like to have fetch request be sent from the component that needs that data. BUT that leads to the waterfall effect (slow)

difference between suspense and useEffect

suspense doesn't give you the flash of loading state but useEffect will

Refactoring from useEffect

add error boundary around PokemonList

remove all set state shenanigans in the use effect and the checks on status - suspense handles this.

pokemonResource is created in the App component and passed into the list

`Do you see any useful hooks coming out of this?`
  ex6 is that. You'll just use a hook that fetches a resource

The same type of render as you fetch can be applied to lazy loaded components

Separate the data fetching from the component that is being lazy loaded - Lazy loading loads the whole file so they have to be separate (unless you use a relay feature or special babel config)

`createPokemonResource` and `PokemonInfo` are now separated (but in the same folder for some co-location)

It allows you to go get the data at the same time as you render then components that use the data.

This will likely be used by the routers that exist out there and you'll use custom hooks
