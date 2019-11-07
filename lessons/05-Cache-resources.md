## Cache resources

**State that comes from the server is basically a cache of state.** It's not UI state.  **How long that cache sticks around is totally up to you**. Right now, our cache  only hangs around until we select a new resource, but we could persist it in  memory somewhere and retrieve it later if needed.

Remember that caches are among the hardest problems in computer science. If you're not careful, you can run into stale data bugs and memory leaks. But let's experiment with it here and see if we can improve the user experience.

---

instead of creating a resource everytime, you create a resource a first time and then read from that - cache you're server state.

`What happens when you want to persist through refresh?`
  You'd do what you would normally do - set in local storage. Or you'd send it back to the server if the data is sensitive. Suspense doesn't change this - just a matter of what your caching.

Here your caching the resource that has access to the data
